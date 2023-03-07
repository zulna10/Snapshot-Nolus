# Snapshot-Nolus

# Services

**Chain ID**: nolus-rila | **Latest Version Tag**: v0.1.43 | **Wasm**: ON


## Public endpoints

* api: [https://api.nolus.zulnaaa.com](https://api.nolus.zulnaaa.com)
* rpc: [https://rpc.nolus.zulnaaa.com](https://rpc.nolus.zulnaaa.com)
* Snapshot : [https://snapshot.nolus.zulnaaa.com](https://snapshot.nolus.zulnaaa.com)

# Snapshot

## Instructions



### Stop the service and reset the data

```bash
sudo systemctl stop nolusd
cp $HOME/.nolus/data/priv_validator_state.json $HOME/.nolus/priv_validator_state.json.backup
rm -rf $HOME/.nolus/data
```

### Download latest snapshot

```bash
curl -L http://snapshot.nolus.zulnaaa.com/nolus/nolus-snapshot.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.nolus
mv $HOME/.nolus/priv_validator_state.json.backup $HOME/.nolus/data/priv_validator_state.json
```

### Restart the service and check the log

```bash
sudo systemctl start nolusd && sudo journalctl -u nolusd -f --no-hostname -o cat
```

