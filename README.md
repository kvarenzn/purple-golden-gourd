<p align="center"><img width="120" src="https://danmaku.meagames.cn/favicon.ico"></p>

# 紫金葫芦（母）

一个单html文件版的B站直播弹幕屏蔽/高亮工具，借助Vue3实现。

## 项目名来源

出自《西游记》平顶山一回。紫金葫芦为太上老君的宝物，可以按照名字将不喜欢的事物收入其内化作脓水。本项目的功能与之类似，用户可以制定一系列匹配规则让不喜欢的弹幕消失，当然也可以将喜欢的弹幕高亮标记出来。

至于后缀，按照西游记原文的描述，“母的紫金葫芦”是赝品，功能弱于“公的紫金葫芦”。而后者在有着封号禁言权力的太上老君手中，对于普通用户，最多只能假赝品聊以慰藉。

## 项目依赖
感谢以下的项目的作者，如果没有他们，就没有这个项目的今天
+ [vue3](https://www.github.com/vuejs/vue)
+ [Sortable.js](https://github.com/SortableJS/Sortable)
+ [clipboard.js](https://github.com/zenorocha/clipboard.js)
+ [mosha-vue-toastify](https://github.com/szboynono/mosha-vue-toastify)
+ [pako](https://github.com/nodeca/pako)

## 项目用途
提供一个便捷的在线直播弹幕工具箱。

## 部署方法
下载`index.html`及`h5-index.html`，将其当作普通的静态资源部署即可。注意：项目用到了桌面通知(`Notification`)相关API，如果你希望部署在`localhost`之外的服务器上，需要有https，否则桌面通知功能不会激活。

`index.html`为桌面版，`h5-index.html`为移动版。二者由于布局和操作逻辑相差甚远故分开置于两个文件内。在部署时需要自行配置根据客户端UA转发的功能。

如果你希望自用，那么也可以直接用浏览器打开`index.html`或`h5-index.html`。

## 功能简介

项目提供一个用来测试弹幕匹配规则的环境。

项目提供一些基本的组件：

+ 使用正则表达式匹配弹幕内容
+ 匹配弹幕发送者UID
+ 匹配弹幕发送者昵称
+ 匹配弹幕类型（滚动弹幕、置顶弹幕等等）
+ 使用前后缀提取弹幕内容（除匹配前后缀外的部分均被视作弹幕的内容）
+ “并且”逻辑运算
+ “或者”逻辑运算

你可以通过任意数量的上述组件的组合来指定你想要的规则。在指定规则后，你也可以

+ 为规则命名
+ 指定匹配后的行为（以某种样式高亮显示匹配的弹幕，或是屏蔽之）
+ 导入或导出你制定的规则

一个常见的应用场景是：在一场直播中标记主播的同传弹幕，甚至在联动时用多条规则分别标记不同主播的同传弹幕。

另外为了方便在观看直播的同时查看匹配高亮规则的弹幕，项目提供桌面通知的功能。匹配规则的弹幕的内容将通过桌面通知功能展示。

## 注意事项
+ 项目不提供直播画面的观看渠道。如果希望在测试弹幕的同时观看直播，请新开一个浏览器窗口或在手机上观看。
+ 关于桌面通知功能
	+ 如果你使用Windows或OS X操作系统，请授权浏览器发送通知。否则即使在浏览器内授权给网页通知权限，你仍不能收到任何通知提醒。
	+ 如果你使用Linux，且使用须自行配置的窗口管理器（例如i3wm，dwm或awesome），请确保桌面通知守护进程已配置好并正在运行。
	+ 由于火狐浏览器的限制，在打开本网页时不会自动弹出请求桌面通知权限的对话框。这时如果你希望使用项目的桌面通知功能，请点击浏览器地址栏左侧的像信息气泡一样的按钮，手动开启请求授权对话框。

## 使用方法
请跟随网页内提示操作。

## 在线版本
在[这里](https://danmaku.meagames.cn)有一个已经部署好的版本，可直接试用。

