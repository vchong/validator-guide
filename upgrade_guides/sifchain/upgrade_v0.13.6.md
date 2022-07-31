# Sifchain v0.13.6 Upgrade

The Upgrade is scheduled for block `7972597`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/7972597)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.6
make install
```

# check the version

```bash
# should be 0.13.6
sifnoded version
# Should be commit e3baa11f0943294f193adba4b470dd5de53bc573
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.6/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.6/bin
```

# check the version again

```bash
# should be 0.13.6
$HOME/.sifnoded/cosmovisor/upgrades/0.13.6/bin/sifnoded version
```
