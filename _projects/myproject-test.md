---
title: My project test.
layout: project
# permalink: mytest/
---
And this is the text I want to show. 
Because the defaults are set in _config.yml, 
this text will be formated as written
in the project layout.

The RAW file can be found [here](https://github.com/M2vH/websitetest/raw/gh-pages/_layouts/project.md)

We can display some code snippets, html test
{% highlight html lineos %}
<!DOCTYPE HTML>
<html>
  <head>
    <title>{{ page.title | hello world! }}</title>
  </head>
  <body>
    <nav>
      <ul>
        <li><a href="{{ site.index }}">Home</a></li>
        </ul>
      </nav>
    
    <div class="container">
    {{ content }}  
    </div>
  </body>
</html>
{% endhighlight %}
