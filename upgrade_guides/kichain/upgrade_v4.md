# Kichain v4 Upgrade

The upgrade is scheduled for block `11830000`. A countdown clock is [here](https://www.mintscan.io/ki-chain/blocks/11830000)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd kichain
git pull
git checkout 4.0.0
make install
```

# check the version

```bash
# should be Mainnet-4.0.0
kid version
# Should be commit b004902f91807096a3d3700edd862bfb711aee54
kid version --long
```

# Copy binary

```bash
mkdir -p $HOME/.kid/cosmovisor/upgrades/v4/bin
cp $HOME/go/bin/kid $HOME/.kid/cosmovisor/upgrades/v4/bin
```

# check the version again

```bash
# should be Mainnet-4.0.0
$HOME/.kid/cosmovisor/upgrades/v4/bin/kid version
```
