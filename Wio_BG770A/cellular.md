# Wio BG770A セルラー関連情報

## バンド

[各携帯電話事業者の通信方式と周波数帯について@総務省](https://www.soumu.go.jp/main_content/000692919.pdf)

|バンド|Wio BG770A<br>LTE Cat.M1|Wio BG770A<br>LTE Cat.NB1|NTTドコモ|KDDI|
|:--|:--|:--|:--|:--|
|B1|Y|Y|Y|Y|
|B2|Y|Y| | |
|B3|Y|Y|Y|Y|
|B4|Y|Y| | |
|B5|Y|Y| | |
|B8|Y|Y| | |
|B11| | | |Y|
|B12|Y|Y| | |
|B13|Y|Y| | |
|B17| |Y| | |
|B18|Y|Y| |Y|
|B19|Y|Y|Y| |
|B20|Y|Y| | |
|B21| | |Y| |
|B25|Y|Y| | |
|B26|Y| |Y|Y|
|B27|Y| | | |
|B28|Y|Y|Y|Y|
|B66|Y|Y| | |
|B42| | |Y|Y|

### バンド指定

* NTTドコモ

    ```
    AT+QCFG="band",0,0xa040005,0x8040005
    ```

* KDDI

    ```
    AT+QCFG="band",0,0xa020005,0x8020005
    ```
