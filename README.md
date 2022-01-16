腾讯云serverless 部署remix
remix + express

### 第一次配置(比较麻烦)

总体来说不太好用，在根目录下新建一个.env，配置好secretkey和id，按照官网教程配置好权限

https://cn.serverless.com/framework/docs-guides-tencent-account

因为腾讯云没有nodejs14环境，所以我加了一个layer，含有nodejs14环境（不要问冷启动时间，问就是1000ms以上）

在server scf_bootstrap可以看到路径

需要在server/serverless.yml配置下layer(上传加改个名字加找对路径)

如果你不喜欢这个存储桶名字的话～，在public目录下修改serverless.yml的bucket

这些配置搞完之后在server的目录下执行`sls deploy`

上传之后会返回一个url，你可以直接访问，记得把/release去掉

注意，这个时候你是没有上传静态文件的，所以样式都会丢

这个时候需要你进入public目录下面执行一下`sls deploy`

然后你注意console返回的cosOrigin，即存储桶地址，如果是一个没创建的存储桶，第一次上传会报不存在，那你就去cos网页上看存储桶地址(他创建了但是报错然后不返回～)，把访问域名记下来，然后粘贴在根目录下面的remix.config.js的publicpath那里,注意看我的例子(后面有个/build)

然后呢你重新先在server目录下sls deploy，然后再public下面sls deploy，就可以看到部署好的项目了

### 第二次及以后

先在server目录下sls deploy，然后再public下面sls deploy，就可以看到部署好的项目了(blablablablabla.......)

建议直接coding这些集成工具走下来吧




