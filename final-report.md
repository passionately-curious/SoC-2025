# Final repot

## Who am I

I am Kishan D, from Mathematics department.  
I am currently studying in 2nd year.  

## Project Description

**Crypto Casino**  
Project aim is to build a decentralized gamling applicatoin.  
My application - [zerok](https://github.com/passionately-curious/zerok)  

## Things done till mid-term

1. Blockchain concepts  
2. Solidity  
3. CryptoZombies tutorial  

[Here](./midterm-report.md) is the detailed mid-term report.  

## What after mid-term

After blockchain concepts and
becoming comfortable with solidity by writing some small contracts,
focus now shifted on the app logic.  

### Mathematics used in gambling

Mentor provided us with resources about gambling mathematics
and instructed us to choose one or two casino games
to write the smart contract.  
I learnt some concepts used in gambling,

- law of large numbers  
- positive rate of return  
- law of small number bias  
- expected values  
- house edge  

These helped me create a game strategy.  
Casino games were new for me,
So I initially thought of choosing some simple games.
My plan was to write

- Coin toss
- Dice
- Slot machine

As time passed, I focused more on security and game design
instead of focusing on quantity of games.
At last I finished with coin toss and dice contracts
with slot machine and frontend in progress.

### Oracles

In gambling applicaions, randomness is very important.
But any randomness generated on chain is deterministic
and not safe to use.
Oracles for the win.
Oracles are used to get off-chain data to on-chain.
Chainlink VRF generates randomness which can be verified on-chain.
Traditional oracles are centralized and not safe.
But chainlink has multiple independent node, which makes it safe.

### Project development

For this project,
I chose hardhat as the development environment.
I could have gone with remix-ide since it has a simple interface,
but I wanted a flexible environment and also
remix-ide abstracts most of the things which I wanted to know.

Hardhat has many plugins which makes development easy.
In web3 apps, testing is very important,
since once deployed cannot be changed.
I spent most of my time writing tests.

### Deployment

Contracts written in solidity are compatible on EVM-compatible chains.
For this project, just deploying in a testnet.
I chose sepolia testnet.
Got some test ETH form the faucets which helped me in testing.

[screenshot](./assets/transactions.png)

### Node services

I could have run my own node since it was just a project
but I chose to go with alchemy for its ease.
