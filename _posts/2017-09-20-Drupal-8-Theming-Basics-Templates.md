---
layout: post
title: Drupal8 Theming Basics
Date: 2017-09-20 11:00:01
author: "Nitish"
tags: Drupal8 Drupal learning
---

Drupal 8 has changed its theme engine from `phptemplate` to `twig` which is part a of symphony2 framework.<br />
Now twig templates that were defined as `*.html.twig`.<br /><br />

To debug a twig template and print variables you need to enable `debug : true` in `twig.config:`, which is present
in the `services.yml` file in sites->default folder.
Then we can use the `devel` module along with `devel kint`, after enabling this we only need to
call `kint(varibale_name)` in the template. example: `{{ kint(fields) }}`.
<br />
To print a varible in twig we use `{{  }}`. The varible is to be placed inside these curly braces.
like `{{ fields.field_name.content }}`.<br />
To write a `IF condition` we use, `{% if(fields.field_name.content) is not empty %}` this is accompanied by `{% endif %}`, similarly else `{% else %}`.<br /><br />

Naming views templates: <br />
Surprisingly drupal 8 views has taken the option to add templates and see what templates are being applied on a view by clicking on `information` option in a view.<br />
To override views templates we need to see what templates we need and where to find them.
We can find these in our `core->modules->views->templates`.<br />
Now copy the desired template and put it inside the templates folder in your custom theme or the theme you are using. Views use templates as:
<li>views-view.html.twig:This template is used for all views and contains the layout for the view.</li>
<li>The second template is the style template. The default used template will vary based on the applied view style (grid, table, html list or unformatted).
Grid: views-view-grid.html.twig
Table: views-view-table.html.twig
HTML List: views-view-list.html.twig
Unformatted: views-view-unformatted.html.twig</li>
<li>The third template is "views-view-fields.html.twig". This template is used only if the view row style is set to "Fields". This template is responsible for looping through available fields and print fields wrappers, labels and markup.</li>
<li>The fourth template is "views-view-field.html.twig". This template is used only if the view row style is set to "Fields". This is the last template and is responsible for printing each field markup.</li>
<br />

Naming Custom templates:
A template can be named by using simple rules:
<li>Use the basic template name `+` add view machine name `+` add block/page/display machine name `+` add field name</li> <br />
these can be changed upon requirement as, we might need to add field name is we are adding template of forth style `views-view-field.html.twig`. <br />

For example if we have a `view name: benefit_detail` and display is `block_1` and we want add template of third type `views-view-fields.html.twig` for this specific view, we will add
`views-view-fields--benefit_detail--block_1.html.twig`.

<br />
