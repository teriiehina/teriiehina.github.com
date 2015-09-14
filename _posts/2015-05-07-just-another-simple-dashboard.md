---
layout: post
title: Just another simple dashboard
categories:
- programming
status: publish
type: post
published: true
---


Nobody would refute that a dashboard is useful [1]. So why do we see so few of them in real life ?

Of course, there <a href="https://github.com/Reportr/dashboard">are</a> <a href="https://github.com/keen/dashboards">many</a> <a href="https://github.com/hongrich/Dashboard">ready-to-use</a> <a href="https://github.com/etsy/dashboard">projects</a> you can start from to build your dashboard. <a href="https://github.com/yaronn/blessed-contrib">Even ascii ones</a> ! And you can build your own from scratch. So why don't we see more of screenshots of the way mobile developers keep track of their everyday job ?

Maybe all of us have dashboards but the numbers are so bad, we are ashamed to show them. Maybe those numbers are so good we would look like bragging. Maybe the metrics are so sensitive that if our concurrent could have just a peek at them, we would fall behind in the race to be the next Facebook.

Meh.

What I believe is dashboard are frigging hard/expensive to set up. Start from scratch and you will have to re-invent the wheel to end with something ugly. Take an already existing project and you lose time learning to think like its creators.
<h6>So why is it so hard ?</h6>
<ul>
	<li>We want something beautiful. As developers, we generaly don't think too much into aesthetics, but as the sole purpose of the dashboard is to be seen (no interactions), we understand that it need to be at least clear and meaningfull, but also pleasant to the eye. And we are no graphic designer.</li>
	<li>We need to deal with differents data sources. SCM and CI servers, some monitoring of the app in production, a bit of agility, maybe from differents networks, all mixed in a single window !</li>
	<li>"Just displaying" datas can't be that hard, can it ? So it's likely that the management will give you a third or a fourth of the time really needed.</li>
	<li>And we may want manual inputs as well ! Endless troubles !</li>
</ul>
<h6>How to make it less painfull ?</h6>
What follows is certainly not the best, most elegant, solution of all time. But It Just Works©. We had to deal with every problems listed before. So here's how we did it.

<strong>The front-end.</strong>

Not starting from scratch, not using an existing framework, but something in the middle: a webapp template, without any logic code inside. A simple, but beautiful plain dumb display. <a href="https://almsaeedstudio.com/preview">AdminLTE from Almsaeed Studio was our pick</a>.

To be able to develop the front-end, we use an intermediate datasource. We can mock up our data and even divide the . Simple and effective to fake data and check the behavior of your dashboard as the data changes. <a href="https://www.parse.com">Parse</a> is the perfect choice for this.

The secret to make everything as simple as possible is to not use any application server. Nothing rendered server-side. Just a local webapp. So the deployment of the dashboard on any computer is minimal.

<strong>The "middleware"</strong>

Plain Old Shell Script. With curl[2]. Launched by a jenkins job or cron. Dead simple, dead effective. And it uploads the metrics in Parse.

<strong>The "back-office"</strong>

This is merely exposing an HTTP endpoint from you real datasources. But here is another trick: by using an intermediate datasource, you can make an app (what about a mobile app for example) to update any metrics in your dashboard. Once again, using something like Parse is a real time-saver, but any other similar services will do the trick.

<strong>The metrics</strong>

So, what to display ? As it was once said: «a picture is worth a thousand words» so here it what we use:

<img class="aligncenter wp-image-263 size-large" src="https://wearemobiledevelopers.files.wordpress.com/2015/03/screen-shot-2015-03-26-at-13-01-411.png?w=660" alt="Screen Shot 2015-03-26 at 13.01.41" width="660" height="522" />

And of course, it is responsive, but that is thanks to <a href="https://almsaeedstudio.com/preview">Almsaeed Studio</a>.

<a href="https://wearemobiledevelopers.files.wordpress.com/2015/03/screen-shot-2015-03-26-at-13-01-481.png"><img class="alignnone size-medium wp-image-262" src="https://wearemobiledevelopers.files.wordpress.com/2015/03/screen-shot-2015-03-26-at-13-01-481.png?w=130" alt="Screen Shot 2015-03-26 at 13.01.48" width="130" height="300" /></a>

[1] : if you display meaningless metrics on your dashboard, it isn't a dashboard, it's just a waste of pixels and time.
[2] : easiest way to deal with proxy, and you can prototype your script in ... the shell ! woot \o/