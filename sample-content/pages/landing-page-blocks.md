---
layout: full-width
title: Landing page blocks
permalink: /sample-content/landing-page-blocks/
order: 5
image: "/assets/sample-images/gallery-background.svg"
summary: "Examples of each block and style available in the full-width page layout."
content_separator: true
hero:
  eyebrow: "Full-width layout sample"
  title: "Landing page blocks"
  lead: "Use this page to see each landing page section style and understand which front matter fields are optional."
  image: "/assets/sample-images/gallery-background.svg"
  image_alt: "Abstract image showing a research landscape"
  separator: true
  actions:
    - label: "View sections"
      url: "#standard-section"
    - label: "Read documentation"
      url: "https://github.com/jcu-eresearch/jcu-research-website-theme"
achievements:
  eyebrow: "Achievement tiles"
  title: "Achievements block"
  lead: "Use achievements for project metrics, major outputs, milestones, or key facts. `eyebrow`, `lead`, and `separator` are optional. Each item can use a `value`, an `icon`, or an `image`."
  items:
    - value: "24"
      label: "Research outputs"
      text: "Use `value` for numbers, dates, or short high-impact facts."
    - icon: "A"
      label: "Advisory groups"
      text: "Use `icon` for a compact letter, symbol, or short visual marker."
    - image: "/assets/sample-images/card-green-turtle.svg"
      image_alt: "Green turtle"
      label: "Field sites"
      text: "Use `image` and `image_alt` when a small picture is more meaningful."
carousel:
  eyebrow: "Image carousel"
  title: "Carousel block"
  lead: "Use the carousel for fieldwork, project locations, lab work, community activities, or visual summaries. The carousel `eyebrow`, `title`, `lead`, `separator`, and slide `caption` fields are optional."
  items:
    - image: "/assets/sample-images/gallery-background.svg"
      image_alt: "Abstract image representing a research landscape"
      caption: "Slide captions are optional."
    - image: "/assets/sample-images/gallery-about.svg"
      image_alt: "Abstract image representing project information"
      caption: "Add as many slides as the page needs."
    - image: "/assets/sample-images/gallery-contact.svg"
      image_alt: "Abstract image representing collaboration"
      caption: "Always include useful image alt text."
landing_sections:
  - id: "standard-section"
    title: "Standard text section"
    eyebrow: "Default"
    content: |
      This is the default `landing_sections` style. Use it for ordinary explanatory content.

      Required: `title`.

      Optional: `id`, `eyebrow`, `content`, `link_text`, `link_url`, `actions`, `image`, `image_alt`, `image_position`, `cards`, `style`, and `separator`.
    link_text: "Example text link"
    link_url: "#"
  - title: "Section with image"
    eyebrow: "Media"
    image: "/assets/sample-images/card-research-context.svg"
    image_alt: "Abstract research context image"
    content: |
      Add `image` to place media beside the text. The image sits on the right by default.

      Optional: set `image_position: "left"` to reverse the layout.
  - title: "Image on the left"
    eyebrow: "Media"
    image_position: "left"
    image: "/assets/sample-images/card-project-setting.svg"
    image_alt: "Abstract project setting image"
    content: |
      This section uses `image_position: "left"`. The layout stacks cleanly on small screens.
  - title: "Feature band"
    eyebrow: "Style"
    style: "feature"
    image: "/assets/sample-images/card-tree-kangaroo.svg"
    image_alt: "Abstract feature image"
    content: |
      Use `style: "feature"` for a full-width pale background band. It uses `secondary_color` from `_config.yml`.

      Good for project summaries, research focus areas, or sections that need gentle emphasis.
  - title: "Highlight band"
    eyebrow: "Style"
    style: "highlight"
    content: |
      Use `style: "highlight"` for a strong full-width band using `primary_color`.

      Good for impacts, calls to action, key findings, or short statements that should stand apart.
    link_text: "Optional link"
    link_url: "#"
  - title: "Card grid section"
    eyebrow: "Cards"
    cards:
      - title: "Card with image"
        image: "/assets/sample-images/card-cassowary.svg"
        image_alt: "Southern cassowary"
        text: "Cards can include an optional image, text, and link."
        link_text: "Read more"
        url: "#"
      - title: "Card without image"
        text: "Only `title` is required. Use `text` for a short summary."
        link_text: "Open item"
        url: "#"
      - title: "Card without link"
        image: "/assets/sample-images/card-crocodile.svg"
        image_alt: "Estuarine crocodile"
        text: "Leave out `url` and `link_text` when the card is informational only."
  - title: "Feature card grid"
    eyebrow: "Cards"
    style: "feature"
    cards:
      - title: "Project stream"
        text: "Feature bands can also contain cards."
        link_text: "View stream"
        url: "#"
      - title: "Research output"
        text: "Use cards for media, projects, news, people, outputs, or impact stories."
        link_text: "View output"
        url: "#"
      - title: "Partner activity"
        text: "Keep card text short so the landing page remains easy to scan."
        link_text: "View activity"
        url: "#"
  - title: "Section with action buttons"
    eyebrow: "Actions"
    content: |
      Add up to two optional `actions` to any landing section. The first action uses the primary colour and the second uses the secondary colour.
    actions:
      - label: "Contact us"
        url: "/contact/"
      - label: "Browse samples"
        url: "/sample-content/"
partner_organisations:
  eyebrow: "Partners"
  title: "Partner organisations block"
  content: |
    Use `partner_organisations` for funders, collaborators, institutions, and participating groups. This block is always displayed last when present.
  items:
    - name: "James Cook University"
      logo: "/assets/images/jcu-logo-colour.svg"
      url: "https://www.jcu.edu.au/"
    - name: "Partner organisation"
      logo: "/assets/sample-images/partner-placeholder.svg"
    - name: "Rainforest research partner"
      logo: "/assets/sample-images/partner-rainforest.svg"
    - name: "Reef research partner"
      logo: "/assets/sample-images/partner-reef.svg"
---

## How to use landing page blocks

Create a page with `layout: full-width`, then add the front matter groups you need. You can omit whole groups if a full-width page does not need them.

The main groups are `hero`, `achievements`, `carousel`, `landing_sections`, and `partner_organisations`.

The only group most landing pages should always have is `hero`. Everything else is optional and can be added as the project grows.
