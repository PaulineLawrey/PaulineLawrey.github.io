# Full-width page styles

The `full-width` layout is designed for research project websites that need a polished page without requiring the author to make design decisions. Most content is edited in page front matter.

Landing pages are full-width pages and use the same shared header navigation as every other page. The menu uses `_data/navigation.yml`, which is useful when a page exists in the site but is not represented as a section on the landing page.

Set the default separator behaviour in `_config.yml`:

```yml
theme_settings:
  landing_block_separators: false
```

When `landing_block_separators` is `true`, landing blocks show separator bars unless a block sets `separator: false`. When it is `false`, blocks hide separator bars unless a block sets `separator: true`.

## Use the layout

```yml
---
layout: full-width
title: Home
permalink: /
hero:
  eyebrow: "JCU research project"
  title: "Research with purpose, shared with clarity"
  lead: "A short plain-language description of the project."
  image: "/assets/sample-images/gallery-background.svg"
  image_alt: "Description of the hero image"
  separator: true
  actions:
    - label: "Explore our research"
      url: "#our-research"
    - label: "Contact us"
      url: "/contact/"
---
```

The hero follows `theme_settings.landing_block_separators` unless `hero.separator` is set.

## Main sections

Use the ordered `blocks` list for every block below the hero. Each item needs one of these types:

- `achievements`: facts, outcomes, or milestones
- `carousel`: a sequence of project images
- `standard`: text, images, actions, or cards on the normal page background
- `feature`: the same fields on a band using `secondary_color`
- `highlight`: the same fields on a strong band using `primary_color`
- `partner-logos`: organisation and funder logos

Blocks render in list order, so authors can place a section before or after the carousel without using duplicate YAML keys.

Recommended sections for research project sites are:

- Our research
- In the media
- Our projects
- Latest news
- Impacts
- Who we are
- Partner organisations
- Contact us

Sections can contain text, an image, a text link, up to two action buttons, or a set of cards.

```yml
blocks:
  - type: "feature"
    title: "Our research"
    eyebrow: "Focus"
    image: "/assets/sample-images/card-research-context.svg"
    image_alt: "Abstract research context image"
    content: |
      Explain the research problem, why it matters, and how the project responds.
    actions:
      - label: "Read about the research"
        url: "/research/"
      - label: "Meet the team"
        url: "/people/"
    separator: true
```

The optional `actions` list supports up to two buttons. The first uses the primary colour and the second uses the secondary colour. Use `link_text` and `link_url` instead when a section only needs a quiet text link.

Set `separator: true` on any block to add an accent separator bar after it.

## Achievements

Use `type: "achievements"` for three prominent facts, outcomes, or milestones. Each tile can use `value`, `icon`, or `image`.

```yml
blocks:
  - type: "achievements"
    title: "Progress at a glance"
    separator: true
    items:
      - value: "12"
        label: "Active studies"
        text: "Research activities underway with communities and partners."
      - icon: "P"
        label: "Publications"
        text: "Papers, reports, and datasets from the project."
      - image: "/assets/sample-images/card-green-turtle.svg"
        image_alt: "Green turtle"
        label: "Field sites"
        text: "Places where project activities are happening."
```

## Image carousel

Use `type: "carousel"` for a short sequence of project images. `eyebrow`, `title`, and `lead` are optional.

```yml
blocks:
  - type: "carousel"
    eyebrow: "Gallery"
    title: "Research in context"
    lead: "Use the carousel for fieldwork, project locations, lab work, or community activities."
    separator: true
    items:
      - image: "/assets/sample-images/gallery-background.svg"
        image_alt: "Abstract background image"
        caption: "Project context and research setting"
      - image: "/assets/sample-images/gallery-about.svg"
        image_alt: "Abstract project information image"
        caption: "Research activities and project updates"
```

## Card sections

Cards work well for media items, projects, news, people, or impact stories.

```yml
blocks:
  - type: "standard"
    title: "Latest news"
    eyebrow: "Updates"
    cards:
      - title: "Project milestone"
        text: "A short update about recent progress."
        link_text: "Read more"
        url: "/news/project-milestone/"
```

## Partner organisations

Use `type: "partner-logos"` for funders, collaborators, and institutions. Its position in `blocks` determines where it is displayed.

The `title` is optional. Omit it or set it to an empty string to hide the visible heading; the theme retains an accessible label for the section. Set `background: "primary"` to place the block on a full-width primary-colour band with automatically contrasting text. Logo images have no tile background, allowing transparent monochrome logos to sit directly on the band.

```yml
blocks:
  - type: "partner-logos"
    background: "primary"
    title: ""
    content: |
      Recognise the organisations that make the project possible.
    items:
      - name: "James Cook University"
        logo: "/assets/images/jcu-logo-colour.svg"
        url: "https://www.jcu.edu.au/"
```

## Style options

The layout uses the existing theme colours:

- `primary_color` for hero headings, primary buttons, links, highlight sections, and achievement icons
- `secondary_color` for feature bands, coloured content-block backgrounds, secondary buttons, and supporting emphasis
- `accent_color` for structural emphasis
- `surface_color` and `border_color` for cards and callouts

Useful optional future settings would be:

- `hero_overlay_color` if using photographic hero images that need consistent text contrast
- `landing_card_background_color` if cards need to differ from other surfaces
- `landing_highlight_text_color` if a site uses a very light primary colour
- `landing_section_spacing` if a site needs denser or more spacious landing pages

## CSS classes

The layout generates these main classes:

- `.landing-page`
- `.site-header`
- `.header-nav`
- `.header-submenu`
- `.landing-hero`
- `.landing-hero-content`
- `.landing-hero-media`
- `.landing-actions`
- `.landing-button`
- `.landing-block--separator`
- `.landing-section`
- `.landing-section--feature`
- `.landing-section--highlight`
- `.landing-section--with-media`
- `.landing-card-grid`
- `.landing-card`
- `.landing-achievement-grid`
- `.landing-achievement`
- `.landing-carousel`
- `.landing-carousel-slide`
- `.landing-partners`
- `.landing-section-actions`

Researchers usually should not need to edit these classes. Change content in front matter first, and only edit CSS for project-specific design requirements.
