- [中文輸入法相關](#中文輸入法相關)
  - [安裝 gcin](#安裝-gcin)
  - [gcin 可能在 konsole 無法使用](#gcin-可能在-konsole-無法使用)
- [Terminal color theme](#terminal-color-theme)
- [音源調整](#音源調整)
- [藍芽](#藍芽)
  - [快速連線](#快速連線)
  - [電腦睡眠喚醒重啟藍芽](#電腦睡眠喚醒重啟藍芽)


# 中文輸入法相關

## 安裝 gcin

`sudo apt install gcin`

`im-config` 設定輸入法

## gcin 可能在 konsole 無法使用

安裝 gcin qt module, X為終端機使用的qt版本

`apt install gcin_qtX_module`

再到 ~/.bash.rc 中加上

`export QT5_IM_MODULE=gcin`

# Terminal color theme

Terminal Sexy 可以把轉換主題到特定 terminal 的格式
ex:把 mac 終端機主題輸出成 konsole 的

# 音源調整

提高 pulseaudio 的解析

在 `/etc/pulse/daemon.conf` 中加入

```
resample-method = src-sinc-medium-quality
default-sample-format = s24le
default-sample-rate = 96000
```

# 藍芽

## 快速連線

當已配對過的裝置啟動時，讓電腦自動去連線

改 `/etc/bluetooth/main.conf`

```
FastConnectable = true
```

## 電腦睡眠喚醒重啟藍芽

藍芽可能在睡眠喚醒後明明已經斷線，卻看起來還保留睡眠前已連線的狀態，得手動重啟，很不方便，可以用這段 script 讓他自動重啟

`sudo nano /lib/systemd/system-sleep/bt`

```
#!/bin/sh

case $1 in
  post)
    service bluetooth restart
    ;;
esac
```

`sudo chmod +x /lib/systemd/system-sleep/bt`
