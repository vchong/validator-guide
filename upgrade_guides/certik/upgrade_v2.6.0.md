# Certik 2.6.0 Upgrade

The Upgrade is scheduled for block `10485430`. A countdown clock is [here](https://www.mintscan.io/certik/blocks/10485430)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd certik
git pull --force --tag
git checkout v2.6.0
make install

# Because we use cosmovisor, this is a hack that is needed for a smooth handoff between two binaries
mv ~/go/bin/shentud ~/go/bin/certik
ln -s ~/.certik/ ~/.shentud
```

# check the version

```bash
# should be 2.6.0
certik version
# Should be commit cb63bff6d1eeec29d6ca130795fdde0cd94e4b88
certik version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.certik/cosmovisor/upgrades/v2.6.0/bin
cp $HOME/go/bin/certik $HOME/.certik/cosmovisor/upgrades/v2.6.0/bin
```

# check the version again

```bash
# should be 2.6.0
$HOME/.certik/cosmovisor/upgrades/v2.6.0/bin/certik version
```
