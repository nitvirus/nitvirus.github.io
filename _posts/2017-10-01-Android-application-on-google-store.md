---
layout: post
title: My First Android application Published on Google store
Date: 2017-10-01
author: "Nitish"
tags: Android application Android development
---
Hell Yeah,
I have published my android application on google store. This is pretty basic app, that gives the webview of this blog on your mobile phone.
<br />
<b>The link is <a href ="https://play.google.com/store/apps/details?id=com.nitvirus.android.nitishme">Nitish me</a>
Do support this app.</b>

Coming to code:

An Android app uses 3 basic files to render the output and basic functionality, the files can be increase on number of activities that are there in your app but basically there are 3 files named: `AndroidManifest.xml`,`MainActivity.java` and `main_activity.xml`.
<br />
<br />
The logic:
The logic behind this app is to show the already made web apge or web application in andorid app, we do this by defining our page in
`webView.loadUrl`
and enabling `setJavaScriptEnabled(true);`
We have defined our view to be webview in main_activity.xml.

Code:
we define webview in our main_activity file
{% highlight xml %}
<WebView
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      android:layout_centerHorizontal="true"
      android:id="@+id/webView"/>
{% endhighlight %}

and in our MainActivity java file we define logic to find our view webview and open the web applicationin in it.

{% highlight java %}
WebSettings webSettings = webView.getSettings();
        webSettings.setJavaScriptEnabled(true);
        webView.setWebViewClient(new WebViewClient());
        webView.loadUrl("url to load");
{% endhighlight %}

We save this and run our application and VOILA,
we see the result.

Next plans, to make RSS app to get content through RSS and show it in the application.
