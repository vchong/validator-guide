# Stargaze 6 upgrade

The Upgrade is scheduled for block `3626432`. A countdown clock is [here](https://www.mintscan.io/stargaze/blocks/3626432)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd stargaze
git pull
git checkout v6.0.0
make install
```

# check the version

```bash
# should be v6.0.0
starsd version
# Should be commit b8294bc957300b07ed40981b1bd08adc548020b3
starsd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.starsd/cosmovisor/upgrades/v6/bin
cp $HOME/go/bin/starsd $HOME/.starsd/cosmovisor/upgrades/v6/bin
```

# check the version again

```bash
# should be v6.0.0
$HOME/.starsd/cosmovisor/upgrades/v6/bin/starsd version
```
