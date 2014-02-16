---
layout: page
title: 孔庆云的足迹
tagline: keivn's blog
---
{% include JB/setup %}

<div class="row-fluid">
    <div class="span12" display="none"></div>
  {% for post in site.posts %}
        {% capture summary %}{{post.content | split:'<!--more-->' |first }}{% endcapture%}
		<div class="span12 row" style="margin-left:0px">
        <h2><a class="title" href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>
        <div class="post_at_index">
            {{summary}}
        {% if summary != post.content %}<a href="{{ BASE_PATH }}{{ post.url }}" rel="nofollow">Read more...</a>{% endif %}
        </div>
        <br/>
        <div>
          <cite>{{ post.date | date: "%Y-%m-%d" }}</cite> <i class="icon-tag"> </i>{% for tag in post.tags %}<a href="{{ BASE_PATH }}{{ site.JB.tags_path }}#{{ tag }}-ref">{{ tag }}</a>{% if forloop.last %}{% else %}, {% endif %}{% endfor %}
		</div>
        
        <hr/>
    </div>
 {% endfor %}
</div>


