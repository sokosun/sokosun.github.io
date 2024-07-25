---
title: "Android用ケーブルレリーズ"
date: 2024-07-25T22:02:15+09:00
---

# 概要

Android のカメラを遠隔操作するために ATOMS3 を使用して USB 接続のケーブルレリーズを作った話

# はじめに

最近の自撮り棒は Bluetooth 接続して接続するものばかりで有線(USB)接続タイプが見当たらないので自作してみました。

Bluetooth は接続先を切り替える際に、先につながっている機器を操作して切断し、次につなぎたい機器を操作して接続する必要があるので、複数の機器で共有しているとつながっている機器がどれか分からなくなってイライラするんですよね。有線なら一目瞭然なのに。

# 完成写真

![](../../media/cable_release_0.jpg)

# 実装

Android のカメラのシャッターはキーボードの Volume UP キーに割り当てられているので ATOMS3 に USB キーボード(っぽい)プログラムを書き込んでシャッターとしました。なお、ATOMS3(ESP32) を Bluetooth キーボードとして動かすには [BleKeyboard.h](https://github.com/T-vK/ESP32-BLE-Keyboard)、USB キーボードとして動かすには [USBHIDKeyboard.h](https://github.com/espressif/arduino-esp32/tree/master/libraries/USB/src) をインクルードするのが一般的なのですが、(前者ではできるにもかかわらず)後者では Volume UP キーが操作できません。Volume UP キーなどマルチメディアキーを操作する場合は [USBHIDConsumerControl.h](https://github.com/espressif/arduino-esp32/tree/master/libraries/USB/src) をインクルードする必要があります。

# ソースコード

[https://github.com/sokosun/atoms3_cable_release_for_Android](https://github.com/sokosun/atoms3_cable_release_for_Android)

