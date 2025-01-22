# soracom/soracom-uptime-tcpclient

WioCellularArduinoTcpClientクラスで送受信するスケッチです。
稼働時間をSORACOM Unified Endpointへ送信します。

## 概要

5分周期に、稼働時間をSORACOM Unified Endpointへ送信します。
送信にはTCPを使います。

## 詳細

WioCellularArduinoTcpClientクラスはClientクラスを継承しているので、Clientクラスを使う通信プロトコルのライブラリを利用することができます。
例えば、[ArduinoHttpClientライブラリ](https://docs.arduino.cc/libraries/arduinohttpclient/)ライブラリや[PubSubClientライブラリ](https://docs.arduino.cc/libraries/pubsubclient/)があります。

下記コードで、WioCellularArduinoTcpClientインスタンスを使えるようにします。

```cpp
WioCellularArduinoTcpClient<WioCellularModule> client{ WioCellular, WioNetwork.config.pdpContextId };```

WioCellularArduinoTcpClientインスタンスの使い方は、Clientクラスと同じです。

`client.connect()`で接続しておき、

```cpp
client.connect(HOST, PORT);
```

送信は`client.write()`を呼びます。

```cpp
client.write(reinterpret_cast<const uint8_t*>(data), size);
```

受信は`client.read()`を呼びます。

```cpp
const int recvSize = client.read(recvData, sizeof(recvData));
```

受信したデータがあるかどうかを確認したいときは`client.available()`を呼びます。

```cpp
availableSize = client.available();
```
