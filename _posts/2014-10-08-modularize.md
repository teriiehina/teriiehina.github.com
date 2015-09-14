---
layout: post
title: How to modularize an iOS app
categories:
- programming
status: publish
type: post
published: true
---
This is the first post of a serie which will try to make you through the process of modularizing an existing iOS app.

We will be using (of course?) Cocoapods. A great introduction is the blog post <a href="http://dev.hubspot.com/blog/architecting-a-large-ios-app-with-cocoapods">Using CocoaPods to modularize a Big iOS</a> App by <a href="http://dev.hubspot.com/blog/author/anthony-roldan">Anthony Roldan</a> at <a href="http://dev.hubspot.com/blog">Hubspost's blog</a>.

Here's some questions we will try to address through this serie:
<ul>
	<li>How coupled are the existing classes ? (aka how big is the spaghetti plate ?)</li>
	<li>Should we think by screen or by layer ? Both ? Neither ?</li>
	<li>How big the toolbox (utility classes commons to many screens) should be ?</li>
	<li>How do you begin ? Taking a big dive and go for the most important screen or begin at the suburbs of your app (I guess we can all answer to that one right now... but maybe not)</li>
	<li>How do you do that in an app being shipped every 4 to 6 weeks ? Of course you will need heavy testing to prevent any major crash but how can you minimize the burden on the other developers' productivity ?</li>
	<li>Won't having a pod for each screen/layer/brick slow down the pace of development ?</li>
</ul>
The first "real" post will try to answer the first two questions :)