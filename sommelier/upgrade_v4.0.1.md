# Sommelier v4.0.1 Upgrade

The Upgrade is scheduled for block `3610000`.

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
wget https://github.com/PeggyJV/sommelier/releases/download/v4.0.1/sommelier_4.0.1_linux_amd64.tar.gz
tar -xf sommelier_4.0.1_linux_amd64.tar.gz
sudo mv sommelier /usr/bin
rm -rf sommelier_4.0.1_linux_amd64* LICENSE README.md
```

# check the version

```bash
# should be 4.0.1
sommelier version
# Should be commit d3ba28a65be54faf87a4976e25a80a023417d9a8
sommelier version --long
```

# Make new directory and copy binary

```bash
mkdir -p $HOME/.sommelier/cosmovisor/upgrades/v4/bin
cp /usr/bin/sommelier $HOME/.sommelier/cosmovisor/upgrades/v4/bin
```

# check the version again

```bash
# should be 4.0.1
$HOME/.sommelier/cosmovisor/upgrades/v4/bin/sommelier version
```
