---
layout: post
title:  "electron实现定时录制屏幕问题记录"
---

# 定时录制屏幕
## electron版本31.3.1
## 问题
### 1、录制声音时候只录制到麦克风的声音
- [x] 音频通过loopback可以录制系统音频
```
session.defaultSession.setDisplayMediaRequestHandler((request, callback) => {
    desktopCapturer.getSources({ types: ['screen'] }).then((sources) => {
      callback({ video: sources[0], audio: 'loopback' })
    })
  })
```
### 2、录制视频时候会录制到整个屏幕
- [ ] 可以选择录制区域
- [ ] 可以选择录制窗体
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> are supported
- [x] list syntax is required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
