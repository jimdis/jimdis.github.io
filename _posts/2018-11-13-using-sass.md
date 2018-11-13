---
layout: post
title:  "Using Sass"
categories: misc
---
So, this is the first time I've tried using a CSS preprocessor, in this case [Sass](https://sass-lang.com). Compared to good ol' plain CSS, it takes some getting used to, but one thing I immediately liked was defining some base variables for font-family and colors. I created a site using just html and css for a previous course and my basic idea was copying the overall feel of that site and modifying the [minima](https://github.com/jekyll/minima) template accordingly. I have to say it was much quicker than I thougt once I figured out how [everything works](https://jekyllrb.com/docs/themes/)...

I started out modifying minima.css by changing the `$brand-color` to my color of choice. I also changed the `$background-color` and `$text-color`. The fonts needed some change too, so I changed the `$base-font-family` and added a `$heading-font-family` to separate the style of headings from other text.