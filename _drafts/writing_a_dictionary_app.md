---
layout: post
title: Writing a dictionary app, part 1
categories:
- Programmation
status: draft
type: post
published: false
---

I want to write a dictionary app. More precisely, a french/tahitian dictionary.

# Requirements

  - simple
  - open-data and open-source
  - avalaible without any internet connection, even at first launch
  - cross-platform (i.e. native on iOS and Android, Responsive Web for everybody else)
  - crowd-sourced (not à la wiki but a system that won't require me to input a lot of data all by myself)
  - state of the art in software development

# File format

I have been working for a while on such an app and while I have attained a not too bad product, I am stuck on the file format.
A guy once said that you have to design the data models and then the program that will manipulate them.

After some research, here are the dictionary file formats I found:

  - XDXF
  - dicML
  - Lingoes .LD2
  - Babylon .BGL
  - ABBYY Lingvo .LSD, .DSL, .LSA and .DAT
  - StarDict files
  - Dictd files

The first two are the most interesting as they are both open-source and in XML.
While I usually don't like the verbosity of XML, it is indeed handy to keep the data free of any specific tools
(remember the 'open-data' bit in bthe 'Requirements').
  
