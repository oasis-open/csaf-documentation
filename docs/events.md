# Adding a New Event Page

## Folder and Website Sections Structure

The `/events/` section of the website contains the list of the events,
pages of which are uploaded to the "/community-days/" and "/workshops/"
folders.
The structure of the `/community-days/` and `/workshops/` website sections
directly matches the structure of these folders.

---

### Managing Markdown Files

Hugo will automatically organize your event pages when you follow
the [Creating New Event Pages](#creating-new-event-pages) steps.
This keeps everything tidy and makes sure your event lists show up correctly
on the site.

If you ever need to add or update an event file by hand,
please follow these rules:

**File Name**

- Use the year of the event as the file name.

- For example: `2024.md`

**File Location**

- Put each year’s file into the folder for its event type.

- For example, a community days event in 2024 goes here:
  `content/community-days/2024.md`

Here’s what your folders might look like:

```
content
├─events.md
├─community-days/
│   ├── 2024.md
│   └── ...
└─workshops/
    ├── 2024.md
    └── ...
```

---

### Managing Images and Downloadable files

All event images and files for downloading by users
go into the `static/events/` folder.
You’ll see two subfolders there already:

- `community-days/`

- `workshops/`

To organize files:

1. **Create a Year Folder**:
   Inside the appropriate event type folder make a new folder
   named for the year.

   * Example: `static/events/workshops/2025/`

2. **Add Event Images**:
   Inside the year folder, drop in all images for each individual event.

3. **Upload downloadable files**:
   If you want to upload files to share with the users, create a dedicated
   folder `download` inside of the year folder and upload such files there.

   * Example: `static/events/workshops/2025/download/`

Here’s how it might look:

```
static/
└── events/
  ├── community-days/
  │ └── 2025/
  │   ├── download/
  │   │   ├── event_program.pdf
  │   │   └── presentation.odp
  │   ├── header.png
  │   └── image1.png
  └── workshops/
    └── 2025/
  │   ├── download/
  │   │   ├── event_program.pdf
  │   │   └── presentation.odp
      ├── header.png
      └── image1.png
```

When inserting images or links to the downloadable files
in your Markdown file, **do not** include `/static` in the file path.

✅ Correct:

```
![Image description](/events/workshops/2025/image1.png)

[Download the program](/events/workshops/2025/download/event_program.pdf)
```

🚫 Incorrect:

```
![Image description](/static/events/workshops/2025/image1.png)

[Download the program](/static/events/workshops/2025/download/event_program.pdf)
```

---

## Creating New Event Pages

You can either start with a ready-to-use template or create a blank page.

- **Using a template** (recommended for easier setup):

  ```
  hugo new <event-type>/<year>.md
  ```

  Available event types: `workshops`, `community-days`.

  Examples:

  ```
  hugo new workshops/2025.md
  hugo new community-days/2025.md
  ```

- **Starting with an empty page:**

  ```
  hugo new --kind=event <event-type>/<year>.md
  ```

  Example:

  ```
  hugo new --kind=event workshops/2025-munich.md
  ```

> **Important:** Use hyphens (`-`) if you need separate words in filenames.

> All event files must use the `.md` file extension.

---

## License Information

Each Markdown file must begin with a license block.
**Do not remove or move this block.**
It ensures legal compliance and correct attribution.

If needed, update the license details to reflect the actual license
under which your content should be published.

Example:

```markdown
<!--
  SPDX-FileCopyrightText: 2025 OASIS CSAF TC
  SPDX-License-Identifier: LicenseRef-OASIS-CSAF-TC-License
-->
```

---

## Updating pages of the events

### Front Matter Parameters

Each event page begins with technical information called **front matter**.
These help control how the page looks and where it appears.

Example:

```yaml
---
title: 'Workshop 2024'
subtitle: ''
weight: 1
type: 'event'
draft: true

params:
  event:
    dates: 'December 9-12, 2024'
    location_long: 'Germany, Information Security Hub at Munich Airport (Südallee 1, 85356 München, Germany)'
    location_short: 'München, Germany'
    year: 2024
  render:
    lists:
      display_in_lists: true
      display_on_top: true
    images:
      preview: '/events/default/workshop_list.png'
      header: '/events/workshops/2024/person-using-the-trackpad.jpg'
---
```

#### Required Settings

Required parameters **must not** be empty.

- **`title`**
  It will be shown at the top of the event page and in event lists.

  - If you generate an event page from a template,
    it will have the event type and the year as a default title.

  - You can write a custom title anytime.

- **`type`**
  *Please don’t change this!*

  - It’s a technical setting that tells Hugo how to build the page.

- **`draft`**
  Controls whether the event is published on the website.

  - `true` = hidden (not published)

  - `false` = visible (published).

  Set to `false` when the event is ready to go live.

- **`params.event.dates`**
  The event’s date.

  - It will appear on the page and in event lists.

- **`params.event.location_long`**
  The full location name.

  - Shown on the event page.

  - Example: `Information Security Hub at Munich Airport (Südallee 1, 85356 München, Germany)`

- **`params.event.location_short`**
  A shorter location name.

  - Shown in event lists.

  - Example: `'München, Germany'`

---

#### Optional Settings

- **`subtitle`**
  If provided, displayed in the header section of the event page
  right below the title.

  Example:

  ```markdown
  title: 'Community Days 2025'
  subtitle: 'Call for Presentations'
  ```

- **`weight`**
  Controls the order of events in lists.

  - Lower numbers appear higher on the list.

  - Default is `1`.

  [More about changing event order](#changing-the-order-of-events-in-lists)

- **`params.render.images.preview`**
  A preview image for the event card shown on the main `/events/` page.

  - If not added, the card will not have an image.

- **`params.render.images.header`**
  The big header background image at the top of the event page.

  - If not added, a blue-black gradient will be used.

- **`params.render.lists.display_in_lists`**
  Should this event appear in the list pages
  (`/events/`, `/workshops/`, `community-days`)?

  - `true` = show in the lists

  - `false` or not set = not shown in the lists

  ⚠️ This does not control whether the page is live —
    it just hides or shows it in the list views.
    To publish or unpublish, use the `draft` setting.

- **`params.render.lists.display_on_top`**
  Do you want the event to appear in a large card
  at the top of the `/events/` page?

  - `true` = featured at the top

  - `false` or not set = shown in the “Previous Events” section

⚠️ This setting only affects how the event is displayed —
not whether it is listed at all.
Use `display_in_lists` (above) to include it in the list.

---

### Event information visibility

#### Publishing an Event and Displaying it in Lists

Published events can be visible on the following pages:

- The event page (for Example `/workshops/2024/`)

- List pages `/events/` and `/workshops/` or `/community-days/`
depending on the folder where event file is uploaded.

Page visibility is defined on the top of its .md-file.

To **unpublish** an event or year page (hide it completely), set:

  ```yaml
  draft: true
  ```

This will remove the page from all the list pages and make it not accessible
by its direct URL.

**To hide a link to the event from the lists** without unpublishing its page,
set:

  ```yaml
  params:
    ...
    render:
      lists:
        display_in_lists: true
  ```

This will remove the page from all the list pages,
but it can still be found by its direct URL.

---

#### How to Feature an Event at the Top of the Events Page

The `/events/` page has **two sections**:

1. **Highlighted Events** – Big cards shown at the top of the page

2. **Previous Events** – Regular event list shown below

To choose **where** your event appears, adjust this setting
at the top of the event’s `.md` file:

**To Feature the Event at the Top (Highlighted)**

Change `display_on_top` to `true`:

```yaml
---
params:
  render:
    lists:
      display_on_top: true
---
```

This will display the event as a **large card at the top** of the `/events/`
page.

**To Show It in the “Previous events” Section**

Change `display_on_top` to `false`:

```yaml
---
params:
  render:
    lists:
      display_on_top: false
---
```

This will place the event **in the regular list** under "Previous events"
headline.

---

#### Changing the Order of Events in Lists

Events are sorted based on two parameters from the front matter:

- **Year** Newer events appear first.

- **Weight:** Pages with lower numbers appear first.

- **Title:** If Weight is the same (or missing), events
are sorted alphabetically by title.

**Default behavior:**
All events have a default weight of `1`.
This means they are normally sorted by their years and then - by titles.

**To change the order manually:**
Set a different weight at the top of the event page file:

```yaml
---
weight: 2
---
```

- Lower weight → Higher in the list.

- Higher weight → Lower in the list.

- 0 → Below all the other numbers within the same year.

---

### Using Shortcodes

Shortcodes help keep all event pages consistent.
You can add them in your Markdown files as needed.

---

#### 📩 `{{< register-button >}}`

By default adds a "Register now" button that links to `mailto:csaf@bsi.bund.de`.

Dafault text on the button and link can be replaced by adding custom values
in the double quotes.

Examples:

```markdown
{{< register-button email="cfp@csaf.io" >}}
{{< register-button text="Submit Your Proposal" >}}
{{< register-button email="cfp@csaf.io" text="Submit Your Proposal" >}}
```

---

#### 🖼️ `{{< text-and-image >}}...{{< /text-and-image >}}`

Displays an image alongside a block of text.

Example:

```markdown
{{< text-and-image >}}
![image](/events/<year>/<event-name>/<filename>)

Markdown text.
{{< /text-and-image >}}
```

- On large screens: image appears to the right.
- On small screens: image appears above the text.

---

#### 🔶 `{{< paragraph-accent >}}...{{< /paragraph-accent >}}`

Highlights a block of text with a vertical orange line on the left.

Example:

```markdown
{{< paragraph-accent >}}
Markdown text.
{{< /paragraph-accent >}}
```

#### 🟦 `{{< block-with-background >}}...{{< /block-with-background >}}`

Highlights a block by adding light-blue background and dark-blue border.

Example:

```markdown
{{< block-with-background >}}
Markdown text.
{{< /block-with-background >}}
```

---

#### 🗓️ `{{< event-timetable >}}...{{< /event-timetable >}}`

Formats a schedule block with a vertical orange line on the left
and larger text.

Example:

```markdown
{{< event-timetable >}}
**Workshop 1:**

09.12.2024 13:30–18:00 (Part 1)

10.12.2024 08:00–12:30 (Part 2)

(limited to 40 participants)
{{< /event-timetable >}}
```

---

#### 🔗 `{{< internal-link "Header Name" >}}`

Creates a link to a section header within the same page.

Example:

```markdown
{{< internal-link "Welcome & Keynote" >}}
```

Useful for making a table of contents.

---

#### 🗺️ `{{< open-street-maps "lat,lon[,zoom]" >}}`

Embeds an OpenStreetMap with a marker at the given coordinates.

Examples:

```markdown
{{< open-street-maps "48.350442,11.774101" >}}
{{< open-street-maps "48.350442,11.774101,16" >}}
```

- Without zoom: defaults to `14`.
- With zoom: set it manually (e.g., `16`).

---

#### 📝 `{{< session-card >}}...{{< /session-card >}}`

Renders a session description as a styled card.

Example:

```markdown
{{< session-card >}}

### Welcome & Keynote

#### Speaker:

**Abstract:**

**Bio:**

{{< /session-card >}}
```

---

#### TLP:Label

5 tags that insert TLP labes with proper styling:

```markdown
{{< tlp-red >}}
{{< tlp-amber >}}
{{< tlp-amber-strict >}}
{{< tlp-green >}}
{{< tlp-clear >}}
```

**Examples**

In the table of contents: within the table cell.

```markdown
| 13:30 - 13:45 CET | {{< internal-link "Welcome & Keynote" >}} {{< tlp-clear >}} | Justin Murphy (CISA) |
```

In the seccion card: after the opening `{{< session-card >}}` tag
and before the heading.

```markdown
{{< session-card >}}

{{< tlp-clear >}}

### Welcome & Keynote

...
{{< /session-card >}}
```

---

## Publishing a Page

When the page is ready to go live, set `draft` to `false`
at the top of the file:

```yaml
---
draft: false
---
```

This will make the page accessible to users.
