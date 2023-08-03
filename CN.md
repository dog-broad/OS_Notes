# Distance Vector Routing

Distance Vector Routing is a simple and decentralized routing algorithm used in computer networks. It helps routers in a network to share information about the best paths to reach different destinations. Each router maintains a table that contains the distance to all known destinations, and the path to reach them.

Here's a step-by-step algorithm for Distance Vector Routing:

1. Initialize: Each router starts with its own distance table, which contains the cost (distance) to reach itself as 0 and infinity (∞) for all other destinations.

2. Share Information: Routers periodically exchange their distance tables with their directly connected neighbors.

3. Update Distance Table: When a router receives a distance table from a neighbor, it recalculates its own distance table using the information received. It checks if there are any shorter paths to other destinations through this neighbor. If it finds a shorter path, it updates its distance table.

4. Propagate Changes: If any router's distance table is updated, it shares the changes with its neighbors.

5. Repeat Steps 3 and 4: The process continues until no further changes occur in the distance tables.

Let's illustrate the algorithm with a tiny example network:

Suppose we have a simple network with four routers A, B, C, and D connected as follows:

```
  (A)----1----(B)----3----(C)
   |            |
   |            |
   2            1
   |            |
   |            |
  (D)-----------|
```

Initially, the routers' distance tables look like this (cost to reach themselves is 0, and ∞ indicates an unknown path):

```
| Destination | Cost (A) | Cost (B) | Cost (C) | Cost (D) |
|-------------|---------|---------|---------|---------|
|     A       |    0    |    ∞    |    ∞    |    ∞    |
|     B       |    ∞    |    0    |    ∞    |    ∞    |
|     C       |    ∞    |    ∞    |    0    |    ∞    |
|     D       |    ∞    |    ∞    |    ∞    |    0    |
```

Step 1: Initialize the distance tables.

Step 2: Routers exchange distance tables.

Step 3: Router A receives the distance table from B, and it updates its table with the new information.

```
| Destination | Cost (A) | Cost (B) | Cost (C) | Cost (D) |
|-------------|---------|---------|---------|---------|
|     A       |    0    |    1    |    ∞    |    2    |
|     B       |    1    |    0    |    ∞    |    ∞    |
|     C       |    ∞    |    ∞    |    0    |    ∞    |
|     D       |    2    |    ∞    |    ∞    |    0    |
```

Step 4: Router A propagates the changes to its neighbors, C and D.

Step 5: Router C receives the distance table from A, and it updates its table with the new information.

```
| Destination | Cost (A) | Cost (B) | Cost (C) | Cost (D) |
|-------------|---------|---------|---------|---------|
|     A       |    0    |    1    |    2    |    2    |
|     B       |    1    |    0    |    ∞    |    ∞    |
|     C       |    2    |    ∞    |    0    |    ∞    |
|     D       |    2    |    ∞    |    ∞    |    0    |
```

Step 6: Router C propagates the changes to its neighbors, A and B.

The process will continue with routers exchanging information and updating their distance tables until no more changes occur. Eventually, all routers will have consistent and up-to-date distance tables, and they will know the best paths to reach different destinations in the network.


# Explain three way handshaking connection mechanisms in TCP(connection establishment,Data Transfer, connection Relase)

### 1. Connection Establishment

The three-way handshake is the process by which a TCP connection is established between a client and a server. It involves three steps:

**Step 1: Client sends SYN (Synchronize)**
1. The client initiates the connection by sending a SYN packet to the server.
2. The SYN packet contains a randomly generated sequence number (ISN - Initial Sequence Number) to start the connection.

**Step 2: Server Responds with SYN-ACK (Synchronize-Acknowledge)**
1. Upon receiving the SYN packet, the server acknowledges the request and responds with a SYN-ACK packet.
2. The SYN-ACK packet includes its own randomly generated sequence number (ISS - Initial Sequence Number) and acknowledges the client's ISN by adding 1 to it.
3. The server also includes its window size, indicating the maximum amount of data it can receive.

**Step 3: Client Acknowledges with ACK (Acknowledge)**
1. The client receives the SYN-ACK packet from the server.
2. It acknowledges the server's ISN by adding 1 to it and sends back an ACK packet to the server.
3. The ACK packet confirms the establishment of the connection and also contains the client's window size.

At this point, the connection is considered established, and both client and server are ready to exchange data.

### 2. Data Transfer

After the connection establishment, the client and server can exchange data using TCP. Here's how data transfer works:

1. **Sending Data (Client to Server)**
   - The client sends data in segments, each segment containing a sequence number.
   - The server receives the segments and sends an acknowledgment (ACK) back to the client, acknowledging the receipt of data.
   - If the client doesn't receive an ACK for a segment within a timeout period, it retransmits the data to ensure reliability.

2. **Receiving Data (Server to Client)**
   - The server sends data in segments to the client, each segment with its own sequence number.
   - The client acknowledges the received segments by sending ACK packets back to the server.
   - If the server doesn't receive an ACK for a segment within a timeout period, it retransmits the data to ensure reliability.

### 3. Connection Release

When either the client or the server wants to close the connection, a connection release process is initiated:

**Step 1: Initiating Connection Release**
1. The client or server that wants to close the connection sends a FIN (Finish) packet to the other side.
2. The FIN packet indicates the party's intention to terminate the connection.

**Step 2: Acknowledgment of FIN**
1. The receiving party acknowledges the FIN packet by sending an ACK packet back.

**Step 3: Finalizing Connection Release**
1. The receiving party may also send its own FIN packet to indicate its intention to close the connection.
2. The other party acknowledges the FIN packet with an ACK.

Once both sides have exchanged FIN and ACK packets, the connection is considered closed gracefully.

The three-way handshake and connection release mechanisms in TCP ensure reliable and orderly communication between client and server, while the data transfer process guarantees that data is successfully delivered and received.