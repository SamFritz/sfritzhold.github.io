---
title: Digital Projects
permalink: /digitalprojects/
layout: single
toc: false
toc_label: " "
toc_icon: "star"
toc_sticky: true
---

UNDER CONSTUCTION

<!-- 1. Post File [2018-09-30-Sample-Post.md] -->
---
layout: post
title:  A Sample Post
date:   2018-09-30
author: Mike the Blogger
description: This is the one blog post to rule them all
featured-image: my-awesome-photo.jpg
featured-image-alt: Mike the Blogger speaking at Times Square, New York City, New York
categories: Side Hustle
---

<!-- 2. post.hml; located in the _layouts directory -->
<!-- some page content -->
<header class="post-header">
   <h1 class="post-title">{{ page.title }}</h1>
   <time datetime="{{ page.date | date_to_xmlschema }}">{{ page.date | date: "%b %-d, %Y" }}</time>
   {% if page.author %} • {{ page.author }}{% endif %}
   <!-- call the featured-post-image.html template file -->
   {% if page.featured-image %}{% include post-featured-image.html image=page.featured-image alt=page.featured-image-alt %}{% endif %}
</header>
<!-- other page content -->

<!-- 3. index.html, located in project's root directory -->
<!-- some HTML content -->
{% for post in site.posts limit:3 %}
    <div>
        <h2>
          <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </h2>
        <!-- call the featured-post-image.html template file -->
        {% if post.featured-image %}{% include post-featured-image.html image=post.featured-image alt=post.featured-image-alt %}{% endif %}
        <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
        {% if page.author %} • <span itemprop="author" itemscope itemtype="http://schema.org/Person"><span itemprop="name">{{ page.author }}</span></span>{% endif %}
    </div>   
{% endfor %}
<!-- some other HTML content -->