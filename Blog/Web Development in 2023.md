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

## Servers and Templates

Over time, dynamic features were introduced such as making your HTML life easier with templates, or requesting server-side data with API calls.

## Client-side rendering

Spearheaded by React, a whole new breed of web development technologies appeared out of nowhere and took us all by surprise. You could just serve a mini skeleton HTML containing just a root element, and a huge javascript bundle that runs on the browser and dynamically fills the content of the website with a virtual DOM. Without going into the depths of what a virtual DOM does, you can simply think of it as React (or any other client-side rendering framework) taking control over the browser and displaying content dynamically, as an additional layer on top of the HTML we sent from the server-side.

It sounded promising, especially given the fact that clients become more powerful over time. Our smartphones and laptops have faster CPUs, and our browsers receive frequent updates with shiny new web features. 

## The return to staticness


By order of "staticnes":
- SSG (static site generation): we serve static HTML
- ISR (incremental static regeneration): we serve periodically updated static HTML
- SSR (server-side rendering): we serve dynamically (on-request) generated static HTML
- CSR (client-side rendering): we serve a javascript bundle and the client generates HTML

