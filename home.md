Sito di prova riguardo {{ site.title }} di {{ site.author.name }}.

{{ page.example }}

{% include big-cat.html %}

{% for i in site.data.animals %}
- The {{ i.name }} is a {{ i.size }} animal.
{% endfor %}

## Large animals

{% for i in site.data.animals %}
{% if i.size == "large" %}- <strong style="color: {{ i.color }};">{{ i.name }}</strong>
{% else %}- <small>{{ i.name }}</small>
{% endif %}
{% endfor %}

## Small animals

{% assign small_animals = site.data.animals | where: "size", "small" %}
{% for i in small_animals %}
- {{ i.name | upcase }}
{% endfor %}
