---
title: Web Development in 2023
date: '2022-10-01'
tags: [webdev]
draft: true
summary: What's going on in web development, from the point of view of an backend / machine learning person.
---

This blog post was written from the point of view of a back-end guy looking into web development in 2023. My experience covers mostly data science, machine learning research and  a little bit of static site blogging using Jekyll.

In 2023, web development looks nothing like it did in 2010, and the sheer amount of resources available makes it daunting for any newcomer to understand what's going on. In this post, I aim to cover a brief history of web development and what the present and future of the space looks like.

## The Static Beginnings

In the beginning, there was only static. Websites were pure HTML that was manually edited. If you wanted to add a new product to your online store, you would add a new `div` to your `index.html`. 

Unironically, you should still start from here if you're new to web development, and in some cases this is also enough for a very simple site.

## Servers and Templates

Over time, dynamic features were introduced such as making your HTML life easier with templates, or requesting server-side data with API calls. Among others, Django and Ruby on Rails became extremely popular 

Django is a Python framework for web applications that became very popular alongside Ruby on Rails as a way to write most of your business logic in a language that you may already be very familiar with, rather than Javascript. On top of writing backend code such as API endpoints and routes, you could also leverage their templating to write more accessible HTML and simple interactivity.

However, these frameworks missed the Javascript revolution, becoming hard to integrate with modern frameworks like React and lacking serverless capabilities. It's not that they can't do it (see XXX and YYY for examples on how people are tying to make it happen), but the fundamental 


## Client-side rendering

Spearheaded by React, a whole new breed of web development technologies appeared out of nowhere and took us all by surprise. You could just serve a mini skeleton HTML containing just a root element, and a huge javascript bundle that runs on the browser and dynamically fills the content of the website with a virtual DOM. Without going into the depths of what a virtual DOM does, you can simply think of it as React (or any other client-side rendering framework) taking control over the browser and displaying content dynamically, as an additional layer on top of the HTML we sent from the server-side.

It sounded promising, especially given the fact that clients become more powerful over time. Our smartphones and laptops have faster CPUs, and our browsers receive frequent updates with shiny new web features. 

## The return to staticness

By order of "staticness":
- SSG (static site generation): we serve static HTML
- ISR (incremental static regeneration): we serve periodically updated static HTML
- SSR (server-side rendering): we serve dynamically (on-request) generated static HTML
- Middleware: 
- CSR (client-side rendering): we serve a javascript bundle and the client generates HTML

The term serverless is quite of a misnomer and very confusing, but you better get used to it, as it will surely remain an important buzzword in the field for years to come. But what does it mean?

Serverless stands for "managed", meaning that you do not need to be in charge of the server yourself. Of course, a server running your code still exists. The whole internet runs on servers, which is why "serverless" is such a confusing name. 

Traditionally, you would have your own on-premise servers, or hire a cloud server from a provider such as AWS or GCS. You are still in charge of managing server capacity, scaling, etc.

With serverless, you hand over all responsibility to the provider, and simply define the code that you want to run. Provision, scaling, regional replication, and any other server-related matters will be handled by the provider, and you will be billed in milliseconds of execution time instead of a monthly server upkeep fee. You are no longer charged for idle-time! You no longer need to worry about choosing the right container size! However,  tt also means that you are now heavily restricted by the capabilities of the serverless provider, which are usually much narrower than an 

## Serverless Databases

## Starting a project in 2023? Make it serverless!
