| Field               | Value                                                                                |
| :------------------ | :----------------------------------------------------------------------------------- |
| Repository URL      | [https://github.com/hieule314/cse134b-hw3](https://github.com/hieule314/cse134b-hw3) |
| Part 1 Deployed URL | https://hieule-cse134b-hw3.netlify.app/part1/cheese.html                             |
| Part 2 Deployed URL | https://hieule-cse134b-hw3.netlify.app/                                              |

# CSE 134B — Homework 3

Hieu Le's personal portfolio, styled with hand-authored CSS. The portfolio
extends the four HTML pages from Homework 2. The cheese exercise is in `part1/`.
There are no scripts, frameworks, or build dependencies.

The Projects page offers a browser preview and a download of the supplied resume
at `assets/documents/hieu-le-resume.pdf`. The PDF is unchanged and only loads
when a visitor follows a resume link.

## Design

Warm cream, dark brown, and forest green connect the pages. Pixel headings,
square frames, and CSS illustrations reflect my interest in games. Body text
uses a readable system font stack. My own photos appear on Home and About;
compressed web copies in `assets/images/` keep image downloads smaller.

Images use native `<picture>`, `srcset`, and `sizes` to choose an appropriate
WebP size for the display. JPEG fallbacks remain available. All image versions
stay in the same `assets/images/` folder; a browser downloads the selected
version rather than every version. Above-the-fold portraits load eagerly;
gallery images load lazily and decode asynchronously.

The pixel font uses WOFF2 with a TrueType fallback and `font-display: swap`.
The portrait's Display P3 colors were converted to tagged sRGB for the WebP
copies. Media demonstrations use `preload="none"`; the video has explicit
dimensions to reserve its space before playback.

The shared `styles.css` includes design variables on `:root`, Grid and Flexbox,
a narrow-screen layout at `48rem`, and comments explaining attribute and
combinator selectors. Buttons use `em` padding; font sizes use `rem`.

All animation uses CSS only. Native `view()` timelines reveal sections and cards
as they enter the screen, while a clipped gradient fills readable shadow text with
ink as you scroll. These effects are feature-guarded and only run on screens
when reduced motion is not requested. Unsupported browsers, reduced-motion
preferences, and printing retain the normal visible content. Keyboard focus and
fragment navigation reveal interactive targets immediately. No per-word spans,
JavaScript, or animation libraries are needed.

The Home and About introductions use larger text to balance the portrait: `1.5rem` on
wide screens and `1.125rem` on narrow screens. Homepage project links cover
their cards, navigation and social links have larger touch targets, and skip
links move focus into the main content. Essential content stays in the HTML.

The experiments page keeps native media, dialog, disclosure, form, SVG, MathML,
custom-element, and template examples. The old JavaScript examples have been
removed. Its decorative canvas court uses CSS; the adjacent description and SVG
remain available without CSS. The inquiry form remains a disabled demonstration.

## Preview

From the repository root, run:

```sh
python3 -m http.server 8000
```

Open `http://localhost:8000/` for the portfolio or
`http://localhost:8000/part1/cheese.html` for Part 1. For Netlify, publish the
repository root with no build command. The deployed URLs above are the HW3
site; the original HW2 repository and deployment remain separate.

## Verification

- Checked Home, About, Projects, Experiments, and Cheese in Chrome at 375px and 1280px.
  No page-wide horizontal scrolling was observed.
- Checked all five pages at 375px with the author stylesheet removed. Navigation,
  content, images, and native controls remained available in reading order.
- Used Tab through the shared navigation and sample form; focus outlines were
  visible. Opened the native dialog, closed it with Escape, and expanded the
  disclosure with the keyboard.
- Verified the skip link, full-card project links, full-card keyboard focus
  outlines, and navigation targets at least 44px tall at the default font size.
- Checked local file references and fragment links for missing targets, duplicate
  IDs, unbalanced tags, scripts, inline styles, and embedded style blocks.
- Checked all five pages at 375px with the root text size enlarged to 200%.
  Navigation labels and project titles wrap without page-wide horizontal scroll.
- Checked image and font fallbacks using temporary preview copies with WebP
  sources removed and WOFF2 disabled. These copies are not part of the site.
- Checked native scroll reveals, immediate visibility on keyboard focus and
  fragment navigation, and temporary previews of reduced motion and unsupported
  scroll timelines. The fallback previews keep content fully visible.
- The Nu HTML Checker reports no HTML errors across all five pages. Its one
  structural warning is an article without its own heading in the supplied
  cheese HTML, which is preserved as required. Trailing slashes on void elements
  produce informational notices. Both stylesheets pass CSSTree validation.
- Verified both Latin terms, warning background, quotation box model, heading
  sizes, and the later button background on the Cheese page. Its checkboxes and
  text input work with CSS enabled and disabled, including keyboard focus.
- Checked resume preview and download; the downloaded PDF matches the supplied
  file byte for byte. All local asset paths, fragments, and WebP width descriptors
  resolve correctly. All 13 shared CSS variables are used.
- The scroll text's shadow layer uses 70% ink, approximately 5.09:1 against the
  cream background before the darker text reveal.

Measured asset sizes (not a network-speed benchmark):

| Asset                            |                Before |                 After |
| :------------------------------- | --------------------: | --------------------: |
| Full-size image set              | 1,839,345 bytes, JPEG | 1,045,802 bytes, WebP |
| Homepage images at 375px / DPR 1 |         689,924 bytes |          76,110 bytes |
| Pixel font                       |     79,160 bytes, TTF |   22,984 bytes, WOFF2 |

Direct browser verification used Chrome on macOS. Safari automation was
unavailable, and Firefox and other operating systems were not directly tested.
JPEG, TrueType, and generic font fallbacks preserve compatibility without scripts.

These checks cover the local files. After pushing to GitHub, confirm that the
Netlify deployment serves the same version before submitting.

Netlify's optional badge injects JavaScript into the served HTML even when the
repository has no scripts. For this assignment, turn off **Powered by Netlify
badge** under **Project configuration > General**, then confirm the served pages
contain no scripts. See [Netlify's badge settings](https://www.netlify.com/changelog/2026-08-19-pre-launch-toolbar-and-powered-by-netlify-badge/).

## Asset credits

- Personal photographs and interest images supplied by Hieu Le. Compressed web
  copies live together in `assets/images/`; larger originals are kept separately
  from the published site.
- [Pixelify Sans](https://github.com/google/fonts/tree/main/ofl/pixelifysans)
  is served locally, with its SIL Open Font License in `assets/fonts/OFL.txt`.
- The original HW2 sample video comes from
  [MDN's video example](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video).
  The sample tone and favicon were also copied from the existing HW2 assets.

Implementation references: [MDN responsive images](https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Responsive_images),
[MDN CSS view timelines](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/animation-timeline/view),
and [fontTools WOFF2 documentation](https://fonttools.readthedocs.io/en/stable/ttLib/woff2.html).
