---
layout: post
title:  "Sharing Research Tips (like YouTube videos)"
date:   2017-01-13 19:12:29 -0700
excerpt: 
tags: [tinkering, online learning, jekyll, material design]
---
I really like side-projects. So much so, that it is hard for me to keep some of my side projects on the side.

Lately, I've been working (perhaps rather obsessively) on a site that tries to make well-designed instructional modules as easy to embed as YouTube videos. Not just [the videos themselves](https://www.youtube.com/playlist?list=PLV8eqWoGXke5D5bmwscUhow1RJKWZmMRZ), but short instructional sequences that can be embedded directly into all sorts of course management systems or other websites, and updated in one central location.

### The Research Tips and Strategies site

The first step was to put together [a site where you can browse the different research tips](https://dmcwo.github.io/research-tips/) and grab the embed code for the tips you want to include in your own site:

[![Embed Code Icon on the Research-Tips site](https://www.evernote.com/l/AN9zi5uZhdZPA6_2Zc2Vy41CLqPJDI8VIRIB/image.png)](https://dmcwo.github.io/research-tips/)

Clicking that little <i class="fa fa-code" aria-hidden="true"></i> code icon pops open a window and gives you an embed code, e.g.:

```

<iframe src="https://dmcwo.github.io/research-tips/embeds/questions/" width="100%" height="400px"></iframe>

```

### Embedded research tips as mini-slideshows

Copying and pasting the embed code into your site, gives you something like this:

<iframe src="https://dmcwo.github.io/research-tips/embeds/questions/" width="100%" height="400px"></iframe>

The idea here is to use a mini-slideshow to:

1. quickly present a strategy or concept with an example or two
2. give the learner a chance to give it a try it out
3. And then provide a tips page pointing to additional resources, that can include videos and other resources that go into greater detail.


Technology wise, everything is built in <a href="http://jekyllrb.com">Jekyll</a>, hosted on <a href="github.com/dmcwo/research-tips" target="_blank">github</a>, and themed with a <a href="https://github.com/dmcwo/dr-jekylls-materials">jekyll version</a> of the fun and amazing <a href="http://materializecss.com/" target="_blank">materializecss</a> framework. The embeddable slideshows mash-up jekyll and materialize w/ [reveal.js](http://lab.hakim.se/reveal-js/#/) to give it a slideshowey navigation.

There are quite a few things still to work on. Materialize.css and Reveal.js don't always get along, and the result has been some pretty weird behavior with images (which, if I haven't fixed it yet, may be on display in the example above). All along the hope has been to make everything responsive, and that is more or less working with a few quirks here and there.

In the long term, I'm interested in turning this into something that others can use - making it easy to grow a collection of tips and strategies.

It has been a super fun project and I'm excited about trying it out with classes this quarter.

If you would like to see how it works, check out the [code on github](github.com/dmcwo/research-tips). You can even create a new research tip w/ a pull request!


	

