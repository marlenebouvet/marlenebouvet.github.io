---
layout: archive
title: " "
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<style>
  .cv-timeline { --logo-w: 4.6em; padding-left: 10px; margin-bottom: 2em; }
  .cv-timeline--right { --logo-w: 0em; }
  .cv-arrowhead { margin-left: calc(var(--logo-w) + 2px - 9px); width: 0; height: 0; border-left: 9px solid transparent; border-right: 9px solid transparent; border-bottom: 15px solid #8a9aa6; }
  .cv-row { display: flex; align-items: stretch; }
  .cv-logo { flex: 0 0 var(--logo-w); width: var(--logo-w); display: flex; align-items: center; align-self: center; justify-content: center; padding-right: 0.8em; box-sizing: border-box; }
  .cv-logo img { max-width: 100%; max-height: 3.2em; width: auto; height: auto; object-fit: contain; }
  .cv-date { flex: 0 0 10.5em; position: relative; display: flex; align-items: center; border-left: 4px solid #8a9aa6; padding: 1.6em 0 1.6em 1.2em; font-weight: 700; color: #000; font-size: 1.05em; }
  .cv-date::before { content: ""; position: absolute; left: -10px; top: 50%; width: 12px; height: 12px; margin-top: -9px; border-radius: 50%; background: #1a5a85; border: 3px solid #fff; box-shadow: 0 0 0 1px #8a9aa6; }
  .cv-body { flex: 1 1 auto; margin-left: 2cm; min-width: 0; align-self: center; }
  .cv-title { color: #1a5a85; font-weight: 700; font-size: 1.15em; line-height: 1.3; }
  .cv-place { margin-top: 0.15em; font-style: italic; }
  .cv-right { flex: 0 0 auto; margin-left: 1em; display: flex; gap: 0.8em; align-items: center; align-self: center; }
  .cv-right img { max-height: 3.2em; max-width: 6em; width: auto; height: auto; object-fit: contain; }
  @media (max-width: 700px) { .cv-body { margin-left: 1em; } .cv-date { flex-basis: 7em; } .cv-right { display: none; } }
</style>

<h2 class="page__title" style="margin-top: 0.4em; color: #a11828; text-align: center; font-size: 2.4em; margin-bottom: 0.8em">Diplômes</h2>

<div class="cv-timeline">
  <div class="cv-arrowhead" title="Du plus ancien au plus récent"></div>
  {% for d in site.data.cv.diplomes %}
  <div class="cv-row">
    <div class="cv-logo">{% capture cv_logo %}{% if d.logo %}{% include cv-logo.html name=d.logo alt=d.place %}{% endif %}{% endcapture %}{% if cv_logo contains "<img" %}{{ cv_logo }}{% else %}<img src="/images/icons/diplome.svg" alt="Diplôme">{% endif %}</div>
    <div class="cv-date">{{ d.date }}</div>
    <div class="cv-body">
      <div class="cv-title">{{ d.title }}</div>
      {% if d.place %}<div class="cv-place">{{ d.place }}</div>{% endif %}
    </div>
  </div>
  {% endfor %}
</div>

<h2 class="page__title" style="margin-top: 1.6em; color: #a11828; text-align: center; font-size: 2.4em; margin-bottom: 0.8em">Expérience professionnelle</h2>

<div class="cv-timeline cv-timeline--right">
  <div class="cv-arrowhead" title="Du plus ancien au plus récent"></div>
  {% for e in site.data.cv.experience %}
  <div class="cv-row">
    <div class="cv-date">{{ e.date }}</div>
    <div class="cv-body">
      <div class="cv-title">{{ e.title }}</div>
      {% if e.place %}<div class="cv-place">{{ e.place }}</div>{% endif %}
    </div>
    <div class="cv-right">{% for l in e.logos %}{% include cv-logo.html name=l %}{% endfor %}</div>
  </div>
  {% endfor %}
</div>
