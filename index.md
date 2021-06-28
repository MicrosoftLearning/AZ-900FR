---
title: Instructions hébergées en ligne
permalink: index.html
layout: home
---

# Répertoire de contenu

Liens hypertextes vers chacune des procédures pas à pas. Les instructeurs peuvent choisir d’utiliser la procédure pas à pas comme démonstration ou en tant que labo pour les participants. 

## Procédures pas à pas

{% assign wts = site.pages | where_exp:"page", "page.url contains '/Instructions/Walkthroughs'" %}
| Module | Procédure pas à pas |
| --- | --- | 
{% for activity in wts %}| {{ activity.wts.module }} | [{{ activity.wts.title }}{% if activity.wts.type %} - {{ activity.wts.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

