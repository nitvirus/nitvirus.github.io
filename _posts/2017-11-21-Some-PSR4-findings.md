---
layout: post
title: PSR4 and Drupal 8
Date: 2017-11-21
author: "Nitish"
---

What is PSR4?
PSR4 -- Proposal for Standard Request number 4

Why use?
This is a standard using which allow the classes to be automatically discovered and loaded by following a convention for class namespace and file/directory naming.

Drupal 8 initialy used PSR0 but changed to PSR4.

We don't have to use  functions like require_once, include() and module_load,module_load_include function using this.
