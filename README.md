# PodClip website

A static GitHub Pages site for PodClip (`index.html` plus `assets/`). No build step.

## Publishing (its own repo)

1. Create a new GitHub repo for the site and copy the contents of this folder into its root (including `.nojekyll`).
2. Repo **Settings ▸ Pages ▸ Build and deployment**: Source **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. The site appears at `https://<user>.github.io/<repo>/`.

## The download link

Every **Download** button points at `DOWNLOAD_URL`, defined once in the `<script>` at the bottom of `index.html`.
Set it to your releases page, for example `https://github.com/<user>/<repo>/releases/latest`.
The repo that hosts the release must be public for the link to work for everyone.

## Making a release zip

```bash
./scripts/build.sh
ditto -c -k --keepParent build/PodClip.app build/PodClip.zip
```

Upload `build/PodClip.zip` as an asset on a GitHub Release. The app is ad-hoc signed, not notarized, so the install
steps on the page tell people to use **Open Anyway** in Privacy & Security.

## Screenshots

They show a made-up demo episode ("Backyard Radio"), not real show content. To retake them, open a demo episode with
`open --env PODCLIP_OPEN=/path/to/episode build/PodClip.app` and capture the window.
