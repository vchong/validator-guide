# Evmos v8.0.0 Upgrade

The Upgrade is scheduled for block `3620000`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/3620000)

This guide assumes that you use cosmovisor to manage upgrades

# Install v8.0.0

```bash
# get the new version
cd evmos
git pull
git checkout v8.0.0
make install
```

# check the version

```bash
# should be 8.0.0
evmosd version
# Should be commit 9aba6f4fd4c3bc6772c503a2c459111065aba3d8
evmosd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v8.0.0/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v8.0.0/bin
```

# check the version again

```bash
# should be 8.0.0
$HOME/.evmosd/cosmovisor/upgrades/v8.0.0/bin/evmosd version
```
