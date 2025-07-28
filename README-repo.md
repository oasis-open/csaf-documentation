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
  [GitHub Pages](https://csaf-auxiliary.github.io/csaf-website-relaunch).

No manual deployment is required. Changes go live once reviewed and merged.

---

## Development server (with live reload)

To run the Hugo development server with live reload, follow these steps:

### Prerequisites

Before starting the development server, ensure you have the following installed:

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

Clone the repository to your local machine using Git:

```bash
git clone https://github.com/oasis-open/csaf-documentation/main/README-repo.md.git
```

### 2. Install Dependencies

Navigate into the project directory:

```bash
cd your-repository-name
```

Install project dependencies, including the Bootstrap framework:

```bash
npm install
```

### 3. Start the Development Server

```bash
hugo server -D
```

'-D' flag allows to include the draft pages to the build.

The site will be accessible at http://localhost:1313/.

If styles are not rendered correctly (for example the fonts are different from
the published page), start the server with binding:

```bash
hugo server -D --bind 127.0.0.1 --baseURL http://127.0.0.1:1313
```

---

## Directory structure

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

- [Home Page](/docs/index.md)

---

## History

Originally content from the old csaf.io webpage has been used.

New files developed for the webpage mechanics and the custom styles were
developed for the German Federal Office for Information Security (BSI)
([bsi.bund.de](https://www.bsi.bund.de))

The webpage and repo was constructed 2025-03 by
Intevation GmbH ([intevation.de](https://intevation.de))
