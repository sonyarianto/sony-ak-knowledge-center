```twig
{% set newArray = [] %}
{% for name in array %}
   {% if name not in newArray %}
     My name is {{name}}
   {% set newArray = newArray|merge([name]) %}
   {% endif %}
{% endfor %}
```
