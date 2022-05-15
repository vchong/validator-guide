# Osmosis v8.0.0 Upgrade

The upgrade is scheduled for block `4402000`. A countdown clock is [here](https://www.mintscan.io/osmosis/blocks/4402000)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd osmosis
git pull
git checkout v8.0.0
make install
```

# check the version

```bash
# should be 8.0.0
osmosisd version
# Should be commit 16e3b51f19a58f815a4eabcbcee11886eb33e026
osmosisd version --long
```

# Copy binary

```bash
sudo service osmosis stop
cp $HOME/go/bin/osmosisd $HOME/.osmosisd/cosmovisor/current/bin
sudo service osmosis start
```

# check the version again

```bash
# should be 8.0.0
$HOME/.osmosisd/cosmovisor/current/bin/osmosisd version
```
