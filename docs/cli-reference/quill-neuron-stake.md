# quill neuron-stake

Signs topping up of a neuron (new or existing).

## Basic usage

The basic syntax for running `quill neuron-stake` commands is:

``` bash
quill neuron-stake [option]
```

## Flags

| Flag                    | Description                                                          |
|-------------------------|----------------------------------------------------------------------|
| `-h`, `--help`          | Displays usage information.                                          |
| `--already-transferred` | Skips signing the transfer of ICP, signing only the staking request. |

## Options

| Option                           | Description                                        |
|----------------------------------|----------------------------------------------------|
| `--amount <AMOUNT>`              | ICPs to be staked on the newly created neuron.     |
| `--fee <FEE>`                    | Transaction fee, default is 10000 e8s.             |
| `--from-subaccount <SUBACCOUNT>` | The subaccount to transfer from.                   |
| `--name <NAME>`                  | The name of the neuron (up to 8 ASCII characters). |
| `--nonce <NONCE>`                | The nonce of the neuron.                           |

## Examples

The `quill neuron-stake` command is used to lock ICP into a new neuron or add ICP to an existing one.

To stake for example 50 ICP into a neuron named 'primary':

```sh
quill neuron-stake --amount 50 --name primary
```

The command is the same whether the neuron already exists or not.

This command consists of two messages, of which the first one is the ICP transfer. If you've already made this transfer through a different tool, you can add the transfer to the neuron's stake by leaving off the `amount` parameter and adding `--already-transferred`: 

```sh
quill neuron-stake --name primary --already-transferred
```

In addition to the transfer response documented at [`quill transfer`], these commands will produce a response like:

```candid
(
    record {
        result = opt variant {
            NeuronId = record {
                id = 2313380519530470538;
            }
        };
    }
)
```

## Remarks

As this is an update call, it will not actually make the request, but rather generate a signed and packaged request that can be sent from anywhere. You can use the `--qr` flag to display it as a QR code, or if you are not working with an air-gapped machine, you can pipe it to `quill send -`.

For more information about neuron staking, see [Staking and Voting Rewards on the NNS][Staking].

[`quill transfer`]: quill-transfer.md
[Staking]: https://internetcomputer.org/docs/current/tokenomics/nns/nns-staking-voting-rewards
