# Kava v0.19.0 Upgrade

The upgrade is scheduled for block `2098400`. A countdown clock is [here](https://www.mintscan.io/kava/blocks/2098400)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd kava
git pull
git checkout v0.19.0
make install
```

# check the version

```bash
# should be 0.19.0
kava version
# Should be commit 0ba73ff0417cdd246150de56fa29695e8d19fe36
kava version --long | grep commit
```

# Copy binary

```bash
mkdir -p $HOME/.kava/cosmovisor/upgrades/v0.19.0/bin
cp $HOME/go/bin/kava $HOME/.kava/cosmovisor/upgrades/v0.19.0/bin
```

# check the version again

```bash
# should be 1.19.0
$HOME/.kava/cosmovisor/upgrades/v0.19.0/bin/kava version
```
