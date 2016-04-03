# 匠心之路

以下是根据我曾经所在公司的经历总结，供研发团队参考。以通用优先，各平台特有补充。后续会随时调整补充。

## 通用

团队协作的核心是项目管理，无论对于程序开发还是媒体团队都是适用的，其他工具需要配合项目管理平台来选择。
- 项目管理方式：PMP、Scrum、XP
- 协调团队间工作：Redmine(需求过程管理) + Confluence(需求内容管理)、Slack、Gantter、Mantis
- 会议与头脑风暴：MindMup、[HackPad](https://hackpad.com/)、百度脑图

## 研发

大型应用的编程，一般会遇到性能墙和复杂度两类问题。
- 代码仓库：Github、GitLab
- 文档：Typora、Pandoc、Evernote、XMind、Mindjet MindManager、MS Office
- 原型：Axure、[Fuse](https://www.fusetools.com/)
- 规范：RESTful API、语义化版本
- 图像处理：ImageMagick
- 移动测试缺陷发现和管理：[Bugtags](https://www.bugtags.com/)、[Fabric](https://get.fabric.io/)

### 技术

#### Web开发模式和前端演变

2009年至今（我08年开始接触Web开发，之前只能找老前辈了），Web开发模式和前端演变。

| 领域         | 演变过程                                     |
| ---------- | ---------------------------------------- |
| Web开发模式    | Web1.0的 JSP/PHP＋Service > 后端为主的MVC > Ajax的SPA > 前端为主的 MV＊ > Node 带来的全栈 |
| Web前端      | JS ＋ CSS ＋ Html > Router + PageView + API |
| JavaScript | “大教堂式”的YUI/Ext  > “集市式”的jQuery/Prototype > "探索治理"的（MVC Backbone）/（MVVM Angular）/（同构 Meteor）/ (同构 React） |
|            | 基础类库完善 > 标准，关注 Web 性能 > HTML5 > 响应式开发，工程化 > 百花齐放 >前端工业化生产 |

#### JavaScript 技术栈

JavaScript 在经历 端的融合、栈的融合阶段。

JavaScript 可以做很多事情：从前端到后端，从桌面到移动，从应用到游戏。然而，其在大数据、高强度计算等等这些考验性能和执行效率的场景并不适用。总结，JavaScript 成熟的应用空间在前端、轻量级后端和游戏。

- Web前端：React + Redux ＋ React-router
- 服务器端：NodeJS、Express、Gulp
- 浏览器插件和扩展：[Extensions和Bookmarklet](https://github.com/TingGe/chrome-extensions/blob/master/README.md)


- 桌面应用：Electron
- 移动端：React Native、Hybrid App（Cordova + AngularJS + ionic）
- 游戏：Cocos2d-js、Unity3D、Pomelo、Bearcat
- 物联网：Cylon



| 分类     | 内容                                       |
| ------ | ---------------------------------------- |
| 开发语言   | JavaScript/NodeJS、CoffeeScript、Html、CSS、Markdown |
| UI框架   | BootStrap、AmazeUI                        |
| 数据可视化  | D3.js、ECharts、HighCharts                 |
| MV＊    | Chaplin、Backbone、AngularJS、React、Vue、Avalon、Knockout |
| DOM操作  | JQuery、Zepto                             |
| 前端模版   | Handlebars                               |
| 服务器端语言 | Java、PHP                                 |

### 工具

> 软件构建的核心就是管理复杂度。

| 分类            | 内容                                       |
| ------------- | ---------------------------------------- |
| 开发工具          | Atom(安装Config Import Export后，导入本仓库AtomBackups的json即可) |
| 构建工具          | Grunt、Brunch、Gulp、Webpack                |
| 包管理           | NPM、Bower                                |
| 自动化测试         | Mocha、Chai、[Nightmare](http://www.nightmarejs.org/) |
| 静态Web服务器      | [http-server](https://github.com/indexzero/http-server) |
| 抓包和本地替换Web调试  | [Anyproxy](https://github.com/alibaba/anyproxy) |
| 嵌入式数据库        | [NeDB](https://github.com/louischatriot/nedb) |
| PC Web调试      | Chrome（扩展Postman、FE助手等）、Firefox（扩展Firebug）、Wireshark |
| WebView和浏览器调试 | [DebugGap](http://www.debuggap.com/)     |

### Mac或Linux系

- 工具：Term2、Vim、Git、Git flow、Term2、Oh my zsh、Tmux、Nginx
- iOS移动页调试： Safari、Chrome、QQ浏览器、MIHTool、HttpWatch

### Windows系

- 文档：XMLmind_XML_Editor
- 工具：Babun
- PC Web调试：IE、Fiddler
- Android移动页调试： UC浏览器（参见 “[UC浏览器开发者中心](http://www.uc.cn/business/developer/)”）、微信WebView（参见 “[微信调试工具](http://blog.qqbrowser.cc/)”）

## 附录

 1. [初出茅庐的IT人员，怎样才能做好项目经理？](http://www.jianshu.com/p/2f737f8fe75f)
 2. [万恶的PM是推动程序员技术不断进步的不竭动力](http://www.jianshu.com/p/ebd7a8b9bff9)
 3. [阿里内部培训负责人：全方位揭秘阿里面试、晋升、层级、培训体系](http://mp.weixin.qq.com/s?__biz=MjM5MzIxNTQ2MA==&mid=402806994&idx=1&sn=77d8fda6912c16a617e82229e8cc1a52&scene=23&srcid=0319fD0Qyeu9idm7xvmZbbiY#rd)
 4. [这才叫真正的需求管理](http://www.jianshu.com/p/507fea3e2a20)
 5. [浅谈API安全设计](http://www.jianshu.com/p/d7c52d113a68)
 6. [语义化版本 2.0.0](http://semver.org/lang/zh-CN/)
 7. [我的ImageMagick使用心得](http://www.charry.org/docs/linux/ImageMagick/ImageMagick.html)
 8. [近几年前端技术盘点以及 2016 年技术发展方向](http://taobaofed.org/blog/2016/01/04/font-end-tech-inventory/)
 9. [JavaScript 就要统治世界了？](https://segmentfault.com/a/1190000003767058)
 10. [文本三巨头：zsh、tmux 和 vim](http://blog.jobbole.com/86571/)
 11. [终极 Shell——ZSH](http://zhuanlan.zhihu.com/mactalk/19556676)