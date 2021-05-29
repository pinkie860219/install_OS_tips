- [中文輸入法相關](#中文輸入法相關)
  - [安裝 gcin](#安裝-gcin)
  - [gcin 可能在 konsole 無法使用](#gcin-可能在-konsole-無法使用)
- [Terminal color theme](#terminal-color-theme)
- [音源調整](#音源調整)


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
