# Chihuahua chitestnet-4

Install node

```bash
# get the new version
cd chihuahua
git pull
git checkout v3.0.0
make install
```

# check the version

```bash
# should be v3.0.0
chihuahuad version
# Should be commit 36ee9133360dadfe8f96527442908407fd04abb7
chihuahuad version --long | grep commit
```

# Chain ID
chitestnet-4

# Initialize with the chain-id

```bash
chihuahuad init NAME --chain-id chitestnet-4
```

# For Testnet Leader (PLEASE SKIP THIS SECTION)

This section is here for the completion of this guide and for my future copy-pasting. You will most likely skip this section.

First, adjust some params to your liking. For chihuahua, I adjusted denom to uhuahua and gov proposal voting time to 15 minutes.

```bash
chihuahuad add-genesis-account $(chihuahuad keys show -a KEY) 1000000000uhuahua
```

```bash
chihuahuad gentx chihuahua_test 100000000uhuahua \
--chain-id=chitestnet-4 \
--moniker="polkachu.com" \
--commission-max-change-rate=0.01 \
--commission-max-rate=0.20 \
 --min-self-delegation "1" \
--commission-rate=0.05 \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com"
```

# Download the genesis

```bash
https://raw.githubusercontent.com/polkachu/validator-guide/main/testnet-genesis/chihuahua/chitestnet-4/genesis.json
```

# Ask for Tokens

Go to testnet Discord channel and post your address. You will get 10 huahua (or 10,000,000 uhuahua).

# persistent_peers

```
69481a41415fe35deceea497d481ce9f6b134eef@65.109.28.219:12956
```

# explorer

```
https://testnet.ping.pub/chihuahua/staking
```
