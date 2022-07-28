# Terra 2.1.1 upgrade

The Upgrade is scheduled for block `890000`. A countdown clock is [here](https://ping.pub/terra2/gov/894)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd terra
git pull
git checkout v2.1.1
make install
```

# check the version

```bash
# should be v2.1.1
terrad version
# Should be commit 5b37c3db93dee63d8542d7c4adac77fd521787e7
terrad version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.terra/cosmovisor/upgrades/2.1.0/bin
cp $HOME/go/bin/terrad $HOME/.terra/cosmovisor/upgrades/2.1.0/bin
```

# check the version again

```bash
# should be v2.1.1
$HOME/.terra/cosmovisor/upgrades/2.1.0/bin/terrad version
```
