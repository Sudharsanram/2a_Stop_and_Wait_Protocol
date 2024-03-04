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
# CLIENT
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
# SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```

## OUTPUT
# CLIENT
![306664559-5e7536db-fd1a-4b3f-9358-211a771e8100](https://github.com/Sudharsanram/2a_Stop_and_Wait_Protocol/assets/119393980/1f0fc324-f21f-41c8-aa55-4527586b0ad7)
# SERVER
![306664797-08351b08-bc67-42a0-975a-88d1f145a355](https://github.com/Sudharsanram/2a_Stop_and_Wait_Protocol/assets/119393980/405b04e4-69f7-46f1-ae7b-f51df6ce7cc8)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
