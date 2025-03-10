
# 简介
**my.onLocatedComplete** 是监听地理位置定位完成事件的 API，只针对 [my.chooseCity](https://opendocs.alipay.com/mini/api/ui-city) 中属性 setLocatedCity 为 true 的情况。

## 使用限制

- IDE 模拟器暂不支持调试，请以真机调试结果为准。
- 此 API 暂仅支持企业支付宝小程序使用。

## 扫码体验
![|127x157](https://mdn.alipayobjects.com/afts/img/A*uGCmRImDNksq0wpOl9aflwBkAa8wAA/original?bz=openpt_doc&t=2sNXA_LmBkuW7-CwiT-HUAAAAABkMK8AAAAA#align=left&display=inline&height=157&margin=%5Bobject%20Object%5D&originHeight=157&originWidth=127&status=done&style=none&width=127)

# 接口调用

## Herbox
[小程序在线](https://herbox-embed.alipay.com/s/doc-choose-city?theme=light&previewZoom=75&chInfo=openhome-doc) 

## 示例代码

### .axml 示例代码
```html
<!-- API-DEMO page/API/choose-city/choose-city.axml-->
<view class="page">
  <view class="page-description">选择城市 API</view>
  <view class="page-section">
    <view class="page-section-title">my.chooseCity</view>
    <view class="page-section-demo">
      <button type="primary" onTap="chooseCity">选择城市</button>
    </view>
  </view>
  <view class="page-description">修改当前定位城市的名称 API</view>
  <view class="page-section">
    <view class="page-section-title">my.setLocatedCity</view>
    <view class="page-section-demo">
      <button type="primary" onTap="setLocatedCity">修改当前定位城市的名称</button>
    </view>
  </view>
</view>
```

### .js 示例代码
```javascript
// API-DEMO page/choose-city/choose-city.js
Page({
  chooseCity() {
    my.chooseCity({
      showLocatedCity: true,
      showHotCities: true,
      success: (res) => {
        my.alert({
          title: 'chooseCity response: ' + JSON.stringify(res),
        });
      },
    });
  },
  setLocatedCity() {
    my.onLocatedComplete(function(result){
        my.setLocatedCity({
          locatedCityId:result.locatedCityId,
          locatedCityName:'修改后的城市名', 
          success: (res) => {
            my.alert({ content: '修改当前定位城市成功' + JSON.stringify(res), });
          },
          fail: (error) => {
            my.alert({ content: '修改当前定位城市失败' + JSON.stringify(error), });
          },
        });
    });
    my.chooseCity({
      showLocatedCity: true,
      showHotCities: true,
      setLocatedCity: true,
      success: (res) => {
        my.alert({
          title: 'chooseCity response: ' + JSON.stringify(res),
        });
      },
    });
  },
});
```

## 入参
入参为回调函数：

| **属性** | **类型** | **描述** |
| --- | --- | --- |
| 回调函数 | Function | 小程序地理位置定位完成事件的回调函数。 |

## 回调参数
| **属性** | **类型** | **描述** |
| --- | --- | --- |
| longitude | Number | 当前定位城市经度。 |
| latitude | Number | 当前定位城市经度。 |
| locatedCityId | String | 当前定位城市 id，setLocatedCity 的时候带上。 |

### 回调参数示例代码
```javascript
{
    longitude:100.3,
    latitude:30.1,
    locatedCityId:""
}
```
