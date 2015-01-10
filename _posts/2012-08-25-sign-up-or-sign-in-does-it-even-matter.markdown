---
layout: post
title: Sign Up or Sign In, Does it Even Matter?
comments: true
tags:
- signup
- signin
- ux
- user experience
- conversion
- buffer
---
<p><img src="http://media.tumblr.com/tumblr_m9990sD8nB1qz7mjl.jpg" alt="The Hurdle of Signup" title="The hurdle. It&#8217;s a metaphor!"/></p>

<h2>The Idea</h2>

<p>Like any startup, at <a href="http://bufferapp.com">Buffer</a> we are always looking for ways to reduce friction at every stage of using the product, from the moment you land on the homepage to the daily use of our browser extensions and web app.</p>

<p>One of the key points in the user lifecycle is getting people over the hurdle of signing up for your app, of course this should be as seamless as possible, particularly in the consumer internet space. In the last few years this has become easier than ever - with the advent of OAuth solutions such as Facebook Connect and Twitter Sign In users often no longer need to enter any details at all to sign up for your service.</p>

<p>This got us thinking could we completely remove the barrier of signing up all together? <strong>Could we make the account creation experience so easy that you might not even notice it had happened?</strong></p>

<h2>The Approach</h2>

<p>While there are some intricacies to handling a combined signup / signin on the server the first step is authorising the user with their social network of choice - and of course the UI is simpler than ever. We decided on a familiar &#8216;stack&#8217; of social networking buttons that can be consistently reproduced in all of the different sign in locations we have (web, browser extension, mobile).</p>

<p><img src="http://media.tumblr.com/tumblr_m99djgKIaH1qz7mjl.png" alt="Mobile sign in options"/></p>

<p class="caption">Our sign in screen, as seen on mobile.</p>

<p>On the web app the stack sits on the right hand side of our homepage and acts as a bright, strong call to action to. As more networks are added in the future we will likely add a &#8220;more options&#8221; button combined with a memory of the users last sign in choice which will always be displayed at the top of the stack.</p>

<p>Choosing the wording &#8216;Sign In&#8217; on the buttons rather than &#8216;connect&#8217; or other alternative wording hopefully gives the subtle impression that even new users already have an account and they just need to sign in to access it. The key is with &#8216;Sign In&#8217; you don&#8217;t expect to have to do any more work, which makes the hurdle smaller.</p>

<h2>Key Lessons</h2>

<h3>Users are often looking for the words &#8220;sign in&#8221;, &#8220;sign up&#8221; or &#8220;log in&#8221;</h3>

<p>Even (or perhaps especially) with a combined signup / sign in it is important to make it very clear that the user can do both actions with the same buttons. We included a friendly note on every entry point to get this message across</p>

<p><img src="http://media.tumblr.com/tumblr_m997xob0rW1qz7mjl.png" alt="Friendly Note"/></p>

<p class="caption">Let people know that they can do both actions in the same place.</p>

<h3>Many people forget which social network they used previously</h3>

<p>This is one of the biggest problems we had after rolling out the changes, many users were forgetting which social network they had used to login and were creating two, three and even more accounts. Obviously this is a terrible user experience and it can also completely skew your metrics.</p>

<p>We dealt with this situation in a couple of ways; by storing a separate long-life cookie whenever a user signs in we can check on signup if a user has been to Buffer before - we catch people that try to sign up with the cookie and display a screen like this:</p>

<p><img src="http://media.tumblr.com/tumblr_m997vegLV41qz7mjl.png" alt="Continue Screen"/></p>

<p class="caption">Detect and give users the option to sign in again.</p>

<p>Inevitably some users still fall through the cracks, perhaps because they clear their cookies or simply click on &#8216;create account&#8217; anyway. In these cases we need to let them merge their accounts together.</p>

<p>In Buffer we allow users to connect additional social media accounts on the dashboard, when the feature was first launched connecting an account already in the system would throw an error with a message to contact support - this would affect anyone who had accidentally created two accounts! As you can imagine, merging accounts quickly became one of our biggest support requests.</p>

<p>Thankfully we have now completely removed this friction point also, as authorising with the social network is proof of ownership connecting an account that is already in the database simply merges the two together, seamlessly in the background.</p>

<h3>What about their email?</h3>

<p>The disadvantage of users signing up with a social network is that you can&#8217;t always get their email address and other details that may be important for your business. At Buffer we use the email to send alerts if there are any problems or if your Buffer becomes empty as well as optional newsletters and lifecycle triggered retention emails.</p>

<p><img src="http://media.tumblr.com/tumblr_m99bkhb7bn1qz7mjl.png" alt="Email Banner"/></p>

<p class="caption">The passive email banner</p>

<p>Rather than immediately hassle the user after signing in with a social network (that kind of defeats the point, doesn&#8217;t it?) We opted to display a more passive banner at the top the dashboard which lets the user know <strong>the reason</strong> we would like to have their email address, this works well and only displays after a welcome tour which means the user is much more invested in the product than they would have been if asked on a signup page.</p>

<h2>Conclusion</h2>

<p>So, does it matter? I would say that with the right measures in place to catch and automatically repair duplicate accounts it doesn&#8217;t matter at all and in fact reducing complexity of the sign up process is well worth these measures.</p>

<p>It is now very rare that we get any of the support issues above and because the nature of Buffer is managing and connecting many social accounts we were probably more inclined to get these types of problems than many apps would be.</p>

<p><strong>Have you implemented social sign in differently or had interesting problems with it in the past? I&#8217;d love to hear your solutions and thoughts in the comments</strong></p>

<p class="caption">Photo by <a href="http://www.flickr.com/photos/nickuzma">nickuzma</a></p>
