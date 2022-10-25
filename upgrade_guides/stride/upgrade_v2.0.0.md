# Stride v2.0.3 upgrade (notice it is v2.0.3!)

The Upgrade is scheduled for block `754555`. A countdown clock is [here](https://www.mintscan.io/stride/blocks/754555)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd stride
git pull
git checkout v2.0.3
make install
```

# check the version

```bash
# should be v2.0.3
strided version
# Should be commit 650c9903b5adb7a4c4420f6bfcd3153c39308c77
strided version --long | grep commit
```

# Copy binary

```bash
mkdir -p $HOME/.stride/cosmovisor/upgrades/v2/bin
cp $HOME/go/bin/strided $HOME/.stride/cosmovisor/upgrades/v2/bin
```

# check the version again

```bash
# should be v2.0.3
$HOME/.stride/cosmovisor/upgrades/v2/bin/strided version
```
