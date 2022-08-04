# Kava v0.18.0 Upgrade

The upgrade is scheduled for block `974569`. A countdown clock is [here](https://www.mintscan.io/kava/blocks/974569)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd kava
git pull
git checkout v0.18.0
make install
```

# check the version

```bash
# should be 0.18.0
kava version
# Should be commit 29096459253ce1edade676fe8651b87e729c89d8
kava version --long
```

# Copy binary

```bash
mkdir -p $HOME/.kava/cosmovisor/upgrades/v0.18.0/bin
cp $HOME/go/bin/kava $HOME/.kava/cosmovisor/upgrades/v0.18.0/bin
```

# check the version again

```bash
# should be 1.18.0
$HOME/.ava/cosmovisor/upgrades/v0.18.0/bin/kava version
```
