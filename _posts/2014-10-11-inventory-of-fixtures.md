---
layout: post
title: Inventory of fixtures
categories:
- freelancing
status: publish
type: post
published: true
---


So <a href="http://wearemobiledevelopers.wordpress.com/2014/10/08/how-coupled-are-your-classes/">our last post</a> gave us the basic tool to see how intricated our classes were. So let's do the boring job to get everything we need and launch our commands on the corresponding files.

<strong>Caveat</strong>: you may be tempted to compare all the headers imported by source files in a module using <strong><em>comm</em></strong>. Reading <em><strong>man comm</strong></em> could make you think this is a good idea. It isn't, because compare line by line, instead of searching each line of a file in the other one. Therefore I strongly recommend you the following perl oneliner, from this <a href="http://stackoverflow.com/a/17703442/700317">SO answer</a>:
<pre>perl -ne 'print if ($seen{$_} .= @ARGV) =~ /10$/' imported_headers.txt headers.txt | wc -l</pre>
And here is our results. Analysis is coming but can you already see the big problem and the quick win we have at hands ?

<a href="https://wearemobiledevelopers.files.wordpress.com/2014/10/capture-d_c3a9cran-2014-10-09-c3a0-16-59-03.png"><img class="aligncenter wp-image-206 size-full" src="https://wearemobiledevelopers.files.wordpress.com/2014/10/capture-d_c3a9cran-2014-10-09-c3a0-16-59-03.png" alt="Capture d’écran 2014-10-09 à 16.59.03" width="578" height="194" /></a>