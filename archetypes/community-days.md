---
title: 'Community Days {{ replace .Name "-" " " | title }}'
subtitle: 'Call for Presentations'
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
      button:
        url: 'mailto:cfp@csaf.io'
        text: 'Submit Your Proposal'
    images:
      preview: '/events/default/community_days_list.png'
      header: ''
---

`Note:`

`This message is only for editors. Delete this block before publishing the page.`

`Values in backticks below (dates and location) are the placeholders. Update them and remove the backsticks before publishing.`

`To learn how to customize and style an event page, please see the instructions in the README file:`
https://github.com/csaf-auxiliary/csaf-website-relaunch#add-a-page-for-the-event

### About CSAF Community Days

The CSAF (Common Security Advisory Framework) Community Days is an event
dedicated to discussing tools, best practices, innovations and success stories
related to CSAF. We invite practitioners, developers, producers, consumers and
other community members to share their knowledge with the community.

{{< block-with-background >}}

### Call for Presentations

We are looking for presentations about CSAF focusing on tools, success stories,
lessons learned, projects, innovative solutions and the integration or
connection to other cybersecurity standards (e.g. SBOM). If you have insights
to share, we encourage you to submit a presentation proposal!

{{< /block-with-background >}}

### Event Location & Hybrid Format

The CSAF Community Days {{ .Name }} will be held as a hybrid event, allowing
participants to join either in person or virtually. The event will take place
on **`November 14-15, {{.Name }}`** in **`Nürnberg, Germany`**.

We look forward to welcoming attendees both on-site and online for an engaging
and collaborative experience.

_Note: Some parts, e.g. the walk up live review of CSAFs, will only be
available in person._

### Submission Guidelines

{{< paragraph-accent >}}

- Presentation Duration: 20-45 minutes, including Q&A.
- Presentation Format:
  - Tool Demo (Open Source preferred)
  - Presentation
  - Panel
- Submissions should include the title, a brief abstract (150-300 words),
  suggested length (20, 30 or 45 minutes) and a short bio of the presenter.

{{< /paragraph-accent >}}

### How to Submit

Please submit your presentation proposal by clicking on the link below:

{{< register-button email="cfp@csaf.io" text="Submit Your Proposal" >}}

### Important Dates

- Submission Deadline: `{{ .Name }}-09-28T23:59:59-12:00`
- Notification of Acceptance: `October 17, {{ .Name }}`
- Event Dates: `November 14-15, {{ .Name }}`

### Contact Information

If you have any questions, feel free to reach out to us at
[csaf@bsi.bund.de](mailto:csaf@bsi.bund.de).
