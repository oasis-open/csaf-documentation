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

`⚠️ Note:`

`This message is only for editors. Delete this block before publishing the page.`

`Values in backticks below (dates and location) are the placeholders. Update them and remove the backsticks before publishing.`

`To learn how to customize and style an event page, please see the instructions in the`
[README file](/README-repo.md#add-a-page-for-the-event)

## Overview

Event description.

---

## Program

### CSAF Community Day 1 (`November 12, {{ .Name }}`)

`⚠️ Note: tables styling on small screens (tablets and mobile) is optimized
for the current short headers. If longer table headers need to be used,
the styling must be updated to avoid text overlapping.`

| Time              | Session                                   | TLP               | Speaker              |
| ----------------- | ----------------------------------------- | ----------------- | -------------------- |
| 13:30 - 13:45 CET | {{< internal-link "Welcome & Keynote" >}} | {{< tlp-clear >}} | Justin Murphy (CISA) |

## Location

`⚠️ Replace location name and coordinates for the map below and then delete this line.`

Information Security Hub at Munich Airport (Südallee 1, 85356 München, Germany)

{{< open-street-maps "48.350442,11.774101" >}}

## Registration for In-Person Attendance

To attend the CSAF Community Days {{ .Name }} in person, please register by sending an
email to [csaf@bsi.bund.de](mailto:csaf@bsi.bund.de?subject=%5BCSAF%20Community%20Days%20{{ .Name }}%5D%5BRegistration%5D). We look forward to
welcoming you to `Munich`!

{{< register-button email="csaf@bsi.bund.de?subject=[CSAF Community Days {{ .Name }}][Registration]" >}}

## Webex Details

---

{{< session-card >}}

### CSAF Community Days {{ .Name }} Day 1

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
