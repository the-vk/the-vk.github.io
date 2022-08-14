---
layout:     single
title:      "Let there be comments"
date:       2022-08-14 14:30:00 -0700
categories: blog
tags:       blogging utterances comment
---
What is a blog without comments? An article with no feedback.

<!--more-->

Half of blogging charm comes from a live discussion in comments.
Community, feedback, ideas, linkbacks - all of that depends on comments.

So, let there be comments!

## Comment providers for GitHub Pages blogs

Comment providers are off-the-shelf products nowadays. Discourse, Disqus, Facebook, you name it.
Plug some JS on a page and it's good to go.

True to my engineering roots, I want to use [utterance](https://github.com/utterance) for the comments.
Reasons are self-evident:

* Lightweight
* No tracking, no ads, no nonsense
* Powered by GitHub issues

And the most important...

* Easy to enable in the theme [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/)

## How to enable utterances comments on GitHub Pages blog?

It's as easy as 2 minimal updates to `_config.yml`

First, enable comments with Front Matter variable:

```yaml
defaults:
  - scope:
      path: ""
      type: posts
    values:
      comments: true
```

Then configure provider and utterance settings:

```yaml
comments:
  provider: "utterances"
  utterances:
    theme: "github-light" # "github-dark"
    issue_term: "pathname"
    label: "comment" # Optional - must be existing label.
```

That's it! Can't be easier than that.

## Downsides

Of course, there are tradeoffs, as with everything in software engineering.

The theme Minimal Mistakes does not render comments by default in development mode, i.e., running locally
with `bundle exec jekyll serve` command.

[Minimal Mistakes comments config page](https://mmistakes.github.io/minimal-mistakes/docs/configuration/#comments)
recommends to set environment variable `JEKYLL_ENV=production` to run in production mode.

Another downside is that utterances GitHub login widget redirects to `url` set in `_config.yml`.
I have to set it to `http://localhost:4000` to allow GitHub to redirect back to local Jekyll web service.

All in all, it's no big deal. I'm totally happy with the trade-offs. I can have a lively discussions under my posts.

Happy comments!
