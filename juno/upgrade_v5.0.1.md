# Juno v5.0.1 Upgrade

The Upgrade is scheduled for block `3035000 `. A countdown clock is [here](https://www.mintscan.io/juno/blocks/3035000)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd juno
git pull
git checkout v5.0.1
make install
```

# check the version

```bash
# should be v5.0.1
junod version
# Should be commit 77fdc2e9b0b380f640286745356384c64d86fd32
junod version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.juno/cosmovisor/upgrades/veritas/bin
cp $HOME/go/bin/junod $HOME/.juno/cosmovisor/upgrades/veritas/bin
```

# check the version again

```bash
# should be v5.0.1
$HOME/.juno/cosmovisor/upgrades/veritas/bin/junod version
```
