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
~~~ruby
ruby dk.rb init
ruby dk.rb install
~~~



Install Jekyll
====
~~~ruby
gem install jekyll
~~~



Install highlighter
====
But Github doesnt have rouge as of 2014/10/31. 


~~~ruby
gem install rouge
~~~

then I opened my site's config.yml file and added a line 
~~~ruby
highlighter: rouge
~~~

For Github I had to remove the rouge from config,

and could have gone with straight jekyll highlighting

... changing the markdown to redcarpet and using the standard Markdown fences "~~~ruby" for code snippets (in config.yml):

~~~ruby
markdown: redcarpet
~~~
 
... but...

I decided to install python [Python install 2.7.8][pi]
then saved [this page][pip]
and from that download directory ran this 

~~~python
c:\Python27\python.exe get-pip.py
~~~

then this

~~~python
c:\python27\python.exe -m pip install Pygments
~~~




Run 
====
~~~ruby
jekyll serve -w
~~~

open browser at localhost:4000


Editing
====
have fun with markdown syntax, [kramdown flavor][kf]


[rd]: http://rubyinstaller.org/downloads/
[jw]: http://jekyll-windows.juthilo.com
[kf]: http://kramdown.gettalong.org/syntax.html
[pi]: https://www.python.org/downloads/windows/
[pip]: https://bootstrap.pypa.io/get-pip.py
