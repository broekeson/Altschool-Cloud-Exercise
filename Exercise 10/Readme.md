Exercise 10

Task:

193.16.20.35/29

What is the Network IP, number of hosts, range of IP addresses and broadcast IP from this subnet?

Instruction: Submit all your answer as a markdown file in the folder for this exercise.
<br>
Ip address: 193.16.20.35
<br>Subnet: 29

<br>Solution:

- Calculate the Network IP: we need to convert the IP address and subnet mask to binary.

IP address:
```
193.16.20.35 => 11000001.00010000.00010100.0010001
```
Subnet mask:
```
29 => 11111111.11111111.11111111.11111000
```

Now we can calculate the Network IP by ANDing the IP address and subnet mask:
```
11000001.00010000.00010100.0010001
                AND
11111111.11111111.11111111.11111000
                 = 
11000001.00010000.00010100.00100000
```
Now convert the binary to decimal:
```
11000001.00010000.00010100.00100000 => 193.16.20.32
```
The Network IP is: 193.16.20.32

- Calculate the number of hosts for this subnet:
we need to calculate the number of 1's in the subnet mask. We can do this by subtracting the subnet mask from 32.
```
32 - 29 = 3
```
The number of hosts is: 2^3 = 8
Minus Network IP = First Host & Last Host = Broadcast IP
The number of useable hosts is: 8 - 2 = 6

<br> Formula: 2^(32 - subnet) - 2
```
(2^3 - 2 = 6 usable hosts) 
```
The Number of hosts is: 6

- Calculate the range of IP addresses: 
The range of IP addresses can be assigned to hosts is from the first usable host to the last usable host. The first usable host is the Network IP + 1 and the last usable host is the Broadcast IP - 1.

The first usable host is: 
```
Network IP: 193.16.20.32 + 1 = 193.16.20.33
```
The range of IP addresses is:
```
193.16.20.33
193.16.20.34
193.16.20.35
193.16.20.36
193.16.20.37
193.16.20.38
```

- Calculate the Broadcast IP:
The Broadcast IP is the Network IP + the number of useable hosts + 1.
```
The Network IP: 193.16.20.32 + 6 + 1 = 193.16.20.39
```
The Broadcast IP is: 193.16.20.39

We can also calculate the Broadcast IP by ORing the IP address and the inverted subnet mask.
```
11000001.00010000.00010100.0010001
                OR
00000000.00000000.00000000.00000111
                 =
11000001.00010000.00010100.00100111
```
Now convert the binary to decimal:
```
11000001.00010000.00010100.00100111 => 193.16.20.39
```
The Broadcast IP is: 193.16.20.39

[//]: # (end_exercise)
