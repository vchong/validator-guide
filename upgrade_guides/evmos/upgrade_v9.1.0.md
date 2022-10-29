# Evmos v9.1.0 Upgrade

The Upgrade is scheduled for block `6654000`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/6654000)

This guide assumes that you use cosmovisor to manage upgrades

# Install v9.1.0

```bash
# get the new version
cd evmos
git pull
git checkout v9.1.0
make install
```

# check the version

```bash
# should be 9.1.0
evmosd version
# Should be commit 80c38f659a65a983b221e2a568c6172b8ac3bffc
evmosd version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v9.1.0/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v9.1.0/bin
```

# check the version again

```bash
# should be 9.1.0
$HOME/.evmosd/cosmovisor/upgrades/v9.1.0/bin/evmosd version
```
