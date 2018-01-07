---
layout: page
title: About
description: 程序人生
keywords: Yuewu Liu, 刘跃武, able
comments: true
menu: 关于
permalink: /about/
---

我是able，80后。

坚信熟能生巧，技术改变人生。

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
