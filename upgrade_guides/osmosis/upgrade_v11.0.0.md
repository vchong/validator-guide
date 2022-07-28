# Osmosis v11.0.0 Upgrade

The upgrade is scheduled for block `5432450`. A countdown clock is [here](https://www.mintscan.io/osmosis/blocks/5432450)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd osmosis
git pull
git checkout v11.0.0
make install
```

# check the version

```bash
# should be 11.0.0
osmosisd version
# Should be commit 4800c2be72bf643ad0bb68386aaa5a27824f2da3
osmosisd version --long
```

# Copy binary

```bash
mkdir -p $HOME/.osmosisd/cosmovisor/upgrades/v11/bin
cp $HOME/go/bin/osmosisd $HOME/.osmosisd/cosmovisor/upgrades/v11/bin
```

# check the version again

```bash
# should be 11.0.0
$HOME/.osmosisd/cosmovisor/upgrades/v11/bin/osmosisd version
```
