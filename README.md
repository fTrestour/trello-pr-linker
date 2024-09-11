# Trello PR Linker

A simple CLI tool to link a pull request to a Trello ticket directly from the command line.

## Usage

### Prerequisites

Ensure the following environment variables are set:

- `TRELLO_API_KEY`
- `TRELLO_TOKEN`

If a `.env` file exists in the same directory as the `trello` script, it will be automatically sourced.

To obtain your Trello API token:

1. [Create a new power-up in Trello](https://trello.com/power-ups/admin/new).
2. Copy the `API_KEY` value and click on `token` to generate a new token (the secret can be ignored).

Additionally, ensure `jq` and `gum` are installed on your machine:

```bash
brew install jq gum
```

### Installation

1. Ensure the script is executable: `chmod +x ./trello`
2. Add the script to your PATH: `export PATH=$(pwd)/trello:$PATH` (include this in your `.bashrc` or `.zshrc` file for persistence)

### Commands

#### `trello ctx`

Switches the current active list.
The active list ID is saved in `~/.trelloctx`. This command prompts you to select a board first, followed by a list within that board.

#### `trello pr`

Links a pull request to a Trello card in the active list.
It prompts you to select a ticket assigned to you from the active list, then requests the PR URL to associate with the ticket.

#### `--with-review` or `-r`

When used with the `trello ctx` command, this option allows you to set a review list in addition to the active list. You will be prompted to select a review list after selecting the active list. The review list ID is also saved in `~/.trelloctx`.

When used with the `trello pr` command, this option moves the Trello card to the review list after linking the PR URL to the card.
