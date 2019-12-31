---
title: swan.clearStorageSync
header: develop
nav: api
sidebar: remove_swan-clearStorageSync
---

 
**解释**：同步清理本地数据缓存。

**百度APP中扫码体验：**

<img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/storage.png"  class="demo-qrcode-image" />

**方法参数**：无

**图片示例**

<div class="m-doc-custom-examples">
    <div class="m-doc-custom-examples-correct">
        <img src="https://b.bdstatic.com/miniapp/image/clearStorage.gif">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>     
</div>

**代码示例**
<a href="swanide://fragment/1b5a4a2ad3734791147f6d74c02fb4201573634322221" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

```js
Page({
    clearStorage() {
        try {
            swan.clearStorageSync();
        } catch(e) {

        }
    }
});
```

#### 错误码
* Andriod

|错误码|说明|
|--|--|
|1001|执行失败    |

* iOS

|错误码|说明|
|--|--|
|202|解析失败，请检查参数是否正确   |