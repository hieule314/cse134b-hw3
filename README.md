| Field               | Value                                                                                |
| :------------------ | :----------------------------------------------------------------------------------- |
| Repository URL      | [https://github.com/hieule314/cse134b-hw3](https://github.com/hieule314/cse134b-hw3) |
| Part 1 Deployed URL | https://hieule-cse134b-hw3.netlify.app/part1/cheese.html                             |
| Part 2 Deployed URL | https://hieule-cse134b-hw3.netlify.app/                                              |

# CSE 134B — Homework 3

Hieu Le's personal portfolio, styled with hand-authored CSS. The portfolio
extends the four HTML pages from Homework 2. The cheese exercise is in `part1/`.
There are no scripts, frameworks, or build dependencies.

## Design

Warm cream, dark brown, and forest green connect the pages. Pixel headings,
square frames, and CSS illustrations reflect my interest in games. Body text
uses a readable system font stack. My own photos appear on Home and About;
smaller copies in `assets/images/optimized/` load in place of the originals.

The shared `styles.css` includes design variables on `:root`, Grid and Flexbox,
a narrow-screen layout at `48rem`, and comments explaining attribute and
combinator selectors. Buttons use `em` padding; font sizes use `rem`.

Entrance and hover animations use CSS only. Reduced-motion preferences disable
entrance animation, animated scrolling, and movement on hover. All essential
text, navigation, and links remain in the HTML.

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

- Checked Home, About, Projects, and Experiments in Chrome at 375px and 1280px.
  No page-wide horizontal scrolling was observed.
- Checked all four pages at 375px with the author stylesheet removed. Navigation,
  content, images, and native controls remained available in reading order.
- Used Tab through the shared navigation and sample form; focus outlines were
  visible. Opened the native dialog, closed it with Escape, and expanded the
  disclosure with the keyboard.
- Checked local file references and fragment links for missing targets, duplicate
  IDs, unbalanced tags, scripts, inline styles, and embedded style blocks.

These checks cover the local files. After pushing to GitHub, confirm that the
Netlify deployment serves the same version before submitting.

## Asset credits

- Personal photographs supplied by Hieu Le; originals are retained.
- [Pixelify Sans](https://github.com/google/fonts/tree/main/ofl/pixelifysans)
  is served locally, with its SIL Open Font License in `assets/fonts/OFL.txt`.
- The original HW2 sample video comes from
  [MDN's video example](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/video).
  The sample tone and favicon were also copied from the existing HW2 assets.
