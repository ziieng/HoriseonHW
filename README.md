# Horiseon

First Homework assignment for uw-sea-fsf-pt-08-2020-u-c, looking at refactoring [a demo website provided for Horiseon, a fictional SEO company][1].

## Description 
For this assignment, we were provided with a one-page website for a fictional company, and asked to make the code efficient and accessible. The main problems I found to fix were:

  - Repetitive CSS classes, defining a new class for each element instead of re-using the same class for elements that shared the same formatting needs.
  - No semantic HTML tags, making the site harder for screen-readers (and search engine crawlers) to access it.
  - No alt-tag descriptions on any of the images.

## Solution Process
First, I addressed the duplicate CSS classes by assessing how many unique formats there truly were and removing their duplicates. For example, each section in the Benefits side bar had its own CSS class defined - but all three of them were the same. I deleted two of these, and renamed the one that was left as "benefits-block" so it could be applied to all three without confusion. I renamed all the CSS classes that were left in to something that made sense: if this webpage was expanded in the future or this codebase was reused further down the road to make another page, the class names should be somewhat portable.

As I went, I made sure to adjust the HTML file to reflect the new CSS elements so I wouldn't lose track of which one went where. Once all the text-based elements were successfully changed into cleaner CSS without changing the look of the webpage away from the starting point, I started changing HTML tags into their semantic HTML equivalents.

Semantic HTML makes it easier for search engine trawlers to read a page and determine what the important information is, and provides the same benefit to people who are accessing the site via a screen reader. By changing the generic <div> tags into descriptive tags like <header>, <nav>, and so on, the code became easier to follow. At the same time, I had to adjust some pieces of the CSS to make sure the identifiers it used would still match up.

## Alt Text, man

The biggest challenge emerged while adding alt text to all of the images. The big cover image on the website began its life as a background image for an empty div, a crime committed so they could have the cool cover image look and have it scale in an interesting way. However, tracking down how to get the same visual effect while also changing it into an actual image that could have alt text on it was an adventure. I discovered many ways to *not* do it, and eventually stumbled on the one that worked. I haven't nailed down how to make it render faster without going back to its life of accessibility crime, but hope to learn more tricks soon.

My own experience with alt text in the past has largely been on Twitter, where it's used to describe an image in detail for users who have vision impairments. That it's not used the same way in general HTML was something I had to come to terms with partway through this assignment, as well as accepting that I am simply not good at coming up with useful descriptions for things like the abstract icons used in the Benefits section. Maybe that will come with practice.

[1]:<https://ziieng.github.io/HoriseonHW/>