# Joining a testnet

## Using a local version

Assuming that you have following the [installation guide](../building/). You should now have `fetchd` and `fetchcli` successfully installed in your path. You can check this with the following command:

```bash
which fetchd
which fetchcli
```

You can also verify that you are running the correct version for the [network](../networks/).

```bash
fetchd version
fetchcli version
```

### Configuring the client `fetchcli`

In general to configure the CLI to point at a given network it needs as a minimum the following configuration values

```bash
fetchd config chain-id <stargateworld-1>
fetchd config node <https://rpc-stargateworld.fetch.ai:443>
```

**Stargate example**

In the case of the Stargate network this would be as follows:

```bash
fetchcli config chain-id stargateworld-1
fetchcli config node https://rpc-stargateworld.fetch.ai:443
```

### Configuring the server `fetchd`
@@ -74,18 +37,18 @@ Finally connect fetchd to the network by getting it to connect to a seed node fo
fetchd start --p2p.seeds=<network seed peers>
```
**Stargate Example**
Less abstractly then, if a user wants to connect to the Stargate test net for example. You would need to run the following steps:
```bash
# init
fetchd init my-first-fetch-node --chain-id stargateworld-1
# genesis
curl https://rpc-stargateworld.fetch.ai/genesis? | jq .result.genesis > ~/.fetchd/config/genesis.json
# start
fetchd start --p2p.seeds=0831c7f4cb4b12fe02b35cc682c7edb03f6df36c@connect-stargateworld.t-v2-london-c.fetch-ai.com:36656
```
