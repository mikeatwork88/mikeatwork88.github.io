---
layout: post
title:  "Installing Jekyll on Windows"
date:   2014-10-31 14:00:26
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
{% highlight js %}
gem install jekyll
{% endhighlight %}



Install highlighter
====
(But Github doesnt have rouge as of 2014/10/31. )


{% highlight js %}
gem install rouge
{% endhighlight %}

then I opened my site's config.yml file and added a line 

{% highlight js %}
highlighter: rouge
{% endhighlight %}

For Github I had to remove the rouge from config,

and could have gone with straight markdown highlighting

... changing the markdown to redcarpet and using the standard Markdown fences "~~~ruby" for code snippets (in config.yml):

{% highlight js %}
markdown: redcarpet
{% endhighlight %}
 
... but...

I decided to install python [Python install 2.7.8][pi]
then saved [this page][pip]
and from that download directory ran this 

{% highlight bat %}
c:\Python27\python.exe get-pip.py
{% endhighlight %}

then this

{% highlight bat %}
c:\python27\python.exe -m pip install Pygments
{% endhighlight %}




###Run 

{% highlight ruby %}
jekyll serve -w
{% endhighlight %}

open browser at localhost:4000


###Editing

have fun with markdown syntax, [kramdown flavor][kf]

[here's the markdown cheatsheet][mc]


then you can post c-sharp code like 

{% highlight c# linenos %}

        /// <summary>
        /// Method called when a school was selected. It sets the program-concentrations for that school
        /// </summary>
        /// <param name="code">School code</param>
        public void OnSchoolSelected(string code)
        {
            //Load program-concentration list
            var concentrations = _schoolList.Where(s => s.Code == code || code == "ALL" )
                .SelectMany(s => s.Concentrations
                    .Where(c=> code != "ALL" || ( c.Name.StartsWith("B") || s.Code.StartsWith("U") ))
                ).OrderBy(c=>c.Name);

            if (concentrations != null) this.View.ProgramConcentrations = concentrations.ToList();
            else this.View.ProgramConcentrations = new List<ProgramConcentration>();
            
            List<Term> terms = new List<Term>();
            this.View.Terms = terms;
        }
{% endhighlight %} 

[rd]: http://rubyinstaller.org/downloads/
[jw]: http://jekyll-windows.juthilo.com
[kf]: http://kramdown.gettalong.org/syntax.html
[pi]: https://www.python.org/downloads/windows/
[pip]: https://bootstrap.pypa.io/get-pip.py
[mc]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet