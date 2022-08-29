# Solana Fact Votes Block Agg

`solana.fact_votes_block_agg`

| Field            | Type      | Description                                                |
| ---------------- | --------- | ---------------------------------------------------------- |
| block\_id        | integer   | Unique sequential number that identifies the current block |
| block\_timestamp | timestamp | The time the block began                                   |
| num\_votes       | integer   | The number of votes that occurred during the block         |

Validator votes are messages that have a critical function for consensus and continuous operation of the Solana network. A validator receives entries from the current leader and submits votes confirming that those entries are valid. When a validator receives multiple blocks for the same slot, it tracks all possible forks until it can determine a "best" one. A validator selects the best fork by submitting a vote to it.&#x20;

Because validator votes on the Solana network account for a large percentage of transactions on the network, votes on the Solana network are only represented in solana.votes\_block_\__agg in Flipside Solana data.&#x20;
