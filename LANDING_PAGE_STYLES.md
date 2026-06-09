# Landing page styles

The `landing` layout is designed for research project websites that need a polished first page without requiring the author to make design decisions. Most content is edited in `index.md` front matter.

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
layout: landing
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

Use `landing_sections` for the main page areas. Recommended sections for research project sites are:

- Our research
- In the media
- Our projects
- Latest news
- Impacts
- Who we are
- Partner organisations
- Contact us

Sections can contain text, an image, a link, or a set of cards.

```yml
landing_sections:
  - title: "Our research"
    eyebrow: "Focus"
    style: "feature"
    image: "/assets/sample-images/card-research-context.svg"
    image_alt: "Abstract research context image"
    content: |
      Explain the research problem, why it matters, and how the project responds.
    link_text: "Read about the research"
    link_url: "/research/"
    separator: true
```

Set `separator: true` on any item in `landing_sections` to add an accent separator bar after that section.

## Achievements

Use `achievements` for three prominent facts, outcomes, or milestones. Each tile can use `value`, `icon`, or `image`.

```yml
achievements:
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

Set `achievements.separator: true` to add an accent separator bar after the achievements block.

## Image carousel

Use `carousel` for a short sequence of project images. `eyebrow`, `title`, and `lead` are optional.

```yml
carousel:
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

Set `carousel.separator: true` to add an accent separator bar after the carousel.

## Card sections

Cards work well for media items, projects, news, people, or impact stories.

```yml
landing_sections:
  - title: "Latest news"
    eyebrow: "Updates"
    cards:
      - title: "Project milestone"
        text: "A short update about recent progress."
        link_text: "Read more"
        url: "/news/project-milestone/"
```

## Partner organisations

Use `partner_organisations` for funders, collaborators, and institutions. This section is always displayed last on the landing page when it is present.

```yml
partner_organisations:
  title: "Partner organisations"
  content: |
    Recognise the organisations that make the project possible.
  items:
    - name: "James Cook University"
      logo: "/assets/images/jcu-logo-colour.svg"
      url: "https://www.jcu.edu.au/"
```

## Contact call to action

```yml
contact_cta:
  title: "Contact us"
  separator: true
  content: |
    Add a clear route for enquiries.
  link_text: "Get in touch"
  link_url: "/contact/"
```

Set `contact_cta.separator: true` or `partner_organisations.separator: true` to add the same accent separator after those blocks.

## Style options

The layout uses the existing theme colours:

- `primary_color` for hero headings, buttons, links, and highlight sections
- `secondary_color` for achievement icons and supporting emphasis
- `accent_color` for structural emphasis
- `secondary_background_color` plus `secondary_background_opacity` for pale feature bands
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
- `.landing-contact`

Researchers usually should not need to edit these classes. Change content in front matter first, and only edit CSS for project-specific design requirements.
