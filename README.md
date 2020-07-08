##전주 비전대 project
#Install DHT11 sensor
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
##InfluxDB Installation < Influx = 파일을 생성 (공간 확보)>
#1.Repository의 GPG key를 더하기
```
curl -sL https://repos.influxdata.com/influxdb.key | sudo apt-key add -
```
#2.Repository를 더하기
```
echo "deb https://repos.influxdata.com/debian stretch stable" | sudo tee /etc/apt/sources.list.d/influxdb.list
```
#3.프로그램 설치
```
sudo apt update
sudo apt install influxdb
```
#4.프로그램 실행
```
sudo service influxdb start
```
#5.데이터베이스 만들기
```
> create database <데이터베이스이름>
```
```
확인 : show databases
```
##Grafana Installation <Grafana = 웹 즉 웹을 다운받는작업>
#1.Repository의 GPG key를 더하기
```
curl https://bintray.com/user/downloadSubjectPublicKey?username=bintray | sudo apt-key add -
```
#2.Repository를 더하기
```
echo "deb https://dl.bintray.com/fg2it/deb stretch main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```
#3.프로그램 설치
```
sudo apt update
sudo apt install grafana
```
#4.프로그램 실행
```
sudo service grafana-server start
```
#influxdb import with python (python 을 실행했을때 import 에러가 떳을때 설치하면 작동한다)
```
sudo pip install influxdb
```
