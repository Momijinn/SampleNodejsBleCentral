# SampleNodejsBleCentral
node.jsでBLE通信におけるCentralの役割をするサンプルプログラム

## 動作確認環境
* RaspberryPi3
* node v6.11.5

## インストール
```bash
$ sudo apt-get update
$ sudo apt-get upgrade -y
$ sudo reboot
$ sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
$ sudo apt-get install git
$ npm init
$ npm install --save-dev noble
```

## 起動方法
```bash
$ sudo node NodeBleConnection.js
```

## 解説
基本的に下記のところを書き換えればBLE通信ができると思います

周辺のBLE機器をスキャンして検索したいデバイス名があったら接続をします

その後、そのデバイスが持っているServiceのUUIDを検索し見つけたら接続

そしてServiceの中に接続したCharacteristicがあればそれを受け取るようにしています
```javascript
var DEVICE_NAME = "MyBlePeripheral"; //検索したいデバイス名
var SERVICE_UUID = "713d0000503e4c75ba943148f18d941e"; //検索したいサービスのUUID
var SERVICE_CHARACTERISTIC_UUID = "713d0001503e4c75ba943148f18d941e"; //検索したいキャラクタスタティックのUUID
```

ほんとに動くかどうかを試したい場合はBlenano2を購入し、以下のGitHubに上がっているサンプルのPeripheralプログラムをBlenano2書き込んでみてください

https://github.com/Momijinn/SampleBlenano2BlePeripheral.git

## blog
[Autumncolor.com](http://www.autumn-color.com/)