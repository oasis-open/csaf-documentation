# Changing the highlighted link

When a page should be promoted to the site visitors (for example new event),
a banner can be added on the homa page right below the navigation bar.

To add, change or remove the banner, open [/content/\_index.md](/content/_index.md)
and change the data in the front matter (upper section of the file between
the lines of `---` symbols).

## Add or change banner

Add both url and text attributes of params.highlighted_page:

```yml
---
...
params:
  highlighted_page:
    url: '/events/community-days/2025/'
    text: 'Submit your presentation for Community Days 2025.'
---
```

**Note:** the banner is displayed only when both attributes are prsent
and are not empty (not '').

## Remove banner

Change url and text to empty strings:

```yml
---
...
params:
  highlighted_page:
    url: ''
    text: ''
---
```
