# Evmos v8.2.0 Upgrade

The Upgrade is scheduled for block `4888000`. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/4888000)

This guide assumes that you use cosmovisor to manage upgrades

# Install v8.2.0

```bash
# get the new version
cd evmos
git pull
git checkout v8.2.0
make install
```

# check the version

```bash
# should be 8.2.0
evmosd version
# Should be commit 7831a9fe11e8121e0371862c809a74c6f9884e28
evmosd version --long
```

# Stop cosmovisor

```bash
sudo service cosmovisor stop
```

# Copy binary to the v8.1.0 folder

```bash
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v8.1.0/bin
```

# check the version again

```bash
# should be 8.2.0
$HOME/.evmosd/cosmovisor/upgrades/v8.1.0/bin/evmosd version
```

# Start cosmovisor

```bash
sudo service cosmovisor start
```
