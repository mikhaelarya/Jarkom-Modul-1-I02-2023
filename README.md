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

Procedure:

1. Use the following filter to identify all HTTP requests :
```
http (contains server)*
```

	*Note :
contains server is used in the filter above assuming that the name of the web server technology is part of the header somewhere, not knowing where the web server name may be.

2. Identify the bottom HTTP request packet.

3. Extract the Server: header from the bottom HTTP request packet.

4. The server: header contains the web server technology used.

Result:
The web server name is extracted from the server: header in the bottom HTTP request packet.

The name of the server is:
```
gunicorn.
```
