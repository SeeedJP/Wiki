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
ABORT_IF_FAILED(WioCellular.powerOn(POWER_ON_TIMEOUT));
```

SORACOMプラットフォームのAPNを設定します。
APNは一度設定するとセルラーモジュールで記憶するので、`WioCellular.getPdpContext()`で未設定かどうかを確認してからAPNを設定するようにします。
APNを設定するときは電話の機能レベルを最小にしてセルラー通信を止めます。

```cpp
std::vector<WioCellularModule::PdpContext> pdpContexts;
ABORT_IF_FAILED(WioCellular.getPdpContext(&pdpContexts));

if (std::find_if(pdpContexts.begin(), pdpContexts.end(), [](const WioCellularModule::PdpContext& pdpContext) {
    return pdpContext.apn == APN;
    })
    == pdpContexts.end()) {
ABORT_IF_FAILED(WioCellular.setPhoneFunctionality(0));
ABORT_IF_FAILED(WioCellular.setPdpContext({ PDP_CONTEXT_ID, "IP", APN, "0.0.0.0", 0, 0, 0 }));
ABORT_IF_FAILED(WioCellular.setPhoneFunctionality(1));
}
```

SORACOM Unified Endpointへ送信は`WioCellular.openSocket()`、`WioCellular.sendSocket()`、`WioCellular.receiveSocket()`、`WioCellular.closeSocket()`を呼びます。

```cpp
WioCellular.openSocket(PDP_CONTEXT_ID, SOCKET_ID, "TCP", HOST, PORT, 0);
WioCellular.sendSocket(SOCKET_ID, data, size);
WioCellular.receiveSocket(SOCKET_ID, recvData, sizeof(recvData), &recvSize, RECEIVE_TIMEOUT);
WioCellular.closeSocket(SOCKET_ID);
```
