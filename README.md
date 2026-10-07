# Career Radar

A self-updating job radar that filters thousands of listings down to the APM, internship and new grad roles a May 2027 graduate can actually apply to, and alerts me the moment new ones drop.

**[Open the live demo →](https://yeseniananneliza.github.io/Career-Radar/)**

![Career Radar dashboard](screenshot.png)

## The problem

APM programs open for a few weeks a year, and many entry-level PM roles never use the word "APM." Job boards show thousands of listings, most of which a student can't apply to: senior roles, Master's-only roles, internships for terms that have already passed. By the time I found the right roles, the best windows were already closing.

Existing trackers each solved part of the problem. One listed named programs, another tracked internship drops, another covered new grad roles. None filtered by my graduation date, and none told me when something new appeared.

## How it works

The live version is a Python script that runs on my laptop. Every 15 minutes it:

1. **Pulls public job feeds** for new grad roles and internships.
2. **Filters by level.** It drops senior, manager-level, Master's-only and PhD roles, and anything outside the US.
3. **Filters by timing.** Internships have to fall between Winter 2026 and Summer 2027, and postings older than 60 days age out.
4. **Filters by field.** It keeps product, APM-style, and data and analytics roles.
5. **Tags hidden APMs.** A title-pattern tagger catches APM-style roles posted under other names, like "Product Manager-in-Training."
6. **Rebuilds the dashboard** and sends a desktop alert when a new eligible product role appears.

In the snapshot used for this demo, that process narrowed **7,686 listings to 535 eligible roles**, and the tagger caught **99 APM-style roles that never say "APM."**

## What's in the dashboard

- **APM programs:** a directory of named APM and rotational programs with their usual application windows, plus live APM-style roles.
- **Internships, new grad, and data and analytics:** separate lanes with search, filters and sorting.
- **My pipeline:** a board for tracking roles from saved to offer.
- **Insights:** roles by lane, most active companies and new postings per day.
- **How it works:** the filtering steps with real numbers from the snapshot.

## Product decisions

- **Automate only what's reliable.** Sources with structured feeds are automated. Sites without one stay as quick links instead of scrapers that would break.
- **Flag instead of drop.** Roles that don't state a start date or graduation year get a "check" tag instead of being filtered out, so nothing good disappears silently.
- **Keep alerts meaningful.** Alerts fire only for product roles. Data roles update quietly.
- **Separate strategy from action.** The program directory shows which big programs open when. The live listings show what I can apply to today.

## About this demo

This repo hosts a portfolio version of the dashboard, not the live pipeline.

- Listings are a **frozen snapshot from October 7, 2026.** Links may close over time.
- The pipeline board starts with **sample data**, not my real applications. Changes you make save only in your own browser.
- The "Simulate an alert" button shows what the desktop alert looks like.
- Program windows are approximate, based on past recruiting cycles.

## Built with

Python for the live pipeline. The demo is a single HTML file with plain JavaScript and inline SVG charts, with no frameworks or build step.

## Data sources

Listings come from the open-source [SimplifyJobs](https://github.com/SimplifyJobs) new grad and internship lists. The APM program directory is hand-curated.

## Author

**Yesenia Navarro**, Statistics (Data Science emphasis) at San Diego State University, graduating May 2027.

[Portfolio](https://yeseniananneliza.github.io) · [LinkedIn](https://www.linkedin.com/in/yeseniaanavarro) · [Email](mailto:yesenia.annelizan@gmail.com)
