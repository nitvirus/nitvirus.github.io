---
layout: post
title:  "Experimentation with Jekyll!"
date:   2017-08-08 23:57:51 +0530
tags: [jekyll, update]
---
I have started learning and experimenting with jekyll.
The idea came from a good friend of mine, how he had successfully been running his pages on
github.io you can find link to his blog here : http://xn----qtd2fqdgm0bn0ci4k.xn--h2brj9c
crazyrohilla.github.io


Right now what I have learnt:
-(8/8/2017)
1. you need Ruby (>2.0)  to be installed into your system before installing jekyll into your system.
-(9/8/2017)
2. Installing Ruby on your Windows machine can be really pain in the @$$.
3. once you install jekyll, you don't need any database to run the server/ local site
you can   just run jekyll serve to run the local setup.
4. New posts can be posted in the _post folder of you site root
5. Would be learning more about the formatting and how to write markup in jekyll.
-(10/8/2017)
6. command to run jekyll on your local environment:
   {% highlight ruby %}
    bundle exec jekyll serve --port 4444

   {% endhighlight %}

    where --port 4444 gives the port number where this server would run(this could be any port).



7.Themes: jekyll follows gem based themes, meaning some of the site’s directories
(such as the assets,_layouts, _includes, and _sass directories) are stored in
 the theme’s gem, hidden from your immediate view.
 Yet all of the necessary directories will be read and processed during Jekyll’s build process.
