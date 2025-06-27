# How does bitcoin actually work
My understanding about bitcoin from [3blue1brown's video](https://www.youtube.com/watch?v=bBC-nXj3Ng4).
## What is a cryptocurrency?
Cryptocurrency is a digital asset which is based on a `decentralized ledger` that does not require trust in a central authority and is implemented using cryptography.
## Working
Frequent exchange of cash is difficult. How can we overcome this problem? We can maintain a ledger which is accessible by everyone(something like a website). We can record all transactions in that ledger and then settle the cash at the end of every month.
So the protocol would be something like this,
- Anyone can add new lines to the ledger.
- Settle up with cash each month.

But there is a problem in this protocol. Anyone can write in ledger favoring them. We can solve this by `digital signatures`.
### Digital Signatures
Digital signatures depend on the content being signed. Because of this, a signature cannot be copied, since a slight change in the content results in completely different signature which is not valid.
#### How is this implemented?
A private key, public key pair is created by everyone. Private key is kept secret with the person and public key is publicly available. A function takes in the message and the private key and produces a signature as the output. This signature is verified by a function which takes in message, signature and public key and outputs whether if a signature is valid or not.
- Sign(message, secret key) = Signature
- Verify(message, signature, public key) = True/False
Without the secret key, it should be computationally infeasible to create a valid signature.
But what if the same signature is used multiple times, for example a transaction where Alice pays Bob some amount and Bob uses the same signature multiple times. We can overcome this by including an index with the message which results in requiring a new signature for same message or transaction.

---
###
Now the protocol would be,
- Anyone can add new lines to the ledger.
- Settle up with cash each month.
- Only signed transactions are valid.

But what if a person doesn't show up at the time of settling the cash. This can be prevented by everyone paying some money in the pot,and making a transaction invalid if the transaction is spending more than what they have left in the pot. This requires us to know the entire history of transaction. We can continue with transactions on the ledger itself without ever the need of real cash if everyone uses this means of transaction. This makes the transaction history itself a currency. This currency can be used to exchange for real money but the protocol cannot ensure this. This exchange would be same as any other exchanges between two currencies.
The protocol becomes,
- Anyone can add new lines to the ledger.
- Only signed transactions are valid.
- No overspending.
But still our ledger is centralized since the ledger is controlled by the website which maintains the ledger. 
We can make the ledger decentralized by storing copies of the ledger with everyone and making a broadcast of any transaction made. But how does this ensure that that broadcast is received by everyone. And which broadcast to trust is there are multiple broadcasts.
This has a solution.
### Proof of Work
First we need to know what is a [hash](blockchain.md#hash).
We organize the ledger into blocks with some transactions and a Proof of Work in each block. Finding a [nonce](blockchain.md#nonce) such that the block is valid is called PoW. Blocks also contain hash of the previous block to maintain an order. This makes it difficult to chain something in the blockchain since all work should be done again from that block.
- A transaction is verified by its public key.
- A block is verified by [nonce](blockchain.md#nonce).

Anyone can be a block creator (miner) who will listen for transaction and race to find nonce to validate the block. Miners gets some reward by listing a special transaction to the miner for validating the block. Other just using the blockchain for transactions listen to the blocks being broadcast by miners and trust the chain which has more computational work done (longest chain). Attackers cannot attack the blockchain unless they have more than half of the computation power.
Final protocol is,
- Digital signatures
- Ledger = currency
- Decentralize
- Proof of Work
- Blockchain
