# quill get-proposal-info

Displays available information about a proposal.

## Basic usage

The basic syntax for running `quill get-proposal-info` commands is:

``` bash
quill get-proposal-info [option] <identifier>
```

## Arguments

| Argument       | Description              |
|----------------|--------------------------|
| `<identifier>` | The proposal identifier. |

## Flags

| Flag           | Description                                        |
|----------------|----------------------------------------------------|
| `--dry-run`    | Will display the query, but not send it.           |
| `-h`, `--help` | Displays usage information.                        |
| `-y`, `--yes`  | Skips confirmation and sends the message directly. |

## Examples

The `quill get-proposal-info` command is used to list information about an NNS proposal. For example, to get the information for [proposal 107942]: 

```sh
quill get-proposal-info 107930
```

This will produce a response like:

```candid
(
  opt record {
    id = opt record { id = 107_942 : nat64 };
    status = 4 : int32;
    topic = 7 : int32;
    failure_reason = null;
    ballots = vec {};
    proposal_timestamp_seconds = 1_676_558_071 : nat64;
    reward_event_round = 0 : nat64;
    deadline_timestamp_seconds = opt (1_676_903_671 : nat64);
    failed_timestamp_seconds = 0 : nat64;
    reject_cost_e8s = 1_000_000_000 : nat64;
    derived_proposal_information = null;
    latest_tally = opt record {
      no = 60_211_138_783 : nat64;
      yes = 43_800_685_064_905_637 : nat64;
      total = 44_062_955_059_203_007 : nat64;
      timestamp_seconds = 1_676_560_174 : nat64;
    };
    reward_status = 1 : int32;
    decided_timestamp_seconds = 1_676_560_174 : nat64;
    proposal = opt record {
      url = "";
      title = opt "Replace nodes in subnet lspz2";
      action = opt variant {
        ExecuteNnsFunction = record {
          nns_function = 31 : int32;
          payload = blob "<...>";
        }
      };
      summary = "# Replace nodes in subnet lspz2\n\nMotivation: Replacing an AT2 node in accordance with https://forum.dfinity.org/t/the-state-and-direction-of-decentralization-nodes-on-the-internet-computer/9170/105; replacing 1 unhealthy node";
    };
    proposer = opt record { id = 40 : nat64 };
    executed_timestamp_seconds = 1_676_560_174 : nat64;
  },
)
```

## Remarks

As this is a query call, it cannot be executed on an air-gapped machine, but does not require access to your keys. 

For more information about proposals, see [Proposals].

[proposal 107942]: https://dashboard.internetcomputer.org/proposal/107942
[Proposals]: https://internetcomputer.org/docs/current/tokenomics/nns/nns-intro#proposals
