# cellular/cellular-status

セルラー通信の状況を表示するスケッチです。

## 概要

セルラーモジュールの電源をオンして、5秒周期に、セルラー通信の状況をシリアルモニタに表示します。

シリアルモニタの改行コードは`CRのみ`を選択してください。

<a href="../../media/54.png"><img src="../../media/54.png" width="300"></a>

## 最初に表示される情報

|項目|説明|
|:--|:--|
|IMEI|IMEI(international mobile equipment identity)。|
|Revision|セルラーモジュールのファームウェアのレビジョン。|
|SIM Inserted|SIM挿入ステータス。|
|SIM Init|SIMの初期化ステータス。|
|SIM State|PIN状態。|
|IMSI|IMSI(international mobile subscriber identity)。|
|ICCID|ICCID(integrated circuit card identifier)。|
|Phone Number|電話番号。|
|Search ACT|ネットワーク探索のアクセステクノロジー。|
|Search ACT Sequence|ネットワーク探索のアクセステクノロジー順序。|
|Search Band - eMTC|ネットワーク探索のeMTC周波数バンド。|
|Search Band - NB-IoT|ネットワーク探索のNB-IoT周波数バンド。|

### 表示例

```
IMEI:                 865502060041927
Revision:             BG770AGLAAR02A05_JP_01.200.01.200
SIM Inserted:         1(Yes)
SIM Init:             3(CPIN Ready & SMS Done)
SIM State:            READY
IMSI:                 440103167698583
ICCID:                8981100005810680869F
Phone Number:         07043466052
Search ACT:           2(eMTC and NB-IoT)
Search ACT Sequence:  0203(eMTC -> NB-IoT)
Search Band - eMTC:   0x2000000000f0e189f
Search Band - NB-IoT: 0x200000000090f189f
```

## 定期的に表示される情報

|項目順|説明|
|:--|:--|
|1|稼働時間。|
|2|情報の種類。"Status"|
|3|受信信号強度。|
|4|ビット誤り率。|
|5|EPSネットワーク登録状態。|
|6|ネットワークオペレーター。|
|7|パケットドメインサービスの状態。|

### 表示例

```
16	Status	15(-83dBm)	0(0~0.2%)	2(Searching)	JP DOCOMO, 7(eMTC)	1(Attached)
22	Status	17(-79dBm)	0(0~0.2%)	1(Registered, Home Network)	NTT DOCOMO, 7(eMTC)	1(Attached)
27	Status	15(-83dBm)	0(0~0.2%)	1(Registered, Home Network)	NTT DOCOMO, 7(eMTC)	1(Attached)
32	Status	15(-83dBm)	0(0~0.2%)	1(Registered, Home Network)	NTT DOCOMO, 7(eMTC)	1(Attached)
```
