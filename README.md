# UKSI Coding Guide

[![deployment](https://github.com/English-Institute-of-Sport/UKSI_code_guide/actions/workflows/deployment.yml/badge.svg)](https://github.com/English-Institute-of-Sport/UKSI_code_guide/actions/workflows/deployment.yml)

[![Built with Material for MkDocs](https://img.shields.io/badge/Material_for_MkDocs-526CFE?style=for-the-badge&logo=MaterialForMkDocs&logoColor=white)](https://squidfunk.github.io/mkdocs-material/)

**<p style="text-align: center;">Repository for UKSI Coding Guide. This repo contains the documentation itself, the static site generator, and details on the development and deployment environments.</p>**

## Table of Contents
1. [Development](#development)
2. [Adding to, and editing the docs](#4-adding-to-and-editing-the-docs)
3. [Deployment](#deployment)

## Development

### Development Env - Getting Started

This documentation site is built using [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/). To build the development environment follow the instructions below:

### 1. Create a Python venv

#### Prerequisites
You will need a [Python installation](https://www.python.org/downloads/) (3.12 used at time of writing) to build and test this repo. Build the site locally as follows:

#### Clone Source code

1. First `cd` into the desired directory and clone this repo via `ssh`:

```bash
git clone https://github.com/English-Institute-of-Sport/UKSI_code_guide.git
```

2. Change into cloned directory `./STSDocsWebsite`:
```bash
cd ./STSDocsWebsite
```

#### Build virtual environment

1. Create a Python virtual environment:
```bash
python -m venv .venv
```

2. Activate the virtual environment:

On Windows - 
```bash
./.venv/Scripts/Activate.ps1
```

On Linux - 
```bash
source ./.venv/bin/activate
```

3. Use `requirements.txt` to install the required dependencies:
```bash
pip install -r ./requirements.txt
```

### 2. Run site locally in your venv

Assuming that you have activated the venv as per the previous step, you can test the build by running the local dev server:

On Windows - 
```bash
./.venv/Scripts/Activate.ps1
mkdocs serve
```

On Linux - 
```bash
source ./.venv/bin/activate
mkdocs serve
```

In the console, you should see some outputs similar to the messages below and be able to see the docs website running in your browser on localhost.

```
INFO    -  Building documentation...
INFO    -  Cleaning site directory
INFO    -  Documentation built in 1.14 seconds
INFO    -  [14:33:58] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO    -  [14:33:58] Serving on http://127.0.0.1:8000/
INFO    -  [14:34:00] Browser connected: http://127.0.0.1:8000/timing_systems/Out_Of_Stadia/race_walking/race_walk_data_tx/
```

### 3. MKDocs Configuration - editing the website

Site configuration is all held within [`mkdocs.yml`](./mkdocs.yml).

See the [mkdocs website](https://squidfunk.github.io/mkdocs-material/reference/data-tables/) for full details.


### 4. Adding to, and editing the docs

All documentation is stored in the `./docs` directory. `index.md` is our homepage/entry point. From here docs are organised into further sub-directories that should seem fairly logical.

To update or modify a page, simply create a new markdown (`.md`) file or edit an existing one. mkdocs will detect the changes (if `mkdocs serve` is running) and update indexes, tables of contents etc. With this in mind, think carefully about what you call each file as these are used to create the indexing systems. Follow the current naming convention of `Capitalised_Delimited_With_Underscores`.

Assets (images, data files etc.) are stored and organised in `./docs/assets/*`. Here you will find sub-directories for:
- images
- logos
- page templates

Organise assets in a logical way that makes referencing them via relative paths easy.

### Formatting & Layout Guide

Templates can be found in `docs/assets/templates` ....once I've written them.

### Order Pages

Page ordering can be configured using the [MkDocs Awesome Pages Plugin](https://github.com/lukasgeiter/mkdocs-awesome-pages-plugin), which allows pages to configured in a logical order. (By default MkDocs will order pages alphabetically).

The plugin is enable via the `mkdocs.yml` file. To use it simply place a file called `.pages` in a directory and use the `nav` attribute to customise page navigation on that directories' level.

```yaml
nav:
    - subdirectory
    - page1.md
    - page2.md
```

### Diagrams

We have support for `Meramid.js` which allows us to build many kinds of diagrams in markdown rather than having to embed them as images. See [here](https://mermaid.js.org/syntax/examples.html) for further examples.

### Tables

Tables currently follow the same rules are as standard markdown syntax.

Example table syntax:

```markdown
| **Column 1** | **Column 2** | **Column n...** |
| --- | --- | --- |
| Some   | data   | here |
```

Example table rendered:

| **Column 1** | **Column 2** | **Column n...** |
| --- | --- | --- |
| Some   | data   | here |

See [here](https://squidfunk.github.io/mkdocs-material/reference/data-tables/) for further examples.

### Code blocks

Code blocks should indicate the language or or data data. e.g. C++, JSON, etc.

Code blocks are written as follows:
```
```json title="Packet Structure"
{
    "penaltyType": "0",
    "bib": "123",
    "time": "00:00:00",
    "count": "1"
}
```

This example will render as follows:
```json title="Packet Structure"
{
    "penaltyType": "0",
    "bib": "123",
    "time": "00:00:00",
    "count": "1"
}
```

Note: The html title will not render in standard markdown but will in the actual site.

see [here](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/) for further examples for further examples.

### Maths Equations

See [here](https://squidfunk.github.io/mkdocs-material/reference/math/#mathjax-docsjavascriptsmathjaxjs) for further examples.

### Images

`glightbox` is enabled to allow images to be shown in full screen. Generally, if an image is >600px it should be scaled so it does not appear too large on the screen. Use the following inline CSS after the image path:

```markdown
![Image title](path/to/image.jpg){ style="width:600px; "}
```
This will scale the image width to 600 px while maintaining the aspect ratio.

Default alignment is central but you can align left or right using:

```
{ align=left }

or

{ align=right }
```

Add an image caption using:
```html
<figure markdown="span">
  ![Image title](https://dummyimage.com/600x400/){ width="300" }
  <figcaption>Image caption</figcaption>
</figure>
```

See [here](https://squidfunk.github.io/mkdocs-material/reference/images/) for further examples.


### Icons and Emojis

See [here](https://squidfunk.github.io/mkdocs-material/reference/icons-emojis/) for examples and to search available icons. 

### Admonitions

Important notes, warning and other info can be rendered in Admonition boxes. For example:

```
!!! warning
    This is a warning box
```

!!! warning
    This is a warning box

```
!!! note
    This is a note box
```

!!! note
    This is a note box

See [here](https://squidfunk.github.io/mkdocs-material/reference/admonitions/) for further examples.

## Deployment

The site is published using [GitHub Pages](https://pages.github.com/).

Changes that are pushed to the `main` branch will automatically trigger a GitHub Action CI pipeline which will rebuild the site and publish it. 

See [MkDocs website](https://squidfunk.github.io/mkdocs-material/publishing-your-site/) for more details.