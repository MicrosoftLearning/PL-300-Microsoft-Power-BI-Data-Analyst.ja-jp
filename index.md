---
title: オンラインでホストされる手順
permalink: index.html
layout: home
---

# コンテンツ ディレクトリ

各ラボの演習とデモへのハイパーリンクを以下に示します。

## ラボ

{% assign labs = site.pages | where_exp:"page", "page.url contains '/Instructions/Labs'" %}
| コース | モジュール | ラボ |
| --- |--- | --- | 
{% for activity in labs %}| {{ activity.lab.course }} |{{ activity.lab.module }} | [{{ activity.lab.title }}{% if activity.lab.type %} - {{ activity.lab.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

## デモ

{% assign demos = site.pages | where_exp:"page", "page.url contains '/Instructions/Demos'" %}
| コース | モジュール | デモ |
| --- |--- | --- | 
{% for activity in demos %}| {{ activity.demo.course }} |{{ activity.demo.module }} | [{{ activity.demo.title }}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}
