# Jaworski Astrophotography

A complete static portfolio for Jackson Jaworski, based in Auburn, Alabama. The site contains 16 photographs, four main pages, and a dedicated field-notes page for every photograph. It uses HTML, CSS, and a small optional JavaScript enhancement. No installation, build, database, or external font service is required. All photographs and navigation remain available with JavaScript disabled.

## Directory guide

| Path | Purpose |
| --- | --- |
| `index.html` | Editorial homepage with M81/M82, Featured Work, Selected Portfolio, and early experiments |
| `portfolio.html` | Complete collection grouped by subject |
| `equipment.html` | Equipment descriptions and manufacturer source links |
| `about.html` | Personal story and email contact |
| `work/*.html` | 16 individual photograph pages, including technical field notes |
| `css/styles.css` | Shared colors, typography, layouts, and responsive rules |
| `js/main.js` | Keyboard focus enhancement for in-page links |
| `images/portfolio/*.jpg` | Full-pixel-dimension, high-quality browser-ready photographs |
| `images/thumbnails/*.jpg` | Responsive versions, up to 480 and 960 pixels wide |
| `images/favicon.svg` | Simple initial favicon |
| `image-metadata.json` | Reference inventory, original filenames, and metadata |
| `.nojekyll` | Tells GitHub Pages to serve the static files without Jekyll processing |

## Preview locally

Extract the ZIP and open `jaworski-astrophotography/index.html` in your browser. The site also works directly from your filesystem.

For an HTTP preview, open a terminal in the extracted `jaworski-astrophotography` folder and run:

```sh
python3 -m http.server 8000
```

On Windows, use `py -m http.server 8000` if needed. Visit `http://localhost:8000`. Stop the preview with Ctrl+C. Python is only an optional preview server, never a deployment dependency.

## Deploy to GitHub Pages

1. Upload the **contents** of `jaworski-astrophotography` to your chosen repository. `index.html` should be directly in the repository root, not inside an extra wrapper folder. Include `.nojekyll`.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the branch containing the files, normally `main`, and the `/(root)` folder. Save.
5. When GitHub finishes deployment, open the address shown in Pages settings.

All site paths are relative, so the same files support both a user site and a project site under `/repository-name/`. No custom domain or workflow file is required. These steps follow [GitHub’s publishing-source instructions](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

Nothing was published and no GitHub repository was created or modified during preparation.

## Edit content

The HTML is the authoritative **displayed** content; edit it directly and refresh. There is no generation step.

- Change the story and contact address in `about.html`.
- Change homepage selections, introductions, or captions in `index.html`.
- Change equipment descriptions in `equipment.html`.
- Change a photograph’s title, description, observation, equipment, or acquisition fields in its `work/<name>.html` file. Each metadata row is a `dt` label followed by a `dd` value.
- If changing a title or date, also update its card in `portfolio.html` and, if featured, `index.html`.
- `image-metadata.json` is a useful inventory/reference copy, not a runtime data feed. Keep it synchronized for your records; editing JSON alone does not update the pages.
- Header and footer HTML are intentionally repeated so every page works without JavaScript or a template build. For global navigation changes, edit all 20 HTML files. Styles are shared in one CSS file.

Unknown values are explicitly `TBD`. Replace only those you can verify from your own acquisition records.

## Add a photograph

1. Export a high-quality sRGB JPEG, without cropping or upscaling, to `images/portfolio/your-target.jpg`. Keep the original master separately.
2. Export smaller copies to `images/thumbnails/your-target-480.jpg` and `your-target-960.jpg`, with maximum widths of 480 and 960 pixels. Do not upscale an image smaller than those widths.
3. Duplicate a comparable page in `work/`. Rename it `your-target.html` and edit its page title, description, heading, image references, alt text, date, and metadata. Keep unverified values as `TBD`.
4. Update `width` and `height` to the full image’s actual dimensions. Update each `srcset` width to the actual width of that variant. If the source is less than 960 pixels wide, omit the redundant full-size `srcset` entry or use only distinct widths.
5. Copy one `article class="photo-card"` into the relevant section of `portfolio.html`; update its link, image sources, dimensions, alt text, caption, date, and section image count.
6. Optionally add its card to the homepage. The homepage is intentionally selective.
7. Update the Previous/Next links in adjacent detail pages if you want the new page included in that sequence. Add a matching inventory record to `image-metadata.json`.
8. Preview at desktop, tablet, and phone widths and check the full-resolution link before uploading changed files.

The existing detail pages serve as working templates; no unfinished public template page is included.

## Design and image treatment

The charcoal background, Georgia serif headings, restrained sans-serif labels, warm gold accents, asymmetric homepage, and secondary early-work rows follow Reference A. Reference B informs only the structured field notes. No fictional mockup quotations or equipment were used.

All 16 source photographs were opened and reviewed in a contact sheet. TIFF/PNG/JPEG inputs were exported as high-quality JPEGs at their original pixel dimensions, with smaller responsive copies. Embedded color profiles were converted to sRGB where present; transparency was composited onto black. No sharpening, artistic retouching, target cropping, or enlargement was applied. Gallery frames use `object-fit: contain` to preserve the entire composition. Original TIFF/PNG/JPEG masters remain in your supplied `Images.zip`; keep that archive as your master backup. They are not duplicated in this deployment folder.

The timelapse is excluded. The spelling `Dumbbbell` in the original filename is mapped to `dumbbell-nebula` in the website filenames.

## Review before deployment

- **Dates:** The first Moon source is dated May 26, 2021, which precedes the stated July 29, 2021 start of astrophotography. Both supplied facts are preserved. Confirm whether you want either revised.
- **Eclipse date:** The source is named `21-11-29_Lunar-Eclipse.png`. November 29, 2021 is preserved from the filename; confirm this against your records.
- **Unknown acquisition:** Exposure duration/count, total integration, ISO, calibration frames, and processing remain `TBD` on every photograph. Exact field flatteners also remain `TBD`.
- **Equipment mapping:** The eight identified later-setup photographs list the T3i, EvoGuide 50ED, and Star Adventurer 2i. Confirm those per-image associations before replacing further configuration details. The seven early experiments and Polaris trails use the T3i and 18–55 mm lens as instructed. The eclipse’s optics and tracking remain `TBD` because its exact setup was not provided.
- **Locations/targets:** Only explicitly supplied per-image locations are assigned. Other locations and unidentified early star-field targets remain `TBD`.
- **Equipment specifications:** Camera and tracker specifications link to Canon and Sky-Watcher. The optical specifications link to Sky-Watcher’s current EvoGuide listing (50DX branding); the site retains your supplied 50ED equipment name. Lens variants and flattener spacing have not been guessed.
- **Contact:** Verify the public email address `jmjaws1215@gmail.com`.

## Verification status

Passed: 20 HTML entrypoints; all local navigation, image, stylesheet, script, full-resolution, and `srcset` references; in-page anchors; one H1 per page; requested navigation order; alt text and image dimensions; JavaScript syntax; acquisition `TBD` checks; serving every file through a local HTTP server under a repository-style subpath.

Responsive CSS includes desktop, tablet, and phone layouts, but **browser visual verification remains outstanding**. The available browser preview connection was refused, so desktop/tablet/phone screenshots, visual overflow checks, and interactive keyboard testing could not be completed. Before deployment, use your browser’s responsive view at roughly 1440, 768, and 390 pixels, plus 200% zoom. Check the homepage, Portfolio, Equipment, About, and at least one detail page. Confirm all four navigation links and the email/full-resolution links work. This is a testing limitation, not a required site dependency.
