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

Our results is as follows:

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

