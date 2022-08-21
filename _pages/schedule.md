---
layout: default
title: Schedule
permalink: /schedule.html
excerpt: Schedule for the TechExeter / Digital Exeter annual conference on 15th September 2022.
---

{% assign scheduleSorted = site.speakers | concat: site.data.schedule | sort:"track" | sort:"timeslot" %}

<style type="text/css">

  .schedule-wrap {
      margin:0em 0em 2em;
      border-color: #00bfb2;
      border-width: 1em;
      border-style: solid; 
      background-color:#fff;
  }
  .schedule-wrap h1 {
    font-size: 2rem;
    background-color: #fff;
    padding: 0.5em 0.25em;
    margin:0px;
  }
  #schedule {
    padding:0.25em;
    display: grid;
    grid-gap: 0.2em;
    gap:0.2em;
    grid-template-areas:
      "thead  t1head    t2head     workshophead"
      "t-0830 t12-0830  t12-0830   t12-0830 "
      "t-0845 t12-0830  t12-0830   t12-0830 "
      "t-0900 t12-0830  t12-0830   t12-0830 "
      "t-0915 t12-0830  t12-0830   t12-0830 "
      "t-0930 t12-0930  t12-0930   ."
      "t-0945 t1-0945   t12-0945   ."
      "t-1000 t1-0945   t12-0945   ."
      "t-1015 t1-1015   t2-1015    tworkshop-1015"
      "t-1030 t1-1015   t2-1015    tworkshop-1015"
      "t-1045 t1-1015   t2-1015    tworkshop-1015"
      "t-1100 t12-1100  t12-1100   ."
      "t-1115 t12-1100  t12-1100    ."
      "t-1130 t1-1130   t2-1130    ."
      "t-1145 t1-1130   t2-1130    ."
      "t-1200 t1-1200   t2-1200   . "
      "t-1215 t1-1200   t2-1200    ."
      "t-1230 t1-1230   t2-1230    ."
      "t-1245 t1-1230   t2-1230    ."
      "t-1300 t12-1300  t12-1300   ."
      "t-1315 t12-1300  t12-1300   ."
      "t-1330 t12-1300  t12-1300   ."
      "t-1345 t12-1300  t12-1300   ."
      "t-1400 t1-1400   t2-1400    ."
      "t-1415 t1-1400   t2-1400    ."
      "t-1430 t1-1400   t2-1400    ."
      "t-1445 t1-1445   t2-1445    ."
      "t-1500 t1-1445   t2-1445    ."
      "t-1515 t1-1445   t2-1445    ."
      "t-1530 t12-1530  t12-1530   tworkshop-1530"
      "t-1545 t12-1530  t12-1530    ."
      "t-1600 t1-1600   t2-1600    ."
      "t-1615 t1-1600   t2-1600    ."
      "t-1630 t1-1600   t2-1600    ."
      "t-1645 t12-1645  t12-1645   ."
      "t-1700 t12-1700  t12-1700   ."
      "t-1715 t12-1715  t12-1715   ."
      ".      t1-tba    t2-tba     .";
  }
  
  #schedule .small-time {
    display:none;
  }

  @media screen and (max-width: 40em) {
      .schedule-wrap {
        border:0px;
        background:none;
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
      .item {
        border:1px solid #fff;
      }
      #schedule .small-time {
        display:inline-block;
      }
  }

</style>

<div class="container">

<div class="schedule-wrap">
<div id="schedule">

  {% for speaker in scheduleSorted %}
  {% if speaker.schedule-ignore == true %}
  {% else %}
    <div class="item {{ speaker.type }} t{{ speaker.track }}" style="grid-area: t{{ speaker.track }}-{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }};" {% if speaker.type == "time" %} id="time_{{ speaker.timeslot | replace: ".", ""  | replace: ":", "" }}" {% endif %}>
      <div class="small-time">{{ speaker.timeslot }} </div>
      {% if speaker.url %}
      <a href="{{ speaker.url }}">
      {% endif %}
      <h2>{{ speaker.session-title }}</h2>
      {% if speaker.url %}
      </a>
      {% endif %}
      <div class="description">{{ speaker.description }}</div>
      {% if speaker.type != "time" and speaker.type != "break" and speaker.type != "lunch"  and speaker.type != "talk" %}
      <div class="type"> {{ speaker.type }}</div>
      {% endif %}
      <div class="speaker">    
        {{ speaker.name }}
        {% if speaker.co-presenting-primary == 1 %} 
          &amp; {{ speaker.co-presenting[0].name }}
        {% endif %}
      </div>
    </div>
  {% endif %}
  {% endfor %}

  <div class="item head t1" style="grid-area: t1head;" id="track_1">
  <h2>Track 1</h2>
  HENDERSON THEATRE
  </div>
  <div class="item head t2" style="grid-area: t2head;" id="track_2">
  <h2>Track 2</h2>
  MATRIX THEATRE
  </div>
  <div class="item head tworkshop" style="grid-area: workshophead;" id="track_woskhop">
  <h2>Workshop</h2>
  XFI CONFERENCE ROOM
  </div>

</div>
</div>

<div style="text-align:center;"><em>* Schedule is subject to change</em></div>

</div>