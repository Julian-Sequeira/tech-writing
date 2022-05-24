# TLS Communication with SGX Enclaves

Intel-SGX enclaves can *remotely attest* their identities to a remote client - in that process deriving a shared key to communicate securely with that client.
This is a clunky form of communication - suitable if small amounts of information are exchanged, but a longer communication process likely needs a TLS abstraction.

Turns out there are a few applications developed for exactly this! Let's explore them!

## What is TLS?

TLS has runs on top of the TCP/IP layer - operating on layers 4 through 7 of the OSI model. It is intended to protect communication between a client and server. The *TLS handshake* is where the client and server negotiate and establish a shared of set of communication parameters and keys. The *TLS record layer* is then when both parties send each other data. Messages are chunked, compressed, MAC'd, and finally encrypted using shared keys before being sent.

## TLS Libraries
