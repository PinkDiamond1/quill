# quill transfer

Signs an ICP transfer transaction.

## Basic usage

The basic syntax for running `quill transfer` commands is:

``` bash
quill transfer [option] --amount <AMOUNT> <TO>
```

## Arguments

| Argument | Description          |
|----------|----------------------|
| `<TO>`   | Destination account. |

## Flags

| Flag           | Description                 |
|----------------|-----------------------------|
| `-h`, `--help` | Displays usage information. |

## Options

| Option                           | Description                                                           |
|----------------------------------|-----------------------------------------------------------------------|
| `--amount <AMOUNT>`              | Amount of ICPs to transfer (with up to 8 decimal digits after comma). |
| `--fee <FEE>`                    | Transaction fee, default is 10000 e8s.                                |
| `--from-subaccount <SUBACCOUNT>` | The subaccount to transfer from.                                      |
| `--memo <MEMO>`                  | Reference number, default is 0.                                       |

## Examples

The `quill transfer` command is used to transfer ICP from one account to another. 

For example, to transfer 5 ICP to the anonymous principal `2vxsx-fae`:

```sh
quill transfer 1c7a48ba6a562aa9eaa2481a9049cdf0433b9738c992d698c31d8abf89cadc79 --amount 5
```

This will produce a response like:

```candid
(5_581_035 : nat64)
```

This refers to the block index, also known as block height, at which the transaction took place; you can look up this transaction on the [IC dashboard].

## Remarks

As this is an update call, it will not actually make the request, but rather generate a signed and packaged request that can be sent from anywhere. You can use the `--qr` flag to display it as a QR code, or if you are not working with an air-gapped machine, you can pipe it to `quill send -`.

For more information about ICP and transfers, see [ICP Token].

[IC dashboard]: https://dashboard.internetcomputer.org/
[ICP Token]: https://wiki.internetcomputer.org/wiki/ICP_token
