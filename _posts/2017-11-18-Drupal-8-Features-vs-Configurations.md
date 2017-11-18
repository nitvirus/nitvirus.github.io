---
layout: post
title: Features vs Configurarion in Drupal 8
Date: 2017-11-18
author: "Nitish"
---
While developing the drupal 8, as we all know configurations management have come in the core, which means one can easily export and import configurations from an environment to another.

Use case:
We have 3 environments for our application: Dev, Stage, Production.
We have made a field on our dev environment and want to send it across to the other environments.

What configurations are there:
1. Content types
2. Block types
3. Views
4. Configurations coming in admin->Configuration
5. Configurations coming in admin->Appearance

We can import a single configuration or import all the configurations in a single go through Drupal User interface.

We can also make folder under our version control to sync our configurations by changing our `settings.php` file.

for example:
`config_directories = array(CONFIG_SYNC_DIRECTORY => '../config/sync');`

Features
------
If one has developed drupal 7, one know what feature is and how useful this particular module is.

To start feature helps us to bundle or put a particular piece of functionality together and this functionality can be pushed as a whole piece to different environment.
Feature help in syncing together a functionality and this functionality can be turned on or off by just switching the feature on and off.


 
