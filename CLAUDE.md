# sdlab-blog

The System Design Lab blog: Astro, deployed to GitHub Pages at <https://jpm-dev-14.github.io/sdlab-blog/>. One post per build, plus post 0, "Building a system design lab". Voice, structure and provenance rules: the workspace rule `../.claude/rules/blog.md`. Posts are drafted with the workspace skill `/blog-post NN`.

## Conventions

- Posts: `src/content/posts/NN-<slug>.mdx`. Frontmatter: `title`, `description`, `date`, `build`, `repo`, `tag`, `headline`.
- Every number comes from a results file imported into `src/data/<NN>/<tag>/` together with a provenance manifest (repo, tag, path, sha256). Charts read only those files; nobody retypes a number.
- Absolute numbers come from runs on Linux hosts. Runs on the macOS laptop go through Docker's VM, so they appear only as relative comparisons, labeled as laptop runs.
- Links to code point at the tag the post describes, never `main`.
- Nothing is pushed to `main` (which publishes) without the engineer's go-ahead.

## Phase 0 checklist

- [ ] Astro scaffold: content collections, MDX, a minimal readable theme with dark mode, RSS, sitemap
- [ ] Results import script (`pnpm import-results <build-repo> <tag> <path>…`) that reads files with `git -C ../<build-repo> show <tag>:<path>` and writes the provenance manifest
- [ ] Chart component (uPlot or ECharts) that renders from an imported results file
- [ ] GitHub Pages deploy workflow on push to `main`
- [ ] Post 0 drafted with the engineer
