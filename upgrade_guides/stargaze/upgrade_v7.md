# Stargaze v7.0.0 upgrade

The Upgrade is scheduled for block `4448796`. A countdown clock is [here](https://www.mintscan.io/stargaze/blocks/4448796)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd stargaze
git pull
git checkout v7.0.0
make install
```

# check the version

```bash
# should be 7.0.0
starsd version
# Should be commit b0bea28fc695a2a5c567e56a37b289a5b75830cc
starsd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.starsd/cosmovisor/upgrades/v7/bin
cp $HOME/go/bin/starsd $HOME/.starsd/cosmovisor/upgrades/v7/bin
```

# check the version again

```bash
# should be 7.0.0
$HOME/.starsd/cosmovisor/upgrades/v7/bin/starsd version
```
