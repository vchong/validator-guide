# Juno v4.0.0 Upgrade

The Upgrade is scheduled for block `118040`.

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd jackal
git pull
git checkout v1.2.0
make install
```

# check the version

```bash
# should be 1.1.0
canined version
# Should be commit 299fe4bdee7a7a8b45cd2776359243fdf3630e5a
canined version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.juno/cosmovisor/upgrades/unity/bin
cp $HOME/go/bin/canined $HOME/.juno/cosmovisor/upgrades/unity/bin
```

# check the version again

```bash
# should be v4.0.0
$HOME/.juno/cosmovisor/upgrades/unity/bin/canined version
```
