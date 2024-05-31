Mutations are a messy subject. Of course we can just use `fetch` or `axios`  on an POST API endpoint, but when do you update the UI? Immediately, or after the status reply comes back? Ideally, I'd like the former (optimistically assume success), but then you have to manually roll back the changes if you end up receiving an error status.

I've come to love Tanstack Query (formerly React Query) for it makes dealing with queries, and especially mutations, a bliss. When defining a mutation, you can implement a few hooks that get triggered when the mutation starts, succeeds and fails. On start, you can define logic for optimistically updating the data, and on failure you can reset the data to its original state.

The reason why this is way better than using `fetch` or `axios` is that the latter would require me to handle the logic of `setData` by myself. The end result (our fetched data variable) is always tidy and fresh and optimistically up-to-date when using Tanstack Query.

I usually make a separate file with `useMutation` utility functions, as they tend to get verbose (the one thing I don't love about Tanstack Query). Say I have a mutation to add tags to a library entry. I'd create a function like this:

```
export const useAddTagMutation = () => {

  const apiUtils = api.useContext(); <-- TODO: Convert to tanstack
  return api.paper.addUserPaperTag.useMutation(
    {
    ...
    }
  )
}
```

Now we can define what happens when the mutation starts (set data optimistically), finishes (invalidate queries to trigger a re-fetch) and fails (reset old data).

The first one, `onMutation`, might look like this:

```
onMutate: async (newTag) => {
  await apiUtils.paper.getPaperTagsOfUser.cancel(
    {
	userId: newTag.userId,
	paperId: newTag.paperId,
    }
  );

  const previousTags = apiUtils.paper.getPaperTagsOfUser.getData();

  apiUtils.paper.getPaperTagsOfUser.setData(
    {
	userId: newTag.userId,
	paperId: newTag.paperId,
    },
    (previousTags) => {
	if (previousTags === undefined) {
	  return {
	    tags: [
		newTag,
	    ],
	  };
	}
	return {
	  tags: [
	    ...previousTags.tags,
	    newTag,
	  ],
	};
    }
  );
  return { previousTags };
},
```

First we cancel any existing queries that might query data we are planning to mutate, then we get the "old data" (previous tags), and create the "new data" by appending the new tag to the tags lists. We return the "old data" as context for the error function to use it for the reset.

When we succeed (`onSettled`), we simply invalidate related queries so that they can properly sync with the database (the expectation is that nothing will change since the optimistic update correctly predicted the new database state).

```
onSettled: async (newTag, error, variables, context) => {
  await apiUtils.paper.getPaperTagsOfUser.invalidate(
    {
	userId: variables.userId,
	paperId: variables.paperId,
    }
  );
},
```

When we fail (`onError`), we reset the data to the old state.

```
onError: (error, newTag, context) => {
  console.log(error);
  apiUtils.paper.getPaperTagsOfUser.setData
    (
	{
	  userId: newTag.userId,
	  paperId: newTag.paperId,
	},
	context?.previousTags,
    );
},
```

As I said, this is quite verbose, but it allows me to only deal with my data within queries and mutations, and I can always be sure that my query hook is always in sync and immediately up-to-date after a mutation.

```
const { tags, tagQueryStatus } = getUserTagsForPaperQuery({
paperId: paper.id,
userId: session?.user?.id || '',
enabled: isSessionAuthenticated,
});
```