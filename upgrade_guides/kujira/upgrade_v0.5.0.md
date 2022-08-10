# Kujira 0.5.0 Upgrade

The Upgrade is scheduled for block `1764000`. A countdown clock is [here](https://ping.pub/kujira/gov/25)

This guide assumes that you use cosmovisor to manage upgrades

First upgrade the current version to v0.5.0

```bash
# get the new version
cd kujira
git pull
git checkout v0.5.0
make install
```

# check the version

```bash
# should be 0.5.0
kujirad version
# Should be commit 89470bd1ec8e3dd8cd3e8c7a9856e527b2c7f079
kujirad version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.kujira/cosmovisor/upgrades/v0.5.0/bin
cp $HOME/go/bin/kujirad $HOME/.kujira/cosmovisor/upgrades/v0.5.0/bin
```

# check the version again

```bash
# should be 0.5.0
$HOME/.kujira/cosmovisor/upgrades/v0.5.0/bin/kujirad version
```
