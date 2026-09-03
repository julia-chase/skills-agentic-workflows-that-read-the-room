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
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
    title-prefix: "[update-github-info] "
---

# Update GitHub Info

Keep [site/content/github-info.md](../../site/content/github-info.md) current, following Mona's
editorial notes.

## Steps

1. Read [notes/mona-notes.md](../../notes/mona-notes.md) for editorial guidance on tone, style,
   and sourcing.
2. Using only repository context and the existing notes (do not fetch external URLs unless the
   environment explicitly supports web access), identify one concise improvement to
   `site/content/github-info.md`.
3. Update `site/content/github-info.md` with that improvement, following Mona's notes (keep
   summaries short and practical, and prefer updates that help developers learn GitHub faster).
4. Include a short "source" note in the update explaining which local repo context (e.g. notes
   file, existing page content) informed the change.
5. Open a pull request with the updated file so Mona can review the changes before they go live.

If there is nothing new to add since the last update, do not open a pull request.
