---
layout: post
title: You should paint your pixels yourself
categories:
- Void
tags: []
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---

![Painting is fun](/assets/images/24237-hd-face-paint-children.jpg)

Does your iPhone app uses the screen ? I bet it does. Does it display icons on your screen ? I bet it does. Does it do it with code. I bet it does not. But why ?

The usual workflow goes like this: someone is responsible for the UI, someone does the source file, someone slices the source files in PNGs and you put those images in your Xcode project. One `[UIImage imageWithName:whatever]`, your png is ready to be displayed.

This is the usual workflow, but not the only one. You could paint your images, i.e. overriding the `drawRect:` method of your UIViews.

But why would you want to do something so tiresome ? I can see two direct benefits: exercise and animations.
<h3>Exercise...</h3>
You know how dreadful UIBezierPath can be ? But it does not have to be. And <a href="http://martinfowler.com/bliki/FrequencyReducesDifficulty.html">like Martin reminds us: if it hurts, do it more often</a>. The point isn't to become a Quartz master but giving a try once in a while would certainly not harm you.
<h3>... makes you fit ...</h3>
You know what is great with code ? It's much much lighter than PNG. You could always find an image that takes less bytes in PNG than in code but go for average and I bet you you'll gain some spaces.
<h3>... so you are ready for anything ...</h3>
"add_comment_button_selected@2x.png" ? No need anymore as an image you draw yourself will always be retina-ready. And when Apple will give us super-retina or retina-hd screens, you will be OK.
<h3>... even animations ...</h3>
Once your icon is coded, how fast is it to make it glow or make it appear like it is drawn from a pencil ? Very fast. You want to morph it or blend it with the background or
<h3>... with a bit of help.</h3>
And <a href="http://wearemobiledevelopers.wordpress.com/2014/07/15/must-have-tools-list-for-ios-top-developers/#more-102">Jérémie gave us a pretty useful list</a> in which <a href="http://www.paintcodeapp.com/">PaintCode</a> could be your new best friend for painting pixels with code. You could even go further by using SVG but the renderers available right now for iOS aren't very light.

So now, everything should be OK for you to give a try to the wonderful of lighting on your screen pixel by pixel.