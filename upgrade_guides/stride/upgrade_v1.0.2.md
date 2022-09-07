# Stride v1.0.2 upgrade

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd stride
git pull
git checkout v1.0.2
make install
```

# check the version

```bash
# should be v6.0.0
strided version
# Should be commit b8294bc957300b07ed40981b1bd08adc548020b3
strided version --long | head
```

# Stop service

```bash
sudo service stride stop
```

# Copy binary

```bash
cp $HOME/go/bin/strided $HOME/.stride/cosmovisor/genesis/bin
```

# check the version again

```bash
# should be v1.0.2
$HOME/.stride/cosmovisor/current/bin/strided version
```

# Start service

```bash
sudo service stride start
```
