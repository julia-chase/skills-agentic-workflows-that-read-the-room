---
name: update-github-info

on:
  schedule: daily
  workflow_dispatch:

strict: false

permissions:
  contents: read

engine: copilot

tools:
  edit:
  web-fetch:

network:
  allowed:
    - defaults
    - github.blog
    - github.com

safe-outputs:
  create-pull-request:
    title-prefix: "[update-github-info] "
---

# Update GitHub Info

Keep [site/content/github-info.md](../../site/content/github-info.md) current with the latest
GitHub Blog posts and Changelog entries, following Mona's editorial notes.

## Steps

1. Read [notes/mona-notes.md](../../notes/mona-notes.md) for editorial guidance on tone, style,
   and sourcing.
2. Fetch `https://github.blog/latest/` to review the latest GitHub Blog posts.
3. Fetch `https://github.blog/changelog/` to review the latest GitHub Changelog entries.
4. Update `site/content/github-info.md` with short, practical summaries of anything new or
   noteworthy from those two sources, following Mona's notes (keep summaries short and
   practical, prefer updates that help developers learn GitHub faster, and mention the source
   whenever a change comes from the GitHub Blog or GitHub Changelog).
5. Open a pull request with the updated file so Mona can review the changes before they go live.

If there is nothing new to add since the last update, do not open a pull request.
