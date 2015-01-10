---
layout: post
title: ! 'Scaling a Lean Startup, The Story So Far. '
comments: true
tags:
- startups
- scaling
- mongodb
- lean startup
- technology
- buffer
---
<p>Since I joined <a href="http://bufferapp.com">Buffer</a> in September last year we have seen awesome growth that has pushed both our hardware and mine and <a href="http://twitter.com/joelgascoigne">Joel</a>'s sys-admin skills to their limits. In this time we have grown from a single Linode VPS shared with Joel's previous startup to a heady total of 10 VPS's and in the last week we undertook the biggest jump so far, moving our infrastructure from this cluster to <a href="https://aws.amazon.com">Amazon Web Services</a>.</p>

<p>Our approach to scaling has always been based on necessity - with the <a href="http://www.startuplessonslearned.com/2008/09/lean-startup.html">Lean Startup</a> methodology ingrained into the company culture we push code fast and try to avoid prematurely scaling our infrastructure beyond it&#8217;s needs. This has definitely lead to some sleepless nights and the occasional hour of downtime but all in all we feel this approach is much better than over compensating from the beginning and building architecture that you may never need or use. These are a few of the key occasions when scaling became the only option&#8230;</p>

<h3>1 Server: Launch to 20,000 users</h3>

<p>The first version of Buffer was (<a href="http://blog.bufferapp.com/idea-to-paying-customers-in-7-weeks-how-we-did-it">perhaps famously</a>) the embodiment of an MVP, a single pricing page that gauged potential interest in the idea before anything was even built. This was hosted on a tiny Linode VPS, shared with several other projects. Once the idea was validated and for the next year Joel was able to scale Buffer to 20,000 users by increasing the size of the VPS and optimising SQL queries, this meant a few hours of downtime each time the server was resized but allowed costs and time investment to remain low while product market fit was reached, or in Joel&#8217;s words:</p>

<blockquote>
  <p>Focus on &#8220;scaling&#8221; too early and you may well forget to focus on &#8220;building something people want&#8221;. Don&#8217;t make that mistake.</p>
</blockquote>

<h3>2 Servers: Moving to MongoDB</h3>

<p>As I joined Buffer the first feature we decided to build was support for posting to Facebook - the main decision was how to change the code and database schema to accommodate more than just tweets. Over the course of several weeks the model layer was rewritten and the data migrated table by table from MySQL to collections in the document-based datastore <a href="http://mongodb.org">MongoDB</a>.</p>

<p>After the switchover, the new database was kept on the existing server, taking the place of MySQL. This worked well for around a month until early one Sunday morning Buffer suddenly disappeared from the internet. After tailing the error logs we quickly realised that we had reached an inherent limitation of MongoDB - 32-bit processes are limited to ~2gb of data and we had hit that limit.</p>

<p>We searched frantically for a way to get the database back in action on the existing hardware. After half an hour with no luck and <a href="http://twitter.com/leowid">Leo</a> calming distressed users on twitter we realised we had to get in touch with the best person we knew. We called <a href="http://twitter.com/elubow">Eric Lubow</a> from <a href="http://simplereach.com">SimpleReach</a> who put us on the right path in minutes - there was no other option but to accept the downtime and spin up another 64-bit server immediately. Thanks to clear, straight forward advice we got off very lightly with less than two hours of disruption in a quiet period as we setup a server, tarballed the existing data directory and shuttled it across!</p>

<h3>4 Servers: Background Processes</h3>

<p>By November 2011, Buffer had continued to grow to around 70,000 users and with 20,000 tweets per day being sent the website and browser extension were becoming noticeably slower at the peak time of the day (for us this is around 17:00 GMT, early evening in the UK and morning on the East Coast). At this point it was time to queue the sending tasks and have them processed by their own dedicated server. In hindsight this was the turning point where a Buffer &#8216;architecture&#8217; started to emerge, with modular pieces of code and servers that we&#8217;re independent of each other.</p>

<p>As soon as the core task of sending tweets was moved to queues it became obvious that a lot of other processing could be completed this way such as gathering link info, analytics and image processing. We went ahead and moved these tasks to two new utility servers, I&#8217;ll be covering the details behind how we now use queues extensively at Buffer in a future post.</p>

<h3>5 Servers: Upgrading MongoDB</h3>

<p>In December our database server was humming along nicely but quickly filling up it&#8217;s available RAM headroom and running on an out of date version of MongoDB. In order to upgrade the software and the server to more RAM (as we would end up doing several times of the next few months) we needed to be in a replica set configuration that would allow us to take the individual database servers out of circulation one by one to upgrade them.</p>

<p>This proved to be another rocky period with several hours of downtime, we found this was almost entirely caused by issues in the immature PHP drivers which have since been addressed but also partly down to our own lack of experience managing replica sets, firewalls and all of the intricacies of a multi-server setup.</p>

<h3>7 Servers: DiggDigg Acquisition</h3>

<p>In January of this year we hit the 100,000 user milestone and completed our acquisition of the popular WordPress plugin <a href="http://bufferapp.com/diggdigg">DiggDigg</a> which allows any WordPress user to quickly add a sharing bar to their blog or website. Part of the plan behind this move was to add the <a href="http://bufferapp.com/extras/button">Buffer Button</a> to DiggDigg and have it enabled by default for new installations, adding massively to the button&#8217;s reach and Buffer branding around the web.</p>

<p>In order to handle the millions of new button impressions and isolate the web interface from load generated by third party websites it was time to move the button to it&#8217;s own servers and introduce our first load balancer. It was also decided to use Nginx AND just for good measure re-write the entire button to become independent of the Buffer framework.</p>

<p>We definitely teetered on the edge of our seats after deploying all of this previously unused architecture at once, waiting for the load from DiggDigg to hit the servers. But everything went smoothly, the load balancer acted as expected and impressions gradually rose to new highs as people upgraded their plugin (it seems there is no sudden rush of traffic!). The button servers now handle around 4 million impressions per day and rising!</p>

<h3>9 Servers: Sleepless Nights</h3>

<p>Last month we reached 180,000 registered users and completed the acquisition of ShareFeed from <a href="http://www.kissmetrics.com">KISSmetrics</a>. Almost unbelievably, at this time the main website, API, blog and browser extension were all still running from a single Linode VPS (albeit one that had been upgraded on many occasions!). During peak times things we&#8217;re beginning to feel slow again and complaints started to appear on Twitter at predictable times.</p>

<p>Unfortunately late evening Hong Kong time (<a href="http://techcrunch.com/2011/12/20/sharing-scheduler-app-buffer-raises-400000-gets-kicked-out-of-us">where we are currently based</a>) is the peak time for traffic at Buffer. For almost a week I had incredibly restless sleep, I became acutely aware of every email received, waking up at the slightest sound convinced that the site would be down. It was definitely time to upgrade.</p>

<p>Thanks to all we had learnt creating the new environment for the Buttons several months before, we were able to make this move completely seamlessly. By setting up the load balancer, adding the new servers and testing thoroughly before moving the DNS we were able to ensure that the only thing users noticed was a performance increase.</p>

<h3>Thats Not All Folks</h3>

<p>It&#8217;s been an amazing ride so far with both highs and some serious lows, at one point working for nearly 30 hours straight just to keep the site online. We have learnt an incredible amount as a team in the last few months and I can&#8217;t think of any way we could have learnt more, faster.</p>

<p>Last week we migrated the whole of Buffer&#8217;s architecture to Amazon Web Services with less than two hours of scheduled downtime, making a number of huge changes and improvements in the process. I&#8217;ll cover some details of this migration in a future post.</p>

<p><strong>I&#8217;d love to hear any comments your have or similar stories of battling scaling woes as a small startup!</strong></p>
