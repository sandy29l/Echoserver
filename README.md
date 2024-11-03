# Echoserver
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
## SERVER
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
## CLIENT
```
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Santhosh L,")
    s.sendall(b"212222100046")
    data = s.recv(1024)


print(f"Received {data!r}")
```

## OUTPUT:
![Screenshot (84)](https://github.com/user-attachments/assets/bd0b9d61-534f-4a78-aab7-7bc019e8d301)
![Screenshot (83)](https://github.com/user-attachments/assets/d7f10ea5-b474-46ee-820c-4bcb7fcba4b5)



## RESULT:
The program is executed successfully
