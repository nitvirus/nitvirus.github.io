---
layout: post
title: Why Symfony is used with drupal 8?
Date: 2018-03-25
author: "Nitish"
---
Hi there,
Symfony is a web based php MVC framework, by MVC we mean Model, View, controller.
Some concepts like layer seperation is used, but mainly used for request/response optimisation.
Many open source projects like compose, Behat, Doctrine, Drupal and Jhoomla are using Symfony components.

Main advantages of using Symfony:
1. Gives us resusable classes and code which can be used again and again.
2. Allows us to follow standards likeL PSR4, Twig
3. Allows us to use patterns and principles/practices which can be used across various other projects as well.

Drupal does not uses all the symfony componenst only uses some of them, which are:
1. ClassLoader
2. DependencyInjection
3. EventDispatcher
4. HTTPFoundation
5. HTTPKernel
6. Routing
7. Serializer
8. Validator
9. YAML


There are many components present in symfony like:
Asset, Browserkit,cache, console, form, ldap,translation, phpunit bridge etc.
