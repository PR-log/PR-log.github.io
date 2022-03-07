# 파이썬 네트워크
-----

간단한 파이썬 소켓 프로그래밍  
sockt 
```
import socket
from _thread import *

def threaded(client_socket,addr):
    print('Connected by;', addr[0], ':', addr[1]) #접속 확인 출력

    while True:
        try:

            data = client_socket.recv(1024)

            if not data:
                print('Disconnected by ' + addr[0], ':', addr[1])
                break
            print('Recived from ' + addr[0],':', addr[1] , data.decode())

            client_socket.send(data)

        except ConnectionResetError as e:
            print('Disconnected by' + addr[0], ':', addr[1])
            break
    
    client_socket.close()

HOST = '127.0.0.1' #호스트 주소 
PORT = 9999 #임의의 포트

server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
server_socket.bind((HOST, PORT))
server_socket.listen()

print('server start')

while True:
    print('wait')
    client_socket, addr = server_socket. accept()
    start_new_thread(threaded, (client_socket, addr))

server_socket.close()
```
