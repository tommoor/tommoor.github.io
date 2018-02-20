---
layout: post
title: "Reclaim Your Privacy"
date: 2017-01-07 21:00 -0800
comments: true
tags:
- privacy
- security
---

In 2017 it’s incredibly hard to use the internet without constantly giving away your personal information… it’s absolutely the norm for a single website you visit to send personally identifying information to your ISP, the website itself, their advertisers, multiple tracking and analytics companies, plus all the social networks you’re logged into.

I don’t think you have to be paranoid, taking part in nefarious activities or a privacy obsessive to not want this to be the case! To me it seems like common sense that you would reduce the amount of personal information you leave lying around on companies servers in the same way it’s common sense not to leave your bank details lying on the street.

Thankfully with just a little effort you can make a huge difference without having to jump through lots of hoops every time you use the internet!


## Install an AdBlocker
You’re probably already using an AdBlocker, according to [ClarityRay](https://www.quora.com/What-is-the-percentage-of-Internet-users-that-employ-AdBlock-Plus-or-similar-ad-blocking-plugins) on average around 10% of visits to websites use an AdBlocker of some description.

By blocking adverts you reduce visual clutter, increase page load times and limit the amount of information about your browsing habits gathered by third parties. I recommend [UBlock Origin](https://chrome.google.com/webstore/detail/cjpalhdlnbpafiamejdnhcphjbkeiagm) for the lightest footprint.

Since installing on my machine it has blocked 7% of outgoing connections - almost 1 million requests.

Whilst you’re at it don’t forget about your mobile browser. For iOS [‘Focus’ by Firefox](https://itunes.apple.com/us/app/firefox-focus-privacy-browser/id1055677337?mt=8) is the way to go, ensure you enable the integration with Safari to get all it's benefits.


## Ensure HTTPS
The [HTTP Everywhere extension](https://chrome.google.com/webstore/detail/https-everywhere/gcbommkclmclpchllfjekcdonpmejbdp/related) from the EFF makes sure that you always connect to the secure version of web services if available - this prevents your ISP and other middlemen from inspecting and potentially injecting content into webpages you load (Yep, [they](http://arstechnica.com/tech-policy/2014/09/why-comcasts-javascript-ad-injections-threaten-security-net-neutrality/) [do](http://arstechnica.com/uncategorized/2007/12/canadian-isp-tests-injecting-content-into-web-pages/) [this](http://www.infoworld.com/article/2925839/net-neutrality/code-injection-new-low-isps.html)).


## Change Your Default Search Engine
Google is great and the results are obviously top notch - however their data collection policies are really awful. I find for 99% of searches [DuckDuckGo](https://duckduckgo.com) does just as good a job and doesn’t track your activity against an extensive personal profile like Google will.

DuckDuckGo makes a great default search engine that is visually very similar to Google, you can find [quick install instructions here](https://duckduckgo.com/install).


## Chrome Privacy Settings
Using Chrome? Next up lets customize the privacy and content settings to be a little more picky about the data we give away. First off you’ll want to block third party cookies, navigate to: [Chrome Content Settings](chrome://settings/content)

Check “Block third party cookies and site data”. This helps to prevent trackers that may slip through UBlock from tracking you across websites.

Next head to [Chrome Settings](chrome://settings), scroll to the bottom and click the tiny text that says “Show advanced settings…”, scroll again to Privacy (Phew, it’s almost like they don’t want you to find this!).   I would recommend unticking the majority of these settings apart from Send a “Do Not Track” request with your browsing traffic which should be ticked and probably isn't.

<p style="text-align: center;"><img src="/images/chrome-privacy.png" alt="Chrome Privacy"></p>
￼

## Google Privacy Settings
The big G provides a [single dashboard for managing activity](https://myaccount.google.com/activitycontrols) that they track and save. Personally I have everything here disabled (paused) apart from ‘Device Information’ which keeps your apps and settings synced across devices. By default Google will be tracking your location, search history and every webpage you visit if you’re using Chrome - eesh.


## Facebook Privacy Settings
Most of us have a Facebook account even if it doesn’t get used too much. At this point we’ve blocked Facebook’s trackers on other websites, told them not to track us and ensured we’re always viewing Facebook over HTTPS but there’s definitely more to do!   By default Facebook’s advertising policies are quite… invasive, lets turn them down a bit by visiting the [Facebook Privacy Settings](https://www.facebook.com/settings?tab=ads)

<p style="text-align: center;"><img src="/images/facebook-privacy.png" alt="Chrome Privacy"></p>

Turn everything on that page to “No”. Next hit up the [timeline option](https://www.facebook.com/settings?tab=timeline&view) and consider turning off photo tagging suggestions at the bottom of this page.

This is also a good opportunity to double check which apps you’ve authorized to read your Facebook information and remove any you no longer want to have access, the full list of [apps with access to Facebook](https://www.facebook.com/settings?tab=applications).

<p style="text-align: center;"><img src="/images/facebook-apps.png" alt="Chrome Privacy"></p>

At the bottom there is also an “Apps Others Use” section, click edit and untick everything in there which gives permission for your friends to share your data. It won’t have any effect on your personal Facebook experience as far as I can tell.


## Twitter Privacy Settings
We’re getting somewhere, don’t give up yet! Next up is Twitter - similar to Facebook you’ll want to turn off all the advertisement tailoring and maybe the default location tagging depending on your preference on the [Twitter settings](https://twitter.com/settings/security) (Don’t forget to hit ‘Save Changes’ at the bottom of the page)

You might have accidentally uploaded your entire address book to Twitter (they make this way too easy) - double check if that’s the case here and consider deleting the data on the [Twitter contacts dashboard](https://twitter.com/settings/contacts_dashboard).

This is also a good opportunity to double check which apps you’ve authorized to read your Twitter information and remove any you no longer want to have access, here is the full list of [apps with access to Twitter](https://twitter.com/settings/applications).


## Install a Password Manager
If you’re still using a ‘system’ (hey, we’ve all done it!) or worse yet the same password for everything then now is the time to upgrade to a Password Manager, that way if one website gets compromised you don’t risk your other accounts being hacked too.

[1Password](https://1password.com) is pretty awesome and you can make this change gradually by moving your passwords into the manager as you login to services instead of all in one go. You’ll never have to try and remember which dumb rules a website expected for a password ever again.


## Install a Firewall
It’s easy to forget about the desktop apps you use, they are all constantly phoning home too. [Little Snitch](https://www.obdev.at/products/littlesnitch/index.html) will alert you every time an app tries to access the internet and let you set rules for access rather than letting everything out by default.

I’ll be honest, it’s a real pain to use for the first few hours because rules need to be created for all your existing apps but the peace of mind may be worth it - did you know Spotlight makes requests to lots of different services for everything you type in there?


## Use a VPN
A VPN obscures your real IP address, and with it your location. It also creates an encrypted tunnel for all of your internet traffic that prevents your ISP from knowing and logging the websites that you visit.

If you have the technical skills and time I highly recommend setting up your own installation of OpenVPN - [here is a good tutorial](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-16-04) for doing so on a DigitalOcean server that will run you $5/month. [TunnelBlick](https://tunnelblick.net/downloads.html) is a great well maintained, open source OpenVPN client for Mac.


## Fin
Phew! If you got this far then you are now considerably better off than you were at the start of this post.

Is this foolproof? No, of course not - but with a little effort you’ve vastly reduced the amount of personally identifying information that is being gobbled up by companies about you with minimal affect on your everyday computer usage, nice!

**Got any more suggestions for easy to implement privacy fixes? Let me know in the comments.**
