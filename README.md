#
**pea2pea** is a simple, low-level, and customizable implementation of a TCP P2P node.

The core library only provides the most basic functionalities like starting, ending and maintaining connections; the rest is up to a few
low-level, opt-in [protocols]:
- [`Handshake`]requires connections to adhere to a handshake protocol before finalizing connections
- [`Reading`] enables the node to receive messages based on the user-supplied [Decoder]
- [`Writing`] enables the node to send messages based on the user-supplied [Encoder]
- [`Disconnect`] allows the node to perform specified actions whenever a peer disconnects

## goals

- low-level oriented: the user has full control over all connections and every byte sent or received


## how to use it
1. define a clonable struct containing a [`Node`] and any extra state you'd like to carry
2. implement the trivial [`Pea2Pea`] trait for it
3. make it implement any/all of the [protocols]
4. create that struct (or as many of them as you like)
5. enable the protocols you'd like them to utilize

That's it!

## [examples]

- including [noise](https://noiseprotocol.org/noise.html) encryption, simple interop with [`libp2p`](https://crates.io/crates/libp2p), or [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security) connections

