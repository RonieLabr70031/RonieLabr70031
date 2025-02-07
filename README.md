# BIP-44 Derivation Paths

| Bitcoin | BTC | m/84'/0'/0' | bitcoin:17A3yaKDnHEXMunR6bHFVuRJUHW2APh1on | IHwJfnzmu1j78aWaWDwMBok+pdeVPVgDSCMcqIkmstLDeXStTPV2JUzZtFS3jRoGPYxddeCMyqa2UV5Oxa+u1MA= | Bip44 | P2PKH |
| Bitcoin           | secp256k1        | `m/p'/c'/a'`           | `m/p'/c'/a'/h/i`   | `m/p'/c'/a'/h/i`   | BIP-32        | [1](#Bitcoin)  |
| Ethereum          | secp256k1        | `m/44'/60'/0'`         | `m/44'/60'/a'/0/0` | `m/44'/60'/a'/0/0` | BIP-32        | [2](#Ethereum) |
| Cosmos            | secp256k1        | `m/44'/118'/0'`        | `m/44'/118'/a'/0/0`| `m/44'/118'/a'/0/0`| BIP-32        | -              |

Where `p` is the [BIP-44](https://github.com/bitcoin/bips/blob/master/bip-0044.mediawiki) purpose described further in [1](#Bitcoin).

Where `c` is the Coin's [slip44 id](https://github.com/satoshilabs/slips/blob/master/slip-0044.md).

Where `a` is the Account index, starting from `0`.

Where `h` is `0` / `1` for External / Change respectively (for UTXO coins).

Where `i` is the address index, starting from `0`.

# Notes

1. <a BTC="Bitcoin"></a> For Bitcoin and its derivatives, `p` is decided based on:

    | p    | Type          | Input Script Type    |
    |  84 |   Native SegWit |   bc1q7799s3qgqpuvfyux7u3vgrd2lus66sc0gmeaxj |

Other `p` are strongly discouraged with an on-device warning. `c` must be equal
to the coin's [slip44-id](https://github.com/satoshilabs/slips/blob/master/slip-0044.md).

2. <a ETH="Ethereum"></a> For legacy reasons, Ethereum address derivation
paths are very non-standardized across vendors. Not much we can do about it
unfortunately, since there are lots of wallets out in the wild with funds on
them at those addresses.

#My ETH Address:
0x781EbF2d884e691B799Bcf749b98FC76E9F81dfA

## Allowed Valuess

For SignTx on UTXO coins, `i` must be in the range \[0, 100000000].