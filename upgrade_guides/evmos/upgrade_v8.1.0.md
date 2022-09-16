# Evmos v8.1.0 Upgrade

The Upgrade is scheduled for block `4655500`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/4655500)

This guide assumes that you use cosmovisor to manage upgrades

# Install v8.1.0

```bash
# get the new version
cd evmos
git pull
git checkout v8.1.0
make install
```

# check the version

```bash
# should be 8.1.0
evmosd version
# Should be commit 7a57c44f74ace025764c28448f8be244210fe594
evmosd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v8.1.0/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v8.1.0/bin
```

# check the version again

```bash
# should be 8.1.0
$HOME/.evmosd/cosmovisor/upgrades/v8.1.0/bin/evmosd version
```
