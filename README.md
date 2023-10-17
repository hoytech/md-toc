# md-toc: Markdown Table Of Contents Generator

This simple script will scan a markdown file for headers and build a table-of-contents, like this:

<!-- TOC FOLLOWS -->
<!-- START OF TOC -->
<!-- md-toc: https://github.com/hoytech/md-toc -->
* [Usage](#usage)
  * [Setup](#setup)
    * [Custom Nesting](#custom-nesting)
  * [Updating](#updating)
  * [Warnings](#warnings)
* [Author](#author)
<!-- END OF TOC -->

## Usage

### Setup

Before running the first time, put the following on a line by itself (with no leading whitespace):

    <!-- TOC FOLLOWS -->

Then run the script like this:

    md-toc README.md

`md-toc` will collect all `h1`, `h2`... tags (in markdown: `#`, `##`, ...), build nested lists of these, and insert them after the `TOC FOLLOWS` line. The header levels used can be [customised](#custom-nesting).

#### Custom Nesting

By default, it will only include levels 2 through 4, but you can customise this with another argument:

    md-toc README.md 1-5

### Updating

Each time you run `md-toc`, it will again search for the `TOC FOLLOWS` line, and delete everything between the `START OF TOC` and `END OF TOC` comment lines, re-render the new ToC, and insert it.

### Warnings

`md-toc` will warn you in the following cases:

* Duplicate headers
* Broken internal links (ie `[click here](#no-such-header)`)

## Author

Doug Hoyte, 2023

MIT License
