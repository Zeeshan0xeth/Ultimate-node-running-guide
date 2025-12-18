# 100 BASIC TOOLS, TERMS TO KNOW AND SOFTWERE NECESSARY FOR NODERUNNING.
- Ubuntu : means “Linux distribution”
This is one of the most popular operating systems for servers and node running.
e.g. A VPS with Ubuntu 20.04 or 22.04 is often required for testnets.
It’s stable, secure, and widely supported.

- Terminal : means “command-line interface”
Used to type in and run commands that control your system.
e.g. cd, ls, wget — all happen in the terminal.
This is where all node magic begins.


- SSH : means “Secure Shell”
Used to connect securely to your server from anywhere.
e.g. ssh root@your.vps.ip
This gives you remote control over the VPS where your node lives.


- VPS : means “Virtual Private Server”
It’s your personal remote computer in the cloud where your node runs.
Examples: Contabo, Hetzner, DigitalOcean.
e.g. a node needs 16GB RAM and 400GB SSD on a VPS.


- Docker : means “container system”
Used to run software in isolated environments called containers.
e.g. docker run aztecprotocol/aztec
This helps avoid “it works on my machine” problems.


- Docker Compose : means “Docker manager for multiple services”
Used to manage multi-container setups with one config file.
e.g. docker-compose up -d
This spins up several services (like validator + RPC) at once.

- wget : means “web get”
Used to download files directly from a link.
e.g. wget https://github.com/project.tar.gz
This grabs installation scripts or packages.

- curl : means “client URL”
Similar to wget, but can also interact with APIs.
e.g. curl -X POST http://localhost:8545
This is useful for testing if your RPC is live.

- screen : means “terminal session manager”
Lets you run node processes that keep running after you log out.
e.g. screen -S node1 then Ctrl+A+D to detach.
This is essential for long-term uptime.

- tmux : means “terminal multiplexer”
An alternative to screen, with more advanced features.
e.g. tmux new -s swarm
Lets you split your terminal and multitask inside one window.

- apt : means “Advanced Package Tool”
Used to install and manage software on Ubuntu.
e.g. sudo apt install docker
It’s how you get the necessary tools installed.

- .env file : means “environment file”
Stores secrets like private keys and settings.
e.g. PRIVATE_KEY=0xabc...
Used by Docker or scripts to configure your node securely.

- YAML : means “Yet Another Markup Language”
Used in docker-compose.yml to define services.
e.g. used to describe how containers should start.
Easy to read, but spacing is crucial.

- RPC : means “Remote Procedure Call”
It’s how apps talk to the blockchain through your node.
e.g. http://localhost:8545 is a common Ethereum-style RPC.
Used to query balances, send txs, etc.

- Git : means “version control system”
Used to download and manage source code.
e.g. git clone https://github.com/fhenix-network/fhenix
Let’s you pull latest versions of node software.

- Node Logs : means “live activity record”
They show what your node is doing and any errors.
e.g. docker logs -f aztec-node
This is how you troubleshoot syncing or peer issues.

- Syncing : means “downloading blockchain history”
Your node must sync to the current block before fully working.
Can take hours or days depending on chain.
e.g. Aztec, Ethereum, and Mina need full sync.

- Ports : means “entry points for data”
Each service (like RPC, P2P, Metrics) uses a different port.
e.g. Port 8545 for RPC, 30303 for Ethereum P2P
You need to open these in your VPS firewall.

- Firewall : means “traffic filter”
Controls which ports and IPs can access your node.
e.g. ufw allow 8545
Keep your node secure by only allowing needed traffic.

- Crontab : means “auto-scheduler”
Used to automate node restarts or checks.
e.g. crontab -e then add @reboot26  docker start mynode
Keeps your node up even after a reboot.

- Validator : means “block checker and attester”
A node type that helps verify and add blocks to a blockchain.
e.g. Ethereum validators earn ETH for securing the network.
Running one usually requires staking and uptime.

- Full Node : means “complete chain storage”
Stores the entire blockchain history and participates in network validation.
e.g. Bitcoin and Ethereum full nodes.
This is what most testnet tasks require.
⸻
- Light Node : means “partial chain data only”
Connects to full nodes and verifies with less data.
e.g. used in wallets like MetaMask for speed.
Not suitable for validating or earning rewards.

- Bootstrap Node : means “initial peer connector”
Helps new nodes find other nodes in the network.
Needed for P2P connection during setup.
Often predefined in config files.

- P2P (Peer-to-Peer) : means “nodes talk directly”
Used for decentralization — nodes share data without central servers.
e.g. your node connects to others to sync blocks.
Each node helps others stay up to date.

- Seed Phrase : means “wallet recovery phrase”
A 12–24 word backup that unlocks your wallet or node identity.
e.g. gospel suggest sad actor ...
Must be stored securely — it’s your private key.

- Private Key : means “your digital signature”
Used to prove ownership and sign transactions.
Stored in .env or injected by node software.
Never share it — anyone can steal your wallet with it.

- Public Key / Address : means “your wallet ID”
Used to receive funds, tokens, or testnet airdrops.
e.g. 0xAbCd1234...
Safe to share — like your username on chain.

- YAML File : means “configuration file in readable format”
Used in docker-compose.yml and similar setups.
Spacing (indentation) is critical — no tabs allowed.
Defines what services to run and how.

- JSON : means “JavaScript Object Notation”
A data format often used in configs or logs.
e.g. many RPC responses and API configs come in JSON.
Used to set up some chains or wallet configs.

- Logs : means “activity records”
Tracks what your node is doing and when errors happen.
e.g. docker logs -f node
Helps you debug crashes or sync issues.

- Latency : means “delay in response”
Important when interacting with RPCs and other nodes.
Lower latency = faster performance.
Too much latency can drop peers or slow syncing.

- Uptime : means “how long your node stays online”
Nodes that go offline too often may get slashed or earn less.
Uptime is tracked by the chain or project dashboard.
Aim for 90–100% uptime on testnets.

- Slash/Slashing : means “punishment for bad behavior”
In staking networks, going offline or cheating can cost you stake.
e.g. Ethereum or Solana slashing.
Not common in testnets, but serious on mainnet.

- Metrics : means “performance data”
Nodes often expose metrics (CPU, memory, sync status) via ports.
e.g. localhost:9100/metrics
Can be visualized using Prometheus or Grafana.

- Prometheus : means “metrics collector”
A tool that gathers and monitors your node’s performance.
Often used with Grafana for dashboards.
e.g. docker-compose up prometheus grafana.

- Grafana : means “dashboard for metrics”
Visualizes Prometheus metrics with charts and alerts.
Helps track CPU, memory, peers, sync, etc.
Useful for large node setups.

- Snapshot : means “pre-synced chain backup”
Used to start a node without syncing from scratch.
e.g. wget chain.snapshot.gz then import it.
Saves days of syncing.

- Genesis File : means “blockchain starting point”
Defines the very first block and rules of the network.
Must match the chain you’re syncing to.
Usually downloaded from the official repo.

- Binary : means “compiled software”
Many nodes provide a .bin or executable you download and run.
e.g. ./node-linux-amd64
Must be compatible with your system (Intel or ARM).

- Faucet : means “testnet token dispenser”
Used to get free test tokens for running nodes or testing dApps.
e.g. https://faucet.testnet.project.com
You input your wallet address and receive tokens for gas.

- Testnet : means “test blockchain network”
Simulates a real blockchain for developers and node runners.
No real value — but activity may earn airdrops.
e.g. Holesky (Ethereum), Fhenix Devnet, Gensyn RL Swarm.

- Mainnet : means “main blockchain network”
Real funds, real risks — only run nodes here when fully ready.
Mainnets reward validators in real tokens.
e.g. Ethereum Mainnet, Celestia Mainnet.

- CLI : means “Command Line Interface”
Text-based interface to control node binaries and scripts.
e.g. ./gen-node status
Many chains have their own CLI tool for managing the node.

- .bashrc / .zshrc : means “shell configuration files”
Store aliases, environment variables, and setup routines.
e.g. adding export PATH=$PATH:/root/bin
This makes custom tools usable in terminal.

- systemd : means “Linux service manager”
Used to run nodes as background services that start on boot.
e.g. sudo systemctl start aztec
Keeps your node running automatically.

- RPC Endpoint : means “URL to access a node”
Used by wallets and apps to talk to your node.
e.g. http://127.0.0.1:8545
Can be public or private, depending on config.

- Peer Count : means “how many nodes you’re connected to”
Important for syncing and staying updated.
e.g. peer count: 0 means something is wrong.
The more peers, the healthier your node.

- Chain ID : means “unique network identifier”
Prevents accidental transactions on wrong chains.
e.g. Ethereum mainnet is 1, Goerli is 5, Holesky is 17000.
Must be set correctly in configs or CLI.

- Node Key : means “identity key for your node”
Used to identify and authorize your node in the network.
Usually auto-generated or stored in .nodekey.
Not the same as a wallet key.

- Epoch : means “unit of time in some blockchains”
Used to rotate validators, checkpoints, or reward cycles.
e.g. in Ethereum, an epoch is 32 blocks.
Important in staking chains.

- Checkpoint : means “verified point in the chain”
Used to speed up syncing and ensure node trust.
Some nodes start from latest checkpoint to skip validation.
Improves performance and reduces attack risk.

- Pruning : means “deleting old chain data”
Used to save disk space by removing unneeded blocks.
e.g. --pruning=fast
Be careful — may affect archival access.

- Archival Node : means “full node with complete history”
Stores every transaction and block from genesis.
Requires lots of storage (1TB+).
Useful for research and analytics.

- Validator Set : means “list of active validators”
Used in PoS networks to manage consensus.
Your node joins this set if you stake or get whitelisted.
Some chains rotate validators every few hours.

- Whitelisting : means “manual approval to join network”
Required for early testnets or secure networks.
e.g. you submit your wallet or node ID to a form.
Not all projects use this.

- Node ID : means “unique fingerprint for your node”
e.g. enode://... in Ethereum
Used for peers to recognize and connect to you.
Often displayed in logs or configs.

- Disk I/O : means “disk input/output speed”
Measures how fast your node reads/writes data.
Poor disk I/O = slow syncs or failed operations.
Use SSDs, not HDDs, for best performance.

- Resource Limits : means “CPU, RAM, disk quotas”
Some nodes need 8+ cores and 32GB RAM.
Check project docs before running on low-tier VPS.
Monitor usage with top or htop.

- Snapshot Restore : means “importing a pre-synced backup”
Used to skip full chain sync.
e.g. docker cp snapshot.tar.gz /data && tar -xvzf snapshot.tar.gz
Saves time and bandwidth.

- Ports (Opening/Forwarding) : means “unlocking network entry points”
To make your node publicly accessible, ports like 30303 (P2P), 8545 (RPC), or 26656 (Tendermint) must be open.
e.g. ufw allow 30303/tcp
Without open ports, your node won’t connect to peers.

- Firewall (UFW) : means “Uncomplicated Firewall”
Used to manage network rules on Ubuntu.
e.g. sudo ufw allow ssh and sudo ufw enable
Protects your node from unwanted traffic.

- Load Average : means “system demand”
Shows how much work your system is doing over 1, 5, and 15 mins.
e.g. 1.50 0.70 0.45 — higher = heavier load.
Use uptime or top to check this.

- htop : means “interactive system monitor”
Like Task Manager for Linux in your terminal.
e.g. htop
Shows CPU, memory, tasks, and lets you kill processes.

- Nginx : means “web server / reverse proxy”
Used to expose RPCs or dashboards securely.
e.g. https://my-node.xyz points to localhost:8545 via Nginx.
Great for custom domains.

- Reverse Proxy : means “forward web traffic internally”
Lets you expose a private service (like RPC) under a public URL.
e.g. Nginx forwards mydomain.com/rpc to localhost:8545.
Can be secured with SSL.

- SSL / TLS : means “Secure Socket Layer / Transport Layer Security”
Used to encrypt RPCs and dashboards.
e.g. https://my-node.com
Helps prevent MITM attacks or password leaks.

- Certbot : means “Let’s Encrypt tool for SSL”
e.g. sudo certbot --nginx
Used to generate free SSL certificates for Nginx or Apache.
Auto-renews, widely supported.

- Logrotate : means “log file management”
Prevents your logs from growing too big.
e.g. system logs rotate weekly by default.
Essential to avoid disk overflow on VPS.

- Symlink : means “shortcut to a file or folder”
e.g. ln -s /path/to/folder shortcut
Useful in node setups where paths change but configs expect a static one.

- Env Variable : means “config stored in memory”
Used in scripts, Docker, or CLIs to avoid hardcoding secrets.
e.g. export NODE_KEY=xyz123
Safer and more flexible.

- Watchdog Script : means “auto-restart on failure”
A simple script that checks your node status and restarts if needed.
e.g. bash watchdog.sh runs every 5 mins via cron.
Increases uptime during outages.

- Health Check : means “status check on your node”
Some nodes expose an endpoint (like /health) to check if they’re syncing or failing.
Used in monitoring dashboards or watchdogs.

- Fail2Ban : means “ban brute-force IPs”
Protects your VPS from SSH attacks.
e.g. sudo apt install fail2ban
Monitors logs and blocks suspicious behavior.

- Bridges : means “connect different blockchains”
Used in networks like Cosmos or Polkadot to link chains together.
Your node may support bridge relaying.

- Light Client : means “partial node for mobile apps”
Used in wallets to verify state without storing the chain.
Not useful for running full nodes — but good to understand.

- Docker Volume : means “persistent data storage in Docker”
e.g. -v node_data:/data
Keeps your chain data safe even if the container is removed.

- Entrypoint Script : means “initial script in Docker”
Runs setup tasks when a container starts.
e.g. entrypoint.sh might load your .env, pull genesis, and start syncing.

- Node Upgrade : means “switching to a newer version”
Required when testnets release fixes or mainnets fork.
e.g. stop node, pull new binary, restart.
Always follow changelogs before upgrading.

- Rollback : means “return to old version”
If a new version breaks your node, you may revert to a stable backup or older image.
e.g. use an older Docker tag: aztec:v1.3.2
Always keep backups.

- Foundry : means “Rust-based Ethereum development toolkit”
Blazing fast toolset for writing, testing, and deploying smart contracts.
e.g. forge test, forge deploy, cast call.
Favored by devs for its speed and clean workflow.

- Hardhat : means “JavaScript-based Ethereum dev environment”
Used to write, test, and deploy Solidity contracts.
e.g. npx hardhat run scripts/deploy.js
Great for scripting deployments, running local nodes, and testing contracts.

- Cargo : means “Rust package manager and build tool”
Used to compile Rust-based blockchains or tools.
e.g. cargo build --release
Projects like Substrate or Fhenix depend on it.

- Solc : means “Solidity compiler”
Used to compile Solidity smart contracts manually.
e.g. solc --optimize contract.sol
Behind-the-scenes engine in many dev tools.

- Remix IDE : means “web-based Solidity playground”
No-install browser tool to write, compile, and deploy contracts.
e.g. https://remix.ethereum.org
Useful for quick contract testing.

- Ganache : means “local Ethereum blockchain”
Simulates a blockchain for devs to test contracts instantly.
e.g. ganache-cli
Part of the Truffle Suite.

- Truffle : means “Ethereum dev framework (older alternative)”
Used for contract scaffolding, testing, and migrations.
e.g. truffle compile, truffle migrate
Still used but less popular than Foundry/Hardhat today.

- Anvil : means “local Ethereum node from Foundry”
Like Ganache, but blazing fast and Foundry-native.
e.g. anvil
Great for fast testing and simulated forks.

- Node.js : means “JavaScript runtime”
Needed to run tools like Hardhat, web3.js apps, or dApp frontends.
e.g. node scripts/mint.js
Make sure it’s installed on dev systems.

- NPM/Yarn : means “JavaScript package manager”
Used to install smart contract dependencies or web3 tools.
e.g. npm install ethers
Many Hardhat setups require npm install first.

- Ethers.js : means “JavaScript library for Ethereum”
Used to write scripts that interact with contracts.
e.g. const provider = new ethers.providers.JsonRpcProvider()
A lightweight alternative to web3.js.

- web3.js : means “Ethereum JS interaction library”
Older but still used to connect wallets, call contracts, etc.
e.g. web3.eth.getBalance()
Used more in frontend dApps.

- ABI : means “Application Binary Interface”
A contract’s instruction manual — needed to interact with it.
e.g. used by Hardhat, web3.js, etc. to send/read contract data.

- Bytecode : means “compiled contract code”
What’s actually deployed to the blockchain.
e.g. 0x6080604052...
Often comes from tools like Foundry, Hardhat, or Solc.

- CPU : means “Central Processing Unit”
The brain of your node — handles computation, consensus, encryption, and API responses.
e.g. multi-core (4–16 core) CPUs like AMD Ryzen or Intel Xeon are preferred.
More threads = smoother syncing and better multitasking.

- RAM : means “Random Access Memory”
Temporary memory used for fast operations.
e.g. 16GB RAM minimum is often required for nodes like Celestia, Aleo, or Fhenix.
More RAM = faster syncs, fewer crashes, more container headroom.

- Storage (SSD) : means “Solid State Drive”
Fast, reliable storage is non-negotiable.
e.g. Ethereum archival nodes need 1–2TB NVMe SSDs.
Avoid HDDs — they bottleneck syncs and kill node health.

- GPU : means “Graphics Processing Unit”
Used by AI/ML nodes, ZK proof generators (e.g. Aleo, Mina, Gensyn), or compute networks.
e.g. NVIDIA RTX 4090, A6000, or Tesla GPUs are often used.
Make sure drivers + CUDA are properly installed for GPU-based nodes.

- Bandwidth : means “internet data throughput”
Measured in Mbps — determines how fast your node syncs and communicates with peers.
e.g. 100Mbps+ down/up recommended for stable performance.
Unmetered VPS or dedicated servers are ideal.

# THATS IT GG
