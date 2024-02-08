---
layout: default
title: Collections (dev)
nav_order: 9
permalink: /collections.html
---

# Collections

<ul>
{% for coll in site.collections %}
<li> {% raw %}{% raw %}{{{% endraw %}{% endraw %} coll.label }} 
<ul>
{% for d in coll.docs %}
<li>{% raw %}{% raw %}{{{% endraw %}{% endraw %} d.id }}</li>
{% endfor %}
</ul>
</li>
{% endfor %}
</ul>
