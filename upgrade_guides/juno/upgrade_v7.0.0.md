# Juno v7.0.0 Upgrade

The Upgrade is scheduled for block `3851750`. A countdown clock is [here](https://www.mintscan.io/juno/blocks/3851750)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd juno
git pull
git checkout v7.0.0
make install
```

# check the version

```bash
# should be v7.0.0
junod version
# Should be commit 1291b66f3cd3529ad244391619f7b4166bb28373
junod version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.juno/cosmovisor/upgrades/multiverse/bin
cp $HOME/go/bin/junod $HOME/.juno/cosmovisor/upgrades/multiverse/bin
```

# check the version again

```bash
# should be v7.0.0
$HOME/.juno/cosmovisor/upgrades/multiverse/bin/junod version
```
