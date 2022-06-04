# Fetch v0.10.4 Upgrade

The upgrade is scheduled for block `6295500`. A countdown clock is [here](https://www.mintscan.io/fetchai/blocks/6295500)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd fetch
git pull
git checkout v0.10.4
make install
```

# check the version

```bash
# should be v0.10.4
fetchd version
# Should be commit fda87e54332e5d6501a1f297dbf7508cccd303bc
fetchd version --long
```

# Copy binary

```bash
mkdir -p $HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.4/bin
cp $HOME/go/bin/fetchd $HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.4/bin
```

# check the version again

```bash
# should be v0.10.4
$HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.4/bin/fetchd version
```
