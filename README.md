腾讯云serverless 部署remix
remix + express

预览地址：[https://hello.jiahuiblog.com](https://hello.jiahuiblog.com)

(腾讯云，永远滴神～)
## 第一次配置

1. 配置好你的.env环境文件

    在根目录下新建一个.env，配置好secretkey和id，按照官网教程配置好权限

    https://cn.serverless.com/framework/docs-guides-tencent-account

2. 存储桶配置
   1. 手动在网页添加cos存储桶
   2. 复制下存储桶访问地址，粘贴在remix.config.js的`publicPath`那里，注意后面有个`/build`
   3. 把存储桶名字粘贴到`serverless.yml`的`assets`字段下的`bucket`那里

3. 自定义域名配置

    如果你不做自定义域名解析的话可以将`serverless.yml`的`apigw`字段及下方的所有代码注释掉

4. `sls deploy`

## 配置以后

`sls deploy`

非常方便～













