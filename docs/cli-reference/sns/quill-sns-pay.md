# quill sns pay

Signs messages to pay for an open sale ticket that you can create using `quill sns new-sale-ticket`.

This operation consists of two messages:

First, transfer ICP to the sale canister on the NNS ledger, under the subaccount for your principal.

Second, the sale canister is notified that the transfer has been made.

## Basic usage

The basic syntax for running `quill sns pay` commands is:

```bash
quill sns pay --amount-icp-e8s <AMOUNT_ICP_E8S> --ticket-creation-time <TICKET_CREATION_TIME> --ticket-id <TICKET_ID> [option]
```

## Flags

| Flag            | Description                 |
|-----------------|-----------------------------|
| `-h`, `--help`  | Displays usage information. |
| `--notify-only` | No transfer will be made.   |

## Options

| Option                                          | Description                           |
|-------------------------------------------------|---------------------------------------|
| `--amount-icp-e8s <AMOUNT>`                     | The amount of ICP to transfer.        |
| `--subaccount <SUBACCOUNT>`                     | Pay from this subaccount.             |
| `--ticket-creation-time <TICKET_CREATION_TIME>` | The creation_time of the sale ticket. |
| `--ticket-id`                                   | The ticket_id of the sale ticket.     |

## Remarks

Once the pay has been finalized, if it was successful, you will receive your neurons automatically. Your neuron's share of the governance tokens at sale finalization will be proportional to your share of the contributed ICP.

If `--notify-only` is specified, only the notification message will be generated. This is useful if there was an error previously submitting the notification which you have since rectified, or if you have made the transfer with another tool.
