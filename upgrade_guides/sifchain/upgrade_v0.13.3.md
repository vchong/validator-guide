# Sifchain v0.13.3 Upgrade

The Upgrade is scheduled for block `7041982`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/7041982)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifnoded
git pull
git checkout v0.13.3
make install
```

# check the version

```bash
# should be 0.13.3
sifnoded version
# Should be commit c904f56298886fc1dc57ce2b95133da81bce29e9
sifnoded version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/0.13.3/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/0.13.3/bin
```

# check the version again

```bash
# should be 0.13.3
$HOME/.sifnoded/cosmovisor/upgrades/0.13.3/bin/sifnoded version
```
