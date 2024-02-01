---
title: "仮想マウスで EOS Utility を叩く"
date: 2024-01-24T15:18:38+09:00
---

# 概要

AtomS3 Lite を使用して作った仮想マウスデバイスで EOS Utility のシャッターボタンを自動クリックしてみた記録

# EOS Utility

EOS Utility という Canon 純正のソフトウェアを使用すると Canon のカメラと接続して遠隔操作（撮影）ができます。しかしこのソフトウェアは GUI しか提供されていないので一定時間毎に撮影したい場合は一定時間毎に GUI のシャッターボタンをクリックする必要があります。というわけで10秒毎にクリックイベントを発生させる仮想マウスデバイスを作って自動クリックさせてみました。

// Canon のカメラに搭載されているインターバル撮影機能はライブビュー機能と同時に使用することができませんが今回作った仮想マウスデバイスはライブビュー機能と同時に使用することが可能です

# 完成品

{{< video src="../media/virtual_mouse_0.mp4" >}}

あらかじめマウスカーソルをシャッターボタンに合わせた状態で、AtomS3 Lite のボタンを押して青色LED点灯＝10秒毎にクリックイベントを発生するモードにしています。これにより手動で10秒毎にシャッターボタンを押すのと同じ結果が得られます。

# ソースコード

[https://github.com/sokosun/atoms3_timer_clicker](https://github.com/sokosun/atoms3_timer_clicker)
