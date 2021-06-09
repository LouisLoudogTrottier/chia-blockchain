#### Usage: chia [OPTIONS] COMMAND [ARGS]...

  Manage chia blockchain infrastructure (1.1.7.dev176)
```
Options:
  --root-path PATH  Config file root  [default: /home/user/.chia/testnet7]
  -h, --help        Show this message and exit.

Commands:
  configure   Modify configuration
  farm        Manage your farm
  init        Create or migrate the configuration
  keys        Manage your keys
  netspace    Estimate total farmed space on the network
  plotnft     Manage your plot NFTs
  plots       Manage your plots
  run_daemon  Runs chia daemon
  show        Show node information
  start       Start service groups
  stop        Stop services
  version     Show chia version
  wallet      Manage your wallet

  Try 'chia start node', 'chia netspace -d 192', or 'chia show -s'
```

#### Usage: chia configure [OPTIONS]
```
Options:
  -t, --testnet [true|t|false|f]  configures for connection to testnet
  --set-node-introducer TEXT      Set the introducer for node - IP:Port
  --set-farmer-peer TEXT          Set the farmer peer for harvester - IP:Port
  --set-fullnode-port TEXT        Set the port to use for the fullnode, useful
                                  for testing

  -log-level, --set-log-level, --log-level [CRITICAL|ERROR|WARNING|INFO|DEBUG|NOTSET]
                                  Set the instance log level
  -upnp, --enable-upnp, --upnp [true|t|false|f]
                                  Enable or disable uPnP
  --set_outbound-peer-count TEXT  Update the target outbound peer count
                                  (default 8)

  --set-peer-count TEXT           Update the target peer count (default 80)
  -h, --help                      Show this message and exit.
```
#### Usage: chia farm [OPTIONS] COMMAND [ARGS]...
```
Options:
  -h, --help  Show this message and exit.

Commands:
  challenges  Show the latest challenges
  summary     Summary of farming information

#### Usage: chia init [OPTIONS]

  Create a new configuration or migrate from previous versions to current

  Follow these steps to create new certificates for a remote harvester:
  - Make a copy of your Farming Machine CA directory: ~/.chia/[version]/config/ssl/ca
  - Shut down all chia daemon processes with `chia stop all -d`
  - Run `chia init -c [directory]` on your remote harvester,
    where [directory] is the the copy of your Farming Machine CA directory
  - Get more details on remote harvester on Chia wiki:
    https://github.com/Chia-Network/chia-blockchain/wiki/Farming-on-many-machines

Options:
  -c, --create-certs PATH  Create new SSL certificates based on CA in
                           [directory]

  -h, --help               Show this message and exit.
```
#### Usage: chia keys [OPTIONS] COMMAND [ARGS]...
```
  Create, delete, view and use your key pairs

Options:
  -h, --help  Show this message and exit.

Commands:
  add                 Add a private key by mnemonic
  delete              Delete a key by its pk fingerprint in hex form
  delete_all          Delete all private keys in keychain
  generate            Generates and adds a key to keychain
  generate_and_print  Generates but does NOT add to keychain
  show                Displays all the keys in keychain
  sign                Sign a message with a private key
  verify              Verify a signature with a pk
```
#### Usage: chia netspace [OPTIONS]
```
  Calculates the estimated space on the network given two block header
  hashes.

Options:
  -p, --rpc-port INTEGER         Set the port where the Full Node is hosting
                                 the RPC interface. See the rpc_port under
                                 full_node in config.yaml. [default: 8555]

  -d, --delta-block-height TEXT  Compare a block X blocks older to estimate
                                 total network space. Defaults to 4608 blocks
                                 (~1 day) and Peak block as the starting
                                 block. Use --start BLOCK_HEIGHT to specify
                                 starting block. Use 192 blocks to estimate
                                 over the last hour.

  -s, --start TEXT               Newest block used to calculate estimated
                                 total network space. Defaults to Peak block.

  -h, --help                     Show this message and exit.

```
#### Usage: chia plotnft [OPTIONS] COMMAND [ARGS]...
```
Options:
  -h, --help  Show this message and exit.

Commands:
  create  Create a plot NFT
  show    Show plotnft information
```
#### Usage: chia plots [OPTIONS] COMMAND [ARGS]...
```
  Create, add, remove and check your plots

Options:
  -h, --help  Show this message and exit.

Commands:
  add     Adds a directory of plots
  check   Checks plots
  create  Create plots
  remove  Removes a directory of plots from config.yaml
  show    Shows the directory of current plots
```
#### Usage: chia run_daemon [OPTIONS]
```
Options:
  -h, --help  Show this message and exit.
```
#### Usage: chia show [OPTIONS]
```
Options:
  -p, --rpc-port INTEGER          Set the port where the Full Node is hosting
                                  the RPC interface. See the rpc_port under
                                  full_node in config.yaml

  -wp, --wallet-rpc-port INTEGER  Set the port where the Wallet is hosting the
                                  RPC interface. See the rpc_port under wallet
                                  in config.yaml

  -s, --state                     Show the current state of the blockchain
  -c, --connections               List nodes connected to this Full Node
  -e, --exit-node                 Shut down the running Full Node
  -a, --add-connection TEXT       Connect to another Full Node by ip:port
  -r, --remove-connection TEXT    Remove a Node by the first 8 characters of
                                  NodeID

  -bh, --block-header-hash-by-height TEXT
                                  Look up a block header hash by block height
  -b, --block-by-header-hash TEXT
                                  Look up a block by block header hash
  -h, --help                      Show this message and exit.
```
#### Usage: chia start [OPTIONS] [all|node|harvester|farmer|farmer-no-
                  wallet|farmer-only|timelord|timelord-only|timelord-launcher-
                  only|wallet|wallet-only|introducer|simulator]...
```
Options:
  -r, --restart  Restart running services
  -h, --help     Show this message and exit.
```
#### Usage: chia stop [OPTIONS] [all|node|harvester|farmer|farmer-no-wallet|farmer-
                 only|timelord|timelord-only|timelord-launcher-
                 only|wallet|wallet-only|introducer|simulator]...
```
Options:
  -d, --daemon  Stop daemon
  -h, --help    Show this message and exit.
```
#### Usage: chia version [OPTIONS]
```
Options:
  -h, --help  Show this message and exit.
```
#### Usage: chia wallet [OPTIONS] COMMAND [ARGS]...
```
Options:
  -h, --help  Show this message and exit.

Commands:
  get_address       Get a wallet receive address
  get_transaction   Get a transaction
  get_transactions  Get all transactions
  send              Send chia to another wallet
  show              Show wallet information
```
