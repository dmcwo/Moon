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

the next challenges: Moon's navigation buttons currently send you back to the posts page. The solution is to copy the ```post.html``` layout and create a new one for ```presentations```. Then edit this bit:

```
{% if page.project %}
                    <a class="btn zoombtn" href="{{site.url}}/projects/">
                    {% elsif page.presentation %}
                    {% else %}
                    <a class="btn zoombtn" href="{{site.url}}/posts/">
                    {% endif %}
                        <i class="fa fa-chevron-left"></i>
                    </a>
```

to become the simpler:

```
<a class="btn zoombtn" href="{{site.url}}/presentations/"><i class="fa fa-chevron-left"></i></a>
```
then be sure that each ```presentation``` file has ```presentation``` as the layout type in the frontmatter.

*works!!!!!*

Tags don't work yet; they appear, and link to tags page, but the tags for ```presentations``` and I'm guessing the content, isn't included when the page is built (only posts at the moment). I'll look into that later, for now, I'll just remove tags from the presentation sample content.

Default ordering appears to be chronological based on the ```date:``` in the frontmatter for each post.

This post explains how to use frontmatter to create other ways of sorting:

https://github.com/jekyll/jekyll/issues/2515

Navigation!

The Moon theme has a cool ```navigation.yml``` file in the ```_data``` folder. Looks like you can use it to make a list for the nav menu. Updated w/ presentations link. Cool.

Next steps:

* Decide what to store as YAML frontmatter. It seems like you can leverage and style this in layouts and lists, so for presentations, much can be done this way.
* Further style ```presentation-list.html``` and ```presentation.html```` layouts - e.g., 
	* take out "Reading time?"
	* Left align?
	* slide icon?
* Maybe another, better Zotero > Markdown exporter?
* …?


Other useful references:
http://ben.balter.com/2015/02/20/jekyll-collections/
http://jekyllrb.com/docs/collections/
https://mademistakes.com/articles/jekyll-style-guide/





