# Bitcanna v1.4.2 Upgrade

This guide assumes that you use cosmovisor to manage upgrades

```bash
# get the new version
cd bitcanna
git pull
git checkout v1.4.2
make install
```

# check the version

```bash
# should be 1.4.2
bcnad version
```

# Stop service

```bash
sudo service bitcanna stop
```

# Copy binary

```bash
cp $HOME/go/bin/bcnad $HOME/.bcna/cosmovisor/upgrades/strangeBuddheads/bin
```

# check the version again

```bash
# should be 1.4.2
$HOME/.bcna/cosmovisor/current/bin/bcnad version
```

# Start service

```bash
sudo service bitcanna start
```
