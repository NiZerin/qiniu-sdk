# qiniu-sdk
☘️七牛云实时音频云 sdk-php
## 安装

* 通过composer，这是推荐的方式，可以使用composer.json 声明依赖，或者运行下面的命令。SDK 包已经放到这里 [`qiniu/php-sdk`][install-packagist] 。
```bash
$ composer require nizerin/qiniu-sdk:dev-master
```
* 直接下载安装，SDK 没有依赖其他第三方库，但需要参照 composer的autoloader，增加一个自己的autoloader程序。

## 运行环境

| Qiniu SDK版本 | PHP 版本 |
|:--------------------:|:---------------------------:|
|          7.x         |  cURL extension,   5.3 - 5.6,7.0 |
|          6.x         |  cURL extension,   5.2 - 5.6 |

## 使用方法

### 上传
```php
use Qiniu\Storage\UploadManager;
use Qiniu\Auth;
...
    $upManager = new UploadManager();
    $auth = new Auth($accessKey, $secretKey);
    $token = $auth->uploadToken($bucketName);
    list($ret, $error) = $upManager->put($token, 'formput', 'hello world');
...
```

## 测试

``` bash
$ ./vendor/bin/phpunit tests/Qiniu/Tests/
```

## 常见问题

- $error保留了请求响应的信息，失败情况下ret 为none, 将$error可以打印出来，提交给我们。
- API 的使用 demo 可以参考 [单元测试](https://github.com/nizerin/php-sdk/blob/master/tests)。

## 代码贡献



## 贡献记录

- [所有贡献者](https://github.com/nizerin/php-sdk/contributors)

## 联系我们



## 代码许可

The MIT License (MIT).详情见 [License文件](https://github.com/nizerin/php-sdk/blob/master/LICENSE).

[packagist]: http://packagist.org
[install-packagist]: https://packagist.org/packages/nizerin/php-sdk
