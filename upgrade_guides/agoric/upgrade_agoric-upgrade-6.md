# Agoric agoric-upgrade-6 Upgrade

The Upgrade is scheduled for block `5901622`. A countdown clock is [here](https://ping.pub/agoric/gov/9)

This guide assumes that you use cosmovisor to manage upgrades

```bash
wget -O ag0 https://github.com/Agoric/ag0/releases/download/agoric-upgrade-6/ag0-agoric-upgrade-6-linux-amd64
chmod +x ag0
mv ag0 go/bin/
```

# check the version

```bash
# should be agoric-upgrade-6
ag0 version
# Should be commit 31c78ba3aa872b54c4de448763c5b8044b8f950c
ag0 version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-6/bin
cp $(which ag0) $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-6/bin
```

# check the version again

```bash
# should be agoric-upgrade-6
$HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-6/bin/ag0 version
```
