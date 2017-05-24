---
layout: post
title:  "An introduction to liquid for jekyll site creators - Part 1"
date:   2017-05-19 19:12:29 -0700
excerpt: 
tags: [tinkering, jekyll, liquid]
---
I suppose it is a good thing that you can get quite far with [jekyll](https://jekyllrb.com) site creation without really knowing what you are doing. I've been playing around with jekyll for some time, and using it for [some projects at work](http://uclalibrary.github.io/research-tips) without, I've realized recently, a particularly clear understanding of quite a few foundational concepts. 

One rather glaring example: I had seen mention of [Liquid](https://shopify.github.io/liquid/), but didn't understand that I was using it every time I created a layout or a list of posts.

If you're new to jekyll, or if you have been fumbling along like me for a while, and you want to get a clearer picture of how Liquid helps make jekyll's magic happen - this post is for you!

### What is Liquid?

Liquid describes itself as an "open-source template language"[^fn-liquid].

In the context of jekyll, this means that Liquid enables you to use little bits of code, like ``` {% raw %} {{ page.title }} {% endraw %} ```, to display content and information about your site, in this case, the title of a page. So, for example, if I add the code ``` {% raw %} {{ page.title }} {% endraw %} ``` to the code on this page, I will get the title of this page: *{{ page.title }}*.

Liquid calls things like ``` {% raw %} {{ page.title }} {% endraw %} ``` *Objects* and they are extraordinarily handy in jekyll. You'll use objects all the time and find them in jekyll themes and code snippets.

*Objects* come into play quite often in *layouts* which jekyll uses to define how pages that appear frequently in your site will look. Most jekyll themes have a layout called ```post.html``` which defines the structure for every post on your site.

The ```post.html``` file might contain a few lines of code similar to the following, which can describe how the page title and date should appear for every post on the site:

~~~~
{% raw %}
<h3>{{ page.title }}</h3>
<em>{{ page.date | date_to_string }}</em>
{% endraw %}
~~~~

*Objects* also come into play whenever you want to display the title of your site, which is defined in your ```_config.yml``` file. Once defined, you can place the object ``` {% raw %} {{ site.title }} {% endraw %} ``` anywhere in your code, and the title of your site will appear. Change the site title in ```_config.yml``` and it will instantly change everywhere on your site. 

#### A few key things to know about Liquid Objects:
* Objects are wrapped in double curly braces: {% raw %} {{ }} {% endraw %}
* By themselves, objects render content, usually something you have defined in ```_config.yml```, the front matter of one of your posts, something you have defined in a ```_data``` file, or some other bit of content or information about your site.




#### Some common liquid objects used in jekyll, and what they output on this page

``` {% raw %} {{ site.title }} {% endraw %} ```: {{ site.title }}

``` {% raw %} {{site.time}} {% endraw %} ```: {{site.time}}

``` {% raw %} {{ page.title }} {% endraw %} ```: {{ page.title }}

``` {% raw %} {{page.url}} {% endraw %} ```: {{page.url}}

Super useful, right? It gets quite a bit better, though! In the next post, I'll dive into how jekyll leverages Liquid *tags* and *filters* which is where the real magic happens!

Here's a preview!

#### Filters let you fiddle with the output of Liquid objects:

Compare the output for this liquid object:

``` {% raw %} {{page.tags}} {% endraw %} ```: {{page.tags}}

with this output, where we have added a filter to change how the output is displayed:

``` {% raw %} {{ page.tags  | array_to_sentence_string }} {% endraw %} ```: {{ page.tags  | array_to_sentence_string }}




[^fn-liquid]: https://shopify.github.io/liquid/