# Fetch v0.10.5 Upgrade

The upgrade is scheduled for block `7305500`. A countdown clock is [here](https://www.mintscan.io/fetchai/blocks/7305500)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd fetch
git pull
git checkout v0.10.5
make install
```

# check the version

```bash
# should be v0.10.5
fetchd version
# Should be commit 7e4a5ce244676a3ea780944e6f9bcba283333ebd
fetchd version --long
```

# Copy binary

```bash
mkdir -p $HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.5/bin
cp $HOME/go/bin/fetchd $HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.5/bin
```

# check the version again

```bash
# should be v0.10.5
$HOME/.fetchd/cosmovisor/upgrades/fetchd-v0.10.5/bin/fetchd version
```
