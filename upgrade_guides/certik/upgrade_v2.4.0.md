# Certik 2.4.0 Upgrade

The Upgrade is scheduled for block `8705500`. A countdown clock is [here](https://www.mintscan.io/certik/blocks/8705500)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd certik
git pull
git checkout v2.4.0
make install
```

# check the version

```bash
# should be 2.4.0
certik version
# Should be commit 40ac4746a60405074281405972037ac0114cb82b
certik version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.certik/cosmovisor/upgrades/Shield-V2/bin
cp $HOME/go/bin/certik $HOME/.certik/cosmovisor/upgrades/Shield-V2/bin
```

# check the version again

```bash
# should be 2.4.0
$HOME/.certik/cosmovisor/upgrades/Shield-V2/bin/certik version
```
