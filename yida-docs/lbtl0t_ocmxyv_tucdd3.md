---
title: 关于 this 指向
url: https://docs.aliwork.com/docs/yida_support/lbtl0t/ocmxyv/tucdd3
source: docs.aliwork.com
---

# 关于 this 指向

跳到主要内容首页帮助手册用户手册精品模板手册更新日志使用案例表单专题自定义页面专题连接器专题实用工具专题报表专题公式专题方案专题更新日志历史文档场景方案开发者手册搭建技巧使用案例视频中心示例中心开发者中心开发者手册低代码直播开发者论坛校企合作简体中文简体中文English日本語搜索用户手册宜搭简介快速开始表单管理流程设计集成&自动化门户设计报表设计聚合表设计大屏设计自定义页面酷应用平台管理应用管理AI专区插件中心国际化专属宜搭私有化宜搭联系我们开发者功能（需有代码基础）常见问题宜搭 Open API 开放接口JS 动作面板 - 前端代码开发跨应用JS API如何获取 traceid如何调试宜搭页面 JS关于 this 指向关于 didMount宜搭平台接口（页面数据源可直接调用）用户手册开发者功能（需有代码基础）JS 动作面板 - 前端代码开发关于 this 指向本页总览关于 this 指向 1. 前景提要​了解 this 的指向需要先了解 JavaScript 中 this 的指向在绝大多数情况下，函数的调用方式决定了 this 的值（运行时绑定）。this 不能在执行期间被赋值，并且在每次函数被调用时 this 的值也可能会不同。ES5 引入了 bind 方法来设置函数的 this 值，而不用考虑函数如何被调用的。ES2015 引入了箭头函数，箭头函数不提供自身的 this 绑定（this 的值将保持为闭合词法上下文的值）。this - JavaScript | MDNhttps://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/this2. 宜搭动作面板中的 this​在了解了 JavaScript this 之后，在宜搭动作面板中调用函数只需要注意是否有 export 关键字即可。建议，纯工具函数不涉及任何页面上下文，比如随机生成一个字符串 function uid() { return new Date().getTime().toString(32); } , 不需要使用 export 关键字，否则所有方法都要使用 export 关键字，并且使用 this 来调用。案例一export function a() { console.log(this);}export function b() { this.a(); //正确, a 方法中可以正确的获取宜搭渲染引擎上下文 this a(); // 错误, a 方法中无法获取宜搭渲染引擎上下文 this}案例二function a() { console.log(this);}export function b() { this.a(); //错误且会报错，a 方法没有通过 export 关键字导入的方法无法使用宜搭渲染引擎上下文 this 去调用 a(); // 错误, a 方法中无法获取宜搭渲染引擎上下文 this}案例三export function a() { console.log(this);}function b() { a(); // 错误, b 方法没有使用 export 关键字且没有使用 this.a() 来调用，所以 a 方法中无法获取宜搭渲染引擎上下文 this} 此文档对您是否有帮助？如需帮助，请访问 宜搭社区  进行讨论。如果您想通过视频学习，请关注 低代码宝典  进行学习。1. 前景提要​2. 宜搭动作面板中的 this​钉钉扫码,关注宜搭服务窗微信扫码,关注宜搭公众号微信扫码,关注宜搭视频号快捷入口帮助中心更新日志版本价格开发者中心更多开发者社区关于宜搭向团队推荐宜搭联系我们售前咨询技术支持生态与伙伴宜搭阿里云官网Copyright © 2026钉钉（中国）信息技术有限公司和／或其关联公司浙ICP备18037475号-4


