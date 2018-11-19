---
layout: post
title:  "Setting up my Music page"
categories: misc
---
I've been wanting to put some of my music somewhere for a while, but it feels boring to just put it on SoundCloud and hope that someone listens. So I got an idea when reading the Jekyll documentation about [data files](https://jekyllrb.com/docs/datafiles/) - to just generate a page with some of my tracks using a csv-file as a data source with the title, year, and a link to SoundCloud. And why not embed the SoundCloud player automatically as well? It was really quite simple using Jekyll.

1. I put the relevant data into google sheets and saved it as a [csv-file](https://github.com/jimdis/jimdis.github.io/blob/master/_data/music.csv)
2. I made a for loop in [music.html](https://github.com/jimdis/jimdis.github.io/blob/master/music.html) containing the structure and the data.
3. I modified my [main.scss](https://github.com/jimdis/jimdis.github.io/blob/master/assets/main.scss) using the classes in music.html.

Done! Check out [the result](/music/).