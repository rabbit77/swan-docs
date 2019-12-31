---
title: swan.getExtConfig
header: develop
nav: api
sidebar: swan-getExtConfig
---


>基础库 1.10.8 版本开始支持，需要上传小程序包之后，才能通过API获取自定义数据，小程序包上传流程、数据配置参考：[小程序包管理](https://smartprogram.baidu.com/docs/third/apppage/)。


**解释**：获取第三方平台自定义的数据字段。

**百度APP中扫码体验：**

<img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/pages_getExtConfig.png"  class="demo-qrcode-image" />

**方法参数**：Object object

**`object`参数说明**：

|属性名 |类型  |必填 | 默认值 |说明|
|---- | ---- | ---- | ----|----|
|success| Function |   否 | | 返回第三方平台自定义的数据|
|fail  |  Function |   否  | |接口调用失败的回调函数|
|complete   | Function   | 否 | |  接口调用结束的回调函数（调用成功、失败都会执行）|

**success返回参数说明**：

|参数 | 类型 | 说明|
|---- | ---- | ---- |
|extConfig |  Object | 第三方平台自定义的数据 |

**图片示例**

<div class="m-doc-custom-examples">
    <div class="m-doc-custom-examples-correct">
        <img src="https://b.bdstatic.com/miniapp/images/getExtConfig1.gif">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>     
</div>

**代码示例**

<a href="swanide://fragment/8193f2d5f3f69834261c1809c72c36071574154522656" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

* 在 js 文件中

```js
Page({
    getExtConfig() {
        swan.getExtConfig({
            success: res => {
                console.log('自定义的数据', res.extConfig);
                swan.showToast({
                    title: JSON.stringify(res),
                    icon: 'none'
                })
            },
            fail: err => {
                console.log('scanCode fail', err);
            }
        });
    }
});
```



**Tip**

* swan.getExtConfig 暂时无法通过 sawn.canIUse 判断是否兼容，开发者需要自行判断swan.getExtConfig 是否存在兼容。
* 需要小程序授权第三方平台，并且添加自定义字段值（例：{"extEnable":true,"ext":{"appid":"xxx"}}），swan.getExtConfig()方法请求的时候返回的 extConfig 值才不为｛｝

