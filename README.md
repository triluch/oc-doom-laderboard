# OpenCentauri Doom Leaderboard

Speedrun leaderboard for Doom running on the Elegoo Centauri Carbon.
Hosted at: [triluch.github.io/oc-doom-laderboard](https://triluch.github.io/oc-doom-laderboard)

## Categories

- **[CentauriCarbonAny%](https://triluch.github.io/oc-doom-laderboard/categories/centauri-carbon-any)** — any%, no restrictions
- **[CentauriCarbonTouchAny%](https://triluch.github.io/oc-doom-laderboard/categories/centauri-carbon-touch-any)** — any%, touch controls only

## Submitting a run

1. Fork this repo and edit `csv/runs.csv` — add a row at the end:

   | field | description |
   |---|---|
   | `tk_run_id` | unique slug used in the URL, e.g. `yourname-any-2026-04-01` |
   | `tk_run_runner` | your name |
   | `tk_run_verifier` | who verified the run |
   | `tk_run_duration` | time in `H:MM:SS` format |
   | `tk_run_category_dashname` | `centauri-carbon-any` or `centauri-carbon-touch-any` |
   | `tk_run_date` | date of the run, e.g. `2026-04-01` |
   | `tk_run_description` | short description / notes (can be empty) |
   | `tk_run_link` | link to video proof (YouTube or Streamable) |

2. Open a PR — the site regenerates and deploys automatically on merge.

The leaderboard sorts by time and keeps only the fastest run per runner per category.

---

## paceboard — original readme

# paceboard

![Project logo, a sine wave forming gravestones in the negative space.](assets/img/logo.png)

[Blog post](https://info.pace.rip/blog/2021/6/29/) - [Example site](https://info.pace.rip/blog/2021/6/29/paceboard/)

## About

**paceboard** is a template-based static site generator for speedrun leaderboards.

You can configure site details, implement categories, and add runs all from a single Python script (`paceboard.py`).

Category and run information is stored in `csv` files for ease of access and editing.

## Instructions

This guide assumes that you know the basics of hosting your own website. Since paceboard is a *static* site generator, you can host via the free [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages), assuming you know how to use [Git](https://git-scm.com/video/get-going).

Let's get started!

1. Make sure you have the latest version of [Python 3](https://wiki.python.org/moin/BeginnersGuide/Download).
2. [Download](https://github.com/PaceRIP/paceboard/archive/refs/heads/master.zip) or [fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) the paceboard repository.
3. Go to your install location via the command line, then run `python3 paceboard.py`. Follow the prompts to configure and auto-generate your site!
4. Discover you made a typo? Hop into the `csv` folder and you can manually edit the spreadsheets inside. Afterwards, running `python3 scripts/generate.py` will update your site with the new info.

## Template-based?

Within the `templates` folder are the [HTML](https://www.w3schools.com/html/html_intro.asp) files paceboard uses to format the site. If you're feeling intrepid, you can edit these templates to your liking.

During page generation, paceboard swaps out the `tk_` and `lk_` strings with their corresponding values in the database.
