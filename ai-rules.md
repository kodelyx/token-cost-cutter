# Token Cost Cutter (TCC) Rules for AI Agents

This workspace is optimized using Token Cost Cutter (TCC). Always use TCC command wrappers to minimize token usage and prevent context window exhaustion.

## 1. Rules for Running Commands
When running shell commands via terminal tools, always prefix the following commands with `tcc`:

* **System Operations:** `ls`, `tree`, `find`, `grep`, `read`, `wc`, `diff`, `log`, `du`, `df`
* **Version Control:** `git`, `gh`, `glab`
* **JS/TS Development:** `npm`, `pnpm`, `npx`, `tsc`, `next`, `lint`, `prettier`, `format`, `jest`, `vitest`, `playwright`
* **Rust:** `cargo`
* **Python:** `pip`, `ruff`, `pytest`, `mypy`
* **Go:** `go`, `golangci-lint`
* **Ruby:** `rake`, `rubocop`, `rspec`
* **Cloud & DevOps:** `docker`, `kubectl`, `aws`
* **Database:** `psql`, `prisma`
* **Network:** `curl`, `wget`
## 2. Advanced TCC Subcommands (Use for Maximum Efficiency)
TCC provides specialized subcommands that you should use in specific scenarios instead of raw utilities:

* **`tcc smart <file>`**: Use this when you want a quick 2-line technical summary of a file instead of reading the whole file.
* **`tcc deps [path]`**: Use this to quickly summarize project dependencies (reads package.json/Cargo.toml etc. and outputs a concise overview) instead of reading the files manually.
* **`tcc json [--keys-only] <file>`**: Use this to read large JSON files. `--keys-only` is extremely useful to understand the structure of a JSON without downloading thousands of lines of data.
* **`tcc err <command>`**: Use this to run any build or compiler command where you only care about seeing warnings and errors (filters out successful compilation steps).
* **`tcc test <command>`**: Use this to run test suites (e.g., `tcc test npm test`, `tcc test cargo test`). It will only show the failing tests and suppress the verbose passing logs.
* **`tcc env`**: Use this to view environment variables. It automatically masks sensitive keys (passwords, tokens) and removes duplicate PATH noise.
* **`tcc run "<command>"`**: Use this to execute a complex shell expression (such as piped commands) under TCC monitoring.

## 3. Examples
* Use `tcc git status` instead of `git status`
* Use `tcc cargo test` instead of `cargo test`
* Use `tcc npm install` instead of `npm install`
* Use `tcc find . -name "*.js"` instead of `find . -name "*.js"`

## 4. Verify Savings
You can run `tcc gain` or `tcc gain --history` to inspect token savings.
