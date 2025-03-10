
# 简介
**FileSystemManager.getSavedFileList** 获取该小程序下已保存的本地缓存文件列表。

## 使用限制

- 基础库 [1.3.0](https://opendocs.alipay.com/mini/framework/lib) 开始支持，低版本需做 [兼容处理](https://opendocs.alipay.com/mini/framework/compatibility)。
- 此 API 支持个人支付宝小程序、企业支付宝小程序使用。
- 使用此 API 前，请先在开放平台控制台 **创建小程序**、**添加能力**，参见 [接入准备](https://opendocs.alipay.com/mini/02pk4y) 。

# 接口调用

## 示例代码

### .js 示例代码
```javascript
let fs = my.getFileSystemManager();
fs.getSavedFileList({
  success: (res) => {
		console.log("从fileList文件数组中取值", res.fileList);
  }
});
```

## 入参
| **属性** | **类型** | **必填** | **描述** |
| --- | --- | --- | --- |
| success | Function | 否 | 调用成功的回调函数。 |
| fail | Function | 否 | 调用失败的回调函数。 |
| complete | Function | 否 | 调用结束的回调函数（调用成功、失败都会执行）。 |


### success 返回值
| **属性** | **类型** | **说明** |
| --- | --- | --- |
| fileList | `Array<Object>` | 文件数组。 |


### fileList 结构
| **属性** | **类型** | **说明** |
| --- | --- | --- |
| filePath | String | 本地路径。 |
| size | Number | 本地文件大小，以字节为单位。 |
| createTime | Number | 文件保存时的时间戳，从 1970/01/01 08:00:00 到当前时间的秒数。 |
