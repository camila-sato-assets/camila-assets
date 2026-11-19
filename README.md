# camila-assets

Public, direct-download image host for [@camilasato.fit](https://www.instagram.com/camilasato.fit/) feed posts.

Scheduling tools (Buffer and similar) fetch these files by HTTPS URL. Images are AI-generated. Do not treat this repository as a website or a place to discuss the account.

## URL pattern

```
https://raw.githubusercontent.com/pliniomartos/camila-assets/main/instagram/<version>/<filename>
```

Example:

```
https://raw.githubusercontent.com/pliniomartos/camila-assets/main/instagram/v4/post-06-white-drape.png
```

If GitHub Pages is enabled on this repo, the same path also works at:

```
https://pliniomartos.github.io/camila-assets/instagram/<version>/<filename>
```

## Layout

- `instagram/v4/` — 4:5 Instagram feed images from the v4 batch (unsent posts 06–12 at first publish).
- Future batches go in a new folder, for example `instagram/v5/`. Keep the 4:5 post file (not the `-3x4` master).

## Add a new image

From a machine with `gh` authenticated as `pliniomartos` and this repo cloned:

```bash
git clone https://github.com/pliniomartos/camila-assets.git
cd camila-assets
cp /path/to/post-13-example.png instagram/v4/post-13-example.png
git add instagram/v4/post-13-example.png
git commit -m "Add instagram/v4/post-13-example.png"
git push origin main
```

Then confirm the file is fetchable:

```bash
curl -sI "https://raw.githubusercontent.com/pliniomartos/camila-assets/main/instagram/v4/post-13-example.png"
```

Expect HTTP 200 and a `content-type` of `image/png`.
