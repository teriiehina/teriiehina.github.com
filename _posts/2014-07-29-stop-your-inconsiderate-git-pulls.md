---
layout: post
title: Stop your inconsiderate "git pull"
categories:
- IT
tags: []
status: publish
type: post
published: true
---

A recent merge request:

![Too much branch merging](/assets/images/commit_pb.png)

<h3>Why is it a problem ?</h3>
Because when you navigate in your commits log, this is a lot of noise. Of course, you can filter the logs but when you go through your commits log, it's rarely for the beauty of it. It's because you need to fix a bug, or assert if a specific fix made it into the current branch.
<h3>Why does it behave like that ?</h3>
Because
<ul>
	<li>you want to stay up-to-date with "<em>origin/develop</em>" and you pull regularly <strong>AND</strong></li>
	<li>your local "<em>develop</em>" has a change not in "<em>origin/develop</em>"</li>
</ul>
So everytime you pull (aka fetch + merge), git has to create a commit to acknowledge the merge. If you had, in your branch "<em>develop</em>" the same work as in "<em>origin/develop</em>", you will have the so pleasant "fast forward" message :)
<h3>How to prevent that</h3>
<ol>
	<li>git fetch --all</li>
	<li><em>git co -b dev_to_do origin/develop</em></li>
	<li><em>[commit brilliant programming here]</em></li>
	<li>git fetch --all</li>
	<li>git merge origin/develop</li>
	<li>git push origin develop</li>
	<li><em>[create a clear merge request or send a patch]</em></li>
</ol>
<h3>And then ?</h3>
And then, after your merge request has been accepted, the next time you pull "<em>origin/develop</em>" in your local "<em>develop</em>", the work you did in "<em>dev_to_do</em>" will enter your develop with via a fast forward.