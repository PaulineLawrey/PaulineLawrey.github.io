# JCU research website theme

A JCU-themed Jekyll theme for research project communications. The theme is designed for GitHub Pages, so research teams can maintain project websites with Markdown content while reusing shared JCU-styled layouts, navigation, content blocks, and assets.

This repository is both:

- a reusable remote Jekyll theme, consumed with `remote_theme`
- a live sample site showing the page types and content blocks available in the theme

## Use as a remote theme

Create a Jekyll/GitHub Pages repository for your research project, then add this to the project site's `_config.yml`:

```yml
remote_theme: jcu-eresearch/jcu-research-website-theme
plugins:
  - jekyll-remote-theme
```

For production project sites, pin a release once this theme has tagged versions:

```yml
remote_theme: jcu-eresearch/jcu-research-website-theme@v1.0.0
plugins:
  - jekyll-remote-theme
```

GitHub Pages can load public GitHub-hosted Jekyll themes with `remote_theme`. The theme does not need to be published as a RubyGem.

Before other projects can consume this theme, keep this repository public on GitHub.

For local development in a consuming project, use a Gemfile such as:

```ruby
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
```

## Minimal project configuration

In the project site's `_config.yml`, set the project identity and theme settings:

```yml
title: "Research project website"
description: "A JCU-themed static website for research project communications."
url: "https://USERNAME.github.io"
baseurl: "/REPOSITORY-NAME"

remote_theme: jcu-eresearch/jcu-research-website-theme
plugins:
  - jekyll-remote-theme

markdown: kramdown
kramdown:
  input: GFM

theme_settings:
  show_breadcrumbs: true
  logo: "/assets/images/jcu-logo-mono.svg"
  favicon: "/assets/images/favicon.svg"
  project_logo: "/assets/sample-images/project-logo.svg"
  project_logo_alt: "Project logo"
  sidebar_logo_tile_background: "transparent"
  sidebar_logo_tile_border_color: "transparent"
  # Optional project-logo-specific overrides. Leave commented to use the sidebar logo tile settings above.
  #sidebar_project_logo_tile_background: "#FFFFFF"
  #sidebar_project_logo_tile_border_color: "rgba(255, 255, 255, 0.45)"
  font_family: "Lato, Arial, Helvetica, sans-serif"
  heading_font_family: "Lora, Georgia, serif"
  primary_color: "#354F52"
  secondary_color: "#C3D5C7"
  accent_color: "#86466E"
  text_color: "#344054"
  heading_color: "#344054"
  muted_text_color: "#667085"
  background_color: "#F4F6F3"
  surface_color: "#F1E4EC"
  border_color: "#D0D5DD"
  # content_alignment options: "left", "center"
  content_alignment: "left"
  table_banded_rows: true
  block_separator_style: "none"
  partner_logo_max_height: "6rem"
  partner_logo_max_items_per_row: 3
  image_gallery_max_items_per_row: 3
  page_card_columns: 3
  page_card_link_text: "Read more"

defaults:
  - scope:
      path: ""
      type: "pages"
    values:
      layout: "page"
```

If your site uses the default JCU logo and favicon assets from this theme, the paths above will work through the remote theme. To use your own logos or favicon, add files to the consuming site's `assets/images/` folder and update the paths.

The optional `project_logo` appears at the left of the shared site header. The header navigation is used on every page and changes to a burger menu on smaller screens.

The optional `favicon` appears in the browser tab. Set `favicon: false` to omit the favicon link.

The `markdown` and `kramdown` settings enable GitHub-flavoured Markdown features such as pipe tables and task lists.

Set `theme_settings.content_alignment` to `left` or `center` to control how
content is aligned within page, block, card, and full-width section containers.
The default is `left`.

## Navigation

Add `_data/navigation.yml` in the project site:

```yml
- title: Home
  url: /
- title: Project
  url: /project/
  children:
    - title: Research context
      url: /project/research-context/
    - title: Project setting
      url: /project/project-setting/
- title: Contact
  url: /contact/
```

If navigation is omitted, the theme falls back to a single Home link.
Navigation supports two levels. Top-level items appear in the header and any
`children` appear in a dropdown menu.

## Add a page

Create a Markdown file in the project site, such as `outputs.md`:

```yml
---
title: Outputs
permalink: /outputs/
blocks:
  - type: one-column
    title: "Project outputs"
    content: |
      Add reports, papers, datasets, or links here.
---
```

Then add it to `_data/navigation.yml`:

```yml
- title: Outputs
  url: /outputs/
```

## Full-width page layout

Use `layout: full-width` for a polished project page driven by front matter. It supports a hero section, achievement tiles, a carousel, styled sections before or after the carousel, card grids for media/projects/news, people and impact sections, optional section action buttons, and partner logos.

Add those components to the page's ordered `blocks` list. Each block declares a `type` of `achievements`, `carousel`, `standard`, `feature`, `highlight`, or `partner-logos`.

See `FULL_WIDTH_PAGE_STYLES.md` for the editable front matter pattern and the CSS classes generated by the layout.

## Content block types

Content blocks can be added in front matter, or simple narrative blocks can be written inline in the Markdown body.

### Inline blocks

Use Markdown blockquote notation with a short class line when you want styled blocks to appear among ordinary page content:

```md
> ## Section title
>
> Markdown content can include **emphasis**, [links](https://www.jcu.edu.au/), and lists.
{:.jcu-block .jcu-block--coloured-bkgnd}
```

Inline block options:

- `.jcu-block--coloured-bkgnd`: use the configured secondary colour across the full content panel
- `.jcu-block--card`: use the theme card colour with a border
- `.jcu-block--accent`: add the JCU accent line to the left of a block
- `.jcu-block--full`: allow the block to use the full content width
- `.jcu-block--image-left`: float the first image in the block to the left
- `.jcu-block--image-right`: float the first image in the block to the right

Place the class line directly underneath the block it should style.

When normal Markdown content follows an inline block, the theme adds extra spacing automatically.

For GitHub-style alerts, use a labelled blockquote with a JCU alert class:

```md
> **Note**
>
> Highlights information that users should take into account.
{:.jcu-alert .jcu-alert--note}
```

Alert options are `.jcu-alert--note`, `.jcu-alert--important`, `.jcu-alert--warning`, and `.jcu-alert--caution`.

For inline partner logos, use standard Markdown images and linked images, then add the `.jcu-partner-logos` class. The maximum number of tiles in each row is set by `theme_settings.partner_logo_max_items_per_row`.

```md
[![James Cook University logo]({{ "/assets/images/jcu-logo-colour.svg" | relative_url }})](https://www.jcu.edu.au/)
![Partner organisation logo]({{ "/assets/sample-images/partner-placeholder.svg" | relative_url }})
![Rainforest research partner logo]({{ "/assets/sample-images/partner-rainforest.svg" | relative_url }})
{:.jcu-partner-logos}
```

For an inline image gallery, use standard Markdown images or linked images, then add the `.jcu-image-gallery` class. The maximum number of tiles in each row is set by `theme_settings.image_gallery_max_items_per_row`.

```md
[![Southern cassowary]({{ "/assets/sample-images/card-cassowary.svg" | relative_url }})]({{ "/sample-content/content-blocks/southern-cassowary/" | relative_url }})
[![Lumholtz's tree-kangaroo]({{ "/assets/sample-images/card-tree-kangaroo.svg" | relative_url }})]({{ "/sample-content/content-blocks/lumholtzs-tree-kangaroo/" | relative_url }})
[![Estuarine crocodile]({{ "/assets/sample-images/card-crocodile.svg" | relative_url }})]({{ "/sample-content/content-blocks/estuarine-crocodile/" | relative_url }})
{:.jcu-image-gallery}
```

### One column

```yml
- type: one-column
  title: "Section title"
  content: |
    Markdown content goes here.
```

### Two column

```yml
- type: two-column
  title: "Section title"
  columns:
    - title: "Left column"
      content: |
        Markdown content goes here.
    - title: "Right column"
      content: |
        Markdown content goes here.
```

### Image and text

```yml
- type: image-text
  title: "Context with supporting image"
  image: "/assets/sample-images/card-research-context.svg"
  image_alt: "Abstract illustration of research context"
  image_position: "right"
  image_size: "medium"
  background: "secondary"
  background_mode: "behind"
  caption: "Optional image caption."
  content: |
    Markdown content goes here.
```

Options:

- `image_position`: `left` or `right`
- `image_size`: `small`, `medium`, or `large`
- omit `image` to display the text at full width

### Block backgrounds

Any content block can use the configured secondary colour as its background:

```yml
- type: one-column
  title: "Section title"
  background: "secondary"
  background_mode: "block"
  content: |
    Markdown content goes here.
```

Use `background_mode: "block"` to colour the block itself, or `background_mode: "behind"` to place a larger coloured panel behind the block.

Block separator options are `none`, `line`, `accent`, and `band`.

The full-width layout does not show breadcrumbs. Other pages show breadcrumbs unless `theme_settings.show_breadcrumbs` is set to `false`.

### Markdown tables

Markdown pipe tables use the configured secondary colour for the header row. Internal table lines use a muted version of the secondary colour, with no lines on the outer edges.

```md
| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |
```

Set alternating table row backgrounds in `_config.yml`:

```yml
theme_settings:
  table_banded_rows: true
```

### Image gallery

```yml
- type: gallery
  title: "Featured links"
  columns: 3
  items:
    - title: "Project context"
      image: "/assets/sample-images/gallery-background.svg"
      url: "/project/research-context/"
```

For front matter gallery blocks, `columns` overrides `theme_settings.image_gallery_max_items_per_row`. Inline `.jcu-image-gallery` blocks use only the value from `_config.yml`. Both gallery styles treat the configured value as a maximum and step down to fewer tiles per row as the screen narrows.

### Partner logos

Set logo defaults in `_config.yml`:

```yml
theme_settings:
  partner_logo_max_height: "6rem"
  partner_logo_max_items_per_row: 3
```

Then add a logo block to any page:

```yml
- type: partner-logos
  title: "Project partners"
  columns: 3
  content: |
    Optional introductory text.
  partners:
    - name: "James Cook University"
      logo: "/assets/images/jcu-logo-colour.svg"
      url: "https://www.jcu.edu.au/"
    - name: "Partner organisation"
      logo: "/assets/sample-images/partner-placeholder.svg"
```

For front matter partner-logo blocks, `columns` overrides `theme_settings.partner_logo_max_items_per_row`. Inline `.jcu-partner-logos` blocks use only the value from `_config.yml`. Both partner logo styles treat the configured value as a maximum and step down to fewer logos per row as the screen narrows.

### Page cards

Set card defaults in `_config.yml`:

```yml
theme_settings:
  page_card_columns: 3
  page_card_link_text: "Read more"
```

Then add a card block to any page. The `folder` value matches Markdown pages in that folder:

```yml
- type: page-cards
  title: "Project pages"
  folder: "project-pages/"
  columns: 2
  link_text: "Read more"
```

Each page in the folder can provide card metadata:

```yml
---
title: Research context
permalink: /project/research-context/
order: 1
image: "/assets/sample-images/card-research-context.svg"
summary: "A short overview of the project setting."
---
```

If `columns: 1`, each card uses a wide layout with the image on the left and the summary on the right on desktop screens.

## Local development

Use Ruby `3.3.4` to match the GitHub Pages build environment, then run:

```bash
bundle install
bundle exec jekyll serve
```

The configured GitHub Pages URL for this sample repository is:

```text
https://PaulineLawrey.github.io/jcu-research-website-theme/
```

## Maintaining the theme

Keep reusable presentation files in these folders:

- `_layouts`
- `_includes`
- `_data`
- `assets`

Sample content for previewing the theme is grouped under `sample-content/`. Sample-only media is grouped under `assets/sample-images/`, while the reusable JCU logo assets remain in `assets/images/`.

Research project sites that use this as a remote theme should create their own content pages and navigation data.

When releasing a stable version, create a Git tag such as `v1.0.0` and tell consuming sites to pin that tag in `remote_theme`.
