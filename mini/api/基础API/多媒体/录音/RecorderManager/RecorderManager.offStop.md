
# 简介
取消监听录音结束事件。

## 使用限制

- **基础库** [1.11.0](https://opendocs.alipay.com/mini/framework/lib) 开始支持，低版本需要做 [兼容处理](https://docs.alipay.com/mini/framework/compatibility)。
- 使用此 API 前，请先在开放平台控制台 **创建小程序**、**添加能力**，可查看 [接入准备](https://opendocs.alipay.com/mini/02pj5u)。
- 此 API 暂仅支持企业支付宝小程序使用。

# 接口调用

## 示例代码

### .js 示例代码
```javascript
let recorderManager = my.getRecorderManager();
recorderManager.start();
const recorderStopCallback = res => {
 console.log('结束录音');
  console.log(res.tempFilePath);
};
recorderManager.onStop(recorderStopCallback);
setTimeput(() => {
 recorderManager.offStop(recorderStopCallback);
}, 5000);
```

## 入参

### function callback
录音结束事件的回调函数。
