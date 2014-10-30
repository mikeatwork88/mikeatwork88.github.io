---
layout: post
title:  "Installing Jekyll on Windows"
date:   2014-10-30 14:00:26
categories: jekyll install
---

Super easy

Install Ruby
====
I [installed Ruby 1.9 from here][rd] because I read that was the most stable (and I chose every checkbox option but you only need PATH for this project),
but [instructions here][jw] said to install 2.0.0 


Install Ruby development Kit
====
[from here][rd].  Get the matching version to the ruby you installed above.  This just unzips.  I unzipped to the Ruby base directory/RDK.

then drop to command line, cd to that directory, and run 
{% highlight ruby %}
ruby dk.rb init
ruby dk.rb install
{% endhighlight %}



Install Jekyll
====
{% highlight ruby %}
gem install jekyll
{% endhighlight %}



Install rouge
====
I use rouge just because I don't have python installed at the moment.  Rouge uses ruby.
{% highlight ruby %}
gem install rouge
{% endhighlight %}

then I opened my site's config.yml file and added a line 
{% highlight ruby %}
highlighter: rouge
{% endhighlight %}



Run 
====
{% highlight ruby %}
jekyll serve -w
{% endhighlight %}

open browser at localhost:4000


Editing
====
have fun with markdown syntax, [kramdown flavor][kf]


[rd]: http://rubyinstaller.org/downloads/
[jw]: http://jekyll-windows.juthilo.com
[kf]: http://kramdown.gettalong.org/syntax.html
