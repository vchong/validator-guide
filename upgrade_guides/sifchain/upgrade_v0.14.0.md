# Sifchain v0.14.0 Upgrade

The Upgrade is scheduled for block `8071370`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/8071370)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.14.0
make install
```

# check the version

```bash
# should be 0.14.0
sifnoded version
# Should be commit acb759c474d84eb20f27f98c80d2a6eeab7bee62
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.14.0/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.14.0/bin
```

# check the version again

```bash
# should be 0.14.0
$HOME/.sifnoded/cosmovisor/upgrades/0.14.0/bin/sifnoded version
```
