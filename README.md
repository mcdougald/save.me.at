<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/hero-dark.png">
    <img src=".github/assets/hero.png" alt="save.me.at landing page" width="880">
  </picture>
</p>

<h1 align="center">save.me.at</h1>

<p align="center"><strong>Save the page, not just the link.</strong></p>

<p align="center">
  <img src="https://img.shields.io/badge/status-in%20development-171717?style=flat-square" alt="Status: in development">
  <img src="https://img.shields.io/badge/license-source--available-404040?style=flat-square" alt="License: source-available">
  <img src="https://img.shields.io/badge/self--host-supported-525252?style=flat-square" alt="Self-host: supported">
  <img src="https://img.shields.io/badge/part%20of-me.at-737373?style=flat-square" alt="Part of me.at">
</p>

<p align="center">
  <a href="#features">Features</a> ·
  <a href="#how-it-works">How it works</a> ·
  <a href="#built-with">Built with</a>
</p>

A bookmark is only as good as the site it points at, and sites go away. I built save.me.at so a dead link is not a lost page: bookmarks and read-later, designed to keep a readable copy of everything you save. Everything you save gets tags, collections and full-text search, an hourly sweep tells you which links stopped answering, and the whole library exports as readable files whenever you want to leave.

> **Status:** in development. Saving, the library, search and export work today. The archiver that makes the readable copy is written and tested, but it does not run yet when a page is saved.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/overview-dark.svg">
    <img src=".github/assets/overview.svg" alt="save.me.at at a glance: save from anywhere, find it again, one page one bookmark, know when links die" width="880">
  </picture>
</p>

## Why save.me.at

| The usual bookmark manager | save.me.at |
| --- | --- |
| A flat list of links | A library with tags, collections and full-text search |
| A dead link fails silently | An hourly sweep marks links that stopped answering |
| Tracking parameters make duplicates | URLs are normalized, so one page is one bookmark |
| Hard to get your data out | Everything exports as an archive of readable files |

## Features

- **Save from anywhere**: a bookmarklet, a Manifest V3 browser extension, or a REST API with personal tokens (stored only as hashes).
- **A searchable library**: every bookmark with its tags, read state and a dead-link mark, with full-text search and tag or unread filters.
- **One page, one bookmark**: URLs are normalized before they are stored, so tracking parameters do not create duplicates.
- **Guarded fetching**: every fetch is checked against private network addresses and redirects that try to reach them, tested against a corpus of hostile URLs.
- **Dead-link sweep**: an hourly sweep re-checks saved URLs and marks the ones that no longer answer.
- **Collections**: nested collections, private by default, with optional public sharing of links, titles and descriptions.
- **Import and export**: everything saved comes out as an archive of readable files.
- **Readable copies (in progress)**: extraction, sanitizing and a pooled headless-browser renderer, served from object storage through signed URLs.

## How it works

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset=".github/assets/flow-dark.svg">
    <img src=".github/assets/flow.svg" alt="How save.me.at works: save, normalize, guard, index, sweep" width="880">
  </picture>
</p>

A save arrives from the bookmarklet, the extension or the API, and its URL is normalized so the same page never becomes two bookmarks. The page's details are fetched through a guard that refuses private network addresses, then the bookmark joins the full-text index. Every hour a sweep re-checks saved URLs and marks the dead ones.

## Built with

<p>
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 16">
  <img src="https://img.shields.io/badge/React-19-171717?style=flat-square&logo=react&logoColor=white" alt="React 19">
  <img src="https://img.shields.io/badge/TypeScript-5-262626?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript">
  <img src="https://img.shields.io/badge/Tailwind%20CSS-4-404040?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS 4">
  <img src="https://img.shields.io/badge/Drizzle-Postgres-525252?style=flat-square&logo=drizzle&logoColor=white" alt="Drizzle ORM and Postgres">
  <img src="https://img.shields.io/badge/S3-object%20storage-737373?style=flat-square&logo=amazons3&logoColor=white" alt="S3-compatible object storage">
</p>

- Next.js 16 (App Router) and React 19
- TypeScript
- Tailwind CSS 4
- Drizzle ORM and Postgres full-text search
- S3-compatible object storage for archived copies
- A shared headless-browser render pool
- Better Auth (shared me.at account)

## Part of the me.at family

save.me.at is one of my [`*.me.at`](https://me.at) apps. They share one design system, account, and app shell. Development happens in a private monorepo; this repository is the project's public-facing home.

## License

Source-available. See [LICENSE](LICENSE).
