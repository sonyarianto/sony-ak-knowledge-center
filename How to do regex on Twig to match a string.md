See this example:

```twig
{% set a = '/berita/sony-akan-pergi-ke-amerika/page.50/sort.newest' %}
{% if a matches '/(\\/page\\.)/' %}
{{ 'page found' }}
{% else %}
{{ 'page not found' }}
{% endif %}
```

will search string `/page.` on variable `a`
