---
layout: page
permalink: /
---

We make modules for the <a href="http://www.vcvrack.com/">VCVRack</a> software modular synthesis environment. Some are
proprietary and some are open source.<label for="sn-opensource" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-opensource" class="margin-toggle">
<span class="sidenote">
  For open source modules, <a href="https://github.com/{{site.github_username}}">visit us on GitHub</a>.
</span>
Currently, most of our modules are under active development.


## Modules

<figure class="fullwidth modules">
{% assign modules = site.modules | sort: "index", "last" %}
{% for item in site.modules %}
  {% capture status_class %}status-{{item.status}}{% endcapture %}
  {% capture green_class %}{% if item.green %}green{% endif %}{% endcapture %}
  {% assign content = item.content | strip | strip_newlines | strip %}
  <div class="module {{status_class}} {{green_class}}">
    {%if content != '' %}
      <a href="{{ item.url }}">
      <img src="/images/{{item.slug}}.png" alt="">
      </a>
      {% else %}
      <img src="/images/{{item.slug}}.png" alt="">
      {% endif %}
    <h3>
      {%if content != '' %}
        <a href="{{ item.url }}">
        {{ item.title }}
        </a>
      {% else %}
        {{ item.title }}
      {% endif %}
    </h3>
    <p>
      {{ item.description }}
    </p>
      <table>
        {% if item.license != "commercial" %}
          <tr>
            <td>License</td>
            <td>{{item.license}}</td>
          </tr>
        {% endif %}
        {% if item.status != "unavailable" %}
          <tr>
            <td>Status</td>
            <td>{{item.status}}</td>
          </tr>
        {% endif %}
        {% if item.source %}
          <tr>
            <td>
              Source
            </td>
            <td>
              <a href="{{item.source}}">{{item.source_name}}</a>
            </td>
          </tr>
        {% endif %}
      </table>
  </div>
{% endfor %}
</figure>


## Download
{% include download.html %}
<a href="releases">Older releases</a>

## About

Pulsum Quadratum ("vibrating square"<label for="sn-vs" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-vs" class="margin-toggle">
<span class="sidenote">
  For those interested, the <a href="https://nethackwiki.com/wiki/Vibrating_square">Vibrating Square</a>
  is an element from <a href="https://en.wikipedia.org/wiki/NetHack">Nethack</a>.
</span>
 or "pulse wave") releases synthesizer
projects by <a href="https://jonwillia.ms/">Jon Williams</a>.


<!--
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span class="date">({{ post.date | date_to_string }})</span>
      {{ post.content}}
    </li>
  {% endfor %}
</ul>
-->
