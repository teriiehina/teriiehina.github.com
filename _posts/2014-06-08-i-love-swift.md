---
layout: post
title: I love swift
categories:
- Void
tags: [Swift Programming iOS OSX]
status: publish
type: post
published: true
---

I love Swift. I really do. Not only for what it is (an elegant and modern language which is really object oriented) but for what is represent: a whole new view of the Apple dev world. I didn't think I would write here again but [a post by the philantropist Garoo](http://www.ff00aa.com/fr/archives/2014/06/07/11105-on-swift/) tickled my french side, which consists of giving my opinion even it wasn't asked.

# On how Swift works

It really is a beautiful language. I'm no expert in programming languages but I love them. I use Objective-C on a daily basis. I'm fluent in Ruby, worked a bit in Python, and read some Go / Scala / Lisp / Javascript when I'm bored. 

I like to see the expressiveness of Swift. Of course, some idioms are «strange». But we have seen Swift code for less than a week. May I repeat: less than a week. A week. Seven days.

The thing that strikes me the most with Swift is that everything is an object. I think it is in «Advanced Swift» (WWDC 2014, video 404, if you can find it ;)) that one Apple's engineer says that basic types (Int, Float, Bool …) in Swift are just structs. But when you see that Swift's structs can have methods members amd supports protocols, and that the Swift programming guide says that what distinguish structs from classes is inheritance and passing parameters by value (structs) or reference (objects), one can says that structs are objects.

I like that. One could say that Swift is nearer to Smalltalk than Objective-C in this aspect. And I am keen to read Swift's source code. Apple releasing Swift to the open-source world is, imha, a *sine qua non* to Swift's success.

# On what Swift means

But I could love Swift even it was less elegant. Because there is a magic aspect to it: it can use all of the Cocoa/CocoaTouch frameworks from day one. It can be integrated within an existing Objective-C program. It can call Objective-C librairies. And yes, your favorites pods too. Believing in magic is about not knowing the trick and this one isn't very complicated. But still, it's cool.

I like that because it emphasize the distinction between a language and a framework. Why does this matters ? Because most of us think we are developing using a language, where in fact we are developing using frameworks. If we can keep this in our head, it will help us to design a better code, where any class or function could be move one day in a framework. That may seem a small feature, but it is one I care a lot about in my daily work.

Also, if a new language with a different syntax can use an existing framework in Objective-C, maybe another language (C#, Go) can. To my recollection, I think [MonoTouch](http://xamarin.com/platform) re-implements some of CocoaTouch parts. Once again, I'm too lazy to check. And what about using Swift to program a native Android or WP app ? Probability: low. Sexyness: high.

Another striking thing with Swift is that it tells a hidden story of Apple. Even heard about [RubyMotion](http://www.rubymotion.com), the ruby SDK that also use directly the CocoaTouch framework. It seems to me that the RubyMotion's guy (Laurent Sansonetti) could have been involved with Swift. No clue about that. And the fact that it has started four years ago tells us that Apple still has the potential for big surprises (except when chinese factories are involved).

# On the old fart

I don't think Garoo is wrong. He complains about missing or illogical things. Of course it is just a point of view. But the good news is that Objective-C is still working. And if, in a near future, there is more Swift code than Objective-C, that will be in the course of time. There once was a time when the to program on the Mac, you had to use C++ :)

# On the young fart

Even if I do love Swift, I don't plan to use it right now. I did a bit of playground but the projects I work on right now can't be use as experiments. I have a pet project (14 files, 1332 lines of code according to [cloc](http://cloc.sourceforge.net)) that will be entirely converted to Swift asap. "Asap" ... LOL.

And I bet two cents that Google will announce something similar (Go for Android) at IO 2014.