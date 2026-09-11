# AGENTS.md

## Tests

This package's comprehensive tests live in
[github.com/org-ai-assisted/dist-ai](https://github.com/org-ai-assisted/dist-ai),
not in this repo. They are too high-volume to review here and run in CI.

## Conventions

- The `mw-*` scripts use the full 7-directive strict header including `export LC_ALL=C` (no
  `## style-ok: no-strict`). Under the C locale: `nocasematch` is replaced by `${var,,}` ASCII
  lowercasing; other case-folds (`grep -i`, continue-from) are ASCII-keyword only; Python tools
  run in UTF-8 mode so non-ASCII wiki content round-trips.
- The local dist-ai-style gate needs `helper-scripts` as a repo SIBLING (dm-consumer.yml sets
  `dist-ai-tests.helper-scripts: true`); without it SC1091 false-flags the
  `${HELPER_SCRIPTS_PATH:-}` source lines. Symlink:
  `ln -s <dm>/packages/kicksecure/helper-scripts ~/private-sources/helper-scripts`.
