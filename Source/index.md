---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<h1>
    {{ site.data.Settings.title}}
</h1>

<p>
    {{ site.data.Settings.description }}
</p>

<p>
Post Count: {{ site.posts | size }}
</p>

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})

    {{ post.excerpt }}
{% endfor %}
