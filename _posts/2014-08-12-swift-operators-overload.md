---
layout: post
title: Operator overload ? Easy boy, easy
categories:
- programming
tags: [swift, noway]
status: publish
type: post
published: true
---

A lot of "new" things in Swift aren't that new: generics and operator overloading have been avalaible in C++ for centuries. But for iOS/Mac-only (aka Objective-C) developers, this is new. And with the discovery of a new hammer comes the transformation of everything into nails.

Generics are OK: they may make the code a little bit less readable at first but we are helping the compiler helps us.

My main concern is about operator overloading. It is of a concern because of <a href="http://nshipster.com/swift-operators/">the last NSHipster article which is on operators</a>. Even if this article gives guideline at the end, there is one argument in my opinion that makes operator overloading a bad idea. (If you need more arguments to convince your team not to use them, you can check <a href="http://inessential.com/2014/08/11/mattt_on_swift_operators">this article from Brent Simmons</a>)

Of course, those things are sexy and they <em>look</em> like they can make us save some time. After all, with a single symbol, you can do a lot of things. But you lose <strong>expressiveness</strong>.

<strong>You</strong> do understand what an overloaded "<strong>+</strong>" does on this data model, but what about the next programmer that will have to update the code 3 months later. And what will happen when people start to add code in this operator not so logical to add in a "+" operator ?

Big troubles. Spare them. Use operator overloading only in project where you will always and forever be the only programmer ;)