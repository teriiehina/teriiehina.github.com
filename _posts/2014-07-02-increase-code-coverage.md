---
layout: post
title: How to increase tests coverage on an existing codebase
categories:
 - programming
 - testing
status: publish
type: post
published: true
---

TDD sure is cool but how do you TDD on an existing codebase ? ;)

Tests coverage sure got a lot of benefits and you sure should want to add them to existing code. But how ?

More clearly : how can you motivate your programmers to add tests (unit, functional, behavior, whatever) to a code that was committed 3 months ago and is working "perfectly" ?
<h4>Face the cold reality</h4>
If the code hasn't been TDD-ed or was brought to this world with no consideration whatsoever to testing, things like isolation, mocking and dependency-injection will be missed. A lot.

Thus don't go on the "increase the coverage by 1% a day" or others similar rules before you can grasp the whole picture. That sole grasping thing could take a few days :)
<h4>You Can’t Improve What You Can’t Measure</h4>
The good news is <a href="https://github.com/jonreid/XcodeCoverage">tests coverage for iOS is fairly easy nowadays</a> so you can raise awareness among your programmers without frightening them.
<h4>Bugs are opportunity</h4>
More important than your testing frameworks or your testing techniques is your test plan. What to test, with which tests case, that's the hard part to do right.  And it is time-consuming. If you aren't lucky enough to have a Q&amp;A departement, bugs are your new best friends.
<blockquote>bug = "a test case" + "a test that fail" (for free !)</blockquote>
So next time a bug appears in you Jira/Mantis/Redmine/Github/Bitbucket, ask yourself if it can be converted to a test.
<h4>Go for unit testing</h4>
Functional/behavior testing is the most interesting but also the most difficult (to program as well as to set up). So don't put the cart before the horse and accept to go slowly in the beginning of your endless quest. And <a href="http://en.wikipedia.org/wiki/Model_View_ViewModel">MVVM</a> should give you a pretty decent way to "test the views" of your application.
<h4>And just do it.</h4>