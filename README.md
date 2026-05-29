# auto-git

Automate your Git workflow with AI-powered commit messages and smart remote management.

## Features

*   **Gemini AI Integration**: Leverages Google Gemini to automatically generate professional, Conventional Commit-compliant commit messages based on your staged changes.
*   **Smart Remote Management**: Automatically detects HTTPS GitHub remotes and converts them to SSH, streamlining authentication without manual configuration.
*   **Robust Fallback Mechanisms**: Ensures workflow continuity by falling back to a structured, timestamped default message if the Gemini API is unreachable or fails to generate a response.
*   **Simplified Synchronization**: Streamline repetitive tasks with the `sync` command, which stages, generates AI-based commit messages, and pushes to the remote in one sequence.

## Prerequisites

*   **Bash**: Shell environment.
*   **Git**: Version control system.
*   **gemini-cli**: The script invokes `gemini`. Ensure it is installed and configured in your environment.

## Installation

1. Download the `auto-git` script to a directory of your choice (e.g., `~/scripts/auto-git`).
2. Make the script executable:
   `chmod +x ~/scripts/auto-git`
3. Create a symbolic link in your `~/bin` directory (ensure `~/bin` is in your `$PATH`):
   `ln -s ~/scripts/auto-git ~/bin/auto-git`

## Usage

Execute commands using the following syntax:
`auto-git <command> [path] [branch]`

If a path is not provided, it defaults to the current directory (`.`). If a branch is not provided, it defaults to `main`.

### Commands

*   **`commit`**: Stages all local changes (`git add -A`) and generates a professional commit message using Gemini.
*   **`amend`**: Rewrites the last commit message using Gemini based on the diff of the latest commit.
*   **`push`**: Checks the remote URL and automatically switches to SSH if an HTTPS GitHub remote is detected, then pushes to the specified branch.
*   **`sync`**: Executes `commit` followed immediately by `push`.
