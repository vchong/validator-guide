# Sifchain 1.0.14-beta Upgrade

The Upgrade is scheduled for block `9263818`. A countdown clock is [here](https://www.mintscan.io/sifchain/blocks/9263818)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd sifchain
git pull
git checkout v1.0.14-beta
make install
```

# check the version

```bash
# should be 1.0.14-beta
sifnoded version
# Should be commit 02f2b8b3755ada1a51986e95eac815c47c7732f0
sifnoded version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sifnoded/cosmovisor/upgrades/1.0.14-beta/bin
cp $HOME/go/bin/sifnoded $HOME/.sifnoded/cosmovisor/upgrades/1.0.14-beta/bin
```

# check the version again

```bash
# should be 1.0.14-beta
$HOME/.sifnoded/cosmovisor/upgrades/1.0.14-beta/bin/sifnoded version
```
