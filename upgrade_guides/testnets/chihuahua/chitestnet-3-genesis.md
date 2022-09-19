# Chihuahua chitestnet-3

Install node

```bash
# get the new version
cd chihuahua
git pull
git checkout v2.0.2
make install
```

# check the version

```bash
# should be v2.0.2
chihuahuad version
# Should be commit eeb863cfbcf2731c20b1e9970f99a786507f0332
chihuahuad version --long
```

# Initialize with the chain-id

```bash
chihuahuad init <NAME> --chain-id chitestnet-3
```

# Download the genesis

```bash
https://raw.githubusercontent.com/polkachu/validator-guide/main/upgrade_guides/testnets/chihuahua/genesis.json
```

# Ask for Tokens

Go to testnet Discord channel and post your address. You will get 1000 stake

# persistent_peers

```
17d5b12792435e3e81381e659349c736cec94cc9@65.109.28.219:12956
```

# explorer

```
https://testnet.ping.pub/chihuahua/staking
```
