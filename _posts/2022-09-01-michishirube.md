---
layout: post
title: "スマート盲導杖『みちしる兵衛』～AI搭載白杖による視覚障害者歩行支援～"
permalink: /projects/2022/michishirube
thumbnail: /assets/img/thumbnails/2022/michishirube.webp
description: "『みちしる兵衛』は、独自の機械学習モデルに基づくAIを搭載した白杖です。視覚障害者の方々の歩行中に、線路や横断歩道、クルマといった危険を検出・通知し、より安心して歩行ができるよう補助します。"
---

{% assign pj = site.data.projects | where_exp: "pj", "pj.id == 'michishirube'" | first %}

<img class='top-img lazyload' src='/assets/img/spinner.svg' alt='サムネイル画像' loading='lazy'
{% if pj.thumbnail %}    data-src='/assets/img/thumbnails/{{ pj.year }}/{{ pj.thumbnail }}'
{% else %}               data-src='/assets/img/thumbnails/tbu.webp'
{% endif %}                 style='margin-bottom: 10px; border-radius: 6px;' />

{{ pj.description }}

<div style='display: flex; flex-wrap: wrap'>
  {% if pj.link %}
    {% if pj.link contains 'github.com' %}
       <a href='{{ pj.link }}' target='_blank' class='button'>ソースコードを見る</a>
    {% else %}
       <a href='{{ pj.link }}' target='_blank' class='button'>公式サイトを見る</a>
    {% endif %}
  {% endif %}

  <a href="https://twitter.com/intent/tweet?text={{ pj.title }}&via=MitouJr&hashtags=未踏ジュニア&related=MitouJr&lang=jp&url={{ site.url }}/projects/{{ pj.year }}/{{ pj.id }}" class="button" target="_blank" rel="noopener">ツイートする</a>
</div>

### クリエータ {#creator}
<p>
  {% for creator_id in pj.creator_ids %}
    {% include creator.html is_simple=true %}
  {% endfor %}
  <small>(<a href='/projects/{{ pj.year }}'>{{ pj.year }}年度</a> 採択 / {% include link-to-mentor.html id=pj.mentor_id %}PM)</small>
</p>

{% if pj.comment %}
### PMコメント {#comment}
<p class="project-comment">{{ pj.comment }}</p>
{% endif %}

{% if pj.promotion %}
{% if pj.promotion contains '.gif' %}
## デモ動画 {#demo}
<img class='top-img lazyload' src='/assets/img/spinner.svg' alt='デモ動画 (Gif)'
     data-src='/assets/img/thumbnails/{{ pj.year }}/{{ pj.promotion }}' loading='lazy'
     style='margin-bottom: 10px; border-radius: 6px;' />
{% else %}
## デモ動画 {#demo}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.promotion }}?rel=0" frameborder="0" allowfullscreen=""></iframe>
</div>
<a href="https://youtu.be/{{ pj.promotion }}" target="_blank" rel="noopener" class="button">YouTube で見る</a>
{% endif %}
{% endif %}

{% if pj.final %}
## 発表動画 {#final}
<div class="youtube">
  <iframe width="560" height="315" class="lazyload" data-src="https://www.youtube.com/embed/{{ pj.final }}?rel=0{% if pj.final_start %}&start={{ pj.final_start }}{% endif %}" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>
</div>
<a href="https://youtu.be/{{ pj.final }}{% if pj.final_start %}?t={{ pj.final_start }}{% endif %}" target="_blank" rel="noopener" class="button">YouTube で見る</a>
{% endif %}

<style type="text/css">
  .prev { display: table-cell; color: white; text-align: left;   }
  .toc  { display: table-cell; color: white; text-align: center; }
  .next { display: table-cell; color: white; text-align: right;  }
  .nav a:link, .nav a:visited { color: white; }
</style>
<div style="display: table; border-collapse: separate; border-spacing: 15px 0; font-size: 70%; width: 100%; padding: 10px 10px; margin-top: 100px; background-color: rgb(40, 161, 58);">
  <p class="nav prev"><a href='motion_rapid'>&larr; 前<br>
    Motion Rapid - 動画編集ソフトのようなUIでC...</a></p>
  <p class="nav next"><a href='hak'>次 &rarr;<br>
    HAK － Hand Action Keyboard － 物...</a></p>
</div>

{% include project-navigation.html %}