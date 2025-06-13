# soracom/soracom-uptime

稼働時間をSORACOM Unified Endpointへ送信するスケッチです。

## 概要

5分周期に、稼働時間をSORACOM Unified Endpointへ送信します。
送信にはTCPを使います。

## 詳細

WioCellular.hをインクルードして、WioCellularインスタンスを使えるようにします。

```cpp
#include <WioCellular.h>
```

セルラーモジュールとのインターフェースを初期化して、セルラーモジュールの電源をオンします。

```cpp
WioCellular.begin();
if (WioCellular.powerOn(POWER_ON_TIMEOUT) != WioCellularResult::Ok) abort();
```

ネットワーク探索のアクセステクノロジーと順序、LTE-M周波数バンド、SORACOMプラットフォームのAPNを設定します。

```cpp
WioNetwork.config.searchAccessTechnology = SEARCH_ACCESS_TECHNOLOGY;
WioNetwork.config.ltemBand = LTEM_BAND;
WioNetwork.config.apn = APN;
WioNetwork.begin();
```

必要に応じて、通信可能になるまで待機します。

```cpp
if (!WioNetwork.waitUntilCommunicationAvailable(NETWORK_TIMEOUT)) abort();
```

SORACOM Unified EndpointへTCP送信は`WioCellularTcpClient2.open()`、`WioCellularTcpClient2.waitforConnect()`、`WioCellularTcpClient2.send()`、`WioCellularTcpClient2.receive()`を呼びます。

```cpp
WioCellularTcpClient2<WioCellularModule> client{ WioCellular };
client.open(WioNetwork.config.pdpContextId, HOST, PORT);
client.waitforConnect();
client.send(str.data(), str.size());
client.receive(recvData, sizeof(recvData), &recvSize, RECEIVE_TIMEOUT);
```

TCPの代わりにUDPで送信したいときは`WioCellularUdpClient2`を使います。

```cpp
WioCellularUdpClient2<WioCellularModule> client{ WioCellular };
client.open(WioNetwork.config.pdpContextId, HOST, PORT);
client.waitforConnect();
client.send(str.data(), str.size());
client.receive(recvData, sizeof(recvData), &recvSize, RECEIVE_TIMEOUT);
```
