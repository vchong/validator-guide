# Kujira 0.6.0 Upgrade

The Upgrade is scheduled for block `3750000`. A countdown clock is [here](https://cosmos.mintthemoon.xyz/kujira/gov/53)

This guide assumes that you use cosmovisor to manage upgrades

First upgrade the current version to v0.6.0

```bash
# get the new version
cd kujira
git pull
git checkout v0.6.0
make install
```

# check the version

```bash
# should be 0.6.0
kujirad version
# Should be commit a2772d40d135f68b587aec6c01c9c9a3c74c40a5
kujirad version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.kujira/cosmovisor/upgrades/v0.6.0/bin
cp $HOME/go/bin/kujirad $HOME/.kujira/cosmovisor/upgrades/v0.6.0/bin
```

# check the version again

```bash
# should be 0.6.0
$HOME/.kujira/cosmovisor/upgrades/v0.6.0/bin/kujirad version
```
