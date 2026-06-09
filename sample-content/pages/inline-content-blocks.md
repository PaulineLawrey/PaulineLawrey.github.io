---
title: Inline content blocks
permalink: /sample-content/inline-content-blocks/
order: 3
image: "/assets/sample-images/card-project-setting.svg"
summary: "Examples of content blocks written directly in the Markdown page body."
---

This page demonstrates content blocks written inline with the rest of the page content. The class line after each block keeps the authoring pattern short while still allowing Markdown inside the block.

> ### Background colour ribbon
>
> This block uses `.jcu-block` and `.jcu-block--coloured-bkgnd` for a full-width pale secondary background.
>
> The content inside can include **emphasis**, [links](https://www.jcu.edu.au/), and ordinary Markdown lists.
>
> - Write the block where it should appear on the page.
> - Keep using Markdown for the content.
> - Add the class line directly underneath the block.
{:.jcu-block .jcu-block--coloured-bkgnd}

> ![Abstract project setting image]({{ "/assets/sample-images/card-cassowary.svg" | relative_url }})
> ### Block with image left
> The image is floated to the left of the text. Add the image as the first line inside the block and include `.jcu-block--image-left` in the class line.
{:.jcu-block .jcu-block--image-left}

This paragraph sits between two inline blocks, so authors can mix normal page content and styled sections in the order they want readers to encounter them.

> ## Card block with accent
>
> This version uses `.jcu-block--card` and `.jcu-block--accent`. It is useful for a short note, project update, or highlighted takeaway.
>
> Use it for brief notes that should stand apart from the surrounding page content.
{:.jcu-block .jcu-block--card .jcu-block--accent}

The card style can also be combined with the secondary block style when the section should use the full-width pale secondary background.

> ## Card block with secondary background
>
> This combines `.jcu-block--card` and `.jcu-block--coloured-bkgnd`, so the block uses the secondary background treatment while keeping the same spacing as the card block.
{:.jcu-block .jcu-block--card .jcu-block--coloured-bkgnd}

The same card block can include an image and the image can be floated to the left or right. Add the image as the first line inside the block and include `.jcu-block--image-left` or `.jcu-block--image-right` in the class line.

## Card blocks with image

> ![Abstract project setting image]({{ "/assets/sample-images/card-project-setting.svg" | relative_url }})
>
> ### Card block image at top
>
> This block uses `.jcu-block` and `.jcu-block--card``. The image is written as a normal Markdown image inside the block.
{:.jcu-block .jcu-block--card}

> ![Abstract project setting image]({{ "/assets/sample-images/card-project-setting.svg" | relative_url }})
>
> ### Card block, image to the left
>
> This block adds `.jcu-block--image-left` to float the first image to the left of the Markdown content.
>
> The image stacks above the text on smaller screens.
{:.jcu-block .jcu-block--card .jcu-block--image-left}

> ![Abstract research context image]({{ "/assets/sample-images/card-research-context.svg" | relative_url }})
>
> ### Card block image to the right
>
> This version uses `.jcu-block--image-right` to float the first image to the right while the text starts on the left.
{:.jcu-block .jcu-block--card .jcu-block--image-right}


## Inline partner logos

This example uses `.jcu-partner-logos`, combined with `.jcu-block--coloured-bkgnd`. The maximum number of logo tiles in each row is set in `_config.yml` with `partner_logo_max_items_per_row`.

[![James Cook University logo]({{ "/assets/images/jcu-logo-colour.svg" | relative_url }})](https://www.jcu.edu.au/)
![Partner organisation logo]({{ "/assets/sample-images/partner-placeholder.svg" | relative_url }})
![Rainforest research partner logo]({{ "/assets/sample-images/partner-rainforest.svg" | relative_url }})
![Reef research partner logo]({{ "/assets/sample-images/partner-reef.svg" | relative_url }})
{:.jcu-block .jcu-block--coloured-bkgnd .jcu-partner-logos}

## Inline image gallery

This example uses `.jcu-image-gallery`. The maximum number of image tiles in each row is set in `_config.yml` with `image_gallery_max_items_per_row`, and the layout steps down to fewer items per row as the screen narrows.

[![Southern cassowary]({{ "/assets/sample-images/card-cassowary.svg" | relative_url }})]({{ "/sample-content/content-blocks/southern-cassowary/" | relative_url }})
[![Lumholtz's tree-kangaroo]({{ "/assets/sample-images/card-tree-kangaroo.svg" | relative_url }})]({{ "/sample-content/content-blocks/lumholtzs-tree-kangaroo/" | relative_url }})
[![Estuarine crocodile]({{ "/assets/sample-images/card-crocodile.svg" | relative_url }})]({{ "/sample-content/content-blocks/estuarine-crocodile/" | relative_url }})
[![Green turtle]({{ "/assets/sample-images/card-green-turtle.svg" | relative_url }})]({{ "/sample-content/content-blocks/green-turtle/" | relative_url }})
{:.jcu-image-gallery}

## Alert blocks

Alert boxes use `.jcu-alert` plus a type class.

> **Note**
>
> Uses `.jcu-alert--note` for general information that users should take into account, even when skimming.
{:.jcu-alert .jcu-alert--note}

> **Important**
>
> Uses `.jcu-alert--important` for crucial information necessary for users to succeed.
{:.jcu-alert .jcu-alert--important}

> **Warning**
>
> Uses `.jcu-alert--warning` for critical content demanding immediate user attention due to potential risks.
{:.jcu-alert .jcu-alert--warning}

> **Caution**
>
> Uses `.jcu-alert--caution` for negative potential consequences of an action.
{:.jcu-alert .jcu-alert--caution}
