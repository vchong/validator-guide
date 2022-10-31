# Chihuahua v3.1.0 Upgrade

The Upgrade is scheduled for block `4673333`. A countdown clock is [here](https://www.mintscan.io/chihuahua/blocks/4673333)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd chihuahua
git pull
git checkout v3.1.0
make install
```

# check the version

```bash
# should be v3.1.0
chihuahuad version
# Should be commit d6e9f55c5d7dbee8c6e2c3e34144a9b81ceae8c7
chihuahuad version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.chihuahua/cosmovisor/upgrades/v310/bin
cp $HOME/go/bin/chihuahuad $HOME/.chihuahua/cosmovisor/upgrades/v310/bin
```

# check the version again

```bash
# should be v3.1.0
$HOME/.chihuahua/cosmovisor/upgrades/v310/bin/chihuahuad version
```
