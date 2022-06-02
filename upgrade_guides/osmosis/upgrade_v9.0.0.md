# Osmosis v9.0.0 Upgrade

The upgrade is scheduled for block `4707300`. A countdown clock is [here](https://www.mintscan.io/osmosis/blocks/4707300)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd osmosis
git pull
git checkout v9.0.0
make install
```

# check the version

```bash
# should be 9.0.0
osmosisd version
# Should be commit 3a131a06366cb4de4590facc8b3ed2e704acdf6f
osmosisd version --long
```

# Copy binary

```bash
mkdir -p $HOME/.osmosisd/cosmovisor/upgrades/v9/bin
cp $HOME/go/bin/osmosisd $HOME/.osmosisd/cosmovisor/upgrades/v9/bin
```

# check the version again

```bash
# should be 9.0.0
$HOME/.osmosisd/cosmovisor/upgrades/v9/bin/osmosisd version
```
