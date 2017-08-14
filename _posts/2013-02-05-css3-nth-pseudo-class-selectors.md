---
title: CSS3 :nth pseudo class selectors
author: Vince
layout: post
permalink: /css3-nth-pseudo-class-selectors/
categories:
  - Blog Posts
tags:
  - CSS3
  - Development
---
The :nth pseudo class selectors were added in CSS3 and let you specify sibling elements of the same type based on their location within the parent.

Lets start off with a basic table with class &#8220;everyOtherRow&#8221;. As you may have guessed by the class name, we are going to be changing the style of every other row using CSS.

    <ul class='everyOtherRow'>
        <li>One</li>
        <li>Two</li>
        <li>Three</li>
        <li>Four</li>
        <li>Fine</li>
        <li>Six</li>
        <li>Se7en</li>
        <li>Eight</li>
        <li>Nine</li>
    </ul>
    

Here it is.

  * One
  * Two
  * Three
  * Four
  * Fine
  * Six
  * Se7en
  * Eight
  * Nine

Now lets add some style to the everyOtherRow class.

    <style>
    .everyOtherRow{
        border:1px solid black;
        list-style-type: none;
        padding:0px;
    }
       .everyOtherRow li{
        color:red;
    }
    </style>
    

And we get this:



<ul class='everyOtherRow1'>
  <li>
    One
  </li>
  <li>
    Two
  </li>
  <li>
    Three
  </li>
  <li>
    Four
  </li>
  <li>
    Fine
  </li>
  <li>
    Six
  </li>
  <li>
    Se7en
  </li>
  <li>
    Eight
  </li>
  <li>
    Nine
  </li>
</ul>

Before if I wanted to have rotating background colors for each row, I&#8217;d have to either set them manually by giving each other row its own class or output the rows in a loop and use a ternary operator to change the class back and forth.

    rowClass = rowClass == 
    'greyBackground' ? 'whiteBackground' : 
    'greyBackground';
    

Yuck, right? Let&#8217;s use a :nth-of-type pseudo selector instead!

    .everyOtherRow li:nth-of-type(odd){
        color:white;
        background-color:grey;
    }
    

This will apply the style to every other LI tag inside the `.everyOtherRow` UL list.



<ul class='everyOtherRow2'>
  <li>
    One
  </li>
  <li>
    Two
  </li>
  <li>
    Three
  </li>
  <li>
    Four
  </li>
  <li>
    Fine
  </li>
  <li>
    Six
  </li>
  <li>
    Se7en
  </li>
  <li>
    Eight
  </li>
  <li>
    Nine
  </li>
</ul>

Now lets try something else. Maybe we want the top list item to have a background color of green and the bottom to have a background color of yellow.

    .everyOtherRow li:nth-of-type(1){
        color:white;
        background-color:green;
    }
    

By giving nth-of-type as numeric argument you can specify which sibling the selector is applied to.

    .everyOtherRow li:nth-last-of-type(1){
        color:black;
        background-color:yellow;
    }
    

The nth-last-of-type works similarly, but starts from the last child of the parent instead of the first.



<ul class='everyOtherRow3'>
  <li>
    One
  </li>
  <li>
    Two
  </li>
  <li>
    Three
  </li>
  <li>
    Four
  </li>
  <li>
    Fine
  </li>
  <li>
    Six
  </li>
  <li>
    Se7en
  </li>
  <li>
    Eight
  </li>
  <li>
    Nine
  </li>
</ul>

There are also :nth-child selectors which work similarly, but are a bit more conditional/strict. [Css-tricks.com has a great writeup about their differences here.][1]

 [1]: http://css-tricks.com/the-difference-between-nth-child-and-nth-of-type/