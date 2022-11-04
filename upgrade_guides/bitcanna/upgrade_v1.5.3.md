# Bitcanna v1.5.3 Upgrade

The Upgrade is scheduled for block `5787420`. A countdown clock is [here](https://www.mintscan.io/bitcanna/blocks/5787420)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd bitcanna
git pull
git checkout v1.5.3
make install
```

# check the version

```bash
# should be 1.5.3
bcnad version
# should be 73092a570571045ed44e00ede7a01a016af44b61
bcnad version --long | grep commit
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.bcna/cosmovisor/upgrades/trichomemonster-ica/bin
cp $HOME/go/bin/bcnad $HOME/.bcna/cosmovisor/upgrades/trichomemonster-ica/bin
```

# check the version again

```bash
# should be 1.5.3
$HOME/.bcna/cosmovisor/upgrades/trichomemonster-ica/bin/bcnad version
```
