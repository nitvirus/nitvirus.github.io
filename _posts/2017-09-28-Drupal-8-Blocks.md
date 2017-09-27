---
layout: post
title: Drupal8 Blocks
Date: 2017-09-28
author: "Nitish"
tags: Drupal8 Drupal learning
---
Hey there,

Coming straight to the point, there has been a lot of changes in Drupal8, on how blocks are made and rendered on frontend.
<br />
To make a block in Drupal 7 we have to declare it in the `hook_block_info()` which gave the basic definition of the block.
<br />
 `hook_block_configure` and `hook_block_save` can be used respectively to give the configurational settings and save our settings in database or in a particular variable. We mainly used `hook_block_view` to show the output.

 <br />
 In Drupal8 this has changed completely.
 Blocks in Drupal 8 are actually made up of two separate API structures to create a user experience similar to what Drupal has maintained in past iterations. These two APIs are the <b>Block Plugin API, which is a stand-alone reusable API</b> and <b>the Block Entity API</b> which is a Drupal 8 specific use case of block placement and visibility control.
