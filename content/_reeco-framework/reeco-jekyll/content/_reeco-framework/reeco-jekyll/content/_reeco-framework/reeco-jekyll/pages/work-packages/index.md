---
layout: default
title: Work packages
has_children: true
has_toc: false
nav_order: 5
---

# {% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %} page.title }}

The Research Ecosystem, from the perspective of the project work packages.


{% assign children_list = site.pages | where: "parent", page.title %}
{% for child in children_list %}
<div class="wrkpckg">
<h2><a href="{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %} child.url | absolute_url }}">{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %} child.long-title }}</a></h2>
{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %} child.description }}
</div>
{% endfor %}


