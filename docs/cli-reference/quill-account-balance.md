# quill account-balance

Queries a ledger account for its balance.

## Basic usage

The basic syntax for running `quill account-balance` commands is:

``` bash
quill account-balance [flag] <account id>
```

## Arguments

| Argument       | Description                                                |
|----------------|------------------------------------------------------------|
| `<account id>` | The id of the account to query. Optional if a key is used. |

## Flags

| Flag           | Description                                        |
|----------------|----------------------------------------------------|
| `--dry-run`    | Will display the query, but not send it.           |
| `-h`, `--help` | Displays usage information.                        |
| `-y`, `--yes`  | Skips confirmation and sends the message directly. |

## Examples

The `quill account-balance` command is used to check the ICP balance of a particular NNS ledger account.

For example, to check the balance of the account `345f723e9e619934daac6ae0f4be13a7b0ba57d6a608e511a00fd0ded5866752`, you would say:

```sh
quill account-balance 345f723e9e619934daac6ae0f4be13a7b0ba57d6a608e511a00fd0ded5866752
```

This will produce a response like 

```candid
(record { e8s = 800_000_000 : nat64 })
```

"e8s" is a shorthand for meaning the number of 1e-8s, or one-hundred-millionths, of an ICP in integer form; this response must be divided by 100,000,000 to get the real balance, which in this case would be 8.0 ICP.

## Remarks

As this is a query call, it cannot be executed on an air-gapped machine, but does not require access to your keys. You can use the `quill public-ids` command to get your account ID. 

For more information about the ICP ledger, see [The Ledger Canister].

[The Ledger Canister]: https://internetcomputer.org/docs/current/references/ledger
