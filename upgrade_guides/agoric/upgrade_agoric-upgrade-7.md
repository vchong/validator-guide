# Agoric agoric-upgrade-7 Upgrade

The Upgrade is scheduled for block `6263783`. A countdown clock is [here](https://ping.pub/agoric/gov/12)

This guide assumes that you use cosmovisor to manage upgrades

```bash
wget -O ag0 https://github.com/Agoric/ag0/releases/download/agoric-upgrade-7/ag0-agoric-upgrade-7-linux-amd64
chmod +x ag0
mv ag0 go/bin/
```

# check the version

```bash
# should be agoric-upgrade-7
ag0 version
# Should be commit ee4376c49b0931914e8e921ee4ded0026aafeeb8
ag0 version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-7/bin
cp $(which ag0) $HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-7/bin
```

# check the version again

```bash
# should be agoric-upgrade-7
$HOME/.agoric/cosmovisor/upgrades/agoric-upgrade-7/bin/ag0 version
```
