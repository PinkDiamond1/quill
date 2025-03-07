# quill list-proposals

Queries for a list of pending proposals.

## Basic usage

The basic syntax for running `quill list-proposals` commands is:

``` bash
quill list-proposals [option]
```

## Flags

| Flag           | Description                                        |
|----------------|----------------------------------------------------|
| `--dry-run`    | Will display the query, but not send it.           |
| `-h`, `--help` | Displays usage information.                        |
| `-y`, `--yes`  | Skips confirmation and sends the message directly. |

## Options

| Option            | Description                        |
|-------------------|------------------------------------|
| `--limit <LIMIT>` | Only displays `<LIMIT>` proposals. |

## Examples

The `quill list-proposals` command is used to list the most recent NNS proposals. For example, to fetch the most recent 5 proposals:

```sh
quill list-proposals --limit 5
```

This will produce a response like:

```candid
(
    record {
        proposal_info = vec {
            <info>
        }
    }
)
```

where `<info>` is data in the same structure found in [`quill get-proposal-info`].

## Remarks

As this is a query call, it cannot be executed on an air-gapped machine, but does not require access to your keys.

For more information about proposals, see [Proposals].

[`quill get-proposal-info`]: quill-get-proposal-info.md
[Proposals]: https://internetcomputer.org/docs/current/tokenomics/nns/nns-intro#proposals
