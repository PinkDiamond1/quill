# quill ckbtc withdrawal-address

Displays the address that you or a specified user can deposit ckBTC at to retrieve BTC.

The `--of` parameter is required if a signing key is not provided.

If you have made a transfer to this address, use the `--already-transferred` flag with [`quill ckbtc retrieve-btc`](./quill-ckbtc-retrieve-btc.md) to register it.

## Basic usage

The basic syntax for running `quill ckbtc withdrawal-address` commands is:

```bash
quill ckbtc withdrawal-address [option]
```

## Flags

| Flag           | Description                      |
|----------------|----------------------------------|
| `-h`, `--help` | Displays usage information.      |
| `--testnet`    | Uses ckTESTBTC instead of ckBTC. |

## Options

| Option      | Description                                                                 |
|-------------|-----------------------------------------------------------------------------|
| `--of <OF>` | The principal to get the withdrawal address for. Optional if a key is used. |
