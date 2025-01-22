# cellular/cellular-mqtt-pubsubclient

MQTTブローカーへ稼働時間を送信（パブリッシュ）しながら、購読（サブスクライブ）したメッセージを受信し、シリアルモニタに表示します。

## 概要

MQTTブローカー`test.mosquitto.org:1883`に接続して以下の処理を行います。

* 5分周期に、稼働時間を送信します。トピックは`WioCellular/<IMSI>/upstream`です。
* 購読したメッセージを受信して、シリアルモニタに表示します。トピックは`WioCellular/<IMSI>/downstream`です。

送受信にはMQTTを使います。

WioCellularライブラリはTLS暗号通信には対応していません。
TLSのMQTT通信をしたいときは[SORACOM Beam](https://soracom.jp/services/beam/)をご活用ください。

## MQTT通信の確認方法

### PCにメッセージを受信

Wio BG770Aから送信されたメッセージを確認するコマンドです。
（`<IMSI>`の部分はSIMのIMSIに書き換えてください。）

```
mosquitto_pub -h test.mosquitto.org -p 1883 -t "WioCellular/<IMSI>/downstream" -m "<MESSAGE>"
```

### PCからメッセージを送信

Wio BG770Aへメッセージを送信するコマンドです。
（`<IMSI>`の部分はSIMのIMSIに書き換えてください。）

```
mosquitto_sub -h test.mosquitto.org -p 1883 -t "WioCellular/<IMSI>/upstream"
```

## 詳細

MQTT通信PubSubClientクラスを使います。
下記コードで、PubSubClientインスタンスを使えるようにします。

```cpp
#include <WioCellular.h>
#include <PubSubClient.h>

static WioCellularArduinoTcpClient<WioCellularModule> TcpClient{ WioCellular, PDP_CONTEXT_ID };
static PubSubClient MqttClient{ TcpClient };
```

PubSubClientインスタンスには事前に

* MQTTブローカーのホスト名
* MQTTブローカーのポート番号
* キープアライブ間隔
* 購読したメッセージを受信したときに呼び出すコールバック関数

を設定します。

```cpp
MqttClient.setServer(MQTT_BROKER_HOST, MQTT_BROKER_PORT);
MqttClient.setKeepAlive(MQTT_KEEP_ALIVE);
MqttClient.setCallback(MqttClientCallback);
```

MQTTブローカーへの接続は`PubSubClient::connect()`を呼びます。
引数でクライアントIDやユーザー名、パスワードなどを指定できます。
このサンプルはクライアントIDだけを指定しています。

接続に成功したら、購読するトピックを`PubSubClient::subscribe()`で設定します。
既に設定済みであっても再接続したときは再度設定する必要があります。

```cpp
MqttClient.connect(ClientId.c_str());
MqttClient.subscribe(SubscribeTopic.c_str());
```

接続している間は、必ず定期的に`PubSubClient::loop()`を呼んでください。
購読しているメッセージの受信やキープアライブを処理するためです。

```cpp
MqttClient.loop();
```

購読したメッセージを受信すると`PubSubClient::setCallback()`で設定したコールバック関数が呼び出されます。

コールバック関数の引数でトピックとメッセージ、メッセージ長が渡されます。

```cpp
static void MqttClientCallback(char* topic, byte* payload, unsigned int length) {
  ...
}
```

メッセージの送信は`PubSubClient::publish()`を呼びます。

```cpp
MqttClient.publish(PublishTopic.c_str(), str.c_str());
```

このサンプルは購読したメッセージを受信するため常時接続していますが、ネットワークやサーバーの事情で接続が切れてしまうことがあります。
突然の接続断にもきちんと対処しておきましょう。

```cpp
void loop(void) {
  if (!MqttClient.connected()) {
    if (!MqttClient.connect(ClientId.c_str())) {
      // 接続エラー
    } else {
      // 接続成功
    }
  } else {
    // 接続中
    WioCellular.doWork(10);
    MqttClient.loop();
    if (!MqttClient.connected()) break;
  }
}
```
