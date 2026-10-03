# CLAUDE.md

The GitHub profile README for @benbalter. Most of [README.md](README.md) is hand-written, but parts are rewritten weekly by bots.

## Commands

- CI is super-linter ([.github/workflows/linter.yml](.github/workflows/linter.yml)), including markdownlint and zizmor ([.github/linters/zizmor.yaml](.github/linters/zizmor.yaml)). There's no local runner; after pushing, watch it with `gh pr checks --watch`.

## Generated files

Don't hand-edit these; the next bot run overwrites them.

- `<!-- BLOG-POST-LIST:START -->` to `END` in the README: latest posts from the blog feed, written by [update-readme.yml](.github/workflows/update-readme.yml) on Sundays at 00:00 UTC.
- `<!-- PROFILE-FACTS:START -->` to `END` in the README and the cards in [profile/](profile/): written by [update-stats.yml](.github/workflows/update-stats.yml) on Sundays at 06:00 UTC. Change the card options in that workflow instead.

## Gotchas

- Both bots push straight to `master`, so fetch and rebase before pushing, and expect README conflicts on branches that span a Sunday.
- Keep the marker comments exactly as they are. update-stats.yml fails if it can't find the `PROFILE-FACTS` pair.
- Linters for bot-written content (Biome, jscpd, Prettier for Markdown, natural language) are off on purpose; see the comments in linter.yml before turning them back on.
