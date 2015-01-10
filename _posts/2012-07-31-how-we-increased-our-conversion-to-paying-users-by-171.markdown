---
layout: post
title: ! 'How We Increased Our Conversion to Paying Users by 171% '
comments: true
tags:
- buffer
- startups
- abtesting
- testing
- experiment
- analytics
- kissmetrics
- conversion
---
<p>At <a href="http://bufferapp.com">Buffer</a> we are currently focused on driving growth to a new level, in the process we are trying many different channels to increase the number of visitors and signups including content marketing, web stores, mobile markets and more.</p>

<p>In the past week I decided to take a quick look at our homepage and how we might improve our conversion instead of driving more new visitors - after all, if we can improve the conversion whilst still increasing visitors it has a compound affect!</p>

<p>Previously we have not had much luck with A/B testing, it&#8217;s something we often do and have infact built an internal library called &#8216;Einstein&#8217; which makes it super easy for anyone on the team to deploy a <a href="http://www.startuplessonslearned.com/2008/09/one-line-split-test-or-how-to-ab-all.html">one-line split test</a> anywhere in the product. We have continuously been amazed at how seemingly large changes can actually make very little difference to conversion and activation, particularly in the early days of the product (more on this later).</p>

<h3>Examples of Some Failed A/B Tests</h3>

<h4>Homepage Tagline Changes</h4>

<p>This is an area we predicted would have a big effect, the thinking being that the main headline on the landing page would be a driving factor in whether people are interested in the value (and we all know not many users read further than the headline!).</p>

<p>In the early days <a href="http://joel.is">Joel</a> tested between several variations of text including &#8220;<strong>Be awesome on Twitter</strong>&#8221;, &#8220;<strong>Get 200% more clicks on Tweets</strong>" and "<strong>A Smarter Way to Share</strong>&#8221;. Unfortunately none of these variations had a significant impact on conversion.</p>

<h4>Colour of Call to Action</h4>

<p>After meeting <a href="http://twitter.com/tferriss">Tim Ferris</a>, he suggested that we try a higher contrast, orange call to action. At the time we had a single signup button that was a dark shade of green. The difference was similar to below (although unfortunately we don&#8217;t still have the exact screenshots).</p>

<p><img src="http://media.tumblr.com/tumblr_m81738uiAj1qz7mjl.png" alt="Changing colour and location of signup"/></p>

<p class="caption">The two variations used, with a bright central call to action.</p>

<h4>Positioning Changes</h4>

<p>We also tried moving the main call to action on the homepage to see if this would have any impact, flipping the page horizontally as well as trying a stark version with no introductory video and a large central signup button! The affect? Negligible.</p>

<h4>Interstitials vs Dropdowns</h4>

<p>We have also done split tests on internal product features and design variations, one in particular showed 50% of new users an interstitial to install our browser extension whilst the other 50% saw a drop down bar once they began using the product. The hope here was to increase the activity of new users by ensuring they installed the extension, but after running the test for several weeks the cohort analysis showed no discernable difference.</p>

<h3>The First Successful A/B Test</h3>

<p>In the past week we ran a new A/B test on the homepage that shows potential users more detail about <a href="http://bufferapp.com">Buffer</a>, in particular some of our most popular features run directly below the signup box (multiple accounts, analytics and team members). The hypothesis was that potential users are now discovering Buffer through more channels than just our content marketing efforts and a lot of people might not understand how much Buffer can offer when they first land on the page.</p>

<p><img src="http://media.tumblr.com/tumblr_m7vdo2A2ZQ1qz7mjl.png" alt="The two variations used"/></p>

<p class="caption">The two variations used, original on the left and the variation on the right.</p>

<p>We are now tracking all of the tests we perform with <a href="http://www.kissmetrics.com">Kissmetrics</a> which enables us to easily produce reports for our entire funnel, which currently looks like:</p>

<p><img src="http://media.tumblr.com/tumblr_m8180zPFEh1qz7mjl.png" alt="The conversion funnel"/></p>

<p>The results (and the trigger for this post!) seem to be for the first time both very positive and statistically significant although entirely unexpected. Every point in the funnel proved to be outperforming the original by multiple percentage points, but in particular upgrades were up a whopping 171%.</p>

<p>This outcome was totally unexpected and also shows the importance of tracking your split tests at a <a href="http://www.startuplessonslearned.com/2008/09/one-line-split-test-or-how-to-ab-all.html">macro level</a>, and not just whether there were &#8216;more clicks on the button&#8217;. In this case we would have seen that the increase in signups was statistically insignificant and could have even reverted back to the old layout!</p>

<h3>Conclusions</h3>

<h4>It Takes Many Tries</h4>

<p>A/B Testing is difficult! It could be easy to conclude from the many posts highlighting successful A/B tests that getting clear cut results is simple and you too can double your signups by changing the colour of a button but for us that wasn&#8217;t the case.</p>

<p>So far we&#8217;ve found that getting statistically significant results tends to take many iterations and much bigger changes than you might imagine, I don&#8217;t doubt we will need to perform many more tests to get another significant result of this type.</p>

<h4>Where Your Visitors Come From Makes a Difference</h4>

<p>Many of the unsuccessful tests listed above were performed in the first eight months of Buffer&#8217;s life, at this point in time our inbound traffic was much smaller and the traffic we did have often came from early adopters and detailed blog posts explaining how to use Buffer in great detail.</p>

<p>I am sure this will have had an affect on the results as a larger percentage of these users will have hit the homepage knowing what Buffer is and knowing they wanted to try it out. This may go someway to explaining why many of the tests in the early days displayed little variation at all.</p>

<p><strong>Have you had a run away split test success or perhaps you&#8217;ve tried hundreds of variations with no results - I&#8217;d love to hear your stories in the comments!</strong></p>

<h3>Resources</h3>

<ul><li><a href="http://www.kissmetrics.com">KISSmetrics</a> - Particularly tailored to enable easy tracking of SAAS metrics.</li>
<li><a href="http://getdatadriven.com/ab-significance-test">A/B Significance Test</a> - Handy tool to measure if your results are statistically significant.</li>
<li><a href="http://www.evanmiller.org/how-not-to-run-an-ab-test.html">How not to run an A/B test</a> - Why you shouldn&#8217;t peak at your results early.</li>
<li><a href="http://www.exp-platform.com/Pages/hippo.aspx">A Practical Guide to Controlled Experiments on the Web</a> - The techniques used for experiments at Amazon, Microsoft and NASA.</li>
</ul>
