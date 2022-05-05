<center>
    <p style="font-size: xx-large">SPACETIME METAVERSE</p>
    <img src="../src/spacetime_logo.png" style="height: 200px;">
    <p style="font-size: x-large">Multiplayer Whitepaper</p>
    <p style="font-size: large"><a>spacetimemeta.io</a></p>
</center>
<br><br>

**This document was made by [LiquidBlocks](https://twitter.com/FrdricCt15)**

---

The Spacetime standard kit is meant to allow developers to deploy complete and compatible virtual environments without worrying about the integration of common metaverse features. One of these features is the integration of multiplayers. In this document I explain the principal challenges of a complete metaverse-like multiplayer experience and propose solutions.

## **Part 1. Problems to solve**

In order to implement a multiplayer experience that is pleasant to the users and relevant to the emerging web3 technologies, we must go off the common tracks and solve some of the problems with usual implementation methods.

1. **Connections.** The way users connect to each others and the environments.
2. **Profiles Storage.** Where do we store the users profile information.(avatar, username, profile pictures)

Once these two problems solved, the rest is simply to create a pleasant video game experience by including:

1. **Environment interactions.** What controls, constraints and options are needed for a smooth experience?
2. **User interactions.** What basic interactions are needed for metaverse experience? (Chat, Voice Call, Exchanges, PvP)

## **Part 2. Connections**

In Spacetime meta, we want the users to own their profiles in a web3 fashion. In the next sub-sections, we will describe the problems with web2 solutions and propose a web3 solution. We will also present a way to safely identify users in a decentralized way over peer 2 peer connections.

### **Part 2.1. Web2 solution**

The common way to handle connections in web2 is to have a private database containing the connection information of your users (username and passwords). Then the users uses his username/password combination and connect to a server. Once connected to the server, the server will relay the information to other users creating a multiplayer experience. 

Nowadays, this solution is very easy to setup for a developer since a lot of plugins are available. On the downside it has multiple consequences for the user:

1. **Users do not own their profiles.** This system encourages the collection of data since privately owned servers are responsible for relaying the information between users and allows giant companies like Facebook and Google to intercept and analyze this data to create massive database of users personal information. We have seen how this can create problems in events like the [Facebook–Cambridge Analytica data scandal](https://en.wikipedia.org/wiki/Facebook%E2%80%93Cambridge_Analytica_data_scandal).
2. **Heavy account management.** Having username and password for each and every different application takes time to manage and is a security risk for the users.
3. **Breaks the metaverse experience.** You are prompted with login interfaces and profile setup everywhere and every time you enter a new virtual environment. Also, having multiple tech giants fighting for user retention can create massive walls between users who chose different providers. This was the case for many years in video game industry with competition between Xbox and Playstation wo would not allow their users to play with one an other.

### **Part 2.2. Web3 solution**

The main objective of web3 and blockchain is decentralization, the goal is to remove the trust intermediary. To achieve this optimal in regard to a multiplayer connection system, we must follow a few rules:
1. Users must owns his profile as a non-fungible Cardano native token.
2. Connection does not require third party to verify identity instead, we use asymmetric encryption.
3. Connection must allow be peer to peer and not require a private third party to relay non-encrypted information. 

Following these guidelines would have positive consequences for the users:

1. **Users own their profiles.** The user becomes responsible for the security of his account and chose what information to share with businesses.
2. **Single account to manage.** The user only have to manage and secure the private key of a his blockchain wallet.
3. **Metaverse experience.** The metaverse identity will be the same no mather where you go, thus increasing the impression that the metaverse is a single giant scene.

In the next part, we propose an implementation of the web3 solution using webRTC and asymmetric encryption.

## **Part 3. Web3 implementation**

In this section we describe a way of connecting two users in a peer to peer way and verify each others identity without a third party.

The first part is to create a peer to peer connection.

### **Part 3.1. WebRTC**

[WebRTC](https://webrtc.org/) is a open web standard allowing developers to add real-time peer to peer communication capabilities to web applications. The webRTC technology is available in all modern browsers as a JavaScript API.

The first step to our decentralized communication system is to implement RTC stream of data between peers. Once we have this connection, it will be easy to implement multiplayer functionalities on top of this data exchange. Doing so will ensure us to respect the third rule of our system: *Connection must allow be peer to peer and not require a private third party to relay non-encrypted information.*

The only problem is we need a way to make sure the peer we are connecting to is the right person. This is where we introduce the asymmetric encryption to verify the identity of the other peer.

### **Part 3.2. Asynchronous encryption**

As described in the identity whitepaper, Spacetime meta considers every $handle CNFT as an individual profiles. 

### **Part 3.2.1. Situation**

This bring us to the following example situation:
We have two users, Alice and Bob. Both own their own Spacetime profiles as handles in their wallets.

Alice owns the $alice handle.
Bob owns the $bob handle.

Alice and Bob establish a peer to peer connection via webRTC and are ready to exchange information. Now the problem is:

### **Part 3.2.2. Problem**

How can Bob confirm that the person he is connected to really is Alice?

### **Part 3.2.3. Solution**

This solution is simply a modified handshake including some blockchain necessity.

**Step 1.** Alice generates a new pair of throwaway keys inside of the Spacetime Extension.

**Step 2.** Alice creates and submits a transaction to attach the public key to her $alice handle. The metadata would look something like: 

```
{
    77223004: {
 		handle: $alice, 
 		public_key: <alice_public_key>
 	}
}
```

*(Note that this format is an extension of the format used in the Spacetime Meta identities.)*

*(Step 1 and 2 are preparation steps and should be made before trying to connect to someone. Step 3 is the regular starting point for a connection.)*

**Step 3.** Alice goes to the signaling server and posts her public key as her peer_id. 

*(Bob must already know what handle he wants to connect to. In this example he wants to connect to $alice. Consider handles as profiles in the metaverse. Recommend reading the identity whitepaper for clarifications.)*

**Step 4.** Bob scans the blockchain to find the latest metadata attached to the $alice handle and extracts the public key. 

**Step 5.** Bob goes to the turn server, find and connect to Alice (bob should be using his own public key as his peer_id)

*(At this point there is a peer to peer connection between Alice and Bob. In the next step, they will do a custom handshake to verify each other’s identity.)*

**Step 6.** Bob generates a random and non deterministic string. (can't be guessed)

**Step 7.** Bob encrypts the secret random string with Alice’s public key and sends it to Alice via the peer 2 peer connection. 

**Step 8.** Alice decrypts Bob's secret message using her private key and returns the plain text to him.

**Step 9.** Upon receiving the decrypted messages, Bob is now guaranteed that the peer_id he is connected to is the rightful owner of the $alice handle
