---
layout: page
title: 孔庆云的足迹
tagline: keivn's blog
---
{% include JB/setup %}

<div class="row-fluid">
    <div class="span12" display="none"></div>

  {% for post in site.posts %}
	{% assign option_index = forloop.index0 %}
	{% if option_index < 10 %}
        {% capture summary %}{{post.content | split:'<!--more-->' |first }}{% endcapture%}
		<div class="span12 row" style="margin-left:0px">
        <h2><a class="title" href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h2>
        <div class="post_at_index">
            {{summary}}
        {% if summary != post.content %}<a href="{{ BASE_PATH }}{{ post.url }}" rel="nofollow"><b>查看全文</b></a>{% endif %}
        </div>
        <br/>
        <div>
          <cite>{{ post.date | date: "%Y-%m-%d" }}</cite> <i class="icon-tag"> </i>{% for tag in post.tags %}<a href="{{ BASE_PATH }}{{ site.JB.tags_path }}#{{ tag }}-ref">{{ tag }}</a>{% if forloop.last %}{% else %}, {% endif %}{% endfor %}
		</div>
        
        <hr/>
    </div>
	{% endif %}
 {% endfor %}
</div>

<h3><a href="/archive.html" target="_blank">全部博文</a></h3>

