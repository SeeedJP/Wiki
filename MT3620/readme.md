# Azure Sphere MT3620 開発キット

Azure Sphereは、Azure Sphere MCU、Azure Sphere OS、および Azure Sphere Security Service を三位一体で提供することで、セキュリティに対する開発リソースやコストをかけずにインテリジェントな製品とエクスペリエンスを実現することができます。

MT3620開発キット（Azure Sphere MT3620 Development Kit）は、Azure Sphereに対応したMT3620の開発ボードです。

![enter image description here](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/azure.jpg)

Azure Sphere MT3620開発キットは、開発者がAzure Sphereを体験し、手早くプロトタイプをすることができるように設計されました。MT3620は、初のAzure Sphere認証MCUです。MT3620には、3つのユーザーアクセス可能なマイクロコントローラーのコア、1つのArm Cortex-A7と2つの汎用のArm Cortex-M4  with FPUコアを備えています。MT3620は、GPIO, UART, I2C, SPI, I2S, PWM, ADCといった多岐にわたるオンチップのペリフェラルに接続したときのリアルタイム要求をサポートするよう設計されています。また、デュアルバンド802.11 b/g/n無線LANに加えて、セキュアブートとセキュアなシステムオペレーションのための統合された専用のCM4Fコアによるセキュリティサブシステムも備えています。

現時点でのAzure Sphereソフトウェアリリースは、全てのMT3620のハードウェア機能をサポートしていない点にご注意ください。Arm Cortex-M4Fコアといくつかのペリフェラル(ADC, I2C, I2S, PWM and SPI)、 Wi-Fi 802.11a、RTCなどが未サポートです。ADCとI2Cについては、UARTとI2CやADCをブリッジする[MT3620 Grove Shield board](https://www.seeedstudio.com/MT3620-Grove-Shield-p-3145.html)を併用することで制限を回避することも可能です。

MT3620開発キットは、MT3620のハードウェア資源の多くを拡張ピンヘッダに接続しています。ブレッドボードに配線したり、拡張ボード（シールド）を追加することで、ユーザーは手軽にその他のハードウェアアクセサリに接続することができます。

Azure SphereオペレーティングシステムはMT3620にプリインストールされており、Azure Sphereセキュリティサービスと共にセキュアなIoTプラットフォームとして動作するように設計されています。主な機能は次の通りです。

- 証明書によるデバイス認証
- ソフトウェア認証とセキュア・ブート
- 異常報告による脅威の検出
- セキュリティ・アップデート
- 統合され、セキュアでエンドツーエンドなIoTソリューション

MT3620のソフトウェア開発には、Microsoft Visual Studio IDEを使用します。
- [Visual Studio](https://visualstudio.microsoft.com/) (Community、Professional、エンタープライズをサポート)とAzure Sphere extensionをインストールし、USBで開発ボードをPCと接続してください。
- MT3620開発ボードを使用するには、[Azure Sphere software development kit](http://aka.ms/AzureSphereSDK) SDKに加えて、最新のWIndows Update適用済みのWindows 10 PCが必要です。

<iframe width="800" height="450" src="https://www.youtube.com/embed/iiDF26HNh-Y" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## 機能

- Azure Sphere: IoTデバイス用のエンドツーエンドセキュリティ
- アンテナ・ダイバーシティ対応802.11 b/g/n
- オンチップRAMとFlashを備えた3コアのマイクロコントローラー
- Microsoft Visual Studio開発環境
- デバイスライフタイムのためのオンライン認証とアップデート

## Azure Sphereのはじめかた

MT3620開発ボードを使用するには、最新のWindows Update適用済みのWindows 10 PCに加えて、Visual StudioとAzure Sphere SDKが必要です。

現在のところ、Azure Sphereのドキュメントは英文でのみ提供されています。

- [Install the Azure Sphere SDK](https://docs.microsoft.com/ja-jp/azure-sphere/install/install) 
- [Set up an account](https://docs.microsoft.com/ja-jp/azure-sphere/install/azure-directory-account)
- [Claiming your device](https://docs.microsoft.com/ja-jp/azure-sphere/install/claim-device)
- [Configuring Wi-Fi](https://docs.microsoft.com/ja-jp/azure-sphere/install/configure-wifi)
- [Build an application](https://docs.microsoft.com/ja-jp/azure-sphere/quickstarts/qs-blink-application)
- [Deploy an application over the air](https://docs.microsoft.com/ja-jp/azure-sphere/quickstarts/qs-first-deployment)

## デバイスのクレーム実行時のエラー 
デバイスのクレームを実行時に下記のエラーが起きた場合、 [Microsoftのフォーラム](https://social.msdn.microsoft.com/Forums/en-US/3a9aeca1-d764-40e3-b2da-92ecc5efae19/sphere-update?forum=azuresphere)の英文記事にあるAnswersを参照してください。 

```
C:\Users\Seeed05\Documents>azsphere device claim
error: The Azure Sphere OS on the attached device requires an update to be used with this version of the SDK.
Diagnostic info: [1.2.0, 3]
error: Failed to retrieve device ID from attached device: 'The Azure Sphere OS on the attached device requires an update to be used with this version of the SDK.
Diagnostic info: [1.2.0, 3]'.
error: Command failed in 00:00:00.9187758.
```
## 制限事項

現在のところ、Azure Sphereのソフトウェアリリースは、MT3620の全てのハードウェア機能をサポートしていません。例えば、下記の機能は**未サポート**です。

- Arm Cortex-M4 with FPU
- ADC,、I2C、I2S、PWM、SPIペリフェラル・インターフェース（GPIOとUARTはサポートされています）
- 802.11a (b/g/nはサポートされています)
- RTC

詳細は、[Information and tools for hardware design and manufacture](https://docs.microsoft.com/en-us/azure-sphere/manufacturers/hardware-manufacturing)を参照下さい。



## スペック
### ハードウェア

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-amwm{font-weight:bold;text-align:center;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <td class="tg-amwm" rowspan="2"><br>MCU</td>
    <td class="tg-0lax">Arm Cortex-A7コア @500MHz x1, 4MB RAM</td>
  </tr>
  <tr>
    <td class="tg-0lax">Arm Cortex-M4コア @200MHz x2, 64KB RAM</td>
  </tr>
  <tr>
    <td class="tg-amwm" rowspan="5"><br><br><br><br>ISU</td>
    <td class="tg-0lax">以下に設定可能な「ISU」シリアルインターフェース x4</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;- 最大1MHzのI2C</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;- 最大40MHzのSPI</td>
  </tr>
  <tr>
    <td class="tg-0lax">&nbsp;&nbsp;- 最大3MbpsのUART</td>
  </tr>
  <tr>
    <td class="tg-0lax">ISUはシリアル通信インターフェースです。</td>
  </tr>
  <tr>
    <td class="tg-amwm">コネクティビティ</td>
    <td class="tg-0lax">2.4/5GHz dual-band 802.11 b/g/n Wi-Fi</td>
  </tr>
  <tr>
    <td class="tg-amwm">I2S</td>
    <td class="tg-0lax">I2S(スレーブとTDMスレーブモードをサポート) x1</td>
  </tr>
  <tr>
    <td class="tg-amwm">ADC</td>
    <td class="tg-0lax">12ビットADC入力 x4</td>
  </tr>
  <tr>
    <td class="tg-amwm">RTC</td>
    <td class="tg-0lax">RTC (CR2032 3Vバッテリーホルダ) x1</td>
  </tr>
  <tr>
    <td class="tg-amwm">USB</td>
    <td class="tg-0lax">Micro USBポート(デバッグ兼5V/1A電源用)x1</td>
  </tr>
  <tr>
    <td class="tg-amwm">DCジャック</td>
    <td class="tg-0lax">5V/1A DC電源ジャック x1</td>
  </tr>
  <tr>
    <td class="tg-amwm">動作温度範囲</td>
    <td class="tg-0lax">-40~85°C</td>
  </tr>
  <tr>
    <td class="tg-amwm">サイズ</td>
    <td class="tg-0lax">L:85mm x W:50mm x H:16mm</td>
  </tr>
  <tr>
    <td class="tg-amwm">認証</td>
    <td class="tg-0lax">CE / FCC / MIC / RoHS</td>
  </tr>
</table>


### ソフトウェア

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:black;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
  <tr>
    <td class="tg-0pky">IDE</td>
    <td class="tg-0pky">Visual Studio</td>
  </tr>
  <tr>
    <td class="tg-0lax">システム</td>
    <td class="tg-0lax">Windows10</td>
  </tr>
  <tr>
    <td class="tg-0lax">開発言語</td>
    <td class="tg-0lax">C</td>
  </tr>
</table>



## ハードウェアの概要

### ボードについて

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/Diagram.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/Diagram.png"/></a>

- **J1**: ADCリファレンス電圧 ショート：内部の2.5Vを使用　オープン：外部の1.8Vをピン1に接続 （標準ではオープン） 
- **J2**: 3.3V電源の選択 ショート：システムの3.3Vを有効に　オープン：システムの3.3Vを遮断（標準ではショート）
- **J3**: RTC電源の選択 左側2ピン：背面のCR2032RTCバッテリーを使用　右側2ピン：システムの3.3Vを使用
- **USB ポート**: 電源(5V/1A)とデバッグ用。背面のFT4232HQに接続されています。 
- **システム LED**: LED1（USBポート横）FTDIの動作状況。LED2: 電源インジケーター。LED3: 無線LANステータス。LED4: アプリケーションステータス
- **DC 電源端子**: 5V/1A
- **システムボタン**: 白色のボタンAとBはユーザーボタン。青色はシステムリセットボタン。
- **MT3620**：[MT3620](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/MediaTek%20MT3620%20Product%20Brief.pdf)は、高度に集積され、インターネットに接続するデバイスに求められる高いレベルのセキュリティを備えたハイパフォーマンスなIoT MCUです。MT3620が想定しているアプリケーションは、拡張性の高いI/Oペリフェラル・サブシステムによってスマートホームや商業・工業など多岐に渡り、柔軟性の高い設計が可能です。
- **FT4232HQ**: [FT4232H](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/DS_FT4232H.pdf)はUSB 2.0 High Speed (480Mb/s)とUART/MPSSEを接続するICです。

### ピン配置

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/PinMap.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/PinMap.png"/></a>

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/H1_2.png)

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/H3_4.png)

**Dimensions**

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/dimension.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/dimension.png"/></a>

**電源**

MT3620開発ボードへの電源供給は、オンボードのUSB Micro Bコネクタまたは、DCコネクタと想定されています。 

- GPIO電圧は3.3Vです。
- H3の5V_OUTの供給能力は、500mAです。
- H3の3.3Vの供給能力は、400mAです。
- 一般的な平均消費電力は、無線LANがONのときに5Vで150mAです。Wifiスキャン時には、一般的に330mAです。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/power.png)

## 取り扱い

**同梱品**
Azure Sphere MT3620開発キットのパッケージには、Azure Sphere MT3620開発キットとMicro B USB ケーブルが入っています。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/box.JPG)

**ESD Precautions**
Azure Sphere MT3620開発キットには、静電気の放電に敏感なデバイスが含まれています。静電気の放電によってこれらの装置が損傷するのを防ぐために必要な予防措置を採ってください。

## 認証

- FCC ID: [Z4T-MT3620DEVB](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-FCC-FCC.zip) 
- CE ID: [18/0331/SZ](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-CE.zip)
- MIC ID: [CSRT18207](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-MIC.zip)


## 資料

- **[Product]** [Azure Sphere MT3620 Development Kit Product Brief](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/product_document/Azure%20Sphere%20MT3620%20Development%20Kit%20Product%20Brief-2018-09-10.pdf)
- **[Product]** [Welcome to Azure Sphere](https://docs.microsoft.com/en-us/azure-sphere/)
- **[Certification]** [Azure Sphere MT3620 Development Kit-CE](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-CE.zip)
- **[Certification]** [Azure Sphere MT3620 Development Kit-FCC](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-FCC-FCC.zip)
- **[Certification]** [Azure Sphere MT3620 Development Kit-MIC](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-MIC.zip)
- **[DataSheet]]** [MediaTek MT3620 Product Brief](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/MediaTek%20MT3620%20Product%20Brief.pdf)
- **[DataSheet]** [DS_FT4232H](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/DS_FT4232H.pdf)
- **[Mechanical]** [Azure Sphere MT3620 Development Board-2D-Drawing](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/tree/master/mechanical)
- **[FAQ Web]** [Azure Sphere Forum](https://social.msdn.microsoft.com/Forums/en-US/home?forum=azuresphere)
- **[FAQ Web]** [Azure Sphere Github issues](https://github.com/MicrosoftDocs/azure-sphere-issues/issues?utf8=%E2%9C%93&q=is%3Aissue)

## テクニカルサポート
テクニカルな問題については、私たちの[フォーラム](http://forum.seeedstudio.com/)（英語のみ）に投稿してください。

# MT3620 Grove Shield

現状、[Azure Sphere SDK](http://aka.ms/AzureSphereSDK)はMT3620のADCやI2Cをサポートしていません。このシールドは、MT3620のUARTと、I2C温度センサなど外部のI2Cデバイスとのブリッジの役割をします。このシールドの基本的な機能は、外部のI2Cデバイスとの接続を可能にすることです。また、ADCも搭載していますので、アナログポートからアナログ値の読み取りも可能です。

[MT3620 Grove Shield](https://www.seeedstudio.com/MT3620-Grove-Shield-p-3145.html)には、AD7992(Anlog to I2C)とSC18IM700(I2C to UART)の2つのチップが搭載されています。アナログ信号はAD7992で読まれ、そしてSC18IM700を経由して開発ボードのUARTに接続されます。I2Cセンサは、同様にSC18IM700を通じて開発ボードのUARTに接続されます。

[AD7992](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/AD7992.pdf)は12ビットの低消費電力な I2Cコンパチブルのシリアル・インターフェースを備えたA/Dコンバーターです。A0とA1ピンの信号をI2Cデータに変換します。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/ADC_2_I2C.png)

[SC18IM700](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/SC18IM700.pdf)は、マイコンの標準的なUARTポートとI2Cバスをインターフェースするために設計されました。SDA/SCL信号をGPIO26_TXD0とGPIO28_RXD0との通信に変換します。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/I2C_2_UART.png)

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/MT3620_Grove_Shield-2018-09-11.png)

<div style="text-align:center">MT3620 Grove Shield Hardware Overview</div>