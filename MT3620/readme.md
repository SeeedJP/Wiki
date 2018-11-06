# Azure Sphere MT3620 Development Kit

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

### Board Diagram

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/Diagram.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/Diagram.png"/></a>

- **J1**: ADC Reference Voltage, On: using internal 2.5v; Off: Connect External 1.8v to Pin 1. Off by default. 
- **J2**: 3.3V Isolation, On: Enable system 3.3v power; Off: Cut off the system 3.3v power. On by default.
- **J3**: RTC Power Selection: Left 2 pins: Using RTC Battery(Model:CR2032) at backside.
- **4 User RGB LED**: LED model is LTST-C19HE1WT.
- **USB Port**: Power supply(5V/1A) and debug, connected to FT4232HQ chip at backside. 
- **4 System LED**: Led1(Near USB port): Green, FTDI Activity LED. Led2: RED, Power Indicator. Led3: RGB, Wifi Status. Led4: RGB, App Status.
- **DC Power**: 5V/1A
- **3 System Button**: Button A&B(White) are user botton. Button Reset(Blue) is System Reset.
- **MT3620**：The [MT3620](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/MediaTek%20MT3620%20Product%20Brief.pdf) is a highly integrated, high performance IoT MCU with the high level of security necessary for modern, robust internet-connected devices. The MT3620 targets a wide range of IoT applications including smart home, commercial, industrial and many other domains thanks to its extensive I/O peripheral subsystem that allows device design flexibility and freedom.
- **FT4232HQ**: The [FT4232H](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/DS_FT4232H.pdf) is a USB 2.0 High Speed (480Mb/s) to UART/MPSSE ICs.

### Board Pinmap

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/PinMap.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/PinMap.png"/></a>

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/H1_2.png)

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/H3_4.png)

**Dimensions**

<a href="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/dimension.png" target="_blank"><img src="https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/dimension.png"/></a>

**電源**

Power to the Azure Sphere MT3620 Development Kit is supplied via the on-board USB Micro B connector or directly via the DC connector. 

- GPIO voltage is 3.3v, has a limited overhead of only 100mA available.
- 5v_out on H3 connector has a limited overhead of only 500mA available.
- 3.3v on H3 connector has a limited overhead of only 400mA available. 
- Typical average current consumption is 150mA with 5V Wi-Fi on. Wifi scan current is typically 330ma.

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/power.png)


**Hardware Design and Manufacture**

The current Azure Sphere software release does not support all features of the [MT3620](https://www.mediatek.com/products/azureSphere/mt3620) hardware. For example, the following are **not yet supported** in software:

- 2 x ARM Cortex-M4 with FPU
- ADC, I2C, I2S, PWM and SPI peripheral interfaces (GPIO and UART are supported)
- Wi-Fi 802.11a (b/g/n are supported)
- RTC with clock selection and battery backup

!!!Tip
​    For more info, please refer to [Information and tools for hardware design and manufacture](https://docs.microsoft.com/en-us/azure-sphere/manufacturers/hardware-manufacturing).

## Product Handling

**Packaging**

The Azure Sphere MT3620 Development Kit packaging contains Azure Sphere MT3620 Development Kit and Micro B USB cable.

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/box.JPG)

**ESD Precautions**

The Azure Sphere MT3620 Development Kit contains highly sensitive electronic circuitry and is an Electrostatic Sensitive Device (ESD). Handling The Azure Sphere MT3620 Development Kit without proper ESD protection may destroy or damage it permanently. Proper ESD handling and packaging procedures must be applied throughout the processing, handling and operation of any application that incorporates Azure Sphere MT3620 Development Kit.

## Applications

- Home/Building/Facilities
- Automation
- Security
- Equipment Management
- Utilities
- Public Safety

!!!Tip
​    To understand how Azure Sphere works in a real-world setting, consider [Contoso, Ltds cenario](https://docs.microsoft.com/en-us/azure-sphere/product-overview/scenario).

## Qualification and approvals

- FCC ID: [Z4T-MT3620DEVB](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-FCC-FCC.zip) 
- CE ID: [18/0331/SZ](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-CE.zip)
- MIC ID: [CSRT18207](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/certification/Azure%20Sphere%20MT3620%20Development%20Kit-MIC.zip)

## Quickstarts for Azure Sphere

To use MT3620 Dev Board for Azure Sphere, you’ll need a Windows 10 PC with the latest Windows Updates, alongwith the Visual Studio Tools for Azure Sphere (which will be available for download from Microsoft). These tools will include application templates, development tools and the Azure Sphere software development kit ([SDK](https://azure.microsoft.com/en-us/services/azure-sphere/get-started/)).

The quickstarts guide you through:

- [Install the Azure Sphere SDK](https://docs.microsoft.com/en-us/azure-sphere/install/install) 
- [Set up an account](https://docs.microsoft.com/en-us/azure-sphere/install/azure-directory-account)
- [Claiming your device](https://docs.microsoft.com/en-us/azure-sphere/install/claim-device)
- [Configuring Wi-Fi](https://docs.microsoft.com/en-us/azure-sphere/install/configure-wifi)
- [Build an application](https://docs.microsoft.com/en-us/azure-sphere/quickstarts/qs-blink-application)
- [Deploy an application over the air](https://docs.microsoft.com/en-us/azure-sphere/quickstarts/qs-first-deployment)

!!!Warning 
​    If we see error during claiming your device, please follow the soltuion to update azure sphere on board SDK.   

```c
C:\Users\Seeed05\Documents>azsphere device claim
error: The Azure Sphere OS on the attached device requires an update to be used with this version of the SDK.
Diagnostic info: [1.2.0, 3]
error: Failed to retrieve device ID from attached device: 'The Azure Sphere OS on the attached device requires an update to be used with this version of the SDK.
Diagnostic info: [1.2.0, 3]'.
error: Command failed in 00:00:00.9187758.
```

- Step 1.	In order to access the latest version of the device image you need to be enrolled on [MS Collaborate](http://aka.ms/collaborate). When you download the latest version from there (TP4.2.1) you will have access to a "ReleaseNotesTP4.2.1.pdf" file where the steps to recover the device with the new image are explained.
- Step 2. Open an Azure Sphere Developer Command Prompt; 
- Step 3. In the Azure Sphere Developer Command Prompt, change directory to the root of the unzipped folder; 
- Step 4. Ensure that your board is connected to your computer by USB; 
- Step 5. Issue the following command:

```
azsphere device recover --images <recovery-image-folder>
For example:
azsphere device recover –images images
```

## MT3620 Grove Shield

現状、[Azure Sphere SDK](http://aka.ms/AzureSphereSDK)はMT3620のADCやI2Cをサポートしていません。このシールドは、MT3620のUARTと、I2C温度センサなど外部のI2Cデバイスとのブリッジの役割をします。このシールドの基本的な機能は、外部のI2Cデバイスとの接続を可能にすることです。また、ADCも搭載していますので、アナログポートからアナログ値の読み取りも可能です。

[MT3620 Grove Shield](https://www.seeedstudio.com/MT3620-Grove-Shield-p-3145.html)には、AD7992(Anlog to I2C)とSC18IM700(I2C to UART)の2つのチップが搭載されています。アナログ信号はAD7992で読まれ、そしてSC18IM700を経由して開発ボードのUARTに接続されます。I2Cセンサは、同様にSC18IM700を通じて開発ボードのUARTに接続されます。

[AD7992](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/AD7992.pdf)は12ビットの低消費電力な I2Cコンパチブルのシリアル・インターフェースを備えたA/Dコンバーターです。A0とA1ピンの信号をI2Cデータに変換します。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/ADC_2_I2C.png)

[SC18IM700](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/datasheet/SC18IM700.pdf)は、マイコンの標準的なUARTポートとI2Cバスをインターフェースするために設計されました。SDA/SCL信号をGPIO26_TXD0とGPIO28_RXD0との通信に変換します。

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/I2C_2_UART.png)

![](https://github.com/SeeedDocument/Azure_Sphere_MT3620_Development_Kit/raw/master/img/MT3620_Grove_Shield-2018-09-11.png)

<div style="text-align:center">MT3620 Grove Shield Hardware Overview</div>

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