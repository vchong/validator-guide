# Evmos v7.0.0 Upgrade

The Upgrade is scheduled for block `2476000`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/2476000)

This guide assumes that you use cosmovisor to manage upgrades

# Install v7.0.0

```bash
# get the new version
cd evmos
git pull
git checkout v7.0.0
make install
```

# check the version

```bash
# should be 7.0.0
evmosd version
# Should be commit a1c4b7af4cecd908d703a00bbb808c66ea61ab8a
evmosd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v7.0.0/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v7.0.0/bin
```

# check the version again

```bash
# should be 7.0.0
$HOME/.evmosd/cosmovisor/upgrades/v7.0.0/bin/evmosd version
```
