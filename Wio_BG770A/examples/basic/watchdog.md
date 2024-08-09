# basic/watchdog

ウォッチドッグタイマでプログラムが暴走したり停止したときにCPUを再起動させる操作を示すスケッチです。

## 概要

USERボタンを定期的にクリックしているとプログラムは動き続けますが、クリックせず10秒経過するとCPUが再起動します。
ウォッチドックタイマがCPUをリセット、再起動させます。

## 詳細

ウォッチドッグタイマの操作にAdafruit SleepyDog Libraryを使用します。

Adafruit_SleepyDog.hをインクルードするとWatchdogインスタンスが使えるようになります。

```cpp
#include <Adafruit_SleepyDog.h>
```

ウォッチドッグタイマのタイムアウト時間を`Watchdog.enable()`で設定します。

```cpp
Watchdog.enable(10000);
```

以降、指定した時間以内に定期的に`Watchdog.reset()`を呼んでください。呼ばないとウォッチドッグタイマがCPUをリセット、再起動させます。

```cpp
Watchdog.reset();
```
