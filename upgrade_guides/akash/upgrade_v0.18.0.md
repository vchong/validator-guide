# Akash v0.18.0 Upgrade

The Upgrade is scheduled for block `8526250`. A countdown clock is [here](https://www.mintscan.io/akash/blocks/8526250)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd akash
git fetch --all
git checkout v0.18.0
make install
```

# check the version

```bash
# should be 0.18.0
akash version
# Should be commit 1324f29f656b6aba28e34af982c2ae8842fe863b
akash version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.akash/cosmovisor/upgrades/v0.18.0/bin
cp $(which akash) $HOME/.akash/cosmovisor/upgrades/v0.18.0/bin
```

# check the version again

```bash
# should be 0.18.0
$HOME/.akash/cosmovisor/upgrades/v0.18.0/bin/akash version
```
