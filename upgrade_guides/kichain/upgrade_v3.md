# Kichain v3 Upgrade

The upgrade is scheduled for block `10155750`. A countdown clock is [here](https://www.mintscan.io/ki-chain/blocks/10155750)

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd kichain
git pull
git checkout 3.0.0
make install
```

# check the version

```bash
# should be Mainnet-3.0.0
kid version
# Should be commit dac9a74443d5cdc9d9a87214e03d77d3e2f7883d
kid version --long
```

# Copy binary

```bash
mkdir -p $HOME/.kid/cosmovisor/upgrades/v3/bin
cp $HOME/go/bin/kid $HOME/.kid/cosmovisor/upgrades/v3/bin
```

# check the version again

```bash
# should be Mainnet-3.0.0
$HOME/.kid/cosmovisor/upgrades/v3/bin/kid version
```
