# 2a_Stop_and_Wait_Protocol
### Name:Swetha D
### Reg no:212223040222
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
# Client
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
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
# Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
<h3>Client</h3>
<img width="563" height="208" alt="image" src="https://github.com/user-attachments/assets/70c40600-7c3f-46e2-b8d4-73170242e350" />
<h3>Server</h3>
<img width="621" height="145" alt="image" src="https://github.com/user-attachments/assets/8af7c4e7-2ce7-4e20-84f9-b1495bb68fa8" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
