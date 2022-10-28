# Juno v11.0.0 Upgrade

The Upgrade is scheduled for block `5480000`. A countdown clock is [here](https://www.mintscan.io/juno/blocks/5480000)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd juno
git pull
git checkout v11.0.0
make install
```

# check the version

```bash
# should be v11.0.0
junod version
# Should be commit b27fc7d9312267b293d3355dd4a06523d76e247f
junod version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.juno/cosmovisor/upgrades/v11/bin
cp $HOME/go/bin/junod $HOME/.juno/cosmovisor/upgrades/v11/bin
```

# check the version again

```bash
# should be v11.0.0
$HOME/.juno/cosmovisor/upgrades/v11/bin/junod version
```

# One more thing:
Make sure to set this:

```
iavl-disable-fastnode = false
```