# Sifchain v0.13.4 Upgrade

The Upgrade is scheduled for block `7672952`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/7672952)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.4
make install
```

# check the version

```bash
# should be 0.13.4
sifnoded version
# Should be commit c7cfe3f4ac7363ff4918510590c082954e0ef026
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.4/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.4/bin
```

# check the version again

```bash
# should be 0.13.4
$HOME/.sifnoded/cosmovisor/upgrades/0.13.4/bin/sifnoded version
```
