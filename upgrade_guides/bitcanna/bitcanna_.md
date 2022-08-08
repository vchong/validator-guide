# Bitcanna strangeBuddheads Upgrade

The Upgrade is scheduled for block `4490420`. A countdown clock is [here](https://www.mintscan.io/bitcanna/blocks/4490420)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd bitcanna
git pull
git checkout v1.4.1
make install
```

# check the version

```bash
# should be 1.4.1
bcnad version
# Should be commit 83b2334d5f76da6abf4915dcc5f244b75443be7c
bcnad version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.bcna/cosmovisor/upgrades/strangeBuddheads/bin
cp $HOME/go/bin/bcnad $HOME/.bcna/cosmovisor/upgrades/strangeBuddheads/bin
```

# check the version again

```bash
# should be 1.4.1
$HOME/.bcna/cosmovisor/upgrades/strangeBuddheads/bin/bcnad version
```
