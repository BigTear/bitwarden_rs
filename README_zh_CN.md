## Bitwarden API的Rust实现
### 这是一个用Rust写成的Bitwarden服务端，兼容所有 [Bitwarden客户端](https://bitwarden.com/#download)*，适合自行搭建、低资源消耗的服务器。
---

[![Travis Build Status](https://travis-ci.org/dani-garcia/bitwarden_rs.svg?branch=master)](https://travis-ci.org/dani-garcia/bitwarden_rs)
[![Docker Pulls](https://img.shields.io/docker/pulls/bitwardenrs/server.svg)](https://hub.docker.com/r/bitwardenrs/server)
[![Dependency Status](https://deps.rs/repo/github/dani-garcia/bitwarden_rs/status.svg)](https://deps.rs/repo/github/dani-garcia/bitwarden_rs)
[![GitHub Release](https://img.shields.io/github/release/dani-garcia/bitwarden_rs.svg)](https://github.com/dani-garcia/bitwarden_rs/releases/latest)
[![GPL-3.0 Licensed](https://img.shields.io/github/license/dani-garcia/bitwarden_rs.svg)](https://github.com/dani-garcia/bitwarden_rs/blob/master/LICENSE.txt)
[![Matrix Chat](https://img.shields.io/matrix/bitwarden_rs:matrix.org.svg?logo=matrix)](https://matrix.to/#/#bitwarden_rs:matrix.org)

镜像均基于[Bitwarden API的Rust实现](https://github.com/dani-garcia/bitwarden_rs).

**此项目与[Bitwarden](https://bitwarden.com/)项目或8bit Solutions LLC没有关联。**

#### ⚠️**重要提醒**⚠️：使用此服务器时，任何与Bitwarden相关的错误报告或建议在[此处](https://github.com/BigTear/bitwarden_rs/issues/new)报告，无论使用什么客户端 您正在使用（移动端，电脑端，浏览器...）。 请勿使用官方Github支持渠道。
---

## 功能

基本上提供了Bitwarden API的完整实现，包括：

* 基本的单用户功能
* 组织
* 附件
* Vault API 支持
* 静态 Vault界面
* 网站图标API
* 身份验证器和U2F支持
* YubiKey OTP支持

## 安装
拉取docker映像并挂载数据文件到本地目录实现持久储存：

```sh
docker pull bitwardenrs/server:latest
docker run -d --name bitwarden -v /bw-data/:/data/ -p 80:80 bitwardenrs/server:latest
```
这个操作会覆盖 */bw-data/* 目录下所有文件，你可以设置成其他目录。

**重要提醒**: 有些浏览器（比如Chrome）或者移动端，禁止在非HTTPS网站中使用Web Crypto API。 在这种情况下，您可能会收到类似“Cannot read property 'importKey'”的错误。 要解决此问题，您需要给网站部署SSL证书实现HTTPS访问。

你可以使用 [bitwarden_rs directly](https://github.com/dani-garcia/bitwarden_rs/wiki/Enabling-HTTPS) 配置，或者使用第三方反向代理 ([例子](https://github.com/dani-garcia/bitwarden_rs/wiki/Proxy-examples))。


如果你使用的是域名访问，你可以在 [Let's Encrypt](https://letsencrypt.org/)申请免费SSL证书，或者你也可以用软件生成自签证书，比如使用[mkcert](https://github.com/FiloSottile/mkcert)。 有些代理会自动执行这一步，比如 ([Caddy](https://github.com/BigTear/bitwarden_rs/wiki/Proxy-examples))。

## 用法
查看 [bitwarden_rs wiki](https://github.com/BigTear/bitwarden_rs/wiki) 了解如何配置和使用bitwarden_rs。

## 联系我

有问题，或者BUG，[提 Issue](https://github.com/BigTear/bitwarden_rs/issues/new)。

### 感谢
感谢你们对项目做出的贡献!

- [@Skaronator](https://github.com/Skaronator)
- [@ChonoN](https://github.com/ChonoN)
