---
layout: post
title: Creating URL alias programatically drupal8
Date: 2017-11-08
author: "Nitish"
tags: [drupal8, web development]
---
Hello there,
Recently I came across a peculiar use case:
I had to creat a logic where url aliasing would change on selection of a particular taxonomy term which is referenced in a particular content type.
Let us say we have content type `BOOKS`, and we have vocabulary `type`, we reference this taxonomy in `BOOKS` content type and make a field there. This `type` vocabulary has 2 terms `virtual` and `physical`.
On selection of `virtual` term while amking content the url would be as `\virtual\node:id\node:title` and selection of `physical` the url would become as `\physical\node:title`.

We had already made a pattern using pathauto in our drupal8 application, which needs to be disabled as we now would be putting in logic for url aliasing in our `custom_module.module` file.
We are going to use a hook i.e hook_Entity_TYPE_create().

{% highlight php %}
/**
* Implements hook_ENTITY_TYPE_insert().
*
*/
function my_custom_module_node_insert(NodeInterface $node){

}

{% endhighlight %}


In this custom hook we are using path.alias.storage `service` to declare the url path.

{% highlight php %}
$path = \Drupal::service('path.alias_storage')->save("/node/" . $nid, "/virtual/" . $nid.'/'. $title, "en");

{% endhighlight %}

Hope this helps.
