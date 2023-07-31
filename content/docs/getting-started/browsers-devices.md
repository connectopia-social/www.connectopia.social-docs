---
layout: docs
title: Browsers and devices
description: Learn about the browsers and devices, from modern to old, that are supported by Bootstrap, including known quirks and bugs for each.
group: getting-started
toc: true
---

## Supported browsers

Bootstrap supports the **latest, stable releases** of all major browsers and platforms.

Alternative browsers which use the latest version of WebKit, Blink, or Gecko, whether directly or via the platform's web view API, are not explicitly supported. However, Bootstrap should (in most cases) display and function correctly in these browsers as well. More specific support information is provided below.

You can find our supported range of browsers and their versions [in our `.browserslistrc file`](/blob/v/.browserslistrc):

```text
{{< rf.inline >}}
{{- readFile ".browserslistrc" | chomp | htmlEscape -}}
{{< /rf.inline >}}
```

We use [Autoprefixer](https://github.com/postcss/autoprefixer) to handle intended browser support via CSS prefixes, which uses [Browserslist](https://github.com/browserslist/browserslist) to manage these browser versions. Consult their documentation for how to integrate these tools into your projects.

### Mobile devices

Generally speaking, Bootstrap supports the latest versions of each major platform's default browsers. Note that proxy browsers (such as Opera Mini, Opera Mobile's Turbo mode, UC Browser Mini, Amazon Silk) are not supported.
