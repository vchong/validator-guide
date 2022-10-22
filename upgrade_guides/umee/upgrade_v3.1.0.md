# Umee v3.1.0 upgrade

The Upgrade is scheduled for block `3623090`. A countdown clock is [here](https://www.mintscan.io/umee/blocks/3623090)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd umee
git pull
git checkout v3.1.0
make install
```

# check the version

```bash
# should be v3.1.0
umeed version
# Should be commit ff503f4b760ad0423d7dab42d7b5da91a9c001a1
umeed version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.umee/cosmovisor/upgrades/v3.1.0/bin
cp $HOME/go/bin/umeed $HOME/.umee/cosmovisor/upgrades/v3.1.0/bin
```

# check the version again

```bash
# should be v3.1.0
$HOME/.umee/cosmovisor/upgrades/v3.1.0/bin/umeed version
```

# If you are a validator, take care of Peggo and Price Feeder during upgrade
