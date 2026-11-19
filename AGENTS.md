# schemware.com — agent instructions

`AGENTS.md` and `CLAUDE.md` are identical. Change both together.

## The site

Static HTML and CSS for Schemware, LLC, served by GitHub Pages from `main` at https://schemware.com. There is no build step, no framework and no Jekyll (`.nojekyll`). See `README.md` for the files and DNS.

- `index.html`: home page (hero, Sheepshead product card, About, contact).
- `sheepshead/index.html`: Five-Handed Sheepshead coming-soon page, at `/sheepshead/`.
- `styles.css`: shared styles. Colours follow the Sheepshead iOS app palette in `../../ios/sheepshead_ios/Sheepshead/Sheepshead/Assets.xcassets/Palette`; keep them in step with the app rather than inventing new ones.
- `images/`: the app icon at web sizes, favicon and Apple touch icon, resized from the iOS `AppIcon.appiconset/icon-1024.png`, and `app-store-badge.svg`: Apple's official badge from https://developer.apple.com/app-store/marketing/guidelines/, served locally and never altered. Don't hotlink Apple badges: the old `tools.applemarketingtools.com` host no longer resolves.
- `CNAME`: the custom domain. The owner sometimes edits it in the GitHub web UI, so fetch before committing.

Contact address on the site: `joe@schemware.com`. Schemware is a one-person studio in Hudson, Wisconsin.

## Git process: commit straight to `main`

Schemware is a one-person shop, so this repository does not use branches or pull requests. The owner chose this on 2026-11-19 and will change this file if the process ever changes.

1. `git fetch` and bring local `main` up to date with `origin/main` first (`git pull --rebase`). Commits made in the GitHub web UI, such as `CNAME` edits, land on `origin/main` directly.
2. Work and commit on `main`. Do not create feature branches or open pull requests unless the owner asks for one for a specific change.
3. Keep history linear: rebase unpushed local commits onto `origin/main`; do not create merge commits.
4. Commit only when the owner asks. Pushing publishes the live site, so push only when the owner asks; a request to commit is not a request to push.
5. Never force-push `main`.

Commit messages: a short imperative subject line (under about 72 characters), a blank line, then a body explaining what changed and why.

## Before committing

Preview the pages through a local static server (for example `python3 -m http.server`) because the pages use root-absolute paths such as `/styles.css`; opening the files directly will not load the styles. Check light mode, dark mode and phone width (no horizontal scrolling).
