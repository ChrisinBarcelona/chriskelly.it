# CKLY: Design Language

Derived from the Figma file "CKLY" (Portfolio page, 1728px desktop frames). Where this file and a tool's default disagree, this file wins.

## Thesis

Black page, white light-weight type, no color. The only drama is scale: small working text at 16px against a hero shouted at ~99–128px. Nothing sits in between except 32px for list and label text.

## Principles

1. **Monochrome.** `#000` and `#fff`. The client's work supplies all color. Never add an accent.
2. **One weight.** Neue Haas Grotesk 45 Light everywhere. Emphasis comes from scale, a single italic word, or one Medium (65) menu, never from bold body text.
3. **Whisper or shout.** Two registers: 16px and 99px+. 32px is for things you read in a list. Do not invent 20, 24 or 48.
4. **Hairlines, not boxes.** 1px white rules separate content. The only enclosed shape is the pill tag.
5. **Typographic punctuation is the UI.** Arrows (→), parentheses `(WE)`, abbreviations (BE, IG, GM). Not icons, not buttons.
6. **A 32px frame.** Nav, headings and footers sit on a 32px inset. Big content floats free in the middle.
7. **Say it like a studio.** Declarative, confident, short. "We" voice. No filler.

## Tokens

```css
:root {
  --black: #000000;
  --white: #ffffff;
  --mark:  #d9d9d9; /* menu icon only */

  --font-display: "Neue Haas Grotesk Display Pro", "Helvetica Neue", Helvetica, Arial, sans-serif;
  --font-mono:    "Atkinson Hyperlegible Mono", ui-monospace, monospace;

  --fw-light: 300;  /* 45 Light */
  --fw-medium: 500; /* 65 Medium, hero menu only */

  --text-sm: 16px;      /* nav, body, tags, footer */
  --text-md: 32px;      /* section titles, skills, project names, address */
  --text-hero: 98.88px; /* hero lines, uppercase */
  --text-cta: 128px;    /* "Let's talk" */
  --text-mono: 28.8px;  /* "(WE)" aside, mono, 0.29 of hero */

  --lh-body: 21px;      /* 16px body copy */
  --lh-display: normal;
  --hero-overlap: -13px;/* hero lines stack tight, negative bottom margin */

  --space-frame: 32px;  /* page inset and column gutter */
  --space-rule-y: 7px;  /* padding above/below text in ruled rows */
  --space-row: 2px;     /* gap between ruled rows */

  --rule: 1px solid var(--white);
  --pill: 1px solid var(--white); /* radius 9999px, padding 8px */
}
```

## Type roles

| Role | Face | Size | Notes |
|---|---|---|---|
| Hero | Display 45 Light, uppercase | 98.88 | One line per row, tight overlap. One word in 46 Light Italic ("IMPOSSIBLE"). |
| Hero aside | Atkinson Hyperlegible Mono | 28.8 | Sits on the first line baseline: `(WE)`. |
| CTA | Display 45 Light, sentence case | 128 | "Let's talk" |
| Section title / list | Display 45 Light | 32 | "Projects", "What we do", skills, project names |
| Body / UI | Display 45 Light | 16 / 21 | Nav, copy, tags, footer |
| Hero menu | Display 65 Medium | 16 | `→ Projects`, `→ Skills`, `→ Contact` |

Hero tracking in the file is inconsistent (2.97px on "BUILD BRAND" and "IMPOSSIBLE", 0.48px on "IDENTITIES", none on the rest). Pick one value: **+3% on all hero lines**, or none.

## Layout

- Desktop frame 1728 wide, black, one section per screen (~1117 tall).
- Nav row: `CKLY Studio` left, links centred, a plus mark right. 32px padding.
- Hero block is centred horizontally and vertically, about 719 wide.
- Two-column content uses 531.5px columns with a 32px gutter.
- Projects: one project per 954px band. Text column left (228px wide), image on the right half (832px).
- Footer row: socials left with 60px gaps, `Studio` right.

## Components

- **Pill tag**: 1px white border, fully rounded, 8px padding, 16px text.
- **Ruled row**: 32px text, 1px white bottom rule, 7px vertical padding, 2px between rows.
- **Arrow link**: `→ Label`, 16px Medium.

## Voice

- Headline: "(WE) BUILD BRAND IDENTITIES THAT MAKE YOU IMPOSSIBLE TO IGNORE"
- Section prompts: "What we do", "Got a project in mind?" / "Let's talk"
- Skills: Web Development, Web Design, UI / UX, Strategy, Branding, Art Direction, Packaging, Illustration

## Open decisions (the Figma does not answer these)

1. **Studio or person?** Copy says "CKLY Studio" and "we", the domain is chriskelly.it, the email is studio@ckly.studio. Pick one identity and use it everywhere.
2. **Nav labels disagree.** Top nav: Home, Project, Skills, Call. Hero menu: Projects, Skills, Contact. Contact section: Contact. Choose one set. Suggested: Projects, Skills, Contact.
3. **Font licence.** Neue Haas Grotesk Display Pro is a paid web font (Adobe Fonts or Monotype). Atkinson Hyperlegible Mono is free on Google Fonts.
4. **Not designed yet:** mobile and tablet, hover/focus states, motion, project images (frames are empty), project detail pages, an About section, real project copy (currently lorem ipsum).
5. **Social links** are two-letter codes (BE, IG, GM). Confirm GM, and add accessible labels in code.
