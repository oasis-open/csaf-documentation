---
title: '{{ replace .Name "-" " " | title }}'
subtitle: ''
weight: 1
type: 'event'
draft: true

params:
  event:
    dates: ''
    location_long: ''
    location_short: ''
    year: {{ replace .Name "-" " " | title }}
  render:
    lists:
      display_in_lists: true
      display_on_top: true
    images:
      preview: ''
      header: ''
---
`Note:`

`This message is only for editors. Delete this block before publishing the page.`

` To learn how to customize and style an event page, please see the instructions in the README file: `
https://github.com/csaf-auxiliary/csaf-website-relaunch#add-a-page-for-the-event
