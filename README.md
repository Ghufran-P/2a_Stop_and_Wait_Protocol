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
### SERVER.PY
import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.connect((host,port)) 
while True:
    print(s.recv(1024).decode())
    s.send("Dialogue Completed.".encode())
### CLIENT.PY
import socket 
s=socket.socket() 
host='127.0.0.1'
port=8080
s.bind((host,port)) 
s.listen(5) 
c,addr=s.accept()
while True:
    i=input("Enter Ram's script: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack: 
        print(ack) 
        continue
    else: 
        c.close() 
        break
## OUTPUT
### SERVER.PY
<img width="581" height="162" alt="591504287-fc1ddd1a-0bf6-465e-b109-1f7d4a56f4e7" src="https://github.com/user-attachments/assets/a7f01f51-15d9-4e23-bc7a-595b58693287" />

### CLIENT.PY
<img width="785" height="251" alt="591504474-7133327a-f4fd-4ef4-9e15-f3f08bfdd320" src="https://github.com/user-attachments/assets/fc7f67dc-f99b-4d65-ba54-4a09f18610ca" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
