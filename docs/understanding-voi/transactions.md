# Transactions

Transactions enable accounts to interact with the Voi blockchain by the changing of some type of state. This essentially means a change has been made to the blockchain, as a result of a certain action taken. For example, the transferring of tokens or interacting with smart contracts.

There are seven types of transactions that exist on the Voi blockchain. Three of which are used exclusively to interact with one of the two asset types that are used on Voi blockchain.


### Transaction Types


#### Payment Transactions

A payment transaction sends Voi (Voi blockchains native token) from one account to another.


#### Application Call Transactions

An application call transaction is used to modify and interact with smart contracts. 

Application call transactions can be broken up into a number of subtypes, depending on what actions are being taken with a specific smart contract. These subtypes all use an application call as the transaction type, but the contents of the transaction are different depending on the desired action that is to be taken with the smart contract.

Application calls can take the following actions on a smart contract:



* Modification
    * Create Transaction
    * Update Transaction
    * Delete Transaction
    * Opt In Transaction
    * Opt Out Transaction
    * Clear State Transaction
* Interaction
    * NoOp Transaction

A NoOp subtype transaction is used to call the logic within a smart contract. Because this logic is custom written, the transaction requires the specification of the function to be called and all necessary arguments. This means each NoOp transaction needs to be customized to the specific smart contract it calls.

All smart contracts can be modified using the modification based subtype transactions in a consistent way. 


#### Key Registration Transactions

A key registration transaction is used to register whether the account will be participating in consensus. Registering the participation status of an account as online means it will be using its stake to help secure the network. A key registration transaction can also be used to take the account offline.

To register an account online, the key registration transaction needs to contain the participation key data.

To register an account offline, the key registration transaction does not need any participation key data.


#### State Proof Transactions

A state proof transaction is submitted to the network exclusively by nodes during the consensus process. They contain two main components, a message, and a state proof. The message can be used to verify transactions that occurred in the last 256 blocks prior to the state proof transaction being created. The state proof is used to verify the message.

State proof transactions enable transaction verification to be done in a trustless manner without any dependencies on 3rd parties. This is because it is the independently running nodes in the network that create, sign and submit the state proof transaction.


#### Standard Asset Transactions 

The next three transaction types are only used to interact with Standard Assets. The other asset type (the Smart Asset) is smart contract based, and so all interactions are done with Application Call Transactions. 


##### Asset Configuration

The asset configuration transaction is used to configure a standard asset.

Like the application transaction, the asset configuration transaction has a number of subtypes which dictate the transaction effect.

Asset configuration transactions can take the following actions on a standard asset:



* Create Transaction
* Reconfigure Transaction
* Delete Transaction

All of these subtype transactions can only be performed by specific addresses which are set during the create transaction and can be modified using the reconfigure transaction.


##### Asset Freeze

Standard assets can be configured to enable the asset to be frozen. The asset freeze transaction is used to freeze or unfreeze an account for that specific standard asset, if the standard asset has been configured to allow such an action to be taken. 

Freezing an account for that standard asset would mean that the specified account is unable to send or receive that standard asset.


##### Asset Transfer

The asset transfer transaction is used to move standard assets between accounts as well as being used by accounts to opt in to receive standard assets.

Asset transfer subtype transactions can take the following actions on a standard asset:



* Accepting
    * Opt In Transaction
* Transfering
    * Payment Transaction
    * Clawback Transaction

The opt in subtype transaction means that an account can only receive a standard asset if the user has opted in to using it. 

The payment subtype transaction acts in the same way as a payment transaction for Voi blockchains native token. It enables an account to transfer a standard asset to another account that is opted into the standard asset.

The clawback subtype transaction can be used to transfer tokens into or out of an account that is not owned by the creator of the clawback subtype transaction regardless of if the account is frozen or not. The standard asset would have to be configured appropriately for this subtype transaction to be possible.


#### Grouped Transactions

Voi blockchain enables the ability for transactions to be grouped together into what is referred to as an Atomic Transfer. 

In an atomic transfer either all transactions succeed or all transactions fail. The transactions in the group can all have unique addresses as the sender. This allows for powerful use cases without the need for a smart contract to facilitate them securely.  


### Signing

All transaction types and their subtypes will be rejected by the Voi blockchain unless they are appropriately signed by the correct account.

There are three different ways to sign transactions on the Voi blockchain which primarily depend on the account attempting to submit the transaction.


#### Single Signing

The most common way of signing. Each account's private key will be used to sign a transaction when that account is specified as the sender for any transaction type or subtype.


#### Multi Signing

When the sender of a transaction is the address of a multisig account then the private keys for the accounts that constitute the multisig are used to sign the transaction up to the pre-configured threshold of the multisig. 


#### Delegated Signing

Delegated signing is when an account (multisig or single) has been used to sign a Smart Signature and that very same Smart Signature is then used to sign a transaction on behalf of the account.


### Fees

Every transaction on Voi has to pay at least a minimum fee for a transaction to be accepted plus a dynamic fee that comes into effect when the network is congested.

The additional fee on Voi blockchain is determined solely on the size of the transaction measured in bytes and the network congestion. The amount of congestion on the network dictates the fee per byte.

Every transaction will have a minimum fee so even if the fee per byte is 0, when the network is not congested, transactions will still have to pay the minimum fee. 


#### Fee Delegation

When using grouped transactions Voi blockchain supports the ability for the transaction fees of all the transactions in the group to be divided across the transactions in the group however you want. 

As transactions can all originate from unique addresses this enables powerful use cases in an efficient way without the need of smart contracts.
