<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. 中文輸入法相關</a>
<ul>
<li><a href="#sec-1-1">1.1. apt install gcin之後</a></li>
<li><a href="#sec-1-2">1.2. gcin可能在終端機無法使用</a></li>
</ul>
</li>
<li><a href="#sec-2">2. 終端機color theme</a></li>
<li><a href="#sec-3">3. 音源調整</a></li>
</ul>
</div>
</div>



# 中文輸入法相關<a id="sec-1" name="sec-1"></a>

## apt install gcin之後<a id="sec-1-1" name="sec-1-1"></a>

用im-config設定輸入法

## gcin可能在終端機無法使用<a id="sec-1-2" name="sec-1-2"></a>

安裝 gcin qt module, X為終端機使用的qt版本

    apt install gcin_qtX_module

再到 ~/.bash.rc 中加上

    export QT5_IM_MODULE=gcin

# 終端機color theme<a id="sec-2" name="sec-2"></a>

Terminal Sexy 可以把轉換主題到特定終端機的格式
ex:把mac終端機主題輸出成konsole的

# 音源調整<a id="sec-3" name="sec-3"></a>

提高 pulseaudio 的解析

在 /etc/pulse/daemon.conf 中加入

    resample-method = src-sinc-medium-quality
    default-sample-format = s24le
    default-sample-rate = 96000