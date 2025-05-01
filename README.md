# 2a_Stop_and_Wait_Protocol
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
## Client:
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## Client:
![439240614-d2ee1216-f39f-47a9-b408-9419966b71ce](https://github.com/user-attachments/assets/8f8ad480-c949-453c-8d19-83c4cdcc2347)
## Server:
![439240714-e4c7f19e-7e44-451b-a28f-777093d4b33d](https://github.com/user-attachments/assets/81c22bfa-184a-48f7-92b3-4be9a8ab266d)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
