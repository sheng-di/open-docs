
# 简介
[FileSystemManager.appendFile](https://opendocs.alipay.com/mini/api/0228qi) 的同步版本。

## 使用限制

- 基础库 [2.7.4](https://opendocs.alipay.com/mini/framework/lib-upgrade-v2) 开始支持，低版本需要做 [兼容处理](https://docs.alipay.com/mini/framework/compatibility)。
- 此 API 支持个人支付宝小程序、企业支付宝小程序使用。
- 使用此 API 前，请先在开放平台控制台 **创建小程序**、**添加能力**，参见 [接入准备](https://opendocs.alipay.com/mini/02pk4y) 。
- 此 API 暂不支持在 IDE 模拟器上测试，开发中请使用 [真机调试](https://opendocs.alipay.com/mini/ide/remote-debug) 进行测试。

# 接口调用

## 示例代码

### .js 示例代码
```javascript
const fs = my.getFileSystemManager();
let result = fs.appendFileSync(
  `${my.env.USER_DATA_PATH}/test.txt`,
  '{"123":456, ["abc":789, "efg":"333"]}',
  'utf8'
);
console.log(result);
```

## 入参

#### string filePath
文件地址

#### string/ArrayBuffer data
数据

#### string encoding
编码

### encoding 合法值
| **值** | **说明** |
| --- | --- |
| ascii | - |
| base64 | - |
| hex | - |
| binary | - |
| ucs2/ucs-2/utf16le/utf-16le | - |
| utf-8/utf8 | - |
| latin1 | - |


## 错误码
| **错误码** | **说明** |
| --- | --- |
| 10022 | 指定文件不存在。 |
| 10024 | 指定的路径没有写的权限。 |
| 10025 | 指定路径是一个已经存在的目录。 |

