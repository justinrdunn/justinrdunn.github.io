---
layout: post
title:  "The Title goes here"
date:   2015-09-30 21:01:38
categories: First Post
activetab: blog
---

This is an example to build a first post off of.

will create a link with text "this" and link to "google.com" Remember the order of []() or it won't work!

[This](http://google.com) 

this will make an inline image.

![image description]({{ site.url }}/images/imagename.jpg) 

this will make an image with a caption underneath. 
Optionally you can include side= to align it left or right or center
Optionally you can include size= to make it fill full, half, quarter or third of the area

{% include figure.html src="imagename.jpg" caption="Image caption here" side="left" size="half" %} 

# This makes a header

## This a subheader

### a sub-sub-header

####

#####

###### this is the smallest

1. this will make numbered list
2. here is #2

   this will make text that is alligned with #2

   so not everything in #2 has to be on one line

3. now moving on to #3

* this will make a dotted list
- this will also make a dotted list
+ this too

1. this
  * will make a sub-list

2. this 
  1. too
  2. too

this will put a paypal button on the page

{% include paypalbutton.html %} 

this will put a monthly donation button

{% include paypalmonthlybutton.html %} 

> this will render as a block quote
> \- Albert Einstien *probably*

if you want to make text italic surround it with * like this *hello*

if you want to make it bold use 2 **like this**

_underscores_ also __work__

|Tables are| pretty | easy too |
|:---------|:------:|---------:|
| left     | center | right    |

they dont need to be aligned either

|Tables are| pretty | easy too |
|:----|:----:|-------:|
| left        | center |   right    |
|1|2|3|
|\:--- for left alignment| \:---: for center | \---: for right|

[here](https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet#lists) is a link to a great cheatsheet!

### hopefully that is everything you need feel free to ask questions!
