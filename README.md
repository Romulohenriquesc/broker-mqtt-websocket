# broker-mqtt-websocket

Instalar as dependências

$ sudo apt-get update
$ sudo apt-get install build-essential python quilt python-setuptools python3
$ sudo apt-get install libssl-dev
$ sudo apt-get install cmake
$ sudo apt-get install libc-ares-dev
$ sudo apt-get install uuid-dev
$ sudo apt-get install daemon
$ sudo apt-get install libwebsockets-dev/

Download mosquitto

$ cd Downloads/
$ wget http://mosquitto.org/files/source/mosquitto-1.4.10.tar.gz
$ tar zxvf mosquitto-1.4.10.tar.gz
$ cd mosquitto-1.4.10/
$ sudo nano config.mk

Editar arquivo config.mk

WITH_WEBSOCKETS:=yes

Build mosquitto

$ make
$ sudo make install
$ sudo cp mosquitto.conf /etc/mosquitto

Configurar portas para mosquito
Adicione as seguintes linhas ao /etc/mosquitto/mosquitto.conf na seção "Default Listener":

port 1883
listener 9001
protocol websockets

Adicionar usuário para mosquito
$ sudo adduser mosquitto

Reinicie o computador
$ reboot

Executar mosquito
$ mosquitto -c /etc/mosquitto/mosquitto.conf
