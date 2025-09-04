# KB4 ネットワーク探索の順序と周波数バンドは何を設定すればいいのか

## 質問

サンプルスケッチに`SEARCH_ACCESS_TECHNOLOGY`や`LTEM_BAND`の設定がありますが、何を設定すればいいのかわからない。

```
#define SEARCH_ACCESS_TECHNOLOGY (WioCellularNetwork::SearchAccessTechnology::LTEM)
#define LTEM_BAND                (WioCellularNetwork::ALL_LTEM_BAND)
```

```
WioNetwork.config.searchAccessTechnology = SEARCH_ACCESS_TECHNOLOGY;
WioNetwork.config.ltemBand               = LTEM_BAND;
```

## 回答

`WioNetwork.config.searchAccessTechnology`と`WioNetwork.config.ltemBand`はセルラーモジュールがネットワーク（基地局と読み替えるとイメージしやすい）を検出する振る舞いに関する設定です。

具体的には、次のいずれかを設定するのが良いでしょう。

* キャリアがNTTドコモでLTE-Mの場合

    ```
    #define SEARCH_ACCESS_TECHNOLOGY (WioCellularNetwork::SearchAccessTechnology::LTEM)
    #define LTEM_BAND                (WioCellularNetwork::NTTDOCOMO_LTEM_BAND)
    ```

* キャリアがKDDIでLTE-Mの場合

    ```
    #define SEARCH_ACCESS_TECHNOLOGY (WioCellularNetwork::SearchAccessTechnology::LTEM)
    #define LTEM_BAND                (WioCellularNetwork::KDDI_LTEM_BAND)
    ```

* とにかく広範囲にしたい場合

    ```
    #define SEARCH_ACCESS_TECHNOLOGY (WioCellularNetwork::SearchAccessTechnology::LTEM_NBIOT)
    #define LTEM_BAND                (WioCellularNetwork::ALL_LTEM_BAND)
    ```

    or

    ```
    #define SEARCH_ACCESS_TECHNOLOGY (WioCellularNetwork::SearchAccessTechnology::NBIOT_LTEM)
    #define LTEM_BAND                (WioCellularNetwork::ALL_LTEM_BAND)
    ```

検出する範囲が広いとネットワークを見つけて接続できる機会が増えますが、そのかわりに探索時間が長くなります。ご注意ください。

## 補足説明

`WioNetwork.config.searchAccessTechnology`は探索するアクセステクノロジーと順序です。次のいずれかを設定します。

* `WioCellularNetwork::SearchAccessTechnology::LTEM`

    LTE-Mのみを探索します。

* `WioCellularNetwork::SearchAccessTechnology::NBIOT`

    NB-IoTのみを探索します。

* `WioCellularNetwork::SearchAccessTechnology::LTEM_NBIOT`

    LTE-Mの後に、NB-IoTを探索します。

* `WioCellularNetwork::SearchAccessTechnology::NBIOT_LTEM`

    NB-IoTの後に、LTE-Mを探索します。

`WioNetwork.config.ltemBand`と`WioNetwork.config.nbiotBand`は探索する周波数バンドです。
LTE B1は"0x1"、LTE B2は"0x2"、LTE B1&B2は"0x3"と、周波数バンドそれぞれをビットに割り当てた値のORを設定します。
ビットが"1"の周波数バンドを検出に使用します。
キャリア毎に使用する周波数バンドが決められているので、NTTドコモとKDDIの周波数バンドに合わせた変数をライブラリ内に定義しています。

* `WioCellularNetwork::ALL_LTEM_BAND`

  BG770Aで使用できる全ての周波数バンドです。

* `WioCellularNetwork::NTTDOCOMO_LTEM_BAND`

  NTTドコモのLTE-M周波数バンドです。

* `WioCellularNetwork::KDDI_LTEM_BAND`

  KDDIのLTE-M周波数バンドです。

## 参考リンク

* [Wio BG770A セルラー関連情報](https://seeedjp.github.io/Wiki/Wio_BG770A/cellular.html)
