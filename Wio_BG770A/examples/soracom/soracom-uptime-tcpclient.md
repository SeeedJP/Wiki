# soracom/soracom-uptime-tcpclient

WioCellularTcpClientクラスで送受信するスケッチです。
稼働時間をSORACOM Unified Endpointへ送信します。

## 概要

5分周期に、稼働時間をSORACOM Unified Endpointへ送信します。
送信にはTCPを使います。

## 詳細

WioCellularTcpClientクラスはClientクラスを継承しているので、Clientクラスを使う通信プロトコルのライブラリを利用することができます。
例えば、[ArduinoHttpClientライブラリ](https://www.arduino.cc/reference/en/libraries/arduinohttpclient/)ライブラリや[arduino-mqttライブラリ](https://www.arduino.cc/reference/en/libraries/mqtt/)があります。

下記コードで、TcpClientインスタンスを使えるようにします。

```cpp
static WioCellularTcpClient<WioCellularModule> TcpClient{ WioCellular, PDP_CONTEXT_ID, SOCKET_ID };
```

TcpClientインスタンスの使い方は、Clientクラスと同じです。

`TcpClient.connect()`で接続しておき、

```cpp
TcpClient.connect(HOST, PORT);
```

送信は`TcpClient.write()`を呼びます。

```cpp
TcpClient.write(reinterpret_cast<const uint8_t*>(data), size);
```

受信は`TcpClient.read()`を呼びます。

```cpp
recvSize = TcpClient.read(recvData, sizeof(recvData));
```

受信したデータがあるかどうかを確認したいときは`TcpClient.available()`を呼びます。

```cpp
availableSize = TcpClient.available();
```
