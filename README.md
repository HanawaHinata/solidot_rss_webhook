# solidot网站RSS订阅与钉钉webhook推送对接的PHP版本

### 说明
本项目用于定时爬取 solidot.org 的 RSS 订阅功能，并通过钉钉提供的 WebHook 机器人功能推送订阅消息。


### 快速部署
* 在你的服务器上部署网站运行环境。本代码使用 `mysqli` 扩展连接数据库，因此您的 PHP 环境需要支持此扩展；
* 拉取或下载本项目；
* 修改本项目 `rss_webhook.php` 文件，将其中的 `$webhook` 变量替换为你在钉钉中创建的机器人的 webhook url；
* 如果需要保存爬取数据到数据库，请修改 `common/database.php` ，将 `getConnect` 函数的 `mysqli_connect` 、 
`mysqli_select_db` 值修改为对应的数据库数据；
* 将本项目上传至网站空间；
* 登录服务器 SSH ，根据需要添加 `CornTab` 。例如我要半小时执行一次：
```shell script
*/30 * * * * curl -sS --connect-timeout 10 -m 3600 'https://xxx.com/rss_webhook.php'
```
或者使用其他定时器框架调用本文件亦可。

### License
本项目按照 Apache 2.0 协议自由分发。
