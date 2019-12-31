---
title: RecorderManager
header: develop
nav: api
sidebar: recorder_RecorderManager
---




**解释**：swan.getRecorderManager 的返回值。

**百度APP中扫码体验：**

<img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/fragment_RecorderManager.png"  class="demo-qrcode-image" />

**图片示例**

<div class="m-doc-custom-examples">
    <div class="m-doc-custom-examples-correct">
        <img src="https://b.bdstatic.com/miniapp/images/RecorderManager.gif">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>     
</div>

**代码示例**

<a href="swanide://fragment/70d4f42e90d9ad149e2dc0226bd82d2c1573410962037" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

**在 js 文件中**

```javascript
Page({
    onShow() {
        const recorderManager = swan.getRecorderManager()
        console.log(recorderManager)
        recorderManager.onStart(function() {
            // 开始录音事件
            console.log('recorder start')
        });
        recorderManager.onPause(function() {
            // 暂停录音事件
            console.log('recorder pause')
        });
        recorderManager.onStop(function(res) {
            // 停止录音事件
            console.log('recorder stop', res)
            const { tempFilePath } = res
        });
        recorderManager.onResume(function() {
            // 继续录音事件
            console.log('recorder resume')
        });
        recorderManager.onInterruptionBegin(function() {
            // 终端录音开始事件
            console.log('recorder interruptionBegin')
        });
        recorderManager.onInterruptionEnd(function() {
            // 终端录音结束事件
            console.log('recorder interruptionEnd')
        });

        const options = {
            duration: 10000,
            sampleRate: 44100,
            numberOfChannels: 1,
            encodeBitRate: 96000,
            format: 'aac'
        };

        recorderManager.start(options);
        // recorderManager.stop();
        // recorderManager.resume();
        // recorderManager.pause();
        this.recorderManager = recorderManager;
    }
});
```
#### 错误码

* Andriod

|错误码|说明|
|--|--|
|201|解析失败，请检查参数是否正确|
|1001|执行失败|
|2001|错误调起时机|
|2002|录音执行错误|
|2003|录音调起action错误，无需调用release|
|2004|用户拒绝|

* iOS

|错误码|说明|
|--|--|
|202|解析失败，请检查参数是否正确  |
|2001|错误的调起时机|
|2002|录音执行错误|
|2004|用户拒绝小程序使用麦克风|
