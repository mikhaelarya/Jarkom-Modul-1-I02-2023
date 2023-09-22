# Jarkom-Modul-1-I02-2023
<hr>

### Soal 1

Objective:
Identify the raw sequence numbers (seq nums) and acknowledge numbers (ack nums) of the packets that show the activity of uploading files and its corresponding response.

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
http (contains server)*
```


* Note:
The contains server is used in the filter above assuming that the name of the web server technology is part of the header somewhere, not knowing where the web server name may be.

2. Identify the bottom HTTP request packet.

3. Extract the Server: header from the bottom HTTP request packet.

4. The server: header contains the web server technology used.

Result:
The web server name is extracted from the **server: header** in the bottom HTTP request packet.

The name of the server is:

```
gunicorn.
```


### Soal 3

Objective:
Get the number of packets coming to and from the address 239.255.255.250 with the port 3702

1. Filter the packets to only show packets coming to and from address 239.255.255.250 with ip.dst == 239.255.255.250

2. Filter more packets by only showing ones with port number 3702 by using udp.dstport == 3702

3. Count the number of packets listed
	
* Note :
The filter only checks destination, but none have the address 239.255.255.250 with port 3702 as a source, so it produces the same result anyway.

A lot of the protocols are udp when checked using the address filter. Therefore, udp is assumed as the protocol used for the ports.

Results:
The number of packets commuting via address 239.255.255.250 and port 3702 amounts to **21**, and the Protocol Layer Transport is based on **UDP**.
