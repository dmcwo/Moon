---
layout: post
title:  "Creating a Jekyll Collections for Presentations"
date:   2016-06-02 19:12:29 -0700
excerpt: 
tags: [tinkering, presentations, jekyll]
---
Following up on my [previous post about presentation slides](), I thought I might continue by trying to build a new post type to keep track of professional presentations. Part of the inspiration came from the "Projects" feature in Jekyll's [Moon]() theme. I liked the idea, and wanted to see if it would work for presentations.

But I wasn't sure if the "everything is a post, even if it is a project" approach would work for presentations. With [Moon]() there's only one content type - ```posts``` - projects are posts, too, with a little note in the frontmatter to distinguish them:
```
post:	true 
```

It seemed to me like that might cause trouble. Enter [Ben Balter's fantastic explanation of Jekyll Collections](http://ben.balter.com/2015/02/20/jekyll-collections/).

The steps:
1. Created a new branch ```presentations```
2. Created a ```_presentations``` directory (to hold the content) and a ```presentations``` directory to list the content)
3. Added the following to ```config.yml```

```
# Collections
collections:
    presentations:
        output: true
        permalink: /presentations/:path/
```
4. Threw in a couple of sample ```.md``` files into ```_presentations``` (for testing)
5. Copied ```layouts/post-list.html``` to ```layouts/presentation-list.html and then adapted for the ```presentations``` collection - How does it handle singular and plural?

*It might work*

*It works! More or less!!*




