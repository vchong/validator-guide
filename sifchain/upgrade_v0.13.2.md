# Sifchain v0.13.2 Upgrade

The Upgrade is scheduled for block `6827526`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/6827526)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.2
make install
```

# check the version

```bash
# should be 0.13.2
sifnoded version
# Should be commit fcf0f3b633c021735f3b712c39c91729617746e3
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.2/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.2/bin
```

# check the version again

```bash
# should be 0.13.2
$HOME/.sifnoded/cosmovisor/upgrades/0.13.2/bin/sifnoded version
```
