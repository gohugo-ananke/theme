# Ananke Theme for Hugo

Ananke is a flexible, production-ready starter theme for [Hugo](https://gohugo.io/) focused on accessibility, performance, and maintainable defaults.

![Ananke screenshot](images/screenshot.png)

* Demo: [ananke-theme.netlify.app](https://ananke-theme.netlify.app/)
* Documentation: [ananke-documentation.netlify.app](https://ananke-documentation.netlify.app/)
* Changelog: [CHANGELOG.md](CHANGELOG.md)

> [!IMPORTANT]
>
> Ananke moved to its own organisation on April 23, 2026. Please update your references from `github.com/theNewDynamic/gohugo-theme-ananke` to `github.com/gohugo-ananke/ananke`. Bear with us as we update all documentation and links to reflect this change. Until then, both URLs will continue to work as links as well as in the `git` operations for cloning and submodules.
>
> The following steps should suffice to update your references if you have not changed the setup:
>
> **For Hugo Modules:** search and replace all instances of `github.com/theNewDynamic/gohugo-theme-ananke/v2` with `github.com/gohugo-ananke/ananke/v2` in your site's configuration and run `hugo mod tidy` to update the module dependencies.
>
> **For Git Submodules:** To change the remote URL for your existing submodule, run:
>
> ```bash
> cd path/to/your/repo/themes/ananke # <-- adjust path as needed, keep the 'themes/ananke' part
> git remote set-url origin https://github.com/gohugo-ananke/ananke.git
> ```
>
> Then find `.gitmodules` in the root of your repository and replace all instances of `theNewDynamic/gohugo-theme-ananke` with `gohugo-ananke/ananke` in that file as well.
> Finally, run `git submodule sync` to update the submodule configuration.
>
> **Issues?** Get in touch via [GitHub Discussions](https://github.com/orgs/gohugo-ananke/discussions/944).

## Features

* Responsive layouts and accessible markup
* Configurable hero/header behaviour
* Configurable social follow/share links
* Optional contact form shortcode
* Localized i18n strings in many languages
* SEO defaults with Hugo internal templates
* Reading time/word count support
* Robots.txt handling by environment

## Installation

Ananke supports both installation methods:

* [Install as Hugo Module (recommended)](https://ananke-documentation.netlify.app/installation/gohugo-module/)
* [Install as Git Submodule](https://ananke-documentation.netlify.app/installation/git-submodule/)

If you are new to Hugo, see Hugo's official quick start: [gohugo.io/getting-started/quick-start](https://gohugo.io/getting-started/quick-start/).

## Getting Started

After installation, use these guides to configure your site:

* [Getting Started](https://ananke-documentation.netlify.app/getting-started/)
* [Configuration](https://ananke-documentation.netlify.app/configuration/)
* [Customisation](https://ananke-documentation.netlify.app/customisation/)
* [Troubleshooting](https://ananke-documentation.netlify.app/troubleshooting/)

## Basic configuration examples

A post can define common metadata in its front matter. The default archetype already includes `date`, `tags`, `featured_image`, and `description`; add `author` and `categories` when you need them:

```yaml
---
title: "Post title example"
author: "Jane Example"
date: 2026-05-15T00:00:00+07:00
categories:
  - News
  - Updates
tags:
  - hugo
  - ananke
featured_image: "/images/post-image.jpg"
description: "A short description for listings and metadata."
---
```

Use `featured_image` for the smaller image shown with post teasers and previews. Store the image in your site, for example under `static/images/`, and reference it from the site root as `/images/post-image.jpg`.

Add header navigation through Hugo's menu configuration:

```toml
[[menus.main]]
name = "About"
pageRef = "/about"
weight = 10

[[menus.main]]
name = "Authors"
pageRef = "/authors"
weight = 20
```

Add footer follow links, including email, through the social follow configuration. The available network definitions live in `config/_default/params.toml`.

```toml
[params.ananke.social.follow]
networks = ["email", "github"]

[params.ananke.social.github]
username = "example"

[params.ananke.social.email]
username = "hello@example.com"
```

## Support and Contributions

* Bug reports: [GitHub Issues](https://github.com/gohugo-ananke/ananke/issues)
* Questions and feature ideas: [GitHub Discussions](https://github.com/gohugo-ananke/ananke/discussions)
* Contribution guide: [CONTRIBUTING.md](CONTRIBUTING.md)