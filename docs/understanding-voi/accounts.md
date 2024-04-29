# Accounts

Accounts at their core are structures that contain a few different objects including keys, They are commonly referred to as Addresses as one of the objects that they encapsulate that is visible and commonly used is the Address of the account. 


### Structure


#### Address

The address is the human readable version of the public key that is used as a unique identifier for your account. It is what is used when it comes to identifying and specifying recipients and senders within transactions.

Your address can be freely shared and is how you and others will uniquely identify your account.


#### Seed Phrase

On Voi the seed phrase for an account is 25 human readable words in a specific order.

From this seed phrase you can derive the private key that is used to sign transactions. 

You should never share your seed phrase because you can derive the private key from it.


#### Private Key

The private key of the account can be considered the keys to the castle. With this key you have full control over the account and can derive the public key.

The private key is what is used behind the scenes when you interact with Voi and proves that you own the account and so the address that you are using.

You should never share your private key as you use them to sign data and transactions or verify signatures.


#### Public Key

The public key is seldom exposed, but it is used to derive the address of the account.

Public keys can be freely shared, but it is unlikely you will need to, or that you will even see your public key.


### Attributes


#### Balance

Every account has an associated balance. That is the number of Voi tokens that it holds. 


#### Minimum Balance

Every account that exists on Voi has a minimum balance. This starts at 0.1 Voi and increases with each smart contract opted into or standard asset held. Opting out of already opted into smart contracts or full removal of standard assets from an account decreases the minimum balance. 

As the number of accounts created increases it means that the amount of Voi locked up increases too. It’s worth noting here that every smart contract has an account too, so every smart contract also increases the amount of locked up Voi.


#### Participation Status

Every account on Voi is either Offline or Online. By default all accounts are set to be offline.

Offline accounts are not participating in consensus. Online accounts are participating in consensus and are staking their balance on a node to
[help secure the network](node-runners/overview.md).


### Features

Below are features special to Voi that drastically improve the network’s user experience when compared to other chains. 


#### Multisig

Multisig accounts are represented in Voi the same as normal accounts and are not smart contract based like in other networks.

The primary difference between them and a standard account is that they have a defined threshold on the number of accounts in the multisig that are needed to sign a transaction.

The address of a multisig account is derived from the ordered list of the standard accounts that make up the multisig. Multisigs cannot be nested with other multisig accounts so the ordered list used to derive them can only be made up of standard accounts.


#### Rekeying

Rekeying is a feature that swaps out the private key that is used to sign for an account to a different one. 

This means that accounts can maintain the same public key and address, but a different private key from another account must be used to sign transactions instead. The original private key cannot be used to sign transactions.

You should be sure to retain access to the original private key as if you close out an account then the rekey is reset.
