# Changing the highlighted link

When a page should be promoted to the site visitors (for example new event),
a banner can be added on the top of the site page right below the navigation bar.

To add, change or remove the banner, change the data in
[/data/navbarHighlightedLink.json](/data/navbarHighlightedLink.json).

## Add or change banner

Add both `url` and `text` attributes and set `visible` to `true`.

If banner **should not be shown on some pages**, list their relative paths
in the `exclude`.

Example:

```json
{
  "visible": true,
  "url": "/community-days/2025/",
  "text": "Submit your presentation for Community Days 2025.",
  "exclude": ["/events/", "/workshops/", "/community-days/"]
}
```

If banner should be **visible on all the pages**, set `exclude`
to an empty list:

```json
{
  ...
  "exclude": []
}
```

## Remove banner

To hide banner **from all the pages** set `visible` to `false`.

Example:

```json
{
  "visible": false,
  ...
}
```
