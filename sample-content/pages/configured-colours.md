---
title: Configured colours
permalink: /sample-content/configured-colours/
order: 4
image: "/assets/sample-images/card-green-turtle.svg"
summary: "A visual reference for the colour settings configured in this theme."
---

This page shows the colour values currently configured in `_config.yml`.

{% assign colours = "primary_color:Primary colour:#354F52,secondary_color:Secondary colour:#C3D5C7,accent_color:Accent colour:#86466E,text_color:Text colour:#344054,heading_color:Heading colour:#344054,muted_text_color:Muted text colour:#667085,background_color:Background colour:#F4F6F3,surface_color:Surface colour:#F1E4EC,border_color:Border colour:#D0D5DD" | split: "," %}

<div class="colour-samples">
  {% for colour_item in colours %}
    {% assign colour_parts = colour_item | split: ":" %}
    {% assign colour_key = colour_parts[0] %}
    {% assign colour_label = colour_parts[1] %}
    {% assign colour_default = colour_parts[2] %}
    {% assign colour_value = site.theme_settings[colour_key] | default: colour_default %}
    {% assign swatch_style = "background-color: " | append: colour_value | append: ";" %}
    <article class="colour-sample">
      <div class="colour-swatch" style="{{ swatch_style }}"></div>
      <div class="colour-sample-body">
        <h2>{{ colour_label }}</h2>
        <dl>
          <dt>Setting</dt>
          <dd><code>{{ colour_key }}</code></dd>
          <dt>Value</dt>
          <dd><code>{{ colour_value }}</code></dd>
        </dl>
        <p style="color: {{ colour_value }};">Example text using {{ colour_label | downcase }}.</p>
      </div>
    </article>
  {% endfor %}
</div>

## How these colours are used

- **Primary colour** is used for the shared header background, page titles, standard links, breadcrumb links, page-card headings, Note alerts, and the hover state for heading permalink icons.
- **Secondary colour** is used for feature bands, coloured content-block backgrounds, link hover states, heading permalink icons, Markdown table header backgrounds, and the muted internal lines and banded rows in Markdown tables.
- **Accent colour** is used for page title underline rules, active navigation markers, accent block separators, Warning alerts, and `.jcu-block--accent` lines.
- **Text colour** is used for standard body text, list text, and skip-link backgrounds.
- **Heading colour** is used for most headings, definition-list terms, alert labels, and card or panel headings.
- **Muted text colour** is used for breadcrumbs, supporting text, captions, card summaries, and less prominent labels.
- **Background colour** is used for the main page panel and skip-link text.
- **Surface colour** is used for card-style blocks, page cards, colour sample cards, column panels, generated gallery tiles, and other quiet UI surfaces.
- **Border colour** is used for panel borders, card borders, content block separators, colour sample dividers, and subtle structural lines.
