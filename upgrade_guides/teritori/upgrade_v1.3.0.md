# Teritori v1.3.0 Upgrade

The Upgrade is scheduled for block `378256`. A countdown clock is [here](https://explorer.teritori.com/teritori/gov/4)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd teritori
git pull
git checkout v1.3.0
make install
```

# check the version

```bash
# should be 1.3.0
teritorid version
# Should be commit c0e74d294f36882aa2c18a785d753349c2a322ef
teritorid version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.teritorid/cosmovisor/upgrades/v1.3.0/bin
cp $HOME/go/bin/teritorid $HOME/.teritorid/cosmovisor/upgrades/v1.3.0/bin
```

# check the version again

```bash
# should be v1.3.0
$HOME/.teritorid/cosmovisor/upgrades/v1.3.0/bin/teritorid version
```
