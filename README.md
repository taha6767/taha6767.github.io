# taha6767.github.io

Personal portfolio site for **Taha Disbudak** — CS student at Pomona College.
Built on the [Dopefolio](https://github.com/rammcodes/Dopefolio) template by Ram Maheshwari (GPL-3.0).

## Local development

```bash
npm install          # once
npm run compile:scss # sass/ -> css/style.css
npm run watch:scss   # recompile on save
npm run serve        # http://localhost:8000
```

> The upstream template used `node-sass`, which is dead and cannot build on modern
> Node. This repo uses **dart-sass** instead. Same SCSS, same output.

**Always run `npm run compile:scss` after editing anything in `sass/`.**
`css/style.css` is committed because GitHub Pages serves it directly.

## Structure

```
index.html                    single page: hero, about, experience, projects, education, contact
index.js                      hamburger menu only
css/style.css                 COMPILED — do not edit by hand
sass/
  abstracts/_variables.scss   theme color lives here
  abstracts/_utilities.scss   buttons, headings, containers
  pages/_home.scss            hero + about + contact background
  pages/_experience.scss      experience rows
  pages/_projects.scss        project cards
  pages/_education.scss       education card
  components/_tags.scss       tech-stack pills + skills group labels
  components/_contact-cards.scss
assets/
  img/taha-profile.svg        PLACEHOLDER headshot
  img/logos/*.svg             PLACEHOLDER company/school logos
  resume/*.pdf                PLACEHOLDER resume
  favicon.svg
```

## Theme

`sass/abstracts/_variables.scss` — Pomona blue:

```scss
$themeClrPrimary: #0057b8;
$themeClrDark:    #023a78;
$themeClrTint:    #eef4fb;
```

Change and recompile.

## Placeholders

None. Every link on the page resolves.

The DataFest and RAG Chatbot cards intentionally have no button: neither has a
public repo or demo. If one ever does, add a `project-card__links` block to that
card, matching the Netflix card.

The 5C Halal Menu card links to the live app and its public repo under the
`5cmsa` org. It uses two images, both in `assets/img/projects/`:

- `5c-halal-menu-app.jpg` — a screenshot of the live app (dinner view, so real
  halal dishes and their provenance tags are visible). Re-capture from
  `5cmsa.github.io/5c-halal-menu/?meal=dinner` if the UI changes.
- `5c-halal-menu.png` — the app's own PWA icon (`icons/icon-512.png`), used
  both as a small mark beside the card title and as the hero shortcut chip.

The hero logo strip links to four anchors: `#td-bank`, `#halal-menu`,
`#hci-research` and `#tagsafe`. Experience rows and project cards both carry
`scroll-margin-top: 11rem` so a jump clears the fixed header.

The Netflix Content Analysis card links to the archived Quarto presentation at
`taha6767.github.io/taha6767-portfolio-old/Presentation.html`. If that repo is
ever renamed or unpublished, this link breaks — update it here.

### Note on the resume PDF
`assets/resume/Taha-Disbudak-Resume.pdf` is publicly downloadable once deployed.
It intentionally still lists MEGA Insulation Solutions, which was dropped from
the site's Experience section as a presentation choice.

### Source images
Originals live in `PicturesForTheWebsite/` and are gitignored. The versions in
`assets/` were cropped and downscaled from them.

## Deploy

Pushing to `main` publishes automatically via GitHub Pages.
