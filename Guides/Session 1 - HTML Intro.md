# Session 1 - HTML Intro

## Everything is a document

Websites are just documents (almost always anyway, stay tuned for Session 10).
The simplest of which is [simplest page.html](https://github.com/TheDataShed/learning-frontend/blob/master/simplest%20page.html), open this in a browser of choice, and you'll see you've got an empty web page!
Congrats this is your first web page!

### Elements and Tags
I'll be using this language a lot, so I'm going to define it now.
This is a *tag* `<body>` when you are writing it, when it is used in the browser I'll refer to it as an *element*.

## Basic structure

You'll see in here doctype tag which helps the browser tell what type of document it is, because just having .html on the end isn't enough to determine how it should be handled.

It then has a html tag in which all your web page goes, this has a lang attribute (language attribute) to inform the browser what language the page is in.

It then has a head tag and body tag.

The head is where all your metadata, scripts, fonts and styles can go. You shouldn't put anything you want a user to see in here.

The body is where all the content you want an end user to see should go.

You'll notice that the html, head and body tags all open tag `<html>` and have a corresponding closing tag `</html>`. This should be for every element to ensure its parsed properly.

## Resilience

HTML is a really robust language which comes with its pros and cons. For example I said you should have a closing tag on every element but you don't have to it will still be read and interpreted fine by a browser and shown on the page. However to ensure your site isn't flaky, have weird behaviour and can be used by accessibility tools you *must* close off your tags.

## Elements
There are approximately 50 HTML elements you can use and these (separately and in combination) will achieve everything you want to on the web!
Imagine being able to do everything in your life using only 50 words, I think that this is an amazing fact, everything on the Internet is made up of these!

I'm not going to go through all of them now, but we'll use some of them through these sessions. Here is the [full list](https://developer.mozilla.org/en-US/docs/Web/HTML/Element) if you want to look through it at your leisure, even if you know HTML I'm sure you'll find some that will surprise you!


## index.html

By convention the entry to most websites is via a [index.html](../index.html) file. You can see this follows the same structure as the simplest page, but with a bit more content.

## `<head>`

The head is where all your metadata, scripts, fonts and styles can go. You shouldn't put anything you want a user to see in here.
You can see now it contains a load of metadata tags, these are extra information for your website.

It contains one about what format the content of the page will be in `utf-8` in this case, a.k.a Western script.
A viewport that informs how your website should be viewed and scale on different devices.
For example the metadata tags containing `twitter:` will make a pretty preview when you share your website on Twitter.

Generally speaking I find a set of metadata tags that work for me from examples online and just copy paste them whenever I build a website, as its mostly just changing little bits of config. For example we've changed the content to be _Shed Shop_ related and some image url.

You'll also notice it contains a `<title>` tag. This is what displays in the tab in your browser.
And right at the bottom of this section you'll see some links that choose what the favicon will be, this is the image displayed in the tab in your browser when you view the page.

## `<body>`

This is where all your content should live!

You can see it contains a lot more information now! Let's break it down.

You generally want a header at the top of the page, so we've used the `<header>` tag, which makes sense right?
This contains a heading for the page _Shed Shop_ this is the most important heading on the page so gets the `<h1>` tag.
This has a link around it (an `<a>` tag) which points to the home page, this is good practice as this is what most users expect around the website logo or name.

It then contains a menu (`<ul>` - unordered list) which contains links to other files or pages, that we'll add over later sessions.
This menu is for navigation, so it should go inside a `<nav>` tag, this is great for accessibility!

We've then got a `<main>` tag which is where the main content on the page we care about goes.
You can see this contains some `<div>` tags, these are used whenever you want to divide up some content for organisational or styling purposes. These get overused on the web, because they are generic, but you should use the right tag/element for the job!
There are some less important headings in there so these get a `<h2>` tag because they are less important than a `<h1>`, and then we've got a paragraph of text in a `<p>` tag.

At the bottom we've got a `<footer>` where you would expect to find it, containing our business address.

After this we have a relatively new tag `<noscript>` this is *only* displayed if a user has disabled JavaScript on your site and will display that warning message. This is really helpful if your site relies on JavaScript so the user knows they might not get any content or it might only partly work.

## How a page is read by a browser

Just like we a page reads (parses) a page from top to bottom, this is super important to remember for performance reasons.
Because if you stick lots of stuff in the `<head>` this will slow down how long it is before a user can see content in your `<body>`.
And you must put the `<body>` after the `<head>` this is how *all* browsers expect to read it.

If you open developer tools in your browser (usually you can just press F12). Here's a [link to explain all](https://developers.google.com/web/tools/chrome-devtools/) parts of developer tools in Chrome for example, if you want to know more.

And click on Network, you can see here a list of all the files and resources a web page has loaded. On the right a waterfall over time of when files have been downloaded. Unless you specify the browser will try figure out the best way to bring in the files, again from top to bottom in your web page, and it will wait until the file has finished downloaded before moving onto the next one, hence the waterfall, as file after file is brought in.

This is what determines how quickly a web page loads.



You've made it!! That's Session 1 smashed! :D

