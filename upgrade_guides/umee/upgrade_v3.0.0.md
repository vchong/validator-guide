# Umee v3.0.0 upgrade

The Upgrade is scheduled for block `3215778`. A countdown clock is [here](https://www.mintscan.io/umee/blocks/3215778)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd umee
git pull
git checkout v3.0.0
make install
```

# check the version

```bash
# should be HEAD-ae43ccbd25c382cdfc5bcde26f21bc2002be5bf3
umeed version
# Should be commit ae43ccbd25c382cdfc5bcde26f21bc2002be5bf3
umeed version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.umee/cosmovisor/upgrades/v1.1-v3.0/bin
cp $HOME/go/bin/umeed $HOME/.umee/cosmovisor/upgrades/v1.1-v3.0/bin
```

# check the version again

```bash
# should be HEAD-ae43ccbd25c382cdfc5bcde26f21bc2002be5bf3
$HOME/.umee/cosmovisor/upgrades/v1.1-v3.0/bin/umeed version
```

# If you are a validator, take care of Peggo and Price Feeder during upgrade
