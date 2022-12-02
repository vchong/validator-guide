# Chihuahua chitestnet-5

## Install node

```bash
# get the new version
git clone https://github.com/ChihuahuaChain/chihuahua
cd chihuahua
git pull
git checkout v4.1.0
make install
```

## check the version

```bash
# should be v4.1.0
chihuahuad version
# Should be commit 49a1b6d8f71bb0e981f6ff0fce5deae63e270324
chihuahuad version --long | grep commit
```

## Chain ID

chitestnet-5

## For Testnet Leader (PLEASE SKIP THIS SECTION IF YOU ARE NOT LEADER)

This section is here for the completion of this guide and for future copy-pasting. You will most likely skip this section.

First, create a genesis and adjust some params.

```bash
CHAINID="chitestnet-5"

chihuahuad config chain-id $CHAINID

MONIKER=polkachu
chihuahuad init $MONIKER --chain-id $CHAINID

# modify some params
sed -i 's/"max_deposit_period": "172800s"/"max_deposit_period": "120s"/g' ~/.chihuahuad/config/genesis.json
sed -i 's/"voting_period": "172800s"/"voting_period": "900s"/g' ~/.chihuahuad/config/genesis.json
sed -i 's/"min_commission_rate": "0.000000000000000000"/"min_commission_rate": "0.05"/g' ~/.chihuahuad/config/genesis.json
sed -i 's/"stake"/"uhuahua"/g' ~/.chihuahuad/config/genesis.json
```

Second, create a genesis validator and collect genesis

```bash
# create key
chihuahuad keys add chihuahua_test --recover
VALIDATOR=$(chihuahuad keys show chihuahua_test -a)

# create gentx
coins="900000000000000uhuahua,100000000000stake,100000000000samoleons"

chihuahuad add-genesis-account $VALIDATOR $coins

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

chihuahuad gentx validator 1000000000uhuahua --chain-id $CHAINID --commission-rate="0.05"
chihuahuad collect-gentxs
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

## Initialize with the chain-id

```bash
MONIKER=polkachu # Change it to your moniker
chihuahuad init $MONIKER --chain-id chitestnet-5
```

## Download the genesis

```bash
https://raw.githubusercontent.com/polkachu/validator-guide/main/testnet-genesis/chihuahua/chitestnet-4/genesis.json
```

## Ask for Tokens

Go to testnet Discord channel and post your address. You will get 10 huahua (or 10,000,000 uhuahua).

## persistent_peers

```
69481a41415fe35deceea497d481ce9f6b134eef@65.109.28.219:12956
```

## Explorer (Not ready)

```
https://testnet.ping.pub/chihuahua/staking
```
