# Learn GitHub Actions

A minimal static HTML site used to learn GitHub Actions hands-on.

## What's here

- `index.html`, `style.css` — the site.
- `.github/workflows/01-hello.yml` — runs on every push/PR, prints info, shows a job matrix. Start here to see logs in the **Actions** tab without needing anything else set up.
- `.github/workflows/02-deploy-pages.yml` — builds and deploys the site to GitHub Pages whenever you push to `main`.

## Setup

1. Create a new GitHub repo (public or private) and push this folder to it:
   ```
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. Open the repo on GitHub → **Actions** tab. You should see `01 - Hello Actions` run automatically.
3. To enable Pages deployment: repo **Settings → Pages → Source → GitHub Actions**. Push again (or re-run `02 - Deploy to GitHub Pages` from the Actions tab) and it will publish the site to `https://<you>.github.io/<repo>/`.

## Suggested learning path

1. Watch `01-hello.yml` run and read the logs for each step.
2. Edit a step (change the echo text, add a new `run:` line), push, watch it re-run.
3. Try `workflow_dispatch`: go to Actions → 01 - Hello Actions → **Run workflow** to trigger it manually.
4. Break something on purpose (e.g. typo a command) to see a failed run and how to read the error.
5. Once comfortable, look at `02-deploy-pages.yml` and see how `needs:` chains the `build` and `deploy` jobs, and how `permissions:` grants just enough access to publish.
6. Ideas to extend: add an HTML linter step, add a job that only runs on pull requests, add a `schedule:` trigger.
