# Axelar v0.18.3 Upgrade

```bash
AXELARD_RELEASE=v0.18.3
wget https://github.com/axelarnetwork/axelar-core/releases/download/$AXELARD_RELEASE/axelard-linux-amd64-$AXELARD_RELEASE
mv axelard-linux-amd64-v0.18.3 axelard
chmod +x axelard
mv axelard /home/ubuntu/go/bin
axelard version
```

```bash
mkdir  /home/ubuntu/.axelar/cosmovisor/upgrades/v0.18/bin/ -p
cp /home/ubuntu/go/bin/axelard /home/ubuntu/.axelar/cosmovisor/upgrades/v0.18/bin/
```

```bash
AXELARD_RELEASE=v0.19.2
wget https://github.com/axelarnetwork/axelar-core/releases/download/$AXELARD_RELEASE/axelard-linux-amd64-$AXELARD_RELEASE
mv axelard-linux-amd64-v0.19.2 axelard
chmod +x axelard
mv axelard /home/ubuntu/go/bin
axelard version
```

```bash
mkdir  /home/ubuntu/.axelar/cosmovisor/upgrades/v0.19/bin/ -p
cp /home/ubuntu/go/bin/axelard /home/ubuntu/.axelar/cosmovisor/upgrades/v0.19/bin/
```
