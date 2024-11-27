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

SORACOM Unified Endpointへ送信は`WioCellular.openSocket()`、`WioCellular.sendSocket()`、`WioCellular.receiveSocket()`、`WioCellular.closeSocket()`を呼びます。

```cpp
WioCellular.openSocket(PDP_CONTEXT_ID, SOCKET_ID, "TCP", HOST, PORT, 0);
WioCellular.sendSocket(SOCKET_ID, data, size);
WioCellular.receiveSocket(SOCKET_ID, recvData, sizeof(recvData), &recvSize, RECEIVE_TIMEOUT);
WioCellular.closeSocket(SOCKET_ID);
```
