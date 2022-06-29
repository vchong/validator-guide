# Evmos v6.0.1 Upgrade

The Upgrade is scheduled for block `1042000`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/1042000)

This guide assumes that you use cosmovisor to manage upgrades

# Install v6.0.1

```bash
# get the new version
cd evmos
git pull
git checkout v6.0.1
make install
```

# check the version

```bash
# should be 6.0.1
evmosd version
# Should be commit df1b5fe47621bd4b16ab89165f3e8926e96fb0f1
evmosd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v6.0.1/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v6.0.1/bin
```

# check the version again

```bash
# should be 6.0.1
$HOME/.evmosd/cosmovisor/upgrades/v6.0.1/bin/evmosd version
```
