# henrychung98.github.io

Jekyll site served at the domain root: <https://henrychung98.github.io>

| URL | Source file |
| --- | --- |
| `/` | `index.md` (auto-lists every app) |
| `/ex-rate/` | `_apps/ex-rate.md` (auto-lists that app's pages) |
| `/ex-rate/policy/` | `_apps/ex-rate/policy.md` |
| `/ex-rate/support/` | `_apps/ex-rate/support.md` |
| `/app-ads.txt` | `app-ads.txt` — AdMob verification, do not move or rename |

## Adding a new app

Nothing else needs editing — both lists are generated from the files.

1. Create the landing page `_apps/<app-slug>.md`:

   ```yaml
   ---
   layout: app                       # this flag is what puts it on the home page
   title: My App
   description: One line shown under the name.
   ---
   ```

2. Create its pages in `_apps/<app-slug>/`, e.g. `policy.md` and `support.md`:

   ```yaml
   ---
   title: "My App Privacy Policy"    # the <h1> and browser tab title
   nav_title: Privacy Policy         # the link text on the app page
   order: 1                          # link order on the app page
   updated: 2026-09-22               # optional, shows "Last updated: ..."
   ---
   ```

   The `layout: page` default comes from `_config.yml`, so sub-pages don't set one.

Permalinks come from `permalink: /:path/` on the `apps` collection, so the folder
layout under `_apps/` *is* the URL structure.

## Deployment

GitHub Pages builds this automatically from the **`main`** branch
(Settings → Pages → *Deploy from a branch* → `main` / `/` root). There is no
Actions workflow — pushing to `main` is the deploy.

## Local preview

```sh
bundle install
bundle exec jekyll serve
```
