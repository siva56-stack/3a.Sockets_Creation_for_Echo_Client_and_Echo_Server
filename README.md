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
# client.py
#echo_server.py

import socket

#Create socket object
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

#Bind the socket with host and port
host = '127.0.0.1'
port = 5000
server_socket.bind((host, port))

#Listen for incoming connections
server_socket.listen(1)
print("Echo Server is waiting for connection...")

#Accept client connection
client_socket, addr = server_socket.accept()
print("Connected to:", addr)

while True:
    # Receive message from client
    data = client_socket.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    # Send the same message back to the client
    client_socket.send(data.encode())

#Close sockets
client_socket.close()
server_socket.close()
# server.py
#echo_client.py

import socket

#Create socket object
client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

#Connect to server
host = '127.0.0.1'
port = 5000
client_socket.connect((host, port))

while True:
    # Input message
    message = input("Enter message: ")

    # Send message to server
    client_socket.send(message.encode())

    if message.lower() == 'exit':
        break

    # Receive echoed message
    data = client_socket.recv(1024).decode()
    print("Server echoed:", data)

#Close socket
client_socket.close()
## OUPUT
## server.py
<img width="1181" height="186" alt="Screenshot 2026-11-18 101640" src="https://github.com/user-attachments/assets/e6ad724c-f80d-40a9-bc58-2fcf63ff8ca0" />
## client.py
<img width="1182" height="210" alt="Screenshot 2026-11-18 101726" src="https://github.com/user-attachments/assets/d1998d2c-ccc6-4126-8a99-647c1ab046dc" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
