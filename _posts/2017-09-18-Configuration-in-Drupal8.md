---
layout: post
title: Configuration in Drupal8
Date: 2017-09-18 18:10:01
author: "Nitish"
tags: [Drupal8, Drupal]
published: true
---
Hello,
We have till now covered:
<ul>
<li>
Created a custom module 'hello_world'.
</li>
<li>
Made a page using `routing.yml` file.
</li>
<li>
Made a custom form with fields First name and Last name.
</li>
</ul>
<br />
Next Steps:
In this post we will make a default configuration that would bring out default name in our form
fields and change these default configurations.
<br/>
We will also cover how you can save configurations in files folder and put these configurations under version control.<br />
To make default configuration, we are going to make a new folder `config` under our `hello_world`
module. In this I will make `install` folder and in this folder I will make a file `hello_world.settings.yml`.

<ul>
<li> Set the variables first_name and last_name in the `hello_world.settings.yml`
{% highlight yml %}
hello:
  first_name: 'Nitish'
  last_name: 'Guleria'
{% endhighlight %}
</li>
<li>
To use this set variable in the we are going to use `config()` method
{%highlight php%}
<?php
$config = \Drupal::config('hello_world.settings');
$first_name = $config->get('first_name');
{%endhighlight%}
</li>
After placing these default configurations in settings.yml file disable and re-enable the module.
<li>
Now in our `HelloWorldForms` file put these variables in `#default_value` of these fields.
{% highlight php %}
<?php
$form['candidate_name']['first_name'] = array(
'#type' => 'textfield',
'#title' => t('First Name:'),
'#required' => TRUE,
'#default_value' =>
\Drupal::config('hello_world.settings')->get('hello.first_name'),
);
$form['candidate_name']['last_name'] = array(
'#type' => 'textfield',
'#title' => t('Last Name:'),
'#required' => TRUE,
'#default_value' =>
\Drupal::config('hello_world.settings')->get('hello.last_name'),
{% endhighlight %}
</li>
</ul>
This way you can get default values in your form.
In order to set values I will put
{%highlight php%}
<?php
\Drupal::config('hello_world.settings')
      ->set('mysettingname', 'myfirstvariable')
      ->save();
{%endhighlight%}

where mysettingname would be hello.first_name or hello.last_name
and myfirstvariable would be the form state value.
<br />
<br />
To Summerize: In drupal 8 we have not got `variable_get()` and variable_set()
functions, instead we set variables in the install file and get and set variables through
`\Drupal::config()`.

Cheers.


<br />

Edit: 28th september 2017-09 <br />
We can also define our variables in `.schema.yml` file which would be placed in our custom module where name of module is nitish_guleria.
`nitish_guleria->config->schema->nitish_guleria.schema.yml`
<br />
{% highlight yml %}
nitish_guleria.settings:
  type: mapping
  label: Variable Settings of My Module
  mapping:
    custom_block_settings:
      type: string
    custom_block_setting2:
      type: string
{% endhighlight %}

here `custom_block_settings` and `custom_block_settings2` are the custom variables
