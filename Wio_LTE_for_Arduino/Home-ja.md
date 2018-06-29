# Wio LTE for Arduino

Wio LTE��Arduino IDE�p���C�u�����ł��B

## Wio LTE

![1](img/1.png)

Wio LTE�́ASeeed���J�����Ă���}�C�R�����W���[���ł��B

Grove�R�l�N�^�[��STM32F4�}�C�R���ALTE���W���[�����ڂ��Ă���AArduino IDE�őf�����v���g�^�C�s���O���邱�Ƃ��ł��܂��B

## �@�\

|�J�e�S���[|�@�\|�X�P�b�`��|���L|
|:--|:--|:--|:--|
|�d������|LTE���W���[���d��|||
||Grove�R�l�N�^�[�d��|||
|�\��|�t���J���[LED�\��|basic/LedSetRGB||
|LTE|��M���x|basic/GetRSSI||
||NTP��������|basic/GetTime||
||SMS���M|sms/SendSMS|���{�ꖢ�Ή�|
||SMS��M|sms/ReceiveSMS|���{�ꖢ�Ή�|
||UDP/TCP�N���C�A���g���M|||
||UDP/TCP�N���C�A���g��M|||
||HTTP�N���C�A���gGET||ContentType�Œ�[^1]|
||HTTP�N���C�A���gPOST|http/ifttt-webhook|ContentType�Œ�[^1]|

[^1]: application/x-www-form-urlencoded

## �J�����̃Z�b�g�A�b�v

�J�����̃Z�b�g�A�b�v��[������](Setup-ja)�B

## �n�[�h�E�F�A

�n�[�h�E�F�A�̏���[������](Hardware-ja)�B

## ���t�@�����X�}�j���A��

���t�@�����X�}�j���A����[������](Reference-ja)�B


## �T���v���v���O����

�T���v���v���O������Wio LTE���C�u�����ɓ������Ă��܂��BArdino IDE�́A�t�@�C�� > �X�P�b�`�� > WioLTEforArduino �z����I�����ĊJ���܂��B

|�X�P�b�`��|���e|�K�v�Ȃ���|�ڑ��R�l�N�^�[|
|:--|:--|:--|:--|
|basic/LedSetRGB|LED�����C���{�[�\�����܂��B|||
|basic/GetRSSI|��M�M�����x���V���A�����j�^�ɕ\�����܂��B|||
|basic/GetTime|NTP�T�[�o�[�Ɠ����������āA�������V���A�����j�^�ɕ\�����܂��B|SIM||
|basic/SDReadWrite|TF�J�[�h�ɏ�������/�ǂݍ��݂��܂��B|TF�J�[�h||
|grove/grove-button|Grove - �{�^����ON/OFF���V���A�����j�^�ɕ\�����܂��B|[Grove - �{�^��](https://www.seeedstudio.com/Grove-Button-p-766.html)|D38|
|grove/grove-button-using-int|Grove - �{�^����ON/OFF���V���A�����j�^��LED�ɕ\�����܂��B|[Grove - �{�^��](https://www.seeedstudio.com/Grove-Button-p-766.html)|D38|
|grove/grove-buzzer|Grove - �u�U�[��炵�܂��B|[Grove - �u�U�[](https://www.seeedstudio.com/Grove-Buzzer-p-768.html)|D38|
|grove/grove-magnetic-switch|Grove - ���΃X�C�b�`��ON/OFF���V���A�����j�^�ɕ\�����܂��B|[Grove - ���΃X�C�b�`](https://www.seeedstudio.com/Grove-Magnetic-Switch-p-744.html)|D38|
|grove/grove-rotary-angle-sensor|Grove - �ϒ�R�̉�]�ʂ��V���A�����j�^�ɕ\�����܂��B|[Grove - �ϒ�R](https://www.seeedstudio.com/Grove-Rotary-Angle-Sensor-p-770.html)|A4|
|grove/grove-temperature-and-humidity-sensor|Grove - �����x�Z���T�[�̉��x�A���x���V���A�����j�^�ɕ\�����܂��B|[Grove - �����x�Z���T�[](https://www.seeedstudio.com/Grove-Temperature-%26-Humidity-Sensor-p-745.html)|D38|
|grove/grove-ultrasonic-ranger|Grove - �����g�����Z���T�[�̋������V���A�����j�^�ɕ\�����܂��B|[Grove - �����g�����Z���T�[](https://www.seeedstudio.com/Grove-Ultrasonic-Ranger-p-960.html)|D38|
|grove/grove-gps|Grove - GPS�̈ʒu�����V���A�����j�^�ɕ\�����܂��B|[Grove - GPS](https://www.seeedstudio.com/Grove-GPS-p-959.html)|UART|
|grove/grove-accelerometer|Grove - �����x�Z���T�[�̒l���V���A�����j�^�ɕ\�����܂��B|[Grove - 3���f�W�^�������x�Z���T�[(�}16g)](https://www.seeedstudio.com/Grove-3-Axis-Digital-Accelerometer%28%C2%B116g%29-p-1156.html)|I2C|
|sms/SendSMS|�w��̓d�b�ԍ���SMS�𑗐M���܂��B|SIM||
|sms/ReceiveSMS|��M����SMS���V���A�����j�^�ɕ\�����܂��B|SIM||
|soracom/soracom-funnel|Wio LTE�̉ғ����Ԃ�SORACOM Funnel�֑��M���܂��B|[SORACOM Air SIM](https://soracom.jp/services/air/cellular/), [SORACOM Funnel](https://soracom.jp/services/funnel/)||
|soracom/soracom-harvest|Wio LTE�̉ғ����Ԃ�SORACOM Harvest�֑��M���܂��B|[SORACOM Air SIM](https://soracom.jp/services/air/cellular/), [SORACOM Harvest](https://soracom.jp/services/harvest/)||
|http/ifttt-webhook|Wio LTE�̉ғ����Ԃ�IFTTT��Webhook�֑��M���܂��B|SIM, [IFTTT Webhook](https://ifttt.com/maker_webhooks)||
|mqtt/mqtt-client|Wio LTE�̉ғ����Ԃ�MQTT�u���[�J�[�֑��M���܂��B|SIM, MQTT Broker||
