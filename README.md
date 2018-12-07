### andyliwr-vscode-image-upload
克隆项目至[vscode-qiniu-upload-image](https://github.com/favers/vscode-qiniu-upload-image)

主要更新如下：
1. 修复使用https上传时出现的七牛回调411的错误，见[issue](https://github.com/favers/vscode-qiniu-upload-image/issues/13)
2. 新增选项saveImageToLocal来让用户选择是否将粘贴板的任务存储到项目本地

PS: 项目并非抄袭`vscode-qiniu-upload-image`，我已经提了[`pull-request`](https://github.com/favers/vscode-qiniu-upload-image/pull/14)给原作者，发布到网上只是为了方便自己下载和使用。

参数配置：
```js
{
    // 有效的七牛 AccessKey 签名授权
    "pasteImageToQiniu.access_key": "*****************************************",

    // 有效的七牛 SecretKey 签名授权
    "pasteImageToQiniu.secret_key": "*****************************************",

    // 七牛图片上传空间
    "pasteImageToQiniu.bucket": "blog",

    // 七牛图片上传路径，参数化命名，暂时支持 ${fileName}、${mdFileName}、${date}、${dateTime}
    // 示例：
    //   ${fileName}-${date} -> picName-20160725.jpg
    //   ${mdFileName}-${dateTime} -> markdownName-20170412222810.jpg
    "pasteImageToQiniu.remotePath": "${fileName}",

    // 七牛图床域名
    "pasteImageToQiniu.domain": "http://xxxxx.xxxx.com",

    // http或者https
    "pasteImageToQiniu.schema": "http",

    // 存储区域对应 HTTPS 地址，参考七牛官方文档：https://support.qiniu.com/hc/kb/article/210702。当schema为https时需要定义此选项
    "pasteImageToQiniu.upHttpsHost": "",

    // 是否存储粘贴板图片到本地，值为true的时候请不要定义localPath
    "pasteImageToQiniu.saveImageToLocal": true,

    // 本地储存位置
    "pasteImageToQiniu.localPath":""
}
