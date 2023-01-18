## fly上部署trojan
> 官网    https://fly.io/ 部署项目需要信用卡验证，验证过后就是hobby plan，hobby计划也可以享受3个免费共享cpu、256MB RAM的app，3GB持久化卷（磁盘），160G出口流量，详情参考[Pricing](https://fly.io/docs/about/pricing/)
### 操作
1.  在平台注册号账号并过信用卡验证。安装flyctl命令行工具，详情参看[flyctl安装](https://fly.io/docs/hands-on/install-flyctl/)。git clone本项目到本地磁盘，在该文件夹中打开命令行，输入`flyctl auth login`并回车，在弹出的网页中进行身份验证。
2. 在该文件的命令行中输入`flyctl launch`并回车，依次键入app名称、选择部署地区，等待约3分钟，待最后出现`v2 deployed successfully`，则表示部署成功。
3. 若修改了代码，则只需`flyctl deploy`即可更新云容器的代码。
4. config.json默认配置trojan协议，可自行更改，
ws路径：/api，密码：123

### 说明
该平台可选择在美国、德国、荷兰、新加坡、日本、香港等地区部署，可是分配的域名解析出来的ip地址是在美国德州。我选择的是在香港部署，怀疑是请求先到美国德州，然后平台再反向代理到香港，绕了一大圈，延迟感人。套cloudflare CDN 优选IP还没测试，具体速度不知。

