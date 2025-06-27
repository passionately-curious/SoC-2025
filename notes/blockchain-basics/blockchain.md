# How do blockchains work?
Using [blockchain demo site](https://andersbrownworth.com/blockchain/) for this part of the course.
## Hash
- hash - a fixed length string
- hash function - data -> hash
	data can be of arbitrary length
- Inverse of a cryptographic hash function is computationally infeasible to find.
## Block
How to mine a block? When is the block valid?
To mine a block, a nonce must which makes the block valid. 
### nonce
A number with block data on which hash function is applied to such that the resulting hash meets some condition(for example, hash should start with certain number of zeroes), which varies depending on the chain. The block with a nonce which meets this condition is valid.
###
- This is done by brute-force.
- This is called Proof of Work (PoW).

`Genesis block` - First block in a blockchain, where previous hash points to block which never exists.

## Blockchain
A chain of blocks where hash of each block is the hash(block_data + nonce + prev_hash).  
If any of the block is tampered, all blocks after that becomes invalid since hash of every block is a function of hashes of previous blocks. Therefore, if something to be changed in a blockchain, all work should be done again from that block.
##
A copy of blockchain is with everyone. Whenever transactions are made, they are being broadcast. Miners listen to these transactions. Miners race to find a valid block with those transactions and the first miner to mine a valid block gets rewarded. Then participants listen to the blockchain being broadcast by miners and choose the longest chain since it has the most computation work done. Attackers cannot convince participants with some other transactions unless they have more than half of the computation power.