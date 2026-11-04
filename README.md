# 2a Stop and Wait Protocol
## REG NO : 212225230116
## NAME : JEDIDIAH M D
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

client.py
```
import socket
s=socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
server.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived ".encode())
```
## OUTPUT

<img width="1465" height="297" alt="image" src="https://github.com/user-attachments/assets/b6f90794-b336-4c34-8292-84ef4f27a2ef" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
