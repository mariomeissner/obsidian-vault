---
title: Web Development in 2023
date: '2022-10-01'
tags: [webdev]
draft: true
summary: What's going on in web development, from the point of view of an backend / machine learning person.
---

<Note>This blog post is written from the point of view of a back-end-turned-full-stack engineer by exploring web development in 2023.</Note>

I found the current web development landscape to be highly influenced by its past. Join me in this short journey as I tried to get a basic understanding of how this all came to be.

## The Static Beginnings

In the beginning, there was only static. Websites were pure HTML that was manually edited. If you wanted to add a new product to your online store, you would add a new `div` to your `index.html`. Unironically, you should still start from here if you're new to web development, and in some cases this is also enough for a very simple site. Interactive elements such as drop-downs, checkboxes and text inputs were nothing more than HTML components that the browser implements to provide the necessary interaction.

Total bliss, if you ask me.

But of course, we quickly craved for more.

## Javascript Interactivity

Static HTML-land is boring though, and people quickly realized the need to create more dynamic websites. Javascript entered the scene as a way to add scripts to websites such that the HTML can be manipulated dynamically. The cornerstone for the rise of this trend was jQuery, and people used it for everything from changing the color of a box when the user hovered the mouse over it, to calling separate APIs for dynamic content.

It was also interesting for me to learn that Javascript is nothing more than an implementation of a specification called ECMAScript. It's a unique situation in programming-land where each browser can do their own thing to read and interpret the script text provided by the server, but must adhere to the specifications described in the ECMAScript bible. Coming from Python, this was quite a situation to wrap my head around at the beginning.

The rise and fall of jQuery can be seen clearly on stack overflow, where the most upvoted answers to many common questions involve using the library. 

## Server-side rendering

In a somewhat parallel manner to jQuery, server-first frameworks such as Django and Ruby on Rails were becoming popular and taking over the hearts of many back-end developers, as they could just continue using the languages they already knew and love. 

Most of the business logic would be written in a language that you may already be very familiar with, rather than Javascript. On top of writing backend code such as your own API endpoints and routes, you could also leverage their templating to write more accessible HTML and simple interactivity. Every GET request from the user ran a piece of your backend code to catch the request parameters and render a custom version of the HTML using the templating mechanism.

These frameworks, unlike jQuery, are still alive and well, and many consider them to be the best way to do web dev, even in 2023. Their maturity means you can find a package or plugin to do almost anything with it, and do it well. 

However, these frameworks missed the Javascript revolution, becoming hard to integrate with modern frameworks, while also lacking serverless capabilities. It's not that they can't do it, but they were not designed with these features in mind.

## Client-side rendering

Spearheaded by React, a new category of client-based web frameworks captured the interest of web devs, especially those wishing to focus more on the front-end experience. Mainstream adoption began around 2015. You could just serve a small HTML skeleton containing just a root element, and a huge javascript bundle that runs on the browser and dynamically fills the content of the website with a virtual DOM. Without going into the depths of what a virtual DOM does, you can simply think of it as React (or any other client-side rendering framework) taking control over the browser and displaying content dynamically, as an additional layer on top of the HTML we sent from the server-side. It sounded promising, especially given the fact that client devices were getting more and more powerful CPUs over time, making it reasonable to displace this computational burden.

However, this introduced two major issues:
- Large bundle sizes and client rendering means increased time to interactive (TTI).
- Empty server HTML means very poor search-engine optimization (SEO).

The former means that websites became slower and plagued with loading spinners awaiting some fetched data; the latter means that your website ranks poor on Google because their crawlers don't run Javascript so they only look at the original empty HTML.

## The return to the server

The modern wave of web frameworks attempt to take the best bits and lessons learned from the pure React era, while shifting back to the benefits of the server. [Next.js]() has quickly become a new standard for React web development, by helping shift the computation back to the server. Users can choose with a high degree of granularity how to render each page, depending on interactivity requirements.

By order of "staticness":
- SSG (static site generation): we serve static HTML
- ISR (incremental static regeneration): we serve periodically updated static HTML
- SSR (server-side rendering): we serve dynamically (on-request) generated static HTML (this is like Django!)
- Middleware: ???
- CSR (client-side rendering): we serve a javascript bundle and the client generates HTML

But... why focus so much on staticness? First of all, it solves the two issues mentioned in the previous section: it's fast and its SEO optimized, and we are happy because we can write React code as usual. The higher you are on this staticness ladder, the faster your website becomes, and the easier you can manage your SEO. But of course, it severely limits what you can do. The beauty of these frameworks is that you can pick and choose the method for each page in your website individually.

And then, there's the last little beast that plays into all of this...

## The edge

The edge is a shiny new term to denote servers that are very close to your client, oftentimes also called content delivery networks (CDNs), popularized by providers such as CloudFlare. They're usually only able to serve static content, so they are often used to serve library bundles. However, they can also be used to serve HTML, assuming it's static (doesn't have data requirements).

This brings us back to the staticness ladder. The higher you climb, the more you can make use of CDNs to serve your website. Using this system makes your website blazingly fast.

This "edge" is very different from how Django does things, since the latter requires a managed server running at all times, while the former spins a tiny provider up and down and scales in any direction you need, automatically.

This brings me to my last point...

## The serverlessification

The term serverless is quite of a misnomer and very confusing, but you better get used to it, as it will surely remain an important buzzword in the field for years to come. But what does it mean?

Serverless stands for "managed", meaning that you do not need to be in charge of the server yourself. Of course, a server running your code still exists. The whole internet runs on servers, which is why "serverless" is such a confusing name. 

Traditionally, you would have your own on-premise servers, or hire a cloud server from a provider such as AWS or GCS. You are still in charge of managing server capacity, scaling, etc.

With serverless, you hand over all responsibility to the provider, and simply define the code that you want to run. Provision, scaling, regional replication, and any other server-related matters will be handled by the provider, and you will be billed in milliseconds of execution time instead of a monthly server upkeep fee. You are no longer charged for idle-time! You no longer need to worry about choosing the right container size! However, it also means that you are now heavily restricted by the capabilities of the serverless provider, which are usually much narrower than a self-managed alternative.

Serverless services include, but are not limited to, serving your static page routes on the edge, serving API endpoints (AWS Lambda), provisioning a database (PlanetScale, CockroachDB). 

## Starting a project in 2023? Make it serverless!

Unless you have very specific requirements in mind that block you from doing so, going serverless is a great default for 2023. It allows you to focus on your product, not on the engineering required to get it going. Getting started is usually free or very inexpensive.

My personal project for 2023 is [Paper Studio](https://paperstudio.app), and I am building it on Next.js and PlanetScale. Stay tuned for my updates on this!