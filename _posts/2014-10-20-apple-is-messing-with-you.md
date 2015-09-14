---
layout: post
title: What to do when Apple is messing with you ?
categories:
- freelancing
status: publish
type: post
published: true
---


So you care about app quality. Thus you need to test your app. So you have a lot of tests for several parts of your application. Thus you want to run them as often as possible. And you want to keep track of all those runs. Thus you want to automate all this and record the results. Yes, indeed, I'm talking about the continuous integration we all know about.

But how do you do it ? With Xcode Server, because it's what Apple says you should use ? Or <a href="http://jenkins-ci.org">Jenkins</a> because your company has already one master with severals slaves set up and you just have to create a job ? Oh, look at all those plugins jenkins has to monitor code coverage and to easily notify you wherever *cough cough* slack/irm/jabber *cough cough* you want.

Let's try with Jenkins (or any other CI which isn't Xcode Server). So whatever the tool you are using (<a href="https://travis-ci.org">TravisCI</a>, <a href="https://github.com/facebook/xctool">xctool</a> wrapped in a shell script inside a <a href="https://gitlab.com/gitlab-org/gitlab-ci/blob/master/README.md">gitlab-ci</a> job etc etc...) you won't be able to do without <a href="https://developer.apple.com/library/mac/documentation/Darwin/Reference/ManPages/man1/xcodebuild.1.html">xcodebuild</a>. And this is where it gets less funny (since Xcode 6).

Because after searching for hours, maybe days, blaming you first before trying to reject the fault on anybody else, <a href="http://stackoverflow.com/questions/25380365/timeout-when-running-xcodebuild-tests-under-xcode-6-via-ssh">you will find that when xcodebuild is asked to test a scheme from a headless shell (i.e. ssh, i.e. no GUI), it will time out. Without any meaningful informations</a>.

So you may try whatever you want but you'll always come back to xcodebuild. You will use any tests frameworks that look exotic enough so that you can have a glimpse of hope that it won't be related too much to xcodebuild. But they all are.

Thus your 170+ unit tests and you 90+ UI tests will be as useful as a saddle-less bicycle. For days/weeks/monthts. Whatever. Not Apple problem. <a href="http://radar.apple.com">You can open a radar</a>. You may get an answer. But whatever.

And then, one day (let's say with the Yosemite public release), everything is back into order. And you are required to be grateful. Got that. Be grateful.