# 2a_Stop_and_Wait_Protocol:
## AIM :
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM :
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',7000))
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',7000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
## Client:
![Screenshot 2024-08-22 215640](https://github.com/user-attachments/assets/9054915d-6726-4df5-8808-16bbba27104a)
## Server:
![Screenshot 2024-08-22 215417](https://github.com/user-attachments/assets/ac63b04b-9738-4d8c-809c-413cb1c135ba)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
