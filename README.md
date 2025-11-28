# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
**Client**
```
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    while True:
        message = input("Enter message to send to server: ")
        s.sendall(message.encode())
        data = s.recv(1024)
        print('Received', repr(data.decode()))
```
**Server**
```
import socket

HOST = '127.0.0.1'
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
   s.bind((HOST, PORT))
   s.listen()
   conn, addr = s.accept()
   with conn:
       print(f"Server is listening on {HOST}:{PORT}")
       print('Connected by', addr)
       while True:
           data = conn.recv(1024)
           if not data:
               break
           conn.sendall(data)

```
## OUPUT
**Client**

<img width="488" height="157" alt="image" src="https://github.com/user-attachments/assets/0749b749-308b-4985-9791-08fe8e84e5ec" />


**Server**

<img width="746" height="129" alt="image" src="https://github.com/user-attachments/assets/0a60bbd6-6668-445b-9109-d751620c5767" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
