# one.compost.digital

The first issue of https://compost.digital. A static site built with [hugo](https://https://gohugo.io/).

## First-time setup

1. Clone this repo
2. [Install the hugo CLI](https://gohugo.io/getting-started/installing/)

## Local development

```
hugo server
```

## Build for deployment

```
hugo
```

## How to add content

### Piece pages

- Every piece gets its own folder in `content/pieces/`.
- The default piece layout is [`layouts/pieces/single.html`](layouts/pieces/single.html)

The frontmatter of a piece should have all of these fields:

```yaml
---
title: Seeding the Wild
author: Magma Collective # this needs to match an author name in data/people.yaml
description: In which seeds are strewn into small spaces, while blindfolded, and holding three apricots between two butt cheeks.
tableOfContentsImageUrl: ./images/angelica-gifs/mantis_computer.gif
titleImageUrl: ./images/angelica-gifs/mantis_computer.gif # this is optional
endingImageUrl: ./images/angelica-gifs/mantis_computer.gif
---
```

#### Footnotes

Footnote content can be included in a piece's frontmatter, or in a separate JSON file (see [`content/pieces/the-salt-of-the-cosmos`](content/pieces/the-salt-of-the-cosmos) for an example of the latter).

Every footnote is identified by a unique title. (This can be a number if you want, but then if you reorder them you'll have some serious renumbering to do.)

In the content markdown, you add a footnote reference like so:

```
{{< footnote "Title of footnote goes here" >}}
```

This is called a [hugo "shortcode"](https://gohugo.io/content-management/shortcodes/). It gets replaced by the content in [`layouts/shortcodes/footnote.html`](layouts/shortcodes/footnote.html).

### All other pages

- Every non-piece page gets its own .md file in `content/one-offs/`.
- Every non-piece page gets its own layout file in `layouts/one-offs/`.

### Site Data

#### Table of contents

The sequence of pieces in the table of contents is determined by [`data/piece-sequence.yaml`](data/piece-sequence.yaml)

#### Fundraising goals

See [`data/fundraising-goals.yaml`](data/fundraising-goals.yaml).

#### Author bios

See [`data/people.yaml`](data/people.yaml). The `name` fields in here must match the `author` fields in the piece frontmatter.
