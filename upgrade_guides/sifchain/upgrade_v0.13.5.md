# Sifchain v0.13.5 Upgrade

The Upgrade is scheduled for block `7872730`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/7872730)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.5
make install
```

# check the version

```bash
# should be 0.13.5
sifnoded version
# Should be commit 06521bae0d28e041a687eb980b288c06fdfc6c21
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.5/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.5/bin
```

# check the version again

```bash
# should be 0.13.5
$HOME/.sifnoded/cosmovisor/upgrades/0.13.5/bin/sifnoded version
```
