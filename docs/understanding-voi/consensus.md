# Consensus

In order to have blocks selected and written to the Voi blockchain there needs to be a decentralized consensus mechanism.

Voi blockchain is a Pure Proof of Stake (PPoS) network meaning that blocks are selected and written extremely efficiently in a decentralized way to the blockchain by nodes with tokens staked on them through online accounts.

Accounts used in consensus are selected randomly, but with more weight given to accounts that hold more native tokens.

There are 3 steps necessary to have a single block written to the blockchain within a given round.


### Block Proposal

In this step multiple accounts are selected to propose the new block for the round.

To do this every node in the network runs a pseudorandom function on each account staked on them to determine if an account is selected to propose the block.

Once an account is selected by the pseudorandom function, the node that the account is staked on then propagates the proposed block along with proof, the pseudorandom functions output, that the account was selected in a proposal message.

This is so that other nodes in the network can independently verify that the account was actually selected.


### Soft Vote

In this step the nodes select only one proposed block to get certified.


#### Block Propagation

As multiple accounts are selected to propose the new block it means that nodes receive multiple proposal messages. Each proposed block is verified and validated using the proof contained in the proposal message by the nodes.

Only the top ranking proposal message with the lowest score is propagated to other nodes in the network.


#### Soft Vote Committee

Each node will then once again run a pseudorandom function on each account staked on it to see if the account is selected to be in the soft vote committee.

For any account that is chosen their voting power is relative to the number of native tokens they hold.

The selected accounts vote for the proposal message with the lowest score out of all the proposal messages received by the node after the block propagation. The score is determined in the same way as before using the pseudorandom functions output that is contained in each proposal message to prove the validity of the proposal.

It is the votes from the accounts in the soft vote committee accompanied by the proof that the account is in the committee that will now be propagated to the network.

This is a process that repeats with a new committee each time until a quorum is reached.

Other nodes on the network with accounts not in the committee will receive the votes as well as proof of committee membership from the accounts that cast the votes. Once the votes are validated they are tallied up until the quorum is reached.

Now the quorum is reached we proceed to the certify vote step for the block proposal that passed.


### Certify Vote

A final committee of accounts selected in the same way as in the soft vote committee now validates the passed block proposal for any problems.

If the block proposal is valid this same final committee votes until a quorum is reached to certify the block in the proposal.

Once the block is successfully voted to be certified the node that proposed the block in the first place then creates a certificate for the block and writes it to the ledger.

Once the block is written to the ledger a new round begins for the next block.
