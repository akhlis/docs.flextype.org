---
title: Entries
description: Entries are the fundamental building-blocks of your site. Each entry in Flextype should contains Entry Front Matter block in YAML format at the top of the file and Entry Content marked up using HTML + Markdown + Shortcodes at the bottom of the file.
breadcrumbs:
  0:
    title: "Documentation"
    link: "[url]/en/"
  1:
    title: "Concepts"
    link: "[url]/en/concepts/"
---

Entries are the fundamental building-blocks of your project. We are using jekyll like entries format, it means that each entry in the Flextype should contains **Entry Front Matter** block in valid YAML format at the top of the file and **Entry Content** marked up using HTML + Markdown + Shortcodes and etc... at the bottom of the file.

Here is a basic example:

<div class="file-header"><i class="far fa-file-alt"></i> project/entries/my-entry/entry.md</div>

    ---
    title: My Entry
    description: My entry description
    ---
    My entry content.

Between triple-dashed lines, you can set predefined variables or even create custom ones of your own.

When you will fetch entry above with [Content APIs]([url]/en/concepts/content-apis), data will looks like this:

```json
{
  "data": {
      "title": "My Entry",
      "description": "My entry description",
      "content": "My entry content."
  }
}
```

### Topics

* [Entries and URLs structure](./entries/urls-structure)
* [Variables](./entries/variables)
