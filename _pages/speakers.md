---
layout: default
title: Speakers
permalink: /speakers.html
page_teaser_image: https://conference.techexeter.uk/images/preview_index.jpg
excerpt: Our speakers for the TechExeter / Digital Exeter annual conference on 9th-10th September 2020.
---

{% assign speakersSorted = site.speakers | sort:"headshot" | reverse %}
{% include header.html %}

<div id="main" class="wrapper style1">
<div class="container">


<div class="speakers">

  <h2>Keynotes</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
    {% if speaker.name == "Nicola Whiting" %}
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class="circle" src="{{speaker.headshot}}" alt="Headshot of {{ speaker.name }}"/></a>
        <h2><a href="{{ speaker.url }}">{{ speaker.name }}</a></h2>
        <p>{% if speaker.name != speaker.title %}<strong>{{ speaker.title }}</strong>{% endif %} {% if speaker.company %} <br/>  {{ speaker.company }} {% endif %}</p>
      </div>
    {% endif %}
  {% endfor %}
    {% for speaker in speakersSorted %}
    {% if speaker.name == "Niki Mosier"%}
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class="circle" src="{{speaker.headshot}}" alt="Headshot of {{ speaker.name }}"/></a>
        <h2><a href="{{ speaker.url }}">{{ speaker.name }}</a></h2>
        <p>{% if speaker.name != speaker.title %}<strong>{{ speaker.title }}</strong>{% endif %} {% if speaker.company %} <br/>  {{ speaker.company }} {% endif %}</p>
      </div>
    {% endif %}
  {% endfor %}
    </div>

  <!--
  <h2>Online Hosts</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
    {% if speaker.type == "Host" %}
      <div class="speaker">
        <a href="{{ speaker.url }}"><img class=" circle" src="{{speaker.headshot}}"/></a>
        <h2>{{ speaker.name }}</h2>
        <p><strong>{{ speaker.title }}</strong> {% if speaker.company %}  at {{ speaker.company }} {% endif %}</p>
      </div>
    {% endif %}
  {% endfor %}
  </div>
  -->

  <h2>Speakers</h2>
  <div class="grid-flex">
  {% for speaker in speakersSorted %}
  {% if speaker.name <>"Nicola Whiting" and speaker.name <> "Niki Mosier" and speaker.type <> "Track Host" %}
    {% if speaker.headshot %} 
    <div class="speaker">
        <a href="{{ speaker.url }}"><img class="circle" src="{{speaker.headshot}}" alt="Headshot of {{ speaker.name }}"/></a>
        <h2><a href="{{ speaker.url }}">{{ speaker.name }}</a></h2>
      <p>{% if speaker.name != speaker.title %}<strong>{{ speaker.title }}</strong>{% endif %} {% if speaker.company %}  <br/>  {{ speaker.company }} {% endif %}</p>
    </div>
    {% endif %}
    {% endif %}
  {% endfor %}
  </div>

</div>

<pre style="margin-top:1em"><code>Note: Speaker information is preliminary and subject to change.</code></pre>
<!--
<h2>Speaker topics by tag:</h2>
{% assign alldocs = site.documents  %}	
{% assign grouptag =  alldocs | map: 'tags' | join: ','  | split: ','  | group_by: tag %}
{%- for tag in grouptag -%}
<h3>{{- tag.name -}}</h3>
<ul>
{%- for document in alldocs -%}
  {%- if document.tags contains tag.name -%}
    <li><a href="{{ document.url | capitalize  }}">{{ document.talk-title }} with {{ document.name }}</a></li>
  {%- endif -%}
{%- endfor -%}
</ul>
{%- endfor -%}
-->
</div>
</div>
