# Crypto Please Protocol

![Logo](HORIZONTAL-Black-Gold.png)

## A protocol to send crypto to all internet users.

We are very excited to present you a revolutionary protocol for the Solana Hackathon 3. We have been working on it since the second Solana Hackathon. Lets be honest, most people in the world don't care about the blockchain technology. Most people are already using applications like Venmo, Paypal or Revolut to exchange money or even invest into crypto. On the other side, we have crypto Wallets which gives access the new financial system but they are difficult to use most of the times and more important the onboarding is nonexistent.

That is Until now,  Crypto Please Protocol is the first easy, non custodial and secure protocol to send any kind of crypto to someone who knows literally nothing about crypto and doesn't have yet a crypto-address. Thanks to the Crypto Please Protocol, the sender can generate a URL and 4 digit-pin code that he can share on any messaging system to someone. Then this user is incentivized to download the crypto wallet to get his money.


## State of the art
There has been some solutions such as CELO that aimed to simplify how people can access DeFi, yet upon research, we found some significant flaws which we have listed below. After reviewing other protocols, like the CELO protocol, we found some flaws:
- ID of phone numbers are stored on the chain even if they are encrypted
- you need to have a positive balance of CeloUSD to get the crypto-addresses of a phone number
- it is not possible to send money to a user that has not been registered before.

So the CELO protocol is not blockchain agnostic, and has inherend privacy issues since some private information are stored in the blockchain.
Another side of the same coin is neo-bank application. One key element of Neo-bank application is to able to send money to a phone number to non registered users. This feature increases the traction of neo-banks application, because the new user has a great incentive to register on the application to claim the money waiting for the user to collect.

## Here comes the Crypto Please protocol
Crypto Please Protocol provides a protocol to generate payment links and associated verification code. Only a user who has access to a payment link and its associated verication code can widthdraw some crypto. These payments link are universal which means they can works accross different wallets. The protocol is non-custodial meaning during all the transfer, no third party are involved.
The Crypto Please Protocol enables to send SOL token, SPL token or any crypto-currency to a phone number or an email address via payment links. The protocol is:
- non custodial
- universal (works with all crypto) and no smart-contract involved.
- keeps full-privacy (zero information is leaking on the blockchain)
- can be implemented by any existing crypto-wallet (Trust Wallet, Coin98 etc..) to send payment links without any difficulty to increase their user-base

## How it works
We use deep-link to make sure any user (registered or non-registered) can widthdraw their funds from the payment link. Then we verify the identity of the person who wants to widthdraw the fund by asking him to confirm the verification code associated to the payment link. Then we encrypted the verification code (because we can use Solana address to encrypt messages) into a off-chain database where only the sender can read the answer. We use push notification task to ask the sender to verify the identity of the person claimin fund then unlock the money after the sender phone has successfully verified that the verification code provided is correct.

![Schema](https://static.swimlanes.io/0678b0c0b53e4be1a49056696b3a1a43.png)



## Source Code Repos Solana Defi Hackathon
We worked on 2 repos. A Solana Dart Library and our Flutter application.

- [Solana Dart Library](https://github.com/cryptoplease/dart-solana-lib)
- [Flutter Mobile App](https://github.com/cryptoplease/crypto-please) 

## Customer oriented product development
Using this protocol, we plan to develop it into a beautiful wallet in which the power of DeFi and blockchain technology is working seamlessly in the background. Here is our deck on how the wallet will look like, and what can be expected:

## Team
- Antoine Herzog (Project Lead)
- Anthony Emezu (Art Director)
- Kirill Bubochkin (Senior Flutter Developer)
- Iharob Al Asimi (Senior Flutter Developer)
