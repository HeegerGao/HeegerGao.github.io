# Profile photos — "Refresh to see a different Chongkai"

Every image in this folder is shown on the homepage when a visitor clicks the
**Refresh to see a different Chongkai** button under the profile photo.

## Adding a photo

Upload the image to this folder (`imgs/profile/`) and push — nothing else to
edit. The homepage lists this folder through the GitHub API, so a new photo
shows up within about ten minutes of the upload (the list is cached in each
visitor's browser for ten minutes).

- Formats: `.jpg`, `.jpeg`, `.png`, `.webp`, `.gif`, `.avif`. Any file name works.
- Shape: portrait, about **2 : 3** (for example 1200 × 1800 px). The frame keeps
  the shape of the default photo, so other shapes are centre-cropped to fit.
- Size: keep each file under roughly 500 KB so the swap feels instant.

## How it behaves

- The page always opens on the default photo, `imgs/yuweishijpg.jpg`. To change
  the default, edit the `src` of `<img id="profile-img">` in `index.html`.
- Each click shows another photo from this folder in random order, without
  repeats until all of them have been seen, then comes back to the default.
- The button is hidden while this folder has no photos.
- To remove a photo, delete the file from this folder.

## Notes

- Previewing `index.html` on your own computer shows the photos that are
  already pushed to GitHub, not the ones that only exist locally.
- The folder is listed from the repository `HeegerGao/HeegerGao.github.io`. If
  the repository or this folder is renamed, update `REPO` / `PHOTO_DIR` near the
  bottom of `index.html`.
- If the GitHub API cannot be reached (offline, or the visitor's network has
  used up GitHub's hourly limit), the page falls back to the last list that
  browser saw; with no saved list, the button stays hidden. To make particular
  photos work without the API, add their paths to `EXTRA_PHOTOS` in
  `index.html`.
