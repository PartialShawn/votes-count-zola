{% extends "base.html" %}

{% import "macros/debug.html" as debug %}


{% block site_header_title %}
{% if config.extra.uncouth_theme_use_page_name == true %}
<header>
    <h1>{{ page.title }}</h1>
</header>
{% else %}
{{ super() }}
{% endif %}
{% endblock site_header_title %}

{% block content %}


{% set result_data = load_data(path="data/preliminary_results.json") %}
{% set district_results = result_data[page.extra.district_id] %}
{% block title %}{{ page.title }}{% endblock title %}

{% if config.extra.uncouth_theme_use_page_name == false %}
<header>
    <h1>{{ page.title }}</h1>
</header>
{% endif %}

{{ page.content | safe }}



{% endblock content %}