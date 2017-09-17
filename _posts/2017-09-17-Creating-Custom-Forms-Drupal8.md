---
layout: post
title: Saving Drupal 8 configuration and Creating Custom forms
Date: 2017-09-17 00:10:01
author: "Nitish"
tags: Drupal8 Drupal
---
Good morning,
Its a sunday morning and I am starting the day with a little brush up on my drupal 8 knowledge.<br />
I am going to make a custom form, in that form I will make few fields and get default values from the saved configuration.
This configuration would be set from the form.<br />
I would go on and make settings save in files which would make the configurations under version control.

<ul>
<li>
<b>Step 1:</b> Creating custom form( form API).
Drupal has got a good documentation of form api, it gives you in detail information about how one can create custom forms.<br/>
In the previous post we had created a custom module `hello_world`.
To build a form in drupal 8 we use:
{% highlight PHP %}
 Drupal\Core\Form\FormBase;
 Drupal\Core\Form\FormStateInterface;
{%endhighlight%}

I will make a new routing file so that the form comes on a page.
</li>
<li>
<b>Step 2:</b>We will create another file which will contain call the class and logic for the form.<br />
File would come as `modules/hello_world/src/Form/HelloWorldForm.php`. First we declare the namespace, the other classes we want to use, and extend the FormBase class.

We use to get code from some other classes, using the `use` PHP keyword and then the namespace, using the PSR-4 standard, which will autoload the classes in the files that correspond to these namespaces.


{% highlight PHP%}
<?php
/*
 * @file
 * Contains \Drupal\hello_world\form\HelloWorldForms
 *
 */

namespace Drupal\hello_world\Form;

use Drupal\Core\Form\FormBase;
use Drupal\Core\Form\FormStateInterface;


class HelloWorldForms extends FormBase {
  /*
   * {@inhertdoc}
   *
   */
  public function getFormId() {
      return 'Hello_world_form';
  }
   /**
       * {@inheritdoc}
       */
      public function buildForm(array $form, FormStateInterface $form_state) {

        $form['candidate_name']['first_name'] = array(
        '#type' => 'textfield',
        '#title' => t('First Name:'),
        '#required' => TRUE,
        );
        $form['candidate_name']['last_name'] = array(
        '#type' => 'textfield',
        '#title' => t('Last Name:'),
        '#required' => TRUE,
        );
        $form['actions']['#type'] = 'actions';
        $form['actions']['submit'] = array(
        '#type' => 'submit',
        '#value' => $this->t('Save'),
        '#button_type' => 'primary',
        );
        return $form;
      }

    public function submitForm(array &$form, FormStateInterface $form_state) {

    }
  }
{%endhighlight%}

 I have not used the validateForm which is used for form validations and
 my submitForm function is also empty right now.
<br />
Right now I have got a custom form which has been made on route `hello_world/form`.
Which contains 2 textfields and a submit form.

<br /><br />
Next step is to make a default config that would be loaded in these fields.<br />
First name: Nitish <br />
Last name: Guleria <br />

Let us put this in next blog post.
</li>


</li>
</ul>
