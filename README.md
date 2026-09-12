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

## ⚠️ Placeholders that still need replacing

All image and PDF assets are real. What's left is links.

### Missing links (currently `href="#"`)
| Where | What's needed |
|---|---|
| Hero social icon | LinkedIn URL |
| Contact card | LinkedIn URL |
| Footer social icon | LinkedIn URL |
| DataFest project | Repo / writeup link (button says "Coming Soon") |
| RAG Chatbot project | Repo / demo link (button says "Coming Soon") |

```bash
grep -n "LINK PLACEHOLDER" index.html
```

### Notes on the resume PDF
`assets/resume/Taha-Disbudak-Resume.pdf` is publicly downloadable once deployed.
It still lists MEGA Insulation Solutions, which was removed from the site, and it
contains a phone number. Replace the file to change either.

### Source images
Originals live in `PicturesForTheWebsite/` and are gitignored. Processed versions
in `assets/` were cropped and downscaled from them.

## Deploy

Pushing to `main` publishes automatically via GitHub Pages.
