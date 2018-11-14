---
layout: post
title:  "Using robots.txt"
categories: misc
---

The file [robots.txt](http://www.robotstxt.org/) can be used to guide crawlers (robots) on how to access a website. Like us humans, robots can be good or evil (or a little bit of both). Good robots try to help internet users find your site and get quick access to relevant information through search engines. Evil robots might try to find e-mail addresses to add to their ever-expanding spam databases. The file robots.txt can be used to keep selected files and folders on the server private from robots like Google if you don't want people to be able to google your site. However, evil robots aren't particularly respectful and will probably just ignore robots.txt like my 1-year-old ignores my disallow commands for accessing my computer keyboard...

Since there's no way to prevent "bad" robots from entering your website, and since information wants to be free, I chose not to disallow anything. I also found some SEO tips for Jekyll blogs on Github pages on [a blog](http://vdaubry.github.io/2014/10/21/SEO-for-your-Jekyll-blog/), where I implemented the part about a sitemap and robots.txt (which required a Jekyll gem for generating the sitemap when the site is run locally). So my [robots.txt](/robots.txt) has the [sitemap](/sitemap.xml) path specified in it.