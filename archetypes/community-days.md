---
title: 'Community Days {{ replace .Name "-" " " | title }}'
weight: 2
type: 'event'
draft: true

params:
  event:
    dates: ''
    location_long: ''
    location_short: ''
    year: {{ .Name }}
  render:
    lists:
      display_in_lists: true
      display_on_top: true
    images:
      preview: '/events/default/community_days_list.png'
      header: ''
---
`Note:`

`This message is only for editors. Delete this block before publishing the page.`

` To learn how to customize and style an event page, please see the instructions in the README file: `
https://github.com/csaf-auxiliary/csaf-website-relaunch#add-a-page-for-the-event

## Overview

Event description.

---

## Program

### CSAF Community Day 1

| Time | Session | Speaker |
| --- | --- | --- |
| 13:30 - 13:45 CET | {{< internal-link "Welcome & Keynote" >}} {{< tlp-clear >}} | Justin Murphy (CISA) |

## Location

Information Security Hub at Munich Airport (Südallee 1, 85356 München, Germany)

{{< open-street-maps "48.350442,11.774101" >}}

## Registration for In-Person Attendance

To attend the CSAF Community Days {{ path.Base .File.Dir }} in person, please register by sending an
email to [csaf@bsi.bund.de](mailto:csaf@bsi.bund.de). We look forward to
welcoming you to Munich!

{{< register-button >}}

## Webex Details

---

{{< session-card >}}

### CSAF Community Days {{ path.Base .File.Dir }} Day 1

**Date and time:**

**Join link:**

**Webinar number:**

**Webinar password:**

**Join by phone:**

**Access code:**

{{< /session-card >}}

---

## Sessions

{{< session-card >}}

{{< tlp-clear >}}

### Welcome & Keynote

#### Speaker:

**Abstract:**

**Bio:**

{{< /session-card >}}
