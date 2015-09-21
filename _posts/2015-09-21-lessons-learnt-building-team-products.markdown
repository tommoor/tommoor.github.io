---
layout: post
title: "Lessons learnt building team communication products"
date: 2015-09-21 10:00
comments: true
tags: 
- startups
- journey
- saas
- b2b
---

At [Speak](https://speak.io) we’ve been building team communication products for years, but when we began down this path I don’t think that any of us knew what was ahead. We all came from different backgrounds in gaming, b2c and ecommerce but we’d never tackled anything built for teams.

We’ve come to discover that creating a successful team product has it’s own set of unique challenges...


## Multi platform

Unlike one player consumer apps like games and photography tools, multi platform support is critical to the success of a team product. Whilst it’s easy to forget when living in the tech bubble, not everyone uses your OS of choice and most teams will have a mixture of operating systems in use. If your tool needs to be used by everyone then multi-platform is a must as soon as possible.

If you’re building for web then this means compatibility with all the major browsers, not just Chrome… and desktop apps need to embrace Windows with gusto! 


## Realtime is Hard

If you come from a background of building web experiences that rely on a page reload or short session times, moving to building real-time systems with millisecond race conditions and a client that users keep open for days or even weeks introduces a whole new set of fun challenges. 

At [Speak](https://speak.io) we aim to connect audio in under a second. To achieve this, 50+ messages race through websockets and through our evented system which is built to withstand misordering, mistiming and lost messages altogether. Each layer of the system has to be built with fallbacks and proper error handling to ensure that when things go awry the user experience doesn’t end up suffering.


## Activation is harder

Activation is that ‘magic moment’ when you consider that a user has engaged with your product in a meaningful way. This may be sending an email, creating a post, uploading a file or in our case - having a quick audio call. 

This is exponentially more difficult when you require multiple people to use your product synchronously to achieve it, so anything that can be done to give your team product a one-player experience will pay dividends as users will be more likely to keep the app open and actually still be online when their coworkers signup too...


## Quality is Paramount

Early adopters playing around in their spare time are the most forgiving of users, they’re often amazingly keen to find and report bugs, put up with inconsistencies, fiddle with settings and love to be involved in helping with the product development process.

Every workplace has it’s early adopters for sure, but an entire team of them is an unlikely find! In order for your platform to be adopted in the workplace, beta quality just won’t do. A high level of polish and reliability is a must for the vast majority of teams to adopt and stick with your app.


## Preferences are great

With our last product we were prone to thinking that if you design something well then options aren’t needed. In hindsight, this was a little naive, and when Slack came around this cemented that fact as the app was lauded for its customizability - not complexity.

You can almost think of a team as one user with multiple personalities, one minute they want a preference for this, and then a setting for the opposite, plus an admin control for everything. If you don’t satisfy all of the personalities at once then slowly the team will stop using the product. Clear and well organised preferences and options are the right solution!


## Business != Boring

The trend of employees bringing consumer apps into business isn’t going away and the line between personal life and work continues to blur for creative professionals. Everyone would prefer to have a little fun whilst they work and one way to inject this into your day is to use tools with personality, animation and excitement!


The bar for a great business tool is continuously being raised and we’re excited to be tackling these challenges! Building something for teams yourself? I’d love to hear any thoughts you have on this subject in the comments...
