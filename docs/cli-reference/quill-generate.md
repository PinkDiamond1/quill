# quill generate

Generate a mnemonic seed phrase and generate or recover PEM.

## Basic usage

The basic syntax for running `quill generate` commands is:

``` bash
quill generate [option]
```

## Flags

| Flag                    | Description                       |
|-------------------------|-----------------------------------|
| `-h`, `--help`          | Displays usage information.       |
| `--overwrite-pem-file`  | Overwrite any existing PEM file   |
| `--overwrite-seed-file` | Overwrite any existing seed file. |

## Options

| Option                    | Description                                              |
|---------------------------|----------------------------------------------------------|
| `--pem-file <PEM_FILE>`   | File to write the PEM to.                                |
| `--phrase <PHRASE>`       | A seed phrase in quotes to use to generate the PEM file. |
| `--seed-file <SEED_FILE>` | File to write the seed phrase to [default: seed.txt].    |
| `--words <WORDS>`         | Number of words: 12 or 24 [default: 12].                 |

## Examples

The `quill generate` command has two primary uses - generating a new key, or recovering a key from a seed phrase.

To generate a new key, and output it to a PEM file:

```sh
quill generate --pem-file identity.pem
```

This will generate a new key that you can use to sign IC transactions with quill, or any other IC tool that supports secp256k1, like `dfx`. It will also output a `seed.txt` file containing a seed phrase which can be used to recover this key - write it down in a safe place!

To recover a key from a seed phrase stored in `phrase.txt`:

```sh
quill generate --phrase "$(< phrase.txt)" --pem-file identity.pem
```

## Remarks

Most `quill` commands take `--pem-file` and `--seed-file` parameters, for the key used to sign the messages. Only one of these parameters is needed at a time.
