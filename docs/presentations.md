# Add a link to a new Presentation Video

If you want to add a presentation, there is more work for privacy reasons:

Using a YouTube video cover (a static image with a link)
instead of embedding the video
prevents YouTube from automatically loading tracking scripts, cookies,
and third-party requests when a visitor opens the page.

This ensures that no user data is sent to Google (YouTube's parent company)
until the user explicitly clicks on the link to watch the video.

Follow these steps to **add new presentation**
(in all the steps insert the id of the video instead of the `<video-id>`):

1. Open the [data/presentations.json](/data/presentations.json) file,
   and insert a new block like this:

```
    ,
    {
        "link": <video-id>
    }
```

2. Make a screenshot of the video or get a custom video cover.
Name the file in the format `<video-id>.jpg`.

3. Add the file to the
   [static/youtube_covers/](/static/youtube_covers/) folder.

4. In the same folder create a file with the name `<video-id>.jpg.license`
   and provide the licensing information in this format:

```
SPDX-License-Identifier: LicenseRef-YouTube-Standard-License
SPDX-FileCopyrightText: <channel-name-and-link>
```

Example:
```
SPDX-License-Identifier: LicenseRef-YouTube-Standard-License
SPDX-FileCopyrightText: FIRST <https://www.youtube.com/channel/UCK3_z6YyWvfqrOuCmrfxsTw>
```

Replace `<video-id>` and `<channel-name-and-link>` with the actual ones.

5. Open a pull request.
