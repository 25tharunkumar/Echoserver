# EX NO 01 Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
```
import socket


HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
```
Client Code:
# echo-client.py


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")

```
## OUTPUT:
![WhatsApp Image 2024-09-04 at 19 27 06_c6ae148c1](https://github.com/user-attachments/assets/8a53a9ba-89fe-45c1-b3cd-e1d3d5821bdd)

![WhatsApp Image 2024-09-04 at 19 27 21_666cbbf7(2)](https://github.com/user-attachments/assets/bcf1a468-f7bf-4678-860b-815ade432e7a)

## RESULT:
The program is executed successfully
