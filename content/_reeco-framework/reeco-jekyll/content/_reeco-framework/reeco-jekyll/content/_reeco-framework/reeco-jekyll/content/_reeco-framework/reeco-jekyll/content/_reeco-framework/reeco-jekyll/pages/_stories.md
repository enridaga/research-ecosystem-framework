---
layout: default
title: foo
nav_order: 10
permalink: /stories.html
---

<div class="well">
<h2>Stories</h2>
{% assign stories_grouped = site.stories | group_by: "persona" %} 
{% for group in stories_grouped %}
{% assign personashort = group.name | replace: '["' | replace: '"]'%}
<h3>{% raw %}{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %}{% endraw %} personashort }}</h3>
{% for item in group.items %}
<ul>
{% if item.title contains "Readme" %}
<li><a href="{% raw %}{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %}{% endraw %}item.url | absolute_url}}">{% raw %}{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %}{% endraw %}personashort}}'s description</a></li>
{% else %}
<li><a href="{% raw %}{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %}{% endraw %}item.url | absolute_url}}">{% raw %}{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %}{% endraw %}item.title}}</a></li>
{% endif %}
</ul>
{% endfor %}
{% endfor %}
</div>
