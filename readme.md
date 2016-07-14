# 匠心之路

[TOC]

> 我认为，科技公司是 “价值导向，业务选型，管理整合，技术创新” 的。

以下是根据我曾经所在公司的经历总结，供研发团队参考。以通用优先，各平台特有补充。后续会随时调整补充。

## 管理

> 老子云：“太上，不知有之；其次，亲而誉之；其次，畏之；其次，侮之。”
>
> 公司成长业务增加，核心的关键是让优秀人才的密度超过业务复杂度的增加。

![业务、人才、流程的关系](https://raw.githubusercontent.com/TingGe/develop-tools/master/img/640.png)

*详见：附录「2016码会」张一鸣：为何不赞同控制人力成本*

## 团队协作

> 团队协作的核心是项目管理，其他工具需要配合项目管理平台来选择。

- 项目管理方式：Agile Project Management（Scrum、XP、Kanban、Lean）、PMP
- 协调团队间工作：[Trello](https://trello.com/)、[Slack](https://slack.com/)、[Redmine](http://www.redmine.org/projects/redmine/wiki/Download)（需求过程管理）、[Confluence](https://www.atlassian.com/software/confluence)（需求内容管理）teambition、Gantter、HackPad、Mantis
- 文件共享服务：NAS
- 文档：[Typora](https://typora.io)、[Evernote](https://www.evernote.com/)、MS Office
- 会议与头脑风暴：[MindMup](https://www.mindmup.com/)、百度脑图、XMind、Mindjet MindManager

## 研发

> 大型应用的编程，一般会遇到性能墙和复杂度墙两类问题。

- 应用程序执行容器： [Docker](https://www.docker.com/)
- 代码仓库：Github、[GitLab](https://about.gitlab.com/)
- 代码审核：[Phabricator](https://github.com/phacility/phabricator)
- 原型：Axure、[Fuse](https://www.fusetools.com/)
- 规范：[语义化版本 2.0.0](http://semver.org/lang/zh-CN/)、[表述性状态转移（RESTful API）](http://www.ituring.com.cn/tupubarticle/3790)、面向服务架构（SOA）、远程过程调用（RPC）
- 监控应用：[Zabbix](http://www.zabbix.com/)、[Collected](https://collectd.org/)、 [Trace](https://trace.risingstack.com/)
- 实时数据一站式解决方案：ELK stack（[ElasticSearch](https://www.elastic.co/products/elasticsearch)、[Logstash](https://www.elastic.co/products/logstash)、[Kibana](https://www.elastic.co/downloads/kibana)）
- 移动测试缺陷发现和管理：[Bugtags](https://www.bugtags.com/)、[Fabric](https://get.fabric.io/)

### 技术

>  快速迭代的产品必须有敏捷的技术栈和稳定的框架。

#### JavaScript 应用领域和技术栈

JavaScript 在经历 端的融合、栈的融合阶段。JavaScript 可以做很多事情：从前端到全栈，从桌面到移动、物联网、智能家居，从应用到游戏。然而，其在大数据、高强度计算等等这些考验性能和执行效率的场景并不适用。

| 应用领域          | 技术栈                                      |
| ------------- | ---------------------------------------- |
| 全栈 JavaScript | [React Starter Kit](https://github.com/kriasoft/react-starter-kit)、[MERN](http://mern.io/)、[MEAN](http://mean.io/) |
| 服务器端          | NodeJS                                   |
| 浏览器插件和扩展      | 见 [Extensions和Bookmarklet](https://github.com/TingGe/chrome-extensions/blob/master/README.md) |
| 桌面应用          | [Electron](https://electron.atom.io/)    |
| 移动端           | React Native、Hybrid App（Cordova + AngularJS + ionic） |
| 游戏            | Cocos2d-js、Unity3D、Pomelo、Bearcat        |
| 物联网           | [Cylon](https://cylonjs.com/)、Arduino、Tessel、[Ruff](https://ruff.io/zh-cn/) |

#### Web 前端

|                | 技术                                       |
| -------------- | ---------------------------------------- |
| web UI         | [Bootstrap](http://getbootstrap.com/)、[Ratchet](http://goratchet.com/) |
| Node.js 框架     | [Express](https://github.com/expressjs/express)、[Koa2](https://github.com/koajs/koa/tree/v2.x)、[Hapi](http://hapijs.com/) |
| Node.js ORM 框架 | [Sequelize.js](https://github.com/sequelize/sequelize) |

#### JavaScript 引擎

| Browser, Headless Browser, or Runtime | JavaScript引擎                             |
| ------------------------------------- | ---------------------------------------- |
| Mozilla                               | [Spidermonkey](https://developer.mozilla.org/zh-CN/docs/Mozilla/Projects/SpiderMonkey) |
| Chrome                                | [V8](https://chromium.googlesource.com/v8/v8/) |
| Safari                                | [JavaScriptCore](https://github.com/WebKit/webkit/tree/master/Source/JavaScriptCore) |
| IE and Edge                           | [Chakra](https://github.com/Microsoft/ChakraCore) |
| PhantomJS                             | JavaScriptCore                           |
| TrifleJS                              | V8                                       |
| Node.js                               | V8                                       |
| Ruff                                  | [Duktape](http://duktape.org/)           |

### 模式

> 模式，帮助你设计API、搭建代码架构、优化性能

1. [API模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/api.js)，帮助我们为函数给出更干净的接口，包括

   | 模式   | 说明                     |
   | ---- | ---------------------- |
   | 回调模式 | 传入一个函数作为参数             |
   | 配置对象 | 帮助保持函数的参数数量可控          |
   | 返回函数 | 函数的返回值是另一个函数           |
   | 柯里化  | 新函数在已有函数的基础上再加上一部分参数构成 |

2. [初始化模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/init.js)，帮助我们用一种干净的、结构化的方法来做一些初始化工作，通过一些临时变量来保证不污染全局命名空间。包括：

   | 模式      | 说明                                |
   | ------- | --------------------------------- |
   | 即时函数    | 当它们被定义后立即执行                       |
   | 对象即时初始化 | 初始化工作被放入一个匿名对象，这个对象提供一个可以立即被执行的方法 |
   | 条件初始化   | 使分支代码只在初始化时执行一次，而不是在整个程序生命周期中反复执行 |

3. [性能模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/performance.js)，帮助提高代码执行速度，包括：

   | 模式    | 说明                        |
   | ----- | ------------------------- |
   | 记忆模式  | 利用函数的属性，使已经计算过的值不用再次计算    |
   | 重定义函数 | 重写自身的函数体，使第二次及后续的调用做更少的工作 |

4. 对象创建模式，包括：

   | 模式                                       | 说明                    |
   | ---------------------------------------- | :-------------------- |
   | [命名空间模式 ＋ 依赖声明模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/namespace.js) | 保持全局空间干净、帮助组织代码       |
   | [沙箱模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/sanbox.js) | 唯一的全局变量是一个构造函数        |
   | 链式调用模式                                   |                       |
   | [method() 方法](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/method.js) | 将JavaScript变得像基于类的语法糖 |

5. 代码复用模式。

   > “优先使用对象创建而不是类继承”

   | 模式     | 说明                                       |
   | ------ | ---------------------------------------- |
   | 现代继承模式 | [Object.create()](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/create.js) 、借用方法、绑定、[复制属性](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/extend.js)、[混元](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/mix-ins.js) |
   | 类式继承   | [Klass](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/kclass.js) |

6. 设计模式，包括：

   ![设计模式六大原则](https://raw.githubusercontent.com/TingGe/develop-tools/master/img/2012110233.jpg)

   | 模式                                       | 说明                                       | 遵循原则           |
   | ---------------------------------------- | ---------------------------------------- | -------------- |
   | [单例模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/singleton) | 使用`new`、通过同一个构造函数来创建多个对象时，得到同一个对象的不同引用   |                |
   | [工厂模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/factory.js) | 在运行时通过指定字符串来创建指定类型对象的方法                  | 开闭原则（OCP）      |
   | [遍历模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/iterator) | 提供一种简单的API（hasNext（）、next（））来访问复杂的有序聚合数据的每个元素 |                |
   | [装饰模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/decorate) | 在运行时动态地给一个对象添加一些额外功能                     |                |
   | [策略模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/strategy)（对比 [状态模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/status)） | API一致情况下，允许在运行时选择策略                      |                |
   | [外观模式（"门面模式"）](https://github.com/TingGe/knowledge/blob/master/javascript/%E4%BA%8B%E4%BB%B6%E7%B3%BB%E7%BB%9F/dom-events/dom-events.js) | 包装通用的或者设计很差的方法来提供一个更方便的API               | 迪米特法则（LoD,LKP） |
   | [代理模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/proxy)（对比 适配器模式） | 一个对象充当了另一个对象的接口的角色                       |                |
   | [中介者模式](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/mediator.html) | 各彼此合作的对象通过一个`mediator`（中介者）对象通讯          |                |
   | [观察者模式](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/observer)（“订阅者/发布者”或“自定义事件”） | 创建“可被观察的对象”使它在某个事件发生时通知订阅者的方式            |                |

7. DOM和浏览器中的模式，包括：

   > 遵循分离和渐进增强的思想

   | 类别           | 模式          | 说明                                       |
   | ------------ | ----------- | ---------------------------------------- |
   | DOM编程        | DOM访问       | 避免在循环中访问DOM                              |
   |              |             | 将DOM引用赋给本地变量，然后操作本地变量                    |
   |              |             | 当可能的时候使用selectors API                    |
   |              |             | 遍历HTML collections时缓存length              |
   |              | DOM操作       | [使用文档碎片](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/documentfragment.js) |
   |              |             | “cloneNode父节点＋修改＋replaceChild”           |
   | 事件           | 事件处理        |                                          |
   |              | 事件委托        |                                          |
   | 长时间运行的脚本     |             | setTimeout()                             |
   |              |             | [Web Workers](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.patterns/web-workers) |
   | 远程脚本编程       |             | [XMLHttpRequest](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/xhr.html) |
   |              |             | [JSONP](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/jsonp.html) |
   |              |             | 框架（frame）和图片信标（image beacon）             |
   | 部署JavaScript | 合并脚本        |                                          |
   |              | 压缩 + gzip   |                                          |
   |              | 使用CDN + 缓存头 |                                          |
   |              | 加载策略        | HTML5中更好的`async`                         |
   |              | 引入页面脚本的模式   | `<script>`元素的位置                          |
   |              |             | HTTP 分块                                  |
   |              |             | 动态script元素实现非阻塞下载                        |
   |              |             | 插入`<script>`元素                           |
   |              | 减少初始化工作量    | [延迟加载](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/lazy-load.html) |
   |              |             | [按需加载](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/require.js) |
   |              |             | [预加载 JavaScript](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.patterns/preload-javascript.js) |

### 数据结构与算法

> 经典的有：8大排序算法和4大查找算法

排序：直接插入、希尔排序，[直接选择](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/canvas/selection_sort.html)、堆排序，[冒泡排序](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/canvas/bubble_sort.html)、[快速排序](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/canvas/quicksort.html)，归并排序，基数排序。

![8大排序算法](./img/sorting-algorithm.png)

查找：顺序查找、快速（折半）查找、分块查找和散列表

|        | 平均查找长度（ n=节点数，分b块，s=n/b）                 | 查找效率 |
| :----- | ---------------------------------------- | ---- |
| 顺序     | (n+1)/2                                  | 低    |
| 快速（折半） | Log2(n+1)-1                              | 高    |
| 分块     | (分块查找索引表)平均查找长度=Log2(n/s+1)+s/2；(顺序查找索引表)平均查找长度=(S2+2S+n)/(2S) | 中    |
| 散列表    | 1                                        | 直接寻址 |

#### 示例

1. 数组（[随机打乱一维数组](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/array/index.html)、[多数问题](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/array/candidate.html)、[分治法](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/array/binarysearch.html)）
2. [栈](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/stack)（判断是否回文、实现十进制转其它进制、阶乘）
3. [队列](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/queue)（优先队列）
4. [链表](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/list)（双向链表、单向链表、已排序的双向链表）
5. 树
6. 图（[“邻接表”，深度优先搜索和广度优先搜索](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/adjacencylist)）
7. 堆
8. [散列表](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/hashtable)（线性探测、判断字符串中出现次数最多的字符）
9. [利用对象属性](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/object_prop)（字符串比较、带记忆的函数）
10. [字典类](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/dictionary.html)
11. 贪心解法（[部分背包问题](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/knapsack)、[找零问题](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/greedymoney.html)）
12. [动态规划解法](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/dynamic_programming)（0-1背包问题、[计算斐波那契数列](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/fibonacci/dynfib.js)）
13. 递归解法（[0-1背包问题](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/recursive.html)、[计算斐波那契数列](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/fibonacci/iterfib.js)、阶乘）
14. [使用矩阵](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/findmaxsubstr.html)（求公共字符串问题）
15. 迭代（[计算斐波那契数列](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/fibonacci/iterfib.js)）
16. [生成 UUID](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/Math.uuid.js)
17. [输出螺旋矩形算法](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/helix.html)
18. [穷举法](https://github.com/TingGe/knowledge/tree/master/javascript/others/javascript.algorithms/exhaustive)（鸡兔同笼、韩信点兵、“剪枝”）
19. [Base64](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/Base64.html)
20. [MD5](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/md5.html)
21. [SHA-1](https://github.com/TingGe/knowledge/blob/master/javascript/others/javascript.algorithms/sha1.html)

### 工具

> 软件构建的核心就是管理复杂度。
>
> “图形用户界面让简单的任务更容易完成， 而命令行界面使完成复杂的任务成为可能”。

| 分类              | 内容                                       |
| --------------- | ---------------------------------------- |
| 开发工具            | [Atom](https://atom.io/) （安装 Config Import Export ，导入本仓库 AtomBackups 的 json 即可） |
| JavaScript 代码风格 | [Standard Style](https://github.com/feross/standard) , [Semi-Standard Style](https://github.com/Flet/semistandard) or [Happiness Style](https://github.com/jedwatson/happiness) |
| 构建工具            | NPM Scripts、Rollup、Webpack、Gulp、Grunt    |
| 包管理             | NPM                                      |
| 监控 Node.js 项目依赖 | [updtr](https://github.com/peerigon/updtr)、[greenkeeper](https://github.com/greenkeeperio/greenkeeper) |
| 端到端测试           | [Capybara](https://github.com/jnicklas/capybara)、[VCR](https://github.com/vcr/vcr)、[PhantomJS](http://phantomjs.org/)、[CasperJS](https://casperjs.org/)、[Selenium](http://www.seleniumhq.org/) |
| 单元测试            | Mocha、Chai                               |
| 性能测试（页面响应时间、压测） | loadrunner、jmeter                        |
| 静态Web服务器        | [http-server](https://github.com/indexzero/http-server) |
| 静态api           | [json-server](https://github.com/typicode/json-server) |
| 抓包和本地替换Web调试    | [Anyproxy](https://github.com/alibaba/anyproxy)、Wireshark |
| 嵌入式数据库          | [NeDB](https://github.com/louischatriot/nedb) |
| Node.js 调试      | [Node Inspector](https://github.com/node-inspector/node-inspector) |
| PC Web调试        | Chrome（扩展Postman、FE助手等）、Firefox（扩展Firebug） |
| WebView和浏览器调试   | [DebugGap](http://www.debuggap.com/)     |
| 部署              | [pm2](http://pm2.keymetrics.io/)         |

### Mac或Linux系

- 工具：Term2、Vim、Git、[git-flow](https://github.com/nvie/gitflow)、Oh my zsh、[Tmux](https://github.com/tmux/tmux)、Nginx、htop、nmon
- iOS移动页调试： Safari、Chrome、QQ浏览器、[MIHTool](http://www.mihtool.com/)、HttpWatch

### Windows系

- 文档：XMLmind_XML_Editor
- 工具：Babun
- PC Web调试：IE、Fiddler
- Android移动页调试： UC浏览器（参见 “[UC浏览器开发者中心](http://www.uc.cn/business/developer/)”）、微信WebView（参见 “[微信调试工具](http://blog.qqbrowser.cc/)”）

## 附录

### 管理与协作

1. [擦亮眼睛－如何选择创业公司](https://mp.weixin.qq.com/s?__biz=MzI3MDE0MzAzMw==&mid=2652201810&idx=1&sn=075b31abfaed597f222cbedccb02ab70)
2. [初出茅庐的IT人员，怎样才能做好项目经理？](http://www.jianshu.com/p/2f737f8fe75f)
3. [「2016码会」张一鸣：为何不赞同控制人力成本](https://mp.weixin.qq.com/s?__biz=MzA5NDkzNTExMg==&mid=2649506988&idx=1&sn=926c4f3c79dd1d91a0b452bb889d1221)
4. [如何培养高薪人士的逻辑思维力](https://mp.weixin.qq.com/s?__biz=MzA4NzgxMzQzMA==&mid=2654157986&idx=1&sn=225526ec705084c12a400a9a74dbafde)
5. [阿里内部培训负责人：全方位揭秘阿里面试、晋升、层级、培训体系](http://mp.weixin.qq.com/s?__biz=MjM5MzIxNTQ2MA==&mid=402806994&idx=1&sn=77d8fda6912c16a617e82229e8cc1a52&scene=23&srcid=0319fD0Qyeu9idm7xvmZbbiY#rd)
6. [万恶的PM是推动程序员技术不断进步的不竭动力](http://www.jianshu.com/p/ebd7a8b9bff9)
7. [Agile Project Management For Dummies](http://www.dummies.com/go/agileprojectmanagementfd)
8. [这才叫真正的需求管理](http://www.jianshu.com/p/507fea3e2a20)

### 研发

1. [REST API 安全设计指南](http://blog.nsfocus.net/rest-api-design-safety/)
2. [浅谈API安全设计](http://www.jianshu.com/p/d7c52d113a68)
3. [JavaScript Patterns](https://github.com/TooBug/javascript.patterns)
4. [我的ImageMagick使用心得](http://www.charry.org/docs/linux/ImageMagick/ImageMagick.html)
5. [写给想做前端的你](http://mp.weixin.qq.com/s?__biz=MjM5NTEwMTAwNg==&mid=2650208205&idx=1&sn=fe8d7359a76157dcc8be2937309b9575)

### 技术

1. [JavaScript生态圈现状：初学者地图](http://www.infoq.com/cn/articles/state-of-javascript-2016)
2. [近几年前端技术盘点以及 2016 年技术发展方向](http://taobaofed.org/blog/2016/01/04/font-end-tech-inventory/)
3. [JavaScript 就要统治世界了？](https://segmentfault.com/a/1190000003767058)
4. [Linux 发展史小览](http://m.blog.csdn.net/article/details?id=50822128)
5. [程序员必须知道的8大排序和3大查找](http://www.cr173.com/html/15301_all.html)

### 工具

1. [什么是phantomJS？](http://div.io/topic/1413)
2. [mac 下安装运行 redis](http://yijiebuyi.com/blog/d8ab4b444c16f42cefe30df738a42518.html)
3. [文本三巨头：zsh、tmux 和 vim](http://blog.jobbole.com/86571/)
4. [让Git的输出更友好: 多种颜色和自定义log格式](https://www.pureweber.com/article/git-pretty-output/)
5. [Tmux使用方法](http://www.sbloger.com/blog/2013/07/09/about-tmux.html)
6. [终极 Shell——ZSH](http://zhuanlan.zhihu.com/mactalk/19556676)
7. [commandlinefu](http://www.commandlinefu.com/)
8. [curl 命令使用](http://www.cnblogs.com/wangkangluo1/archive/2012/04/17/2453975.html)
9. [Git 常用命令速查表](http://blog.csdn.net/sunboy_2050/article/details/7529841)
10. [为什么 Linux 的 htop 命令完胜 top 命令](https://linux.cn/article-3141-1.html)
