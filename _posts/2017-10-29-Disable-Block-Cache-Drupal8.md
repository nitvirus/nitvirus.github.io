---
layout: post
title: Disable Block cache drupal8
Date: 2017-10-29
author: "Nitish"
---
During recent development in a drupal8 project, I came across a peculiar problem.
We were getting same content on different nodes.
To put some light on the problem case, we were using context to show blocks of content, which had all the information of a page. This data was coming according to nid and the information was dynamic.
This was a strange behaviour, after some thoughts, came to a conclusion that this could be cache. Hence after clearing the cache of page correct content for that page was coming, but now this "new content" content was getting stuck across different pages.
Hence a decision was made to check for removing the cache.

{% highlight php %}
$build['#cache']['max-age'] = 0;
{% endhighlight %}


more details can be found <a href="https://drupal.stackexchange.com/questions/185215/how-do-i-disable-twig-and-block-cache-for-a-specific-module">here</a>.
