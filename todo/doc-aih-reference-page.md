# doc: aih reference page

- **Priority:** high
- **Touches:** NEW docs/*
- **Blocked by:** —

## Goal
`docs/index.html` is a single self-contained web page that documents the
`aih` tool installed on this machine, built in a way that is consummable by a human.

## Why
This repo is an onboarding sandbox, the goal is to allow a developer to see the aih tool in action. By building documentation a developer can see the tool work and get documentation in a browsable way.

## Notes
- The source of truth is the installed tool, not memory. Run and read:
  `aih help`, `aih version`, `aih protocol`, `aih role worker`,
  `aih role reviewer`, and `aih <verb> --help` for every verb `aih help`
  lists. Quote usage lines verbatim.
- One file, `docs/index.html`, hand-written HTML with inline CSS. No build
  step, no JavaScript framework, no CDN or web font: it must render from
  `file://` with the network off.
- Sections, in order: what aih is (two or three sentences); quickstart
  (`brew install dannycastillo/tap/ai-harness`, `aih init`, write a todo,
  `aih run`); the lifecycle of one todo (claim, work, gate, submit,
  integrate, trunk); a verb reference with one subsection per verb, each
  containing the literal text `aih <verb>` and the verb's `usage:` line;
  the exit codes from `aih help` as a table; the keys of `.ai-harness.conf`
  with a one-line meaning each, taken from the comments in the conf that
  `aih init` wrote in this repo; a footer with the output of `aih version` and today's date.
- Readable on a phone-width window and a laptop. Dark text on light
  background is fine; keep it plain.
- Do not create or edit anything outside `docs/`. The conf is not in Touches.

## Done when
- [ ] `docs/index.html` exists and is the only file this change adds
- [ ] the page opens in a browser from `file://` with no network access
- [ ] every verb listed by `aih help` has a subsection containing `aih <verb>` and its `usage:` line
- [ ] the exit codes table matches `aih help`
- [ ] the footer shows the `aih version` output
- [ ] `aih check` prints clean from the worktree
