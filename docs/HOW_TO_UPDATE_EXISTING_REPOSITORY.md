# Safely updating your GitHub repository

**GitHub target:** `https://github.com/slim274/azure-epicbook-monolithic-app`

This archive provides **README, screenshot evidence, diagrams, and documentation only**. It **does not contain or overwrite application source** (original EpicBook is credited at `https://github.com/pravinmishraaws/theepicbook`).

In your Ubuntu workspace, inspect `git status --short` and `git remote -v` before copying. Back up your current `README.md`, `docs/`, `diagrams/`, and `screenshots/`. Copy just those documentation files from this archive; review `git diff` for unexpected changes.

Before staging, check for secret-bearing `config/config.json`, `.env`, Azure keys or tokens and unredacted private account details. Then use `git add` for the intended documentation files, review `git diff --cached --check`, commit and push only after verifying the remote is correct.
