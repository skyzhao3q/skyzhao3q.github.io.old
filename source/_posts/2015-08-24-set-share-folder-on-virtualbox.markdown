---
layout: post
title: "【Virtual Box】共有フォルダ作成"
date: 2015-08-24 11:18:15 +0900
comments: true
categories: VirtualBox
---
## 【環境】

* ホスト側OS: WIN7(64bit)
* ゲスト側OS: Ubuntu(vboxadditionインストール済)
* 仮想ソフト: VirtualBox　

## 1. ホストにて

共有フォルダを用意する。
たとえば、ディスクストップに`Ubuntu`というフォルダを作成しておく。

## 2. VirtualBoxにて

設定　→　共有フォルダ　→　`+`(フォルダ追加)
* 自動マウント　→　☑
* 永続化する　→　☑

## 3. ゲストにて

```bash
# 新規共有フォルダ
$ sudo mkdir /mnt/Ubuntu
$ sudo chmod 777 /mnt/Ubuntu
# 確認
$ ls -ld /mnt/Ubuntu
# 共有フォルダのひも付け
$ sudo mount -t vboxsf Ubuntu /mnt/Ubuntu
```