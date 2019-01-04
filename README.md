# Vapory wallet generator
Simple script collection, currently in bash and python format, to generate a complete offline Vapory wallet by creating an ECDSA keypair and derive its Vapory address.

You can read my article about it here: https://kobl.one/blog/create-full-vapory-keypair-and-address/

## Python dependencies
- ECDSA https://pypi.python.org/pypi/ecdsa
- pysha3 https://pypi.python.org/pypi/pysha3

You can also use the included requirements.txt file to install them
```bash
pip install -r requirements.txt
```

## Bash dependencies
- OpenSSL
- SHA3sum (keccak-256sum) https://github.com/maandree/sha3sum

*Compiled, statically linked versions of the keccak-256sum executable are available in the lib folder of this repo for i386 and x86_64.*

## Importing private key to gvap
You can use the generated private key to import in to gvap (https://github.com/vaporyco/go-vapory).
```bash
# First save the private hexadecimal key to a file
echo eff415edb6331f4f67bdb7f1ecc639da9bcc0550b100bb275c7b5b21ce3a7804 > key
# Then use account import feature of gvap (here importing in the 'testnet' directory)
./go-vapory/build/bin/gvap --datadir ~/.vapory/testnet account import key
```
Note that gvap will ask you immediately to choose a passphrase to protect the newly imported key.

## Example
```bash
./vapory-wallet-generator.py
Private key: eff415edb6331f4f67bdb7f1ecc639da9bcc0550b100bb275c7b5b21ce3a7804
Public key:  d6dd5241c03bf418b333c256057ee878c34975d6abda075d58e4b9780f4a8659fcc096b6ad763d8e5914f7daa0b7351398b1eb6458e95ac41a2711a0651f3fc6
Address:     0x4206f95fc533483fae4687b86c1d0a0088e3cd48
```

```bash
./vapory-wallet-generator.sh
Private key: 9442b4b82c8011530f3a363cc87a4ea91efd53552faab2e63fd352db9367bb24
Public key:  3f538de115393e2a8851b4c19f686b6bb245213c3823e69336583f1d72c53d20831ea0574900b31d833932b3e8e71b4e99d574c6480890d60153fc2dccbc96d6
Address:     0x083c41ea13af6c2d5aaddf6e73142eb9a7b00183
```
