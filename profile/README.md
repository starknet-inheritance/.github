
# StarkWill 

20% of Bitcoin are said to be lost due to death of owner or forgotten seed and a staggering 85% of users are uncertain on incorperating crytocurrency into their estate planning.

For users who like to inherit their assets, they have to inherit their assets by sharing their private key with successors or use a multisig wallet. We believe that is not the optimal experience for inheritance for 2 main reasons:

1. You wallet is not fully yours - as you have to share your private keys OR gather signatures to perform transaction.
2. Not replicate real world implementation - where will or inheritance are performed after owner death without sharing access to wallet.

While, the current solutions are non-existent or of a bad product market fit, hence we think that StarkWill will be able to solve a pain point in the industry. 

Introducing StarkWill, the go-to application for crypto users to inherit their crypto assets to their successors, build on **StarkNet** with account abstraction technologies.

## Features

Inheritance assets without needs to share private key OR use any multisig wallet:

- Customize percentage of wallet distribution for inheritance
- Guardians/governers selection
- Proof of death voting by guardians
- Recipient claim when owner is unavailable


## How Starkwill works?

This project tries to provide a way for user to create a 'will' for all their crypto assets so as to allow a set of beneficiaries to inherit them, in an event that the user no longer has access to their account (e.g. passed away), according to the will distribution rules set by the user.

![diagram](https://github.com/starknet-inheritance/.github/blob/main/profile/image.png)

1. User first initialize the Will through the factory contract. This is where the rules of the Will are set:-

  - which beneficiaries will receive which tokens for what amount. 
  - a multi sig rules for a list of users (called governors) that may start the Will activation period. 
  - how long should the activation period be.

Each distribution rule is defined by a `Split`, akin to a split of a pie. A `Split` consists of the `beneficiary address`, `token address`, and the `percentage`. It is important that the sum of percentages of all `Split`s with similar `token address` __MUST__ not exceed 100%. A Will may consists of multiple `Split` with different `token address`.

2. Once the Will is created, the owner then __MUST__ approve allowance for all tokens specified in the Will in order to allow the contract to initiate the transfer of the tokens to their respective recipients.

3. The governors can then decide to start the activation process for when the Will owner is determined to have passed away or simply inactive for a long period of time by supplying a multi sig according the multi sig threshold (i.e., how many governors' signatures are required to activate the Will).

4. Once the activation function is called, the activation period starts and during this period, if the Will owner is still alive, they can reject/stop the activation if necessary.

5. If the activation period ends without being rejected, the beneficiaries may start claiming their `Split`s.

## Technologies used

- Cairo
  - Account abstraction
- ReactJS (Nextjs)

## Future Roadmap

- [] Completion of voting mechanism
- [] Higher precision of inheritance timeline
- [] Improve UX for inheritance flow
- [] Push notification
- [] Inheritance on Ethereum (L1) through L1<>L2 interaction
