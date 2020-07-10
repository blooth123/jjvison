## 전주 비전대 project
# DHT11 sensor install
```
git clone https://github.com/adafruit/Adafruit_Python_DHT.git 
cd Adafruit_Python_DHT
sudo python setup.py install
cd examples
```
- run
```
python AdafruitDHT.py 11 4
```
## InfluxDB Installation < Influx = 파일을 생성 (공간 확보)>
# 1.Repository의 GPG key를 더하기
```
curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
```
# 2.Repository를 더하기
```
echo "deb https://repos.influxdata.com/debian stretch stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
```
# 3.프로그램 설치
```
sudo apt update
sudo apt install influxdb
```
# 4.프로그램 실행
```
sudo service influxdb start
```
# 5.데이터베이스 만들기
```
> create database <데이터베이스이름>
```
```
확인 : show databases
```
## Grafana Installation <Grafana = 웹 즉 웹을 다운받는작업>
# 1.Repository의 GPG key를 더하기
```
curl https://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -
```
# 2.Repository를 더하기
```
echo "deb https://dl.bintray.com/fg2it/deb stretch main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
# 3.프로그램 설치
```
sudo apt update
sudo apt install grafana
```
# 4.프로그램 실행
```
sudo service grafana-server start
```
# influxdb import with python (python 을 실행했을때 import 에러가 떳을때 설치하면 작동한다)
```
sudo pip install influxdb
```
### github use 
- Repository down load
```
git clone https://github.com/blooth123/jjvison (blooth123, jjvison = user name, repository name)
```
```
sudo = super user
sudo ufw allow 22 (or) 80 = firewall
```
# vim editor setting
```
vim .vimrc = vim editor setting
set nu = Line namber
set cindent - C language indent
set ts=4 - python tab size 4
if has("syntax") = syntax on
set softtabstop=4
set bg-dark
set expandtab
let python_version_2 = 1 
let python_highlight_all = 1
filetype indent plugin on // 76 line ~ 81 line = python
```
## python code
```
  1 #!/usr/bin/python
  2 
  3 import time
  4 import RPi.GPIO as GPIO
  5 
  6 print GPIO.VERSION
  7 GPIO.setmode(GPIO.BCM)
  8 GPIO.setup(4, GPIO.IN)
  9 
 10 def intterrupt_fired(channel):
 11     print("interrupt Fired")
 12     print(channel)
 13 
 14 GPIO.add_event_detect(4, GPIO.FALLING, callback=interrupt_fired)
 15 
 16 while(True):
 17     time.sleep(1)
 18     print("timer fired")
 19 
```
# sudo raspi-config -> Interfacing Options -> VNC
```
vnc viewer download 
vnc server
```
# sudo raspi-config -> Interfacing Options -> serial
```
entable / disable setting
```
## blooth off
```
sudo systemctl disable hciuartsudo 
->dtoverlay=pi3-disable-bt
vim /boot/config.txt
```
## telegram
### phone
```
telegram download
botfader -> /newbot
bot name -> ( name )_bot
```
# telegram 
```
pip3 install python-telegram-bot --upgrade // bot download
git clone https://github.com/python-telegram-bot/python-telegram-bot --recursive
cd python-telegram-bot/
cd examples
vim timerbot.py -> 80 line (main) -> nuser TOke
```
