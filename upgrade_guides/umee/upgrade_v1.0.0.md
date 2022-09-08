# Umee v1.1.0 upgrade

The Upgrade is scheduled for block `3023282`. A countdown clock is [here](https://www.mintscan.io/umee/blocks/3023282)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd umee
git pull
git checkout v1.1.0
make install
```

# check the version

```bash
# should be v1.1.0
umeed version
# Should be commit f306c0c91bcd5625eef6bab6d3a851ac569100dd
umeed version --long | head
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.umee/cosmovisor/upgrades/v1.1.0/bin
cp $HOME/go/bin/umeed $HOME/.umee/cosmovisor/upgrades/v1.1.0/bin
```

# check the version again

```bash
# should be v1.1.0
$HOME/.umee/cosmovisor/upgrades/v1.1.0/bin/umeed version
```
