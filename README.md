# ULTIMATE-NODE-RUNNING-GUIDE

## What are Crypto Nodes?
Crypto nodes are the computers that form the backbone of a blockchain network. Each node plays a role in maintaining, validating, and storing the blockchain — which is the public ledger of all transactions.

### Type of Crypto Nodes? 
Only the necessary ones are listed below.

Full Nodes : 
- This nodes store entire blockchain history.
- verify all transactions independently.
- Help enforce the rules (called consensus rules).
Example: Bitcoin Core node.

Light Nodes :
- Store only some data (e.g., headers of blocks, not full blocks).
- Rely on full nodes to verify transactions.
- Used in mobile wallets or lightweight apps.
Validator Nodes :

- Actively participate in consensus (approving and adding new blocks).
- Common in Proof-of-Stake systems (like Ethereum 2.0, Solana).
- Usually require staking coins as a security deposit.

Mining Nodes :

- Try to solve cryptographic puzzles (Proof-of-Work).
- Used in Bitcoin and older systems to create new blocks.
- A subset of full nodes.

RPC nodes :

This are remote procedures call nodes, and one of the most important ones.
It allows external apps to :
- Read data from the blockchain (e.g., balances, blocks, transaction status)
- Send transactions to the network (e.g., token transfers, contract calls)
Think of it as a gatekeeper between your app and the blockchain.

Worker Nodes :

Very important to know as well.
Worker nodes are nodes in a decentralized network (or any distributed system) that perform actual tasks or computation assigned to them, but don’t control or coordinate the overall system. 

1) In centralized tech, a worker node :
- Runs your apps/containers (e.g., Docker).
- It Gets instructions from a master node (control plane).
2) Decentralized Compute Networks :
Like: Gensyn, Akash, Render, Bittensor
- Workers: Run AI models, ML training, or GPU-intensive tasks.
-> Example: Gensyn’s RL Swarm is a worker node.
3) Blockchain Validator Systems : In systems like Polkadot, Cosmos, or Layer 2 rollups, worker nodes might:
  - Handle execution of transactions
- Generate zero-knowledge proofs
- Perform tasks like sequencing, state updates, or fraud proofs

That’s the most important nodes to know about, there may be others like storage nodes and the likes but this ones are necessary to know.

* This repo is made to help you install a linux environment to participate in node testnets or the ones that need coding
* Testnet nodes are risky because it costs money & time and is hard because you will get to many issues specially if you are a beginner

# THIS GUIDE CONSISTS OF :
* 1- [How to Buy & Connect to VPS]()
* 2- [Config VPS]()
* 3- [Linux Commands]()
* Optional: [Create VPN]()

## ERRORS
* The best way to find solutions for your errors is the project's discord or chat gpts

## FOLLOW ME
* However you must have my [Github]() & [Twitter]() followed for new node testnet updates

## HELP EDIT THIS GUIDE
* Fork this repo to keep it in front of your eyes
* Please consider creating pull request if you found any issues to edit and complete this repository
