SampleNodejsBleCentral
====
node.jsでBLE通信におけるCentralの役割をするサンプルプログラム

## Description
node.jsでBLE通信におけるCentralの役割を行うためのサンプルプログラム



## Requirement
* node.js
* ライブラリ
    ```bash
    $ npm init
    $ npm install --save-dev noble
    ```
* 動作確認環境
    * RaspberryPi3
    * node v6.11.5

## Usage
```bash
$ sudo node NodeBleConnection.js
```

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

## Install
* NodeBleConnection.jsを管理者権限で起動

* RaspberryPi3でのセットアップ方法
    ```bash
    $ sudo apt-get update
    $ sudo apt-get upgrade -y
    $ sudo reboot
    $ sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
    $ sudo apt-get install git
    $ npm init
    $ npm install --save-dev noble
    ```



## Licence
This software is released under the MIT License, see LICENSE.

## Author
[Twitter](https://twitter.com/momijinn_aka)

[Blog](http://www.autumn-color.com/)