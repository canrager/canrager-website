---
layout: distill
title: Analyse von KI-Transparenz
description: Über die Ermittlung von Themen, die von Sprachmodellen strikt vermieden werden.
header_image: assets/img/refusal_title.png
header_image_class: l-body
header_image_width_desktop: 60%
header_image_width_mobile: 90%
header_image_zoomable: true
header_image_caption:
header_image_padding_bottom: 20px
tags: tools
date: 2026-02-22
giscus_comments: false
featured: false
mermaid:
  enabled: false
  zoomable: false
code_diff: false
map: false
chart:
  chartjs: false
  echarts: false
  vega_lite: false
tikzjax: false
typograms: false

authors:
  - name: Can Rager

bibliography: 2018-12-22-distill.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
---
KI-Systeme müssen im Einklang mit unseren gesellschaftlichen Werten und Absichten handeln. Diese Notwendigkeit wächst, da Modelle zunehmend komplexere Aufgaben mit immer weniger menschlicher Aufsicht übernehmen.
Das Verhalten eines Modells entsteht während des Trainings. Leider teilen die Entwickler populärer KI-Systeme kaum Details über diesen Prozess, was es Nutzern und Prüfern schwer macht, die Vertrauenswürdigkeit zu beurteilen.
Wir haben eine Technik entwickelt, um das Modellverhalten ohne Zugang zu Trainingsdetails zu charakterisieren – mit besonderem Fokus auf Verweigerungsverhalten.

Unser Iterated Prefill Crawler erstellt eine Liste von Themen, die KI-System verweigern. 
Das versetzt Nutzer in die Lage, selbst zu urteilen, ob sie mit dem Verhalten des Modells einverstanden sind. 
Wir haben beispielsweise historische Themen identifiziert, die das Qwen3-Modell meidet.

<div style="max-width: 60%; margin: 0 auto;">
{% include figure.liquid loading="eager" path="assets/img/refusal_long.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<p class="caption">Das KI-System diskutiert intern, ob es Details zu einer Nutzeranfrage über einen Massenprotest weglassen soll, bevor es die Antwort vollständig verweigert.</p>

Crowdstrike-Forscher stellten fest, dass zensierte Modelle mit bis zu 50% höherer Wahrscheinlichkeit schwerwiegende Sicherheitslücken einführen, sobald ein sensibles Thema im Kontext erwähnt wird.<d-cite key="crowdstrike2025aivulnerabilities"></d-cite>
Dieses Ergebnis unterstreicht, dass Nutzer sich einer Zensur bewusst sein müssen, da sie zu unerwarteten Fehlern führen kann.

Unsere Arbeit wurde in den Medien vorgestellt: Volkskrant<d-cite key="volkskrant2026qwen"></d-cite>, Khoury News<d-cite key="khoury2026qwen"></d-cite>, China Media Project<d-cite key="chinamediaproject2026qwen"></d-cite>.
Weitere Details gibt es auf <a href="https://forbidden.baulab.info">unserer offiziellen Projektseite</a>. 
