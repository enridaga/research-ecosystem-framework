---
layout: default
title: Requirements
nav_order: 11
permalink: /personas.html
---

# {% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} page.title }}

The Research Ecosystem, from the perspective of the target communities, exemplified by a set of Persona.

{% assign children_list = site.documents | where: "type", "Persona" %}
{% for child in children_list %}
### <a href="{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} child.url | absolute_url }}">{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} child.long-title }}</a>
{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} child.description }}
{% assign stories = site.documents | where: "type", "Story" %}
<ul>
{% for story in stories %}
{% if story['related-components'] %}
{% assign related = story['related-components'] %}
{% for r in related %} 
  {% if r.persona contains child.component-id %}
<li> <a href="{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} story.url | absolute_url }}">{% raw %}{% raw %}{% raw %}{% raw %}{{{% endraw %}{% endraw %}{% endraw %}{% endraw %} story.name }}</a></li>
  {% endif %}
{% endfor %}
{% endif %}
{% endfor %}
</ul>
{% endfor %}
