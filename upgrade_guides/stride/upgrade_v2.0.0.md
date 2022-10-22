# Stride v2.0.0 upgrade

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd stride
git pull
git checkout v2.0.0
make install
```

# check the version

```bash
# should be v2.0.0
strided version
# Should be commit ff1d2f9ab4512bcfc11b483ada3adb7357ca6c59
strided version --long | head
```

# Copy binary

```bash
mkdir -p $HOME/.stride/cosmovisor/upgrades/v2/bin
cp $HOME/go/bin/strided $HOME/.stride/cosmovisor/upgrades/v2/bin
```

# check the version again

```bash
# should be v2.0.0
$HOME/.stride/cosmovisor/upgrades/v2/bin/strided version
```
