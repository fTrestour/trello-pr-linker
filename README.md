# trello-pr-linker

A simple cli tool that lets you link a pr to a trello ticket from the command line

## Usage

### Prerequisites

Ensure you have the following environment variables set:

- `TRELLO_API_KEY`
- `TRELLO_TOKEN`

To get your trello API token

- Start by [creating a power-up into Trello](https://trello.com/power-ups/admin/new)
- Once created copy the value of the API_KEY and click on `token` to generate a new token (you can ignore the secret)

You must also make sure `jq` and `gum` are installed on your machine:

```bash
brew install jq glow gum
```

### Install

- Make sure the script is executable : `chmod +x ./trello`
- Make sure the script is in your PATH: `export PATH=$(pwd)/trello:$PATH` (add it to your .bashrc or .zshrc file)

### Commands

#### `trello ctx`

Changes the current active list.
The current active list id is stored in `~/.trelloctx`.
It first allows you to select a board and then a list in the picked board.

#### `trello pr`

Links a pull request to a Trello ticket in the current active list.
It first allows you to select a ticket in the current list and then prompts you to provide the URL to the PR.
