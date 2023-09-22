# Jarkom-Modul-1-I02-2023
<hr>

### Soal 1
![alt text](https://github.com/mikhaelarya/Jarkom-Modul-1-I02-2023/blob/main/images/soal1-1.png)
![alt text](https://github.com/mikhaelarya/Jarkom-Modul-1-I02-2023/blob/main/images/soal1-2.png)
Objective:
Identify the raw sequence numbers (**seq nums**) and acknowledge numbers (**ack nums**) of the packets that show the activity of uploading files and its corresponding response.

1. Identify all packets containing the STOR command.

2. Filter the packets to only include those that are FTP.

3. Identify the bottom packet containing the STOR command.
   
4. Extract the raw seq num and ack num from the bottom packet containing the STOR command.

5. Identify the next packet containing the response to the STOR command.

6. Extract the raw seq num and ack num from the packet containing the response to the STOR command.

Results:
```
Upload :
Raw seq num: 258040667
Raw ack num: 1044861039
```

```
Response :
Raw seq num: 1044861039
Raw ack num: 258040696
```

<br><br>

### Soal 2

Objective:
Find the web server name and filter according to a down-top approach.

1. Use the following filter to identify all HTTP requests :

```
http contains server
```


* Note:
The contains server is used in the filter above assuming that the name of the web server technology is part of the header somewhere, not knowing where the web server name may be.

2. Identify the bottom HTTP request packet.

3. Extract the Server: header from the bottom HTTP request packet.

4. The server: header contains the web server technology used.

Result:
The web server name is extracted from the **server: header** in the bottom HTTP request packet.

The name of the server is
```
gunicorn.
```

<br><br>

### Soal 3

Objective:
Get the number of packets coming to and from the address **239.255.255.250** with the port **3702**.

1. Filter the packets to only show packets coming to and from address 239.255.255.250 with
```
ip.dst == 239.255.255.250
```

2. Filter more packets by only showing ones with port number 3702 by using
```
udp.dstport == 3702
```

3. Count the number of packets listed
	
* Note :
The filter only checks destination, but none have the address 239.255.255.250 with port 3702 as a source, so it produces the same result anyway.

A lot of the protocols are udp when checked using the address filter. Therefore, udp is assumed as the protocol used for the ports.

Results:
The number of packets commuting via address 239.255.255.250 and port 3702 amounts to **21**, and the Protocol Layer Transport is based on **UDP**.

<br><br>

### Soal 4

Objective:
Find the checksum value from packet **130**.

1. Scroll to packet 130 in the Wireshark capture window.

2. Expand the UDP packet details.

3. Look for the Checksum field.

4. The checksum value is the two-byte hexadecimal value in the Checksum field.

Result:
The Checksum value from packet 130 is
```
0x18e5
```

<br><br>

### Soal 7

Objective:
Find the amount of packets addressed to **184.87.193.88**.

1. Filter using ip.dst == 184.87.193.88 to only show packets addressed to 184.87.193.88

2. Count the amount of packets listed with the filter

Result:
Number of packets is **6**

<br><br>

### Soal 10
Objective:
Find the credentials to login to telnet using wireshark


Procedure:

1. Apply the following filter to only display telnet packets: **telnet**, then look for packets that contain the string **Data : Password :**. The next packet after the packet that contains **Data : Password :** will contain the username and password data.

2. To only filter the packets to show the ones that contain the password, you can use the following filter: **contains Password :**.

3. The packet that contains **Password :** is packet number 259, it is assumed that the next telnet packet has the value of the password as plaintext. The telnet filter is used again here to find the password : **kesayangannyak0k0**.

4. The password value is then used in the next filter to find the username. The filter used is **telnet contains kesayangannya** , which contains a part of the password.

5. Then, the username is found on the first one listed with the password attached to it, **dhafin:kesayangannyak0k0**

Result:

Packet number 81 contains the username and password:

**Username: dhafin**
**Password: kesayangannyak0k0**

