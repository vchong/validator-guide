# Chihuahua chitestnet-6

## Install node

```bash
# get the new version
git clone https://github.com/ChihuahuaChain/chihuahua
cd chihuahua
git pull
git checkout v4.2.1
make install
```

## check the version

```bash
# should be v4.2.1
chihuahuad version
# Should be commit 3c9d81b261b6e53dabeb65043019baaaed325428
chihuahuad version --long | grep commit
```

## Chain ID

chitestnet-6

## For Testnet Leader (PLEASE SKIP THIS SECTION IF YOU ARE NOT LEADER)

This section is here for the completion of this guide and for future copy-pasting. You will most likely skip this section.

First, create a genesis and adjust some params.

```bash
CHAINID="chitestnet-6"

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
KEY=test
chihuahuad keys add $KEY --recover
VALIDATOR=$(chihuahuad keys show $KEY -a)
COINS="1000000000000uhuahua"

chihuahuad add-genesis-account $VALIDATOR $COINS

chihuahuad gentx $KEY 1000000000uhuahua \
 --chain-id=$CHAINID \
 --moniker="polkachu.com" \
 --commission-max-change-rate=0.01 \
 --commission-max-rate=0.20 \
 --commission-rate=0.05 \
 --min-self-delegation "1" \
 --website "https://polkachu.com" \
 --identity "0A6AF02D1557E5B4" \
 --details "Polkachu is the trusted staking service provider for blockchain projects. 100% refund for downtime slash. Contact us at hello@polkachu.com" \
 --security-contact="hello@polkachu.com"

chihuahuad collect-gentxs
```

Lastly, start the chain

## Initialize with the chain-id

```bash
MONIKER=polkachu # Change it to your moniker
chihuahuad init $MONIKER --chain-id chitestnet-6
```

## Download the genesis

```bash
https://raw.githubusercontent.com/polkachu/validator-guide/main/testnet-genesis/chihuahua/chitestnet-6/genesis.json
```

## Ask for Tokens

Go to testnet Discord channel and post your address. You will get 500 huahua (or 500,000,000 uhuahua) for starting a validator, or more for other purposes.

## persistent_peers

```
37924aed413e8475caff03be96417b6da89b21a9@65.108.226.183:12956
```

## seeds

```
ade4d8bc8cbe014af6ebdf3cb7b1e9ad36f412c0@testnet-seeds.polkachu.com:12956
```

## Explorer

```
https://testnet.ping.pub/chihuahua/staking
```
