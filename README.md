# WPOSS - 阿里云对象存储插件

WordPress 阿里云对象存储插件，基于阿里云 OSS 实现静态资源与网站数据分离，提高网站加载速度。

[![WordPress](https://img.shields.io/badge/WordPress-5.5%2B-blue.svg)](https://wordpress.org/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-777BB4.svg)](https://www.php.net/)
[![License](https://img.shields.io/badge/License-GPLv2-green.svg)](http://www.gnu.org/licenses/gpl-2.0.html)

## 功能特点

- 一键将媒体文件、图片等静态资源同步至阿里云 OSS
- 支持自定义对象存储目录，一个存储桶可服务多站点
- 支持自动文件重命名，解决中文文件名或重复文件名问题
- 支持本地与 OSS 双备份，或仅 OSS 存储（勾选「不在本地保留备份」）
- 支持禁止缩略图裁剪，仅上传主图
- 支持 HTTPS 及自定义域名
- 兼容 WordPress 5.5+，PHP 7.4+（含 PHP 8.x）
- 2020 年重构代码，逻辑更清晰、轻便

## 环境要求

* WordPress 5.5 或更高版本
* PHP 7.4 或更高版本
* 阿里云 OSS 账号及 Bucket

## 安装

1. 将 `wposs` 文件夹上传至 `/wp-content/plugins/` 目录
2. 在后台「插件」列表中激活 WPOSS
3. 进入【设置】→【WPOSS 设置】，填写阿里云 OSS 相关配置

## 配置说明

| 配置项 | 说明 |
|--------|------|
| Bucket 名称 | 阿里云 OSS 控制台创建的 Bucket 名称 |
| EndPoint 地域节点 | 如 `oss-cn-shanghai.aliyuncs.com`，非阿里云服务器使用外网节点 |
| Bucket 域名 | 访问 URL 前缀，如 `https://xxx.oss-cn-shanghai.aliyuncs.com` |
| AccessKey ID / Secret | 阿里云 RAM 子账号的 API 密钥 |
| 自动重命名 | 上传时自动重命名为时间戳格式，避免中文或重复文件名 |
| 不在本地保留备份 | 勾选后，文件仅存于 OSS，本地不保留（请求结束时删除） |
| 禁止缩略图 | 仅上传主图，不生成及上传缩略图 |

## 常见问题

1. **插件报错时**：开启 `WP_DEBUG` 和 `WP_DEBUG_LOG`，在 `wp-content/debug.log` 中查看具体错误
2. **备份策略**：可选择 OSS 与本地同时备份，或仅 OSS 存储以节省本地空间
3. **域名**：支持 HTTPS 及自定义 CNAME 域名绑定

## 插件团队和技术支持

[老蒋](https://www.laojiang.me/)（老蒋和他的伙伴们），本着资源共享原则，在运营网站过程中用到的或者是有需要用到的主题、插件资源，有选择的免费分享给广大的网友站长，希望能够帮助到你建站过程中提高效率。

感谢团队成员，以及网友提出的优化工具的建议，才有后续产品的不断迭代适合且满足用户需要。不能确保100%的符合兼容网站，我们也仅能做到在工作之余不断的接近和满足你的需要。

| 类目            | 信息                                                         |
| --------------- | ------------------------------------------------------------ |
| 插件更新地址    | https://www.laojiang.me/5946.html                            |
| 团队成员        | [老蒋](https://www.laojiang.me/)、老赵、[CNJOEL](https://www.rakvps.com/)、木村 |
| 支持网站        | [乐在云](https://www.lezaiyun.com/)、主机评价网              |
| 建站资源推荐    | [便宜VPS推荐](https://www.zhujipingjia.com/pianyivps.html)、[美国VPS推荐](https://www.zhujipingjia.com/uscn2gia.html)、[外贸建站主机](https://www.zhujipingjia.com/wordpress-hosting.html)、[SSL证书推荐](https://www.zhujipingjia.com/two-ssls.html)、[WordPress主机推荐](https://www.zhujipingjia.com/wpblog-host.html) |
| 提交WP官网（F） | https://cn.wordpress.org/plugins/wposs/                      |

![](wechat.png)

## 更新日志

### 5.0

* 修复「不在本地保留备份」功能：勾选后于请求结束时删除本地文件，不再影响上传流程
* 修复 `legacy_data_replace` 的 SQL 注入风险
* 修复 PHP 8.x 兼容性（Exception 命名空间、restore_options、sanitize_file_name_handler 等）
* 修复 OSS 上传失败时的异常处理
* 增加表单安全校验（wp_nonce_field、esc_html 等）
* 精简设置页：移除图像处理、一键替换 OSS 地址等选项
* 移动端隐藏「关注公众号」侧栏

### 4.9

* 微调样式
* 解决媒体无法删除问题（用户手动替换最新 SDK）

### 4.8

* 兼容 WP 6.2 测试
* 解决 PHP 8.x 激活报错问题

### 4.7

* 兼容 WP 6.1 测试

### 4.6

* 兼容 WP 5.9.3 测试

### 4.5

* 兼容 WP 5.7 测试
* 兼容 PHP 8.0

> 更早版本更新记录详见 [readme.txt](readme.txt)

## 许可证

GPLv2 或更高版本 | [许可证正文](http://www.gnu.org/licenses/gpl-2.0.html)
