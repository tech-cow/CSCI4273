Problem 1
=========
a.) The total transfer time is: 11.07 seconds
```
  time required for handshake: 2 * RTT = 320 ms = 0.32 s
  propagation delay: 0.5 * RTT = 80 ms = 0.08 s
  transmission time: number of packets * (packet size / bandwidth) = 2000 * (8000 b / 1500000 bps) ~ 10.7 s
```

b.) The total transfer time is: 331.07 seconds
```
  time required for handshake: 2 * RTT = 320 ms = 0.32 s
  propagation delay: 0.5 * RTT = 80 ms = 0.08 s
  transmission time: number of packets * ((packet size / bandwidth) + RTT) = 2000 * ((8000 b / 1500000 bps) + 0.16 s) ~ 330.7 s
```

c.) The total transfer time is: 6.8 seconds
```
  time required for handshake: 2 * RTT = 320 ms = 0.32 s
  propagation delay: 0.5 * RTT = 80 ms = 0.08 s
  transmission time: (number of packets / 50) * RTT = (2000 / 50) * 0.16 s = 6.4 s
```

d.) 


It is impossible to cut the transmission time in half for case b even if the bandwidth was "unlimited" since most of the transmission time is from the RTT delay.

Problem 2
=========
a.) RTT = 2 * (385,000 km / 3 * 10^8 m/s) ~ 2.57 s

b.) BDP = 50000000 bps * 2.57 s = 128500000 bits

c.) The transfer time is: 10.425 seconds (assuming we do not wait a RTT on each bandwidth send)
```
  handshake: 2 * RTT = 5.14 s
  propagation delay: 0.5 * RTT = 1.285 s
  transmission time: (file size / bandwidth) = (200000000 b / 50000000 bps) = 4 s
```

d.) Although their bandwidth delay product are the same, they are not the same links because of the delay. If acknowledgements are sent on the links, the link with the shorter delay will have a shorter transmission time.

Problem 3
=========
a.) length of bit: (speed of propagation / bandwidth) = (2.3 * 10^8 m/s  /  10000000 bps) = 23 meters per bit

b.) Number of bits: 434782 bits
```
length of bit: (speed of propagation / bandwidth) = (2.3 * 10^8 m/s  / 10000000000 bps) = 0.023 meters per bit = 2.3 cm per bit
bits on wire: (length of wire / length of bit) = (10000 m / 0.023 m) = 434782.608696 = 434782 bits
```

Problem 4
=========
a.) Since A waits for B's receipt acknowledgement for each packet that A sends, there is not a requirement to acknowledge which packet B receives since only 1 packet is sent on the wire at a time (B only has to acknowledge a single packet received).

b.) A 2-bit sequence number would adequate to detect lost packets, but it would not be enough for if A sends more than 4 packets before waiting for an acknowledgement from B. A 1-bit sequence number would only work if A sends 2 packets before waiting for an acknowledgement from B.

c.) The number of bits in the sequence number will determine how many packets it can send (2^number of bits) before waiting for an acknowledgement. This does not vary from case b since the packet order can always be determined by the sequence number.

Problem 5
=========
a.) Propogation Delay: 0.0002 seconds
```
propogation delay: (distance / propagation speed) = (40 km / 2 * 10^8 m/s) = (40000 m / 200000000 m/s) = 0.0002 s
```

b.) I would suggest the RTT, double that of the propagation delay.

c.) It is possible to still time out because of dropped packets, if a packet is dropped then the algorithm will always time out.

Problem 6
=========
a.)
![](https://github.com/jon5477/CSCI4273/blob/master/Problem%20Sets/Set1/prob6a.jpg)

b.)
![](https://github.com/jon5477/CSCI4273/blob/master/Problem%20Sets/Set1/prob6b.jpg)

Problem 7
=========
![](https://github.com/jon5477/CSCI4273/blob/master/Problem%20Sets/Set1/prob7.jpg)

Problem 8
=========
Bridge X
|Address|Interface|
|-------|---------|
|   1   |    1    |
|   1   |    3    |
|   1   |    2    |
|   2   |    1    |
|   3   |    1    |
|   3   |    3    |

Bridge Y
|Address|Interface|
|-------|---------|
|   1   |    1    |
|   1   |    2    |
|   1   |    1    |
|   1   |    1    |
|   1   |    1    |
|   1   |    2    |

Problem 9
=========
The shortest paths to the root are kept (others are removed). If there is a tie on shortest path, the smallest ID is kept.
The links that are removed are:
```
B2 to A
B3 to B
B3 to F
B6 to I
```

Problem 10
==========
The new root is B2. The links that are removed are:
```
B3 to B
B3 to F
B6 to I
```

Very similar to Problem 9 except since B2 is the new root, the B2 to A path is now a valid short path.

Ping Assignment
===============
Please refer to the link for the results: https://raw.githubusercontent.com/jon5477/CSCI4273/master/Problem Sets/Set 1/Ping.md