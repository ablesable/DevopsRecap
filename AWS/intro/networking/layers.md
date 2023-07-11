Device from specific layer **will understand this layer and all before layers**

1 layer - physical: 
- transmission and reception of raw bit streams
- shared medium

No device addressing, no collision detection on this layer!


-------------
Requires first layer working correctly.\

2 layer - data link:
- transmission of frames 
- Provides controlled access to Layer 1 by no collisions mechanism.
- Media access control
- Identifiable devices


L2 devices has Mac addresses are made of OUI and NIC.
Frame are made of:
- Preamble
- Destination Mac address or broadcasting (ALL F's) MAC HEADER PART
- Source MAC address MAC HEADER PART
- ET (what layer 3 protocol puts data to frame) MAC HEADER PART
- Payload **Needs to be extracted (decapsulated) from the frame**
- Frame Check Sequence (FCS)

If carrier is detected than it will be transmission. If transmission is done at the same time, then it will be **backoff** - moment when two parts will no transmit anything. One side must send something, and a second side must see a carry on.


