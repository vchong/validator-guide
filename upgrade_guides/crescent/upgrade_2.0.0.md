# Crescent 2.0.0 Upgrade

The Upgrade is scheduled for block `1384100`. A countdown clock is [here](https://www.mintscan.io/crescent/blocks/1384100)

This guide assumes that you use cosmovisor to manage upgrades

First upgrade the current version to v2.0.0

```bash
# get the new version
cd crescent
git pull
git checkout v2.0.0
make install
```

# check the version

```bash
# should be 2.0.0
crescentd version
# Should be commit 0b4a7f0e70814d1770c810ae801f42e1067519b4
crescentd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.crescent/cosmovisor/upgrades/v2.0.0/bin
cp $HOME/go/bin/crescentd $HOME/.crescent/cosmovisor/upgrades/v2.0.0/bin
```

# check the version again

```bash
# should be 2.0.0
$HOME/.crescent/cosmovisor/upgrades/v2.0.0/bin/crescentd version
```
