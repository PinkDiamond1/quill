# quill list-neurons

Signs the query for all neurons belonging to the signing principal.

## Basic usage

The basic syntax for running `quill list-neurons` commands is:

``` bash
quill list-neurons [neuron id]...
```

## Arguments

| Argument         | Description                                        |
|------------------|----------------------------------------------------|
| `<neuron id...>` | The optional ids of the specific neurons to query. |

## Flags

| Flag           | Description                 |
|----------------|-----------------------------|
| `-h`, `--help` | Displays usage information. |

## Examples

The `quill list-neurons` command is used to list your neurons.

For example, to list *all* of your neurons:

```sh
quill list-neurons
```

This will produce a response like:

```candid
(
    record {
        neuron_infos = vec {
            <info>
        }
    }
)
```

where `<info>` is data in the same structure found in [`quill get-neuron-info`].

You can also list only selected neurons, for example:

```sh
quill list-neurons 2313380519530470538 4966884161088437903
```

## Remarks

If `<neuron id...>` is specified, they may only be ones that occur in the usual output from `list-neurons`, i.e., they should be IDs of the user's own neurons. The purpose of this option is to narrow the query, and not to allow querying of arbitrary neuron ids.

As this is an update call, it will not actually make the request, but rather generate a signed and packaged request that can be sent from anywhere. You can use the `--qr` flag to display it as a QR code, or if you are not working with an air-gapped machine, you can pipe it to `quill send -`.

For more information about neurons, see [Neurons].

[Neurons]: https://internetcomputer.org/docs/current/tokenomics/nns/nns-intro#neurons
[`quill get-neuron-info`]: quill-get-neuron-info.md
