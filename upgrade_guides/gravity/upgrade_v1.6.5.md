# Gravity v1.6.5

The Upgrade is scheduled for block `2860730`. A countdown clock is [here](https://www.mintscan.io/gravity-bridge/blocks/2860730)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
wget https://github.com/Gravity-Bridge/Gravity-Bridge/releases/download/v1.6.5/gravity-linux-amd64
mv gravity-linux-amd64 $HOME/go/bin/gravity
chmod +x $HOME/go/bin/gravity
```

# check the version

```bash
# should be v1.6.5
gravity version
# Should be commit 190083023b6d4b68b92bf81a93b1983bbb79b436
gravity version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.gravity/cosmovisor/upgrades/polaris/bin
cp $HOME/go/bin/gravity $HOME/.gravity/cosmovisor/upgrades/polaris/bin
```

# check the version again

```bash
# should be v1.6.5
$HOME/.gravity/cosmovisor/upgrades/polaris/bin/gravity version
```
