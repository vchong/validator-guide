# Kujira 0.7.1 Upgrade

The Upgrade is scheduled for block `3495000`. A countdown clock is [here](https://cosmos.mintthemoon.xyz/kujira/gov/49)

This guide assumes that you use cosmovisor to manage upgrades

First upgrade the current version to v0.7.1

```bash
# get the new version
cd kujira
git pull
git checkout v0.7.1
make install
```

# check the version

```bash
# should be 0.7.1
kujirad version
# Should be commit d56e24ace683a7c5deec5a32d66b1848adf7d253
kujirad version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.kujira/cosmovisor/upgrades/v0.7.1/bin
cp $HOME/go/bin/kujirad $HOME/.kujira/cosmovisor/upgrades/v0.7.1/bin
```

# check the version again

```bash
# should be 0.7.1
$HOME/.kujira/cosmovisor/upgrades/v0.7.1/bin/kujirad version
```
