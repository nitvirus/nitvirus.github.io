---
layout: post
title: "Making a simple module with custom page in Drupal 8"
Date: 2017-09-17 00:05:01
author: "Nitish"
tags: Drupal8 Drupal
---

Lets start the Drupal 8 learning with making a simple form and how to create a simple custom module.
This custom module would be called as hello_world.<br />
<ul>
<li><b>STEP 1:</b>
I am going to make "hello_world" folder which can be placed inside custom under modules in the sites root folder.
Create a file hello_world.info.yml
(Drupal 8 has introduced yml format, we should be very careful about spacing here).<br />
Below shows the code that I have put in the info.yml. <br />
{% highlight yml %}
name: Hello World
type: module
description: test module by nitish
core: 8.x
package: nitish
dependencies:
    -drupal:views
configuration: hello_world.settings
php: 5.6
{% endhighlight %}

After this the module should start coming up in the module list under the extend section in the site.
</li><br />
<li><b>STEP 2:</b>
Now we will create a route(<i>A route is a path which is defined for Drupal
to return some sort of content on. For example, the default front page,
'/node' is a route. When Drupal receives a request,
it tries to match the requested path to a route it knows about.
If the route is found, then the route's definition is used to return content.</i>)
In drupal 7 we used <i>hook_menu</i> but this has been removed from drupal 8.
We are using routes here now.<br />
To start make a file hello_world.routing.yml file in the hello_world module folder.
{% highlight yml %}
hello_world:
    path: 'hello_world'
    defaults:
        _title: Nitish is best.
        _controller: '\Drupal\hello_world\HelloWorldController::content'
    requirements:
      _permission: 'access content'
{% endhighlight %}
Here we defined the <b>path</b> which is set to hello_world. The <b>title</b> of the page is Nitish is best.<br />
<b>Controller</b> is set to HelloWorldController files content function(HelloWorldController::content).<br />
<b>Permissions</b> is also set to 'access content'.<br />
</li>
<li><b>STEP 3:</b></li>
Our Controller file.<br />
Now our controller file `HelloWorldController.php` file would be placed in our hello_world module inside src folder in Controller folder.
<br />
So the path would be hello_world->sr->Controller->HelloWorldController.php
<br />
It would contain
{% highlight php %}

/**
 * @file
 * Contains \Drupal\hello\HelloController.
 */

namespace Drupal\Controller\hello_world;


use Drupal\Core\Controller\ControllerBase;


class HelloWorldController extends ControllerBase {
  public function content() {
    return array(
        '#markup' => '' . t('Hello there!') . '',
    );
  }
}
{% endhighlight %}
<br /><br />
Here you can see new stuff like <b>namespace, class, extend</b>.<br />
namespace: came from PHP 5.3
why it is needed: As we use different libraries, modules, we can accidentally resuse a function or class name that has been declared before.
<b>namespaces</b>: can be seen as a particular space provided to our module where we can declare variables and classes.
<br />
<b>Class</b>: Comes from object oriented programming style. It is wrapper which contains the logic of defination of
same kind of methods and variables which would be used.
<br />
<b>Objects</b>: Instance of class. An object is a specific instance of a class; it contains real values instead of variables.
</ul>
