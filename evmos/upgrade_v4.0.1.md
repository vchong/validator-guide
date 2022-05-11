# Evmos v4.0.1 Upgrade

The Upgrade is scheduled for block `257850 `. A countdown clock is [here](https://www.mintscan.io/evmos/blocks/257850)

This guide assumes that you use cosmovisor to manage upgrades

First upgrade the current version to v3.0.2

```bash
# get the new version
cd evmos
git pull
git checkout v3.0.2
make install
```

# check the version

```bash
# should be 3.0.2
evmosd version
# Should be commit a6203ad696015dd6296d04279bf089e6c4afcffd
evmosd version --long
```

# copy binary

```bash
sudo service evmos stop
```

```bash
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/genesis/bin
```

# check the version again

```bash
# should be v3.0.2
$HOME/.evmosd/cosmovisor/genesis/bin/evmosd version
```

```bash
sudo service evmos start
```

# Real upgrade

```bash
# get the new version
git checkout v4.0.1
make install
```

# check the version

```bash
# should be 4.0.1
evmosd version
# Should be commit 2a714e12653e12548cb861f35dbbc69c4a2e09a2
evmosd version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.evmosd/cosmovisor/upgrades/v4.0.1/bin
cp $HOME/go/bin/evmosd $HOME/.evmosd/cosmovisor/upgrades/v4.0.1/bin
```

# check the version again

```bash
# should be 4.0.1
$HOME/.evmosd/cosmovisor/upgrades/v4.0.1/bin/evmosd version
```
