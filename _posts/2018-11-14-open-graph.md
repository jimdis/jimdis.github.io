---
layout: post
title:  "Open Graph and Image front matter"
categories: misc
---

The [Open Graph Protocol](http://ogp.me) was invented by Facebook to enable developers to integrate their pages into Facebook's [Social Graph](https://en.wikipedia.org/wiki/Social_graph) and since then it's become a standard for "rich" links that display more than just a link. In our course we use Slack, and when pasting links from pages that support Open Graph into slack, you don't just get the url - you see the page title, an image, a snippet of content etc. The benefit to the user is that I instantly know if the link is relevant without having to click it. The benefit to the developer/publisher is that it probably draws more clicks than a simple URL if the content looks interesting.

On this site, I simply followed the steps in this [blog post](http://davidensinger.com/2013/04/adding-open-graph-tags-to-jekyll/) by pasting the code into my head.html, and creating a [high-resolution logo](http://localhost:4000/assets/img/logo-high-resolution.png) of this site's favicon and putting it in its proper place (using the recommendations in [this post](https://www.h3xed.com/web-and-internet/how-to-use-og-image-meta-tag-facebook-reddit).

## Update (2018-11-15 - 2018-11-19)
Apparently the Jekyll SEO plugin takes care of Open Graph, so it appeared twice in the HTML head.. That's quite unnecessary, so I undid the above steps, but kept the og:type since it was not handled in Jekyll SEO, and og:image did not work the way I wanted (the [Facebook debugger](https://developers.facebook.com/tools/debug/) complained about these).. So, I had to make some changes to display the image from the relevant post or page. Since I'm lazy, I don't want to specify the full path to an image every time I enter an image in the front matter of a page (which the Jekyll SEO plugin requires to work properly with the `image` front matter), so I did the following changes: 

1) I implemented three front matter variables:
 1. `main- image`
 2. `image-class`
 3. `image-alt`

2) I modified the `head.html`template:
    {% highlight html %}
    {% raw %}
    {% if page.main-image %}
    <meta content="{{ site.url }}/assets/img/{{ page.main-image }}" property="og:image">
    {% else %}
    <meta content="{{ site.url }}/assets/img/logo-high-resolution.png" property="og:image">
    {% endif %}
    {% endraw %}
    {% endhighlight %}

3) I modified the `page.html`, `post.html`and `home.html`:

 {% highlight html %}
    {% raw %}
    {% if page.image %}
    <img class="{{ page.image-class }}" src="/assets/img/{{ page.image }}" alt="{{ page.image-alt }}" />
    {% endif %}
    {% endraw %}
    {% endhighlight %}

4) I also added the following to `_config.yml`:

{% highlight yaml %}
{% raw %}
    defaults:
      - scope:
          path: ""
          type: "posts"
        values:
          image-class: "feature-image"
          image-alt: "Image"

      - scope:
          path: ""
          type: "pages"
        values:
          image-class: "feature-image"
          image-alt: "Image"
{% endraw %}
{% endhighlight %}

The above modifications provided the solution I was looking for - now the featured image is inserted to the html doc with a proper alt tag and the default class "feature-image" unless I want a specific class specified in the front matter, and it is included in the open graph property `og:image`. Of course, I also had to modify the [main.scss](https://github.com/jimdis/jimdis.github.io/blob/master/assets/main.scss) to display the image properly depending on class.