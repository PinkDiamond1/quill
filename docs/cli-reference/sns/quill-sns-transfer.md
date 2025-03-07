# quill sns transfer

Signs a ledger transfer update call.

## Basic usage

The basic syntax for running `quill sns transfer` commands is:

```bash
quill sns transfer <TO> --amount <AMOUNT> [option]
```

## Arguments

| Argument | Description              |
|----------|--------------------------|
| `<TO>`   | The destination account. |

## Flags

| Flag           | Description                 |
|----------------|-----------------------------|
| `-h`, `--help` | Displays usage information. |

## Options

| Option                                | Description                                          |
|---------------------------------------|------------------------------------------------------|
| `--amount <AMOUNT>`                   | Amount of governance tokens to transfer.             |
| `--fee <FEE>`                         | The amount that the caller pays for the transaction. |
| `--from-subaccount <FROM_SUBACCOUNT>` | The subaccount to transfer from.                     |
| `--memo <MEMO>`                       | An arbitrary number associated with a transaction.   |
| `--to-subaccount <TO_SUBACCOUNT>`     | The subaccount of the destination account.           |

## Remarks

The default fee is 0.0001 tokens. Use the `--fee` flag when using an SNS that sets its own transaction fee.

The destination account can be specified as a separate principal and subaccount, or as a single ICRC-1 account.
