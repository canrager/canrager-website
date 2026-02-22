---
layout: distill
title: The Need for AI Transparency
description: Discovering topics that language models refuse to talk about.
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

It is important that AI systems act in line with our social values and intentions, as they complete more complex tasks with less oversight. Model behavior develops during training. Developers of popular AI Systems don't share training details, hindering users and auditors to evaluate trustworthiness. We developed a technique to characterize model behavior without access to training details, with a specific focus on refusal behavior.

Our Iterated Prefill Crawler lists a range of topics that an AI system refuses to discuss. This allows users to judge themselves whether they agree with model behavior. For, instance our identified historical topics omitted by the Qwen3 model.

<div style="max-width: 60%; margin: 0 auto;">
{% include figure.liquid loading="eager" path="assets/img/refusal_long.png" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>
<p class="caption">The AI system internally discusses to omit details about a user query on a mass protest, before refusing to answer all together.</p>

In another striking example, Crowdstrike researchers find that censored models are up to 50% more likely to introduce severe security vulnerabilities, whenever a sensitive subject is mentioned in context.<d-cite key="crowdstrike2025aivulnerabilities"></d-cite> Users need to be aware of censorship, as it can lead to unexpected failures.

Our work is featured on the news: Volkskrant<d-cite key="volkskrant2026qwen"></d-cite>, Khoury News<d-cite key="khoury2026qwen"></d-cite>, China Media Project<d-cite key="chinamediaproject2026qwen"></d-cite>.
For more details, check out <a href="https://forbidden.baulab.info">the official project page</a>. 

