-A flag stands for agressive scan/
-oG flag stands for grepable output
-vv flag (ultra verbose info)

------------
IMPORTANT

Subnetmask is for calulating how many bits are for network, and how many are for devices in that network.
E.g subnetmask 255.255.240.0 is 20. Cause 255 is 8 bits, 255 is 8 bits, 240 is 4 bits in binary encoding. 
If 20 bits are for network, then 12 bits left are for devices in that network. 12 bits for network means 2^12 = 4096 addresses.
