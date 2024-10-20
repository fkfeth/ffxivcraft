# [Final Fantasy XIV Craft (FFXIV Craft)](https://dazemc.github.io/ffxiv-craft)
[![Update and Deploy](https://github.com/dazemc/ffxiv-craft/actions/workflows/jekyll-gh-pages.yml/badge.svg)](https://github.com/dazemc/ffxiv-craft/actions/workflows/jekyll-gh-pages.yml)

## Overview

`ffxiv-craft` is an advanced crafting tool specifically designed for Final Fantasy XIV (FFXIV) players. It leverages Monte Carlo simulation to generate optimal crafting macros, enhancing your crafting experience and efficiency in the game. 

Please note that this tool is a fan initiative and is not officially endorsed or affiliated with Square Enix or its subsidiaries.

## Features

- **Crafting Macro Generator:** Uses Monte Carlo simulations to generate efficient crafting macros, eliminating guesswork from your crafting processes.

- **Crafting Simulator:** The built-in crafting simulator allows you to test the effectiveness of the macros before committing your in-game resources.

- **Auto-updates:** The tool automatically updates the data it uses to generate crafting macros. This ensures that the tool is always up-to-date with the latest game data.

Given the probabilistic nature of Monte Carlo simulations, the resulting macros might vary from run to run. However, the tool is designed to consistently generate successful macros.

## Workflow

The `ffxiv-craft` repository uses a GitHub Actions workflow to automate updates and deployment. The workflow is defined in the `.github/workflows/jekyll-gh-pages.yml` file.

Here's a summary of the workflow steps:

1. **Checkout:** Checks out the repository using `actions/checkout@v3`.
2. **Run Python Script:** Runs `xivapi_calls.py` Python script located in the `scripts` directory.
3. **Setup Pages:** Sets up GitHub Pages using `actions/configure-pages@v3`.
4. **Build with Jekyll:** Builds the project with Jekyll using `actions/jekyll-build-pages@v1`, taking the current directory as the source and placing the output in the `./_site` directory.
5. **Commit Changes:** If there are changes, it commits them with the message "Automatic update" and pushes them to the repository.
6. **Upload artifact:** Uploads the built site as an artifact using `actions/upload-pages-artifact@v1`.
7. **Deploy to GitHub Pages:** Deploys the build artifact to GitHub Pages using `actions/deploy-pages@v2`.

The workflow is triggered on a schedule (every day at 12:00 UTC), on every push to the `main` branch, and on every pull request to the `main` branch.

## Usage

Access to `ffxiv-craft` is straightforward and doesn't require local setup. You can use the tool by visiting the deployed site on GitHub. The user-friendly interface guides you through the process of generating crafting macros.

## To-Do

- **Changelog Updates:** Plan to implement a feature that adds a date and time to the changelog whenever an update has been automatically applied. This will be visible at the head of the simulator page.

- **Webhook Integration:** Intend to run a webhook that will monitor for future updates. The webhook will check `xivapi` for these updates and trigger a build when new data is available.

- **Reorder non-English translations:** Address [this issues](https://github.com/NotRanged/NotRanged.github.io/issues/76) and any other languages that have a similiar issue.

- **Remove last wait.num:** [The last wait is not needed](https://github.com/NotRanged/NotRanged.github.io/issues/78) Add option to remove or set the default behavior to remove.

## Contributing

We always welcome community contributions and feedback! If you have a feature request, want to report a bug, or have developed a new feature that would benefit the community, feel free to open an issue or submit a pull request. Please ensure that you read through the existing issues and pull requests to avoid duplicate entries.
