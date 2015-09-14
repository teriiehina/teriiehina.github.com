---
layout: post
title: How coupled are your classes ?
categories:
- Programming
status: publish
type: post
published: true
---

So, what is, formally, a coupling ? Of course, one will go to Wikipedia's page «<a href="http://en.wikipedia.org/wiki/Coupling_(computer_programming)">Coupling (Computer programming)</a>» to have a first answer. But maybe we can try to search on our own.

For the moment, we will try to modularize on a screen basis, i.e. to move each screen into its own pod. Thus what we want to know is how much "link" there is between a screen and the others modules of the application.

Fortunately, we already have a division of our modules by screen:

<a href="https://wearemobiledevelopers.files.wordpress.com/2014/10/capture-d_c3a9cran-2014-10-08-c3a0-14-23-01.png"><img class="alignnone size-full wp-image-203" src="https://wearemobiledevelopers.files.wordpress.com/2014/10/capture-d_c3a9cran-2014-10-08-c3a0-14-23-01.png" alt="Capture d’écran 2014-10-08 à 14.23.01" width="197" height="240" /></a>

From the outside, this seems nice and clean but maybe not. So how to measure how entagled our code is. A possible start would be to list all the <em><strong>#import</strong></em> of headers which are not in the same module as the importing file.

Let's try with the <strong>HP</strong> module. First, we want to find all the <em><strong>#import</strong></em>.:
<pre>find . -name "*.[hm]" | xargs cat | grep "#import"</pre>
Maybe we would like to know which header is the most imported:
<pre>find . -name "*.[hm]" | xargs cat | grep "#import" | sort | uniq -c | sort</pre>
Next, we want only the name of the header (forgive my shell scripting capabilities please), that we will keep in the <em><strong>/tmp/imported.txt</strong></em> file
<pre>find . -name "*.[hm]" | xargs cat | grep "#import" | sort | uniq | sort | sed 's/#import //' | sed 's/"//g' | sed 's/.*\///' | sed 's/&gt;//' | sed 's/&lt;//' | sed 's/ //g' &gt; /tmp/imported.txt</pre>
Then, we want all the headers in the module, and we will put them in the <em><strong>/tmp/same_modules.txt</strong></em>:
<pre>find . -name "*.h" | sed 's/#import //' | sed 's/"//g' | sed 's/.*\///' | sed 's/&gt;//' | sed 's/&lt;//' | sed 's/ //g' &gt; /tmp/same_module.txt</pre>
At last, we want all the headers in the /tmp/imported.txt but not in the /tmp/same_modules.txt, which we can write as
<pre>comm -2 -3 /tmp/imported.txt /tmp/same_module.txt &gt; /tmp/extern.txt</pre>
So now, a bit of stats:
<pre>➜ HP git:(develop) wc -l /tmp/same_module.txt
 45 /tmp/same_module.txt
➜ HP git:(develop) wc -l /tmp/imported.txt
 120 /tmp/imported.txt
➜ HP git:(develop) wc -l /tmp/extern.txt
 106 /tmp/extern.txt</pre>
So in the HP module, we import <strong>120</strong> headers. <strong>106</strong> of those aren't in the module.

Looks like a lot of fun.
