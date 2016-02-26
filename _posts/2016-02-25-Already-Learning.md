---
layout: post
title: Already Learning
description: "Starting out the blog."
date: 2016-02-25 19:30:00
modified: 2016-02-25
tags:
    Jekyll
    Markdown
categories: [Web Development]
---
# What Are Those?

So, I got my first post in, and I couldn't help but write down the things I've learned in the past couple hours since.
Just as a friendly reminder to myself (or anyone who stumbles upon this blog), what I have found out in this short time.
 
## Site Folder 
 
Its noted in the structure as <code>_site</code>.  You may have noticed it after running <code>bundle exec jekyll serve</code>,
which I wrote about in the first post.  This is where the static content is being compiled together after a file is saved while that
command is running.  If it is not running currently, it will compile on the next run.

## Posts Folder 

This one is where all the blog posts, such as this one, are placed to be read into the site.  From the video's I have seen, it does not look
like this is a default Jekyll folder, so maybe it came with the template I am using?

<code>_posts</code> also has requirements to follow to make the blog work.  Files must be saved in the format <code>YYYY-MM-DD-title.extension</code>.
I am using Markdown to write these posts, so an example would be <code>2016-02-25-post-title.md</code>.

#Side Note

I had issues with this post as well, and my h2 tags were not being rendered.  **Make sure the #'s do not have any spaces to the left.**  They need to be
the very first characters of that line.