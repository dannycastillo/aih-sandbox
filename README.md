# aih-sandbox

A small sandbox for seeing [ai-harness](https://github.com/dannycastillo/homebrew-tap) (`aih`) in action.
It ships with a single todo in `todo/` that asks an agent to build a self-contained
reference page for `aih` at `docs/index.html`.

## Tutorial

1. Install the tool.

   ```sh
   brew install dannycastillo/tap/ai-harness
   ```

2. Clone this repo and initialize a trunk. A trunk is the git branch and worktree where AI agents merge their code.

   ```sh
   aih init
   ```

   It will also ask you if you want to push the trunk automatically. You can answer no for this sandbox.

3. Move into the worktree and see what would run.

   ```sh
   cd ../aih-sandbox-worktrees/YOUR_AIH_WORKTREE
   aih plan
   ```

   You should see one runnable todo, `doc-aih-reference-page`.

4. Run it. A worker claims the todo, writes the page, a reviewer checks it, and the
   result is merged onto the trunk. It takes about a minute.

   ```sh
   aih run
   ```

5. Open the result.

   ```sh
   ls docs
   open docs/index.html
   ```

`aih status` shows active trunks and run state at any point. Logs land in
`.git/ai-harness/log/`.


## Next Steps

Go use aih on a real project! Or have your favorite AI agent build a new set of todos in this project. AI Harness works well with interactive agents. I use Claude Code to create new trunks, retire trunks, manage and monitor aih runs, and even push PRs/MRs for me to review parked todos.

Have fun!

## License

[MIT](LICENSE)
