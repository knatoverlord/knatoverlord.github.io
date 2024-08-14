---
layout: post
title:  "electron实现定时录制屏幕问题记录"
---

# 定时录制屏幕
## electron版本31.3.1
## 问题
### 1、录制声音时候没有录制到系统声音，只录制到麦克风的声音
#### 处理 音频通过loopback可以只录制系统音频
```
session.defaultSession.setDisplayMediaRequestHandler((request, callback) => {
    // desktopCapturer.getSources({ types: ['window'] }).then((sources) => {
    desktopCapturer.getSources({ types: ['screen'] }).then((sources) => {
      callback({ video: sources[0], audio: 'loopback' })
    })
  })
```
### 2、录制视频时候会录制到整个屏幕，只想录制播放视频的窗口
