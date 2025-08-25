# csaf.io source code repository

This repository contains the source code for the website https://csaf.io.

Which is about the Common Security Advisory Framework (CSAF).
CSAF helps organizations to create, distribute, and consume
security advisories in a structured, machine-readable format.

The website itself is build with Hugo and styled using Bootstrap.

For more details about CSAF,
visit the [OASIS CSAF Technical Committee](https://www.oasis-open.org/committees/csaf/charter.php).

Also see [README.md](README.md), [CONTRIBUTING.md](CONTRIBUTING.md)
and [LICENSE.md](LICENSE.md).

---

## Deployment

The website is built and deployed automatically via GitHub Actions.

### How it Works

- The preferred way to update the website is by opening a **pull request**.
  Once merged into `main`, the changes will be deployed automatically.

- Advanced users with the necessary permissions can push directly to `main`,
  but using pull requests is recommended for review and tracking.

- Deployments can also be triggered manually from the **GitHub Actions** tab.

- The latest version is published at
  [GitHub Pages](https://csaf.io).

No manual deployment is required. Changes go live once reviewed and merged.

---

## Development Setup

When doing changes to the website, you can use a local setup
on a GNU/Linux machine to preview the layout.

### Prerequisites

Install the following:
(either from your GNU/Linux distribution packages
or following the generic instruction).

- **Hugo** (v0.145.0 or later, extended edition):
  Required for generating the static website from the source code files.

  - Check if Hugo is installed, by running `hugo version` in the terminal.

  - [Install Hugo](https://gohugo.io/getting-started/installing/) if necessary.

- **Git**: Required to clone the repository.

  - Check if Git is installed by running `git --version`
    in the terminal.

  - [Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) if necessary.

- **Node.js** (v20+) and **npm** (v10.8.2+, installed by default together with Node.js 20+):
  Required for managing project dependencies,
  such as the Bootstrap framework used for styling the pages.

  - Check if Node.js and npm are installed by running `node -v` and
    `npm -v` in the terminal.

  - [Install Node.js and npm](https://nodejs.org/) if necessary.

### 1. Pull the Repository

Clone the repository to your local machine using Git,
use the "<> Code" -> "Clone" information on the GitHub repository
you are working to find out which is _Your-Repository-Link_:

```bash
git clone Your-Repository-Link
```

### 2. Install Dependencies

```bash
cd Your-Repository-Name
```

Install project dependencies, including the Bootstrap framework:

```bash
npm install
```

### 3. Development Server with live Reload

```bash
hugo server -D
```

Check the output of the command, by default, the site will be accessible
by default at http://localhost:1313/ (which is the _baseURL_).

'-D' flag allows to include the draft pages to the build.
Leave it out, if you want to see pages like the production mode will show them.

#### 4. Rendering Quirks

The development server will not do full redirects on missed pages.
(This is a known problem with
hugo [#874](https://github.com/gohugoio/hugo/issues/874)
and does not affect the production site).
To check the 404 pages with the development mode,
you can directly point your browser to _baseURL_/404.html.

If styles are not rendered correctly (for example the fonts are different from
the published page), you may be in the situation that port and
domain or IP address under which you are accessing the development
server do not match what the webpages are configured with.
(You can diagnose the situation when reloading the site with the
browsers development tools' network tab running. The first requests
will be to your URL given in the browser, but subsequent requests
to the _baseURL_ it gets from the server.)

In this situation you can give the correct _baseURL_ to hugo, e.g.

```bash
hugo server -D --baseURL http://localhost:7000
```

Try `--disableFastRender` as option if some changes did not make
the reload, e.g. in the `.scss` files.

#### 5. Build the Static Site

Check how the static site is build in the github workflow
`.github/workflows/hugo.yaml` file.

It means calling `hugo` (an alias for `hugo build`) with similar options
and you get the site files in `public/`.

---

## Directory Structure

- **assets**: Contains the files that are being pre-processed
  (.scss files compiled into .css)
  and icons that have to be injected into HTML for styling;

- **content/**: Contains content files, most of which have only meta headers;

- **layouts/**: Contains custom templates and layout files for rendering the site;

- **static/**: Stores static assets such as images and SCSS files;

- **hugo.toml**: The configuration file for the Hugo site,
  where site-wide settings are defined;

- **data/**: Holds additional JSON data files
  used by Hugo for dynamic content generation;

- **LICENSE.md**: an overview over the licences of the used components;

- **LICENSES/**: Contains the license texts, that are referred to from
  licensing headers or files.

- **package.json** and **package-lock.json**: Manages Node.js dependencies;

---

## Project Settings Defined in `hugo.toml`

The `hugo.toml` file contains the main configuration settings for the Hugo project.

- **languageCode**: Defines the default language for the website
  (set to American English).

- **title**: The title of the website.

- **disableKinds**: Specifies which kinds of content to disable.
  The page types required for generating list-pages are disabled.

- **baseUrl**: Specifies the root URL of your site,
  which is used as the base for all relative links.

- **canonifyURLs**: When set to true, allows Hugo to add baseUrl
  to the relative links.
  At this stage is needed to handle base url that is not the site root.

### Markup Settings

Goldmark Parser is the tool that turns written content from the markdown files
into the final format that appears on the website.

For processing the text, the following settings are applied:
**[markup.goldmark.renderer]:**

- **unsafe = true:** It makes it possible to wrap the Markdown content
  in the .md files (specifically, tools.md) with extra HTML for styling.

**[markup.goldmark.extensions]:**

- **table = true:** Allows rendering markdown tables as `<table>` elements.

**[markup.goldmark.parser]:**

- **autoHeadingID = true:** Automatically generates `id`
  on every `<h1>` – `<h6>`
  (only for content rendered automatically from markdown).

- **autoHeadingIDType = "github":** Generates `id`s as lowercase,
  dash-separated slugs (GitHub style).

---

## How to Update the Website Content

- [Tools](/docs/tools.md)

- [Specifications](/docs/specifications.md)

- [Presentations](/docs/presentations.md)

- [Events](/docs/events.md)

- [Shared components](/docs/shared.md) (Header)

---

## History

Originally content from the old csaf.io webpage has been used.

New files developed for the webpage mechanics and the custom styles were
developed for the German Federal Office for Information Security (BSI)
([bsi.bund.de](https://www.bsi.bund.de))

The webpage and repo was constructed 2025-03 by
Intevation GmbH ([intevation.de](https://intevation.de))
