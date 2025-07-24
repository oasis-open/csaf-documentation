# Adding a new Tool

If you want to add a new CSAF tool,
open [/content/tools.md](/content/tools.md) with the text editor.

Add a section with markdown as content like in this example
(place information about the tool in markdown
between `{{% card %}}` and `{{% /card %}}`):

```markdown
{{% card %}}
### [CSAF Downloader](https://github.com/gocsaf/csaf/blob/main/docs/csaf_downloader.md)
A tool to download CSAF content from a specific domain / CSAF provider.<br>
{{% /card %}}
```

Then open a pull request to the main branch of this repository
as suggested by [Github](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request).