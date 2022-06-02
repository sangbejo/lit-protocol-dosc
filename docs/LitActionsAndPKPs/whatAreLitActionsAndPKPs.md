---
sidebar_position: 2
---

# What are Lit Actions?

Lit Actions are Javascript functions that can utilize the threshold cryptography that powers the Lit Protocol. You can write some JS code, upload it to IPFS, and ask the Lit Nodes to execute that code and return the result. There are JS function bindings to threshold signing and decryption, so that you can ask the Lit Nodes to sign or decrypt some data for you with their private key share. You can collect these signature or decryption shares on the client side, and combine them to get a signature or decryption key. In the case of a signature, you can then use that signature for authentication, for example to write to a Ceramic Data stream, or to send an ETH transaction.

Lit Actions are stored on IPFS and are immutable, like smart contracts. You can think of them as Javascript smart contracts that have network access and can make HTTP requests.

## What are PKPs?

PKP stands for Programmable Key Pair. Each PKP is generated collectively by the Lit Nodes through a process called Distributed Key Generation (aka DKG). This process permits the Lit Nodes to generate a new public/private keypair where nobody knows the whole private key. Instead, each node has a private key share, and they can do everything with it that they could do with a traditional private key, like sign and decrypt data. The difference is that signing with a private key share produces a signature share. These signature shares must be combined above the threshold (current 2/3 of the nodes) to produce the final signature.

## How do Lit Actions and PKPs work together?

A user may generate a new PKP, and may grant a Lit Action the right to sign using it. This means that Lit actions are kind of like smart contracts with a secret key they can use to sign or decrypt things.

## State of the network today - Serrano Testnet

The Lit Actions and PKP network is in a testnet state. In this state, we have not implemented the ability to generate a new PKP, and a single PKP is shared by all Serrano Testnet users. We will soon lift this limitation and provide the ability to generate a new non-shared PKP. The data on the Serrano Testnet is not persistent and may be erased at any time. Therefore, we do not recommend storing anything of value on the Serrano Testnet.