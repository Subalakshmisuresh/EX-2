# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:

AIM:
To write a python program to perform stop and wait protocol


ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program


PROGRAM:

CLIENT:
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
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
 ```

OUTPUT:

CLIENT:

![cn-2c](https://github.com/Subalakshmisuresh/EX-2/assets/121957896/ad779c8c-4060-4c0d-920c-5a1562732656)

SERVER:

![cn-2s](https://github.com/Subalakshmisuresh/EX-2/assets/121957896/0b9ff73d-6ced-4ee9-95e8-d3973c862149)


RESULT:

Thus, python program to perform stop and wait protocol was successfully executed
