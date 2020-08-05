---
permalink: /schedule
title: Schedule
layout: default
classes: wide-hero wide
share: true
header:
#  image: /assets/images/Tech-Exeter-2018-365.jpg
---
{% assign scheduleSortedWeds = site.speakers | where:"day","weds" | concat: site.data.weds-schedule | sort:"track" | sort:"timeslot" %}
{% assign scheduleSortedThurs = site.speakers | where:"day","thurs" | concat: site.data.thurs-schedule | sort:"track" | sort:"timeslot" %}

{% include header.html %}

<div id="main" class="wrapper style1">

<style type="text/css">

  .schedule-wrap {
      margin:1em 0em 2em;
      box-shadow:0px 0px 10px #000;
  }
  .schedule-wrap h1 {
    font-size: 2rem;
    background-color: #e44c65;
    padding: 0.5em 0.25em;
    margin:0px;
    border-top: 4px solid rgba(39,40,51,0.965);
    border-right: 4px solid rgba(39,40,51,0.965);
    border-left: 4px solid rgba(39,40,51,0.965);
  }
  #schedule {
    padding:0.25em;
    display: grid;
    grid-gap: 0.2em;
    gap:0.2em;
    grid-template-areas:
      "thead t1head t2head"
      "t-0900 t123-0900 t123-0900"
      "t-0915 t1-0915 t123-0915"
      "t-0930 t1-0930 t2-0930"
      "t-0945 t1-0930 t2-0930"
      "t-1000 t123-1000 t123-1000"
      "t-1015 t123-1000 t123-1000"
      "t-1030 t1-1030 t2-1030"
      "t-1045 t1-1030 t2-1030"
      "t-1100 t1-1030 t2-1030"
      "t-1115 t1-1030 t2-1030"
      "t-1130 t123-1130 t123-1130"
      "t-1145 t123-1130 t123-1130"
      "t-1200 t1-1200 t2-1200"
      "t-1215 t1-1200 t2-1200"
      "t-1230 t1-1200 t2-1200"
      "t-1245 t1-1200 t2-1200"
      "t-1300 t123-1300 t123-1300"
      "t-1315 t123-1300 t123-1300"
      "t-1330 t123-1330 t123-1330"
      "t-1345 t1-1345 t2-1345"
      "t-1400 t1-1345 t2-1345"
      "t-1415 t1-1345 t2-1345"
      "t-1430 t1-1345 t2-1345"
      "t-1445 t1-1445 t2-1445"
      "t-1500 t1-1500 t2-1500"
      "t-1515 t1-1500 t2-1500"
      "t-1530 t1-1500 t2-1530"
      "t-1545 t1-1500 t2-1530"
      "t-1600 t123-1600 t123-1600"
      "t-1615 t1-1615 t2-1615"
      "t-1630 t1-1615 t2-1615"
      "t-1645 t1-1615 t2-1615"
      "t-1700 t1-1615 t2-1615"
      "t-1715 t123-1715 t123-1715"
      "t-1730 t123-1730 t123-1730"
      "t-1745 t123-1745 t123-1745"
      "t-1800 t123-1800 t123-1800"
      ". t- t- ";
  }
  
  #schedule.thursday {

    padding:0.25em;
    display: grid;
    grid-gap: 0.2em;
    gap:0.2em;
    grid-template-areas:
      "thead t1head t2head"
      "t-0900 t123-0900 t123-0900"
      "t-0915 t1-0915 t123-0915"
      "t-0930 t1-0930 t2-0930"
      "t-0945 t1-0930 t2-0930"
      "t-1000 t123-1000 t123-1000"
      "t-1015 t123-1000 t123-1000"
      "t-1030 t1-1030 t2-1030"
      "t-1045 t1-1030 t2-1030"
      "t-1100 t1-1030 t2-1030"
      "t-1115 t1-1030 t2-1030"
      "t-1130 t123-1130 t123-1130"
      "t-1145 t123-1130 t123-1130"
      "t-1200 t1-1200 t2-1200"
      "t-1215 t1-1200 t2-1200"
      "t-1230 t1-1200 t2-1200"
      "t-1245 t1-1200 t2-1200"
      "t-1300 t123-1300 t123-1300"
      "t-1315 t123-1300 t123-1300"
      "t-1330 t123-1330 t123-1330"
      "t-1345 t1-1345 t2-1345"
      ".      t1-1345 t2-1355"
      "t-1400 t1-1345 t2-1355"
      ".      t1-1345 t2-1405"
      "t-1415 t1-1345 t2-1415"
      "t-1430 t1-1345 t2-1415"
      "t-1445 t1-1445 t2-1445"
      "t-1500 t1-1500 t2-1500"
      "t-1515 t1-1500 t2-1500"
      "t-1530 t1-1500 t2-1530"
      "t-1545 t1-1500 t2-1530"
      "t-1600 t123-1600 t123-1600"
      "t-1615 t1-1615 t2-1615"
      "t-1630 t1-1615 t2-1615"
      "t-1645 t1-1615 t2-1615"
      "t-1700 t1-1615 t123-1700"
      "t-1715 t123-1715 t123-1715"
      "t-1730 t123-1730 t123-1730"
      "t-1745 t123-1745 t123-1745"
      "t-1800 t123-1800 t123-1800"
      ". t- t- ";
  }
  #schedule .small-time {
    display:none;
  }

  @media screen and (max-width: 40em) {
      .schedule-wrap h1 {
        border:0px;
      }
      #schedule {

        box-shadow:none;
        padding:0px;

        grid-gap: 0px;
        gap:0px;
      }
      #schedule .time {
        display:none;
      }

      #schedule .small-time {
        display:inline-block;
      }
  }

 #workshops {

    margin:1em 0em 2em;
    background:#fff;
    box-shadow:0px 0px 10px #999;
    padding:0.25em;
    display: grid;
    grid-gap: 1em;
    gap:1em;
    grid-template-areas:
      "wmorning wmorning"
      "w1000 w1130"
      "wafternoon wafternoon"
      "w1400 w1445";
  }

  #workshops .description { 
    margin:1em 0em 0.5em;
  }
  #workshops .heading h2 { 
    background: #11999E;
    color: #fff;
    padding: 0.5em;
    margin:0px;
  }
  #workshops h2 { margin-top:0px; border-bottom:none; }

</style>

<div class="container">

<div class="schedule-wrap">
<h1 id="weds">Wednesday Schedule - Tech Exeter</h1>
<div id="schedule">

  {% for speaker in scheduleSortedWeds %}
  {% if speaker.schedule-ignore == true %}
  {% else %}
  {% if speaker.type != "Track Host" and speaker.track != "Workshop" %}
    <div class="item {{ speaker.type }} t{{ speaker.track }}" style="grid-area: t{{ speaker.track }}-{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};" {% if speaker.type == "time" %} id="weds_time_{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }}" {% endif %}>
    <div class="small-time">{{ speaker.timeslot }} </div>
    {% if speaker.url %}
    <a href="{{ speaker.url }}">
    {% endif %}
    <h2>{{ speaker.talk-title }}</h2>
    {% if speaker.url %}
    </a>
    {% endif %}
    <div class="description">{{ speaker.description }}</div>
    {% if speaker.type != "time" and  speaker.type != "break" and speaker.type != "lunch" %}
    <div class="type"> {{ speaker.type }}</div>
    {% endif %}
    <div class="speaker">    
      {% if speaker.names != nil %}
      {{ speaker.names }}
      {% else %}
      {{ speaker.name }}
      {% endif %}
    </div>
    </div>
    {% endif %}
  {% endif %}
  {% endfor %}

  <div class="item head t1" style="grid-area: t1head;" id="track_1">
  <h2>Track 1</h2>
  MAIN STAGE
  </div>
  <div class="item head t2" style="grid-area: t2head;" id="track_2">
  <h2>Track 2</h2>
  SESSIONS AREA
  </div>

</div>
</div>


<div class="schedule-wrap">
<h1 id="thurs">Thursday Schedule - Digital Exeter</h1>
<div id="schedule" class="thursday">

  {% for speaker in scheduleSortedThurs %}
  {% if speaker.schedule-ignore == true %}
  {% else %}
  {% if speaker.type != "Track Host" and speaker.track != "Workshop" %}
    <div class="item {{ speaker.type }} t{{ speaker.track }}" style="grid-area: t{{ speaker.track }}-{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};" {% if speaker.type == "time" %} id="thurs_time_{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }}" {% endif %}>
    <div class="small-time">{{ speaker.timeslot }} </div>
    {% if speaker.url %}
    <a href="{{ speaker.url }}">
    {% endif %}
    <h2>{{ speaker.talk-title }}</h2>
    {% if speaker.url %}
    </a>
    {% endif %}
    <div class="description">{{ speaker.description }}</div>
    {% if speaker.type != "time" and  speaker.type != "break" and speaker.type != "lunch" %}
    <div class="type"> {{ speaker.type }}</div>
    {% endif %}
    <div class="speaker">
    {% if speaker.names != nil %}
    {{ speaker.names }}
    {% else %}
    {{ speaker.name }}
    {% endif %}
    </div>
    </div>
    {% endif %}
  {% endif %}
  {% endfor %}

  <div class="item head t1" style="grid-area: t1head;" id="track_1">
  <h2>Track 1</h2>
  MAIN STAGE
  </div>
  <div class="item head t2" style="grid-area: t2head;" id="track_2">
  <h2>Track 2</h2>
  SESSIONS AREA
  </div>

</div>
</div>

<div style="text-align:center;"><em>* Schedule is subject to change</em></div>

</div>

</div>