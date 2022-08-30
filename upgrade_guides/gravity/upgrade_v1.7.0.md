# Gravity v1.7.0

The Upgrade is scheduled for block `3608063`. A countdown clock is [here](https://www.mintscan.io/gravity-bridge/blocks/3608063)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
wget https://github.com/Gravity-Bridge/Gravity-Bridge/releases/download/v1.7.0/gravity-linux-amd64
mv gravity-linux-amd64 $HOME/go/bin/gravity
chmod +x $HOME/go/bin/gravity
```

# check the version

```bash
# should be v1.7.0
gravity version
# Should be commit ???
gravity version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.gravity/cosmovisor/upgrades/pleiades/bin
cp $HOME/go/bin/gravity $HOME/.gravity/cosmovisor/upgrades/pleiades/bin
```

# check the version again

```bash
# should be v1.7.0
$HOME/.gravity/cosmovisor/upgrades/pleiades/bin/gravity version
```
