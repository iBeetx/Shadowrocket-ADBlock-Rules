## 最完善的 iOS 翻墙规则

这里是一系列好用的翻墙规则，针对 [Shadowrocket](https://liguangming.com/Shadowrocket) 开发，支持广告过滤，使用 Python 按照一定的规则和模板定期自动生成，并且使用开源的力量，集众人之力逐渐完善。

**正在使用手机浏览本页面的用户 [请点击这里](https://github.com/h2y/Shadowrocket-ADBlock-Rules/blob/master/readme.md)，查看完整的说明文档。**

**本规则具有以下特点：**

- 黑名单由最新版 GFWList 自动转换；白名单针对全球 top500 站点的连通情况定期自动生成。
- 自动转换最新版本的 `EasyList, Eaylist China, 乘风规则` 为 SR 规则，全面去除广告且去除重复。
- 也包括自定义的广告过滤规则，针对 iOS 端的网页广告、App 广告和视频广告。（[常见广告过滤效果统计](https://github.com/h2y/Shadowrocket-ADBlock-Rules/issues/40)）
- 提供多个规则文件让大家自由选择或者自由切换使用。
- 专门针对 ShadowRocket 开发，可以保证与 SR 的兼容性。

## 规则列表

![规则选择指南](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/guide.png?19115)

规则 | 规定代理的网站 | 规定直连的网站 
--- | ----------- | ------------- 
[黑名单规则 + 去广告](#黑名单过滤--广告) |  被墙的网站（GFWList） | 正常的网站 
[黑名单规则](#黑名单过滤) |   |  
[白名单规则 + 去广告](#白名单过滤--广告) | 其他网站 | top500 网站中可直连的网站、中国网站 
[白名单规则](#白名单过滤) |   |  
[国内外划分 + 去广告](#国内外划分--广告) |  国外网站 | 中国网站
[国内外划分](#国内外划分) |   |  
[全局直连 + 去广告](#直连去广告) | / | 全部
[全局代理 + 去广告](#代理去广告) |  全部 | /
[回国规则 + 去广告](#回国规则--广告) | 中国网站 | 国外网站 
[回国规则](#回国规则) |   |  

- 以上所有规则，局域网内请求均直连。
- 可以下载多个规则切换使用。

## 规则使用方法

在 ShadowRocket 应用中，进入 [配置] 页面，点击扫描二维码的按钮添加规则。再激活添加的规则文件即可。

最好让 ShadowRocket 断开并重新连接一次，以确保新的规则文件生效。 

## 常见问题

- **上千行的代理规则，会对上网速度产生影响吗？**

> 不会的。
>
> 我之前也认为这是一个每次网络数据包经过都会执行一次的规则文件，逐行匹配规则，所以需要尽可能精简。但后来和 SR 作者交流后发现这是一个误区，SR 在每次加载规则时都会生成一棵搜索树，可以理解为对主机名从后往前的有限状态机 DFA，并不是逐行匹配，并且对每次的匹配结果还有个哈希缓存。
>
> 换句话说，2000 行的规则和 50 行的规则在 SR 中均为同一量级的时间复杂度 O(1)。


- **你提供了这么多规则，如何选择适合我的？**

> 最常用的规则是黑名单和白名单。区别在于对待 `未知网站` 的不同处理方式，黑名单默认直连，而白名单则默认使用代理。如果你选择恐惧症爆发，那就两个都下载好了，黑白名单切换使用，天下无忧。

- **你提供了这么多规则，却没有我想要的 o(>.<)o**

> 有任何建议或疑问，[请联系我](#问题反馈)。

- **广告过滤不完全？**

> 该规则并不保证 100% 过滤所有的广告，尤其是视频广告，与网页广告不同的是，优酷等 App 每次升级都有可能更换一次广告策略，因此难以保证其广告屏蔽的实时有效性。


## 相关推荐

[**糖客翻墙提供商 :100: **](https://tangke.win/register?aff=1077)

我所选择的节点提供商。稳定、速度快、价格适中，还支持按流量计费。新用户可以免费试用 15 天。

请大家使用我的推广链接前去注册。


[**AppleDNS**](https://github.com/gongjianhui/AppleDNS)

Hosts 生成工具，生成 `在当前所在网络环境下` Apple 服务器的 DNS 最优解析结果，可以轻微加快访问速度。

电脑需安装 Python，按照 Readme 运行后，将生成的 hosts 粘贴到 `Shadowrocket->Settings->DNS->Hosts` 即可。

**<http://ip111.cn/>**

这是一个很棒的 IP 查询网站，支持同时查询你的境内境外 IP，以及谷歌 IP。

**<https://hzy.pw/>**

我是一名大学生，沉迷技术无法自拔。这是我的个人博客，欢迎来逛逛。

PS：广告位欢迎与我联系~


## 问题反馈

任何问题欢迎在 [Issues](https://github.com/h2y/Shadowrocket-ADBlock-Rules/issues) 中反馈，如果没有账号可以去 [我的网站](https://hzy.pw/p/2096#comments) 中留言。

你的反馈会让此规则变得更加完美。

**如何贡献代码？**

通常的情况下，对 [factory 目录](https://github.com/h2y/Shadowrocket-ADBlock-Rules/tree/master/factory) 下的 3 个 `manual_*.txt` 文件做对应修改即可。


## 捐助

本项目不接受任何形式的捐助，因为自由地上网本来就是大家的权利，没有必要为此付出更多的代价。

但是，作为一个翻墙规则，不可避免的会对网站有所遗漏，需要大家来共同完善，当发现不好用的地方时，请打开 SR 的日志功能，检查一下是哪一个被墙的域名走了直连，或者是哪一个可以直连的域名走了代理。

将需要修改的信息反馈给我，大家的努力会让这个规则越来越完善！


----------------------------------------

## 黑名单过滤 + 广告

黑名单中包含了境外网站中无法访问的那些，对不确定的网站则默认直连。

- 代理：被墙的网站（GFWList）
- 直连：正常的网站
- 包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_top500_banlist_ad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_top500_banlist_ad.png)

## 白名单过滤 + 广告

白名单中包含了境外网站中可以访问的那些，对不确定的网站则默认代理。

- 直连：top500 网站中可直连的境外网站、中国网站
- 代理：默认代理其余的所有境外网站
- 包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_top500_whitelist_ad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_top500_whitelist_ad.png)


## 黑名单过滤

现在很多浏览器都自带了广告过滤功能，而广告过滤的规则其实较为臃肿，如果你不需要全局地过滤 App 内置广告和视频广告，可以选择这个不带广告过滤的版本。

- 代理：被墙的网站（GFWList）
- 直连：正常的网站
- 不包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_top500_banlist.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_top500_banlist.png)


## 白名单过滤

现在很多浏览器都自带了广告过滤功能，而广告过滤的规则其实较为臃肿，如果你不需要全局地过滤 App 内置广告和视频广告，可以选择这个不带广告过滤的版本。

- 直连：top500 网站中可直连的境外网站、中国网站
- 代理：默认代理其余的所有境外网站
- 不包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_top500_whitelist.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_top500_whitelist.png)


## 国内外划分 + 广告

国内外划分，对中国网站直连，外国网站代理。包含广告过滤。国外网站总是走代理，对于某些港澳台网站，速度反而会比直连更快。

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_cnip_ad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_cnip_ad.png)


## 国内外划分

国内外划分，对中国网站直连，外国网站代理。不包含广告过滤。国外网站总是走代理，对于某些港澳台网站，速度反而会比直连更快。

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_cnip.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_cnip.png)


## 直连去广告

如果你想将 SR 作为 iOS 全局去广告工具，这个规则会对你有所帮助。

- 直连：所有请求
- 包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_direct_banad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_direct_banad.png)


## 代理去广告

如果你想将 SR 作为 iOS 全局去广告 + 全局翻墙工具，这个规则会对你有所帮助。

- 直连：局域网请求
- 代理：其余所有请求
- 包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_proxy_banad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_proxy_banad.png)


## 回国规则

提供给海外华侨使用，可以回到墙内，享受国内的一些互联网服务。

- 直连：国外网站
- 代理：中国网站
- 不包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_backcn.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_backcn.png)


## 回国规则 + 广告

提供给海外华侨使用，可以回到墙内，享受国内的一些互联网服务。

- 直连：国外网站
- 代理：中国网站
- 包含广告过滤

规则地址：<https://raw.githubusercontent.com/h2y/Shadowrocket-ADBlock-Rules/master/sr_backcn_ad.conf>

![二维码](https://h2y.github.io/Shadowrocket-ADBlock-Rules/figure/sr_backcn_ad.png)
