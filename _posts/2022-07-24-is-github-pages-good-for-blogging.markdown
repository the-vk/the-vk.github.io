---
layout:     single
title:      "Is GitHub Pages good for blogging?"
date:       2022-07-24 09:00:00 -0700
categories: blog
tags:       blogging github
---
Is GitHub Pages good for blogging? Of course it is!
[GitHub Pages homepage](https://pages.github.com/) discusses blogging with Jekyll.
Is it good for me? Let's find out!

# My blog platform wish list

My wish list is not extensive, just some reasonable things:

* Easy to use formatting language
* Free hosting
* Customizable themes
* RSS or Atom feed
* SEO optimization

Nice to haves:

* Custom domain
* Version control
* Comments

There are some things I don't want:

* Any kind of tracking (I'm a big fan of privacy)
* Bloated JS

Let's see if GitHub Pages can make my wishes true.

## Formatting language

GitHub Pages supports basic HTML and can render Markdown.
HTML is powerful and expressive; Markdown is very easy to use. Check &#10003;

## Free hosting

GitHub Pages is free for everyone. Free plan supports public repos. 
GitHub Pages can host web site from private repo with GitHub Pro.
Nothing can beat free. &#10003;

## Customizable themes

GitHub Pages is powered by [Jekyll](https://jekyllrb.com/).
Jekyll is a beast that takes markdown text + a theme and crunches everything into static HTML.
Themes are not limited to specific template or color scheme. 
Jekyll theme is a [Liquid](https://shopify.github.io/liquid/) template. Everything is customizable.

I can build web pages of any complexity, but web design is not exactly my forte.
I decided to go with a theme [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).
The theme looks nice and clean, supports tons of features out of the box and free to use under MIT license. 
What's not to like? &#10003;

## RSS or Atom feed

Long time ago, when social networks didn't own our digital lives, it was a challenge to let the world know that your 
blog has a new post. Some used email newsletters, some bright minds come up with idea of RSS (Really Simple Syndication) 
feeds. It's an xml file with feed of blog updates, or podcasts, or anything else you'd like to publish.
RSS apps fetch the xml file from time to time and let readers about new blog post.
Atom is the same idea, different format.

Tech is old and may be not exactly popular. Afterall, who doesn't post links to personal blogs to Twitter feed?

Yet it's my opinion that every respectable blog should have an RSS or Atom feed. Or both.
The theme Minimal Mistakes supports RSS out of the box. Look for ![RSS Feed Icon](/assets/images/communication-rss-icon.png)
in the bottom left corner. &#10003;

## SEO Optimization

If site is not indexed by Google, it may not even exist! Google is the entry door to internet for many.
It's a no-brainer.
Jekyll and the theme Minimal Mistakes provide a lot in that department.

* Semantic HTML markdown with `role` attributes
* `<meta>` tags with tons of metadata
* Nice and clean post URL
* Search engines verification tools (to confirm site ownership)

Good enough and easy to use. &#10003;

## Custom Domain

GitHub Pages supports custom domains out of the box. Set up CNAME record and site is good to go. &#10003;

## Version control

I'm engineer, I'm used to keep track of my work. GitHub Pages serve content from a git repo with all power and features 
it comes with, including history change version control. &#10003;

## Comments

Who doesn't want to have a feedback or healthy discussion?
The theme [Minimal Mistakes supports a lot of comments systems](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#comments).
It's not yet enabled here. That's a topic for next blog posts. Stay tuned! &#10003;

## Tracking

Personal data and tracking are the oil of modern web economy. Tracking is pervasive, it's everywhere.
But I don't have to contribute to that! I value privacy.
The theme comes with integration with Google Analytics toolset, but I'm not going to enable that. &#10003;

## Bloated JS

I don't like bloated JS. It's ridiculous to load MBytes of JavaScript and spend non-zero number of CPU cycles to render
a blog post. Blog is all about text and some media, everything else is unnecessary extra.
And of course, nothing can beat static pages. Jekyll is the best tool for that.

What does it take to load a page of this blog? Not much, really.

![Blog network traffic](/assets/images/blog-network-traffic.png)

8 requests, 420KB. Everything is cacheable.
Blog is _lightning_ fast. And I like that.
The blog even gets perfect 100 score from Google Lighthouse.

![Google Lighthouse](/assets/images/blog-google-lighthouse.png)

No bloated JS! &#10003;

# Conclusion

So, is it good? Hell, it's perfect for me!

Even though I'll not use Google Analytics or something, it's nice to know if anyone actually read the blog.
I'll start with Google Search Console to see blog performance at SEO game and write a blog post about that.
