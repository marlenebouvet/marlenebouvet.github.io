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
  .cv-timeline { --logo-w: 6em; padding-left: 12px; margin-bottom: 2.4em; }
  .cv-arrowhead { margin-left: calc(var(--logo-w) + 2.5px - 13px); width: 0; height: 0; border-left: 13px solid transparent; border-right: 13px solid transparent; border-bottom: 22px solid #1a5a85; }
  .cv-row { display: flex; align-items: stretch; }
  .cv-logo { flex: 0 0 var(--logo-w); width: var(--logo-w); display: flex; align-items: center; justify-content: center; align-self: center; padding-right: 0.8em; box-sizing: border-box; }
  .cv-logo img { max-width: 100%; max-height: 3.4em; width: auto; height: auto; object-fit: contain; mix-blend-mode: multiply; }
  .cv-date { flex: 0 0 8.6em; position: relative; display: flex; align-items: center; border-left: 5px solid #1a5a85; padding: 1.5em 0 1.5em 1.3em; font-weight: 800; color: #a11828; font-size: 1.45em; line-height: 1.15; letter-spacing: -0.01em; }
  .cv-date::before { content: ""; position: absolute; box-sizing: border-box; left: -11.5px; top: 50%; width: 18px; height: 18px; margin-top: -9px; border-radius: 50%; background: #a11828; border: 4px solid #fff; box-shadow: 0 0 0 2px #1a5a85; }
  .cv-body { flex: 1 1 auto; margin: 0.45em 0 0.45em 2cm; min-width: 0; align-self: center; display: flex; align-items: center; gap: 1em; background: #f3f6f9; border-left: 5px solid #1a5a85; border-radius: 0 12px 12px 0; padding: 0.8em 1.3em; box-shadow: 0 2px 8px rgba(26, 90, 133, 0.12); transition: transform .15s ease, box-shadow .15s ease; }
  .cv-body:hover { transform: translateX(4px); box-shadow: 0 4px 14px rgba(26, 90, 133, 0.22); }
  .cv-text { flex: 1 1 auto; min-width: 0; }
  .cv-title { color: #1a5a85; font-weight: 800; font-size: 1.5em; line-height: 1.2; }
  .cv-place { margin-top: 0.25em; font-weight: 700; font-size: 1.1em; color: #494e52; }
  .cv-right { flex: 0 0 auto; display: flex; flex-direction: column; gap: 0.6em; align-items: center; justify-content: center; }
  .cv-right:has(img:nth-child(3)) img { max-height: 3em; }
  .cv-right img { max-height: 4em; max-width: 12em; width: auto; height: auto; object-fit: contain; mix-blend-mode: multiply; }
  @media (max-width: 700px) { .cv-body { margin-left: 1em; } .cv-date { flex-basis: 5.6em; font-size: 1.15em; } .cv-right { display: none; } }
</style>

<h2 class="page__title" style="margin-top: 0.4em; color: #a11828; text-align: center; font-size: 2.4em; margin-bottom: 0.8em">Expérience professionnelle</h2>

<div class="cv-timeline">
  <div class="cv-arrowhead" title="Du plus ancien au plus récent"></div>
  {% for e in site.data.cv.experience %}
  <div class="cv-row">
    <div class="cv-logo"></div>
    <div class="cv-date">{{ e.date }}</div>
    <div class="cv-body">
      <div class="cv-text">
        <div class="cv-title">{{ e.title }}</div>
        {% if e.place %}<div class="cv-place">{{ e.place }}</div>{% endif %}
      </div>
      <div class="cv-right">{% for l in e.logos %}{% include cv-logo.html name=l %}{% endfor %}</div>
    </div>
  </div>
  {% endfor %}
</div>

<h2 class="page__title" style="margin-top: 1.6em; color: #a11828; text-align: center; font-size: 2.4em; margin-bottom: 0.8em">Diplômes</h2>

<div class="cv-timeline">
  <div class="cv-arrowhead" title="Du plus ancien au plus récent"></div>
  {% for d in site.data.cv.diplomes %}
  <div class="cv-row">
    <div class="cv-logo"></div>
    <div class="cv-date">{{ d.date }}</div>
    <div class="cv-body">
      <div class="cv-text">
        <div class="cv-title">{{ d.title }}</div>
        {% if d.place %}<div class="cv-place">{{ d.place }}</div>{% endif %}
      </div>
      <div class="cv-right">{% capture cv_logo %}{% if d.logo %}{% include cv-logo.html name=d.logo alt=d.place %}{% endif %}{% endcapture %}{% if cv_logo contains "<img" %}{{ cv_logo }}{% else %}<img src="/images/icons/diplome.svg" alt="Diplôme" style="max-height: 3em">{% endif %}</div>
    </div>
  </div>
  {% endfor %}
</div>
