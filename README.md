<p align="center">
   <a href="https://nlrx-wjc.github.io/Learn-Vue-Source-Code/" target="_blank">
      <img src="./logo.jpg"/>
   </a>
</p>

<p align="center">
  <img alt="GitHub" src="https://img.shields.io/github/license/NLRX-WJC/Learn-Vue-Source-Code">
  <img alt="GitHub stars" src="https://img.shields.io/github/stars/NLRX-WJC/Learn-Vue-Source-Code">
  <img alt="version" src=https://img.shields.io/badge/version-v1.0.0-orange">
</p>

# 1. 前言

博主作为一名前端开发，日常开发的技术栈是`Vue`，并且用`Vue`开发也有一年多了，对其用法也较为熟练了，但是对各种用法和各种`api`使用都是只知其然而不知其所以然，因此，有时候在排查`bug`的时候就会有点捉襟见肘。鉴于此，索性就从`github`上`clone`下来一份`Vue`源码来学习学习，本系列博文将用来记录博主对`Vue`源码的整个学习过程，以及自己对源码的一些理解。一方面开阔自己的知识视野，另一方面也希望这些文字能够带给他人些许帮助。

# 2. 整体规划

## 2.1 源码学习目录

本项目所分析的`Vue.js`源码版本是目前最新的版本，版本号为 v2.6.11 ，其代码目录如下：

```bash
├─dist                   # 项目构建后的文件
├─scripts                # 与项目构建相关的脚本和配置文件 
├─flow                   # flow的类型声明文件
├─src                    # 项目源代码
│    ├─complier          # 与模板编译相关的代码
│    ├─core              # 通用的、与运行平台无关的运行时代码
│    │  ├─observe        # 实现变化侦测的代码
│    │  ├─vdom           # 实现virtual dom的代码
│    │  ├─instance       # Vue.js实例的构造函数和原型方法
│    │  ├─global-api     # 全局api的代码
│    │  └─components     # 内置组件的代码
│    ├─server            # 与服务端渲染相关的代码
│    ├─platforms         # 特定运行平台的代码，如weex 
│    ├─sfc               # 单文件组件的解析代码
│    └─shared            # 项目公用的工具代码
└─test                   # 项目测试代码
```

从上面的目录结构可以看出，`Vue`的整个项目包含了类型检测相关、单元测试相关、与平台无关的核心代码以及跨平台运行的相关代码。

由于我们只是学习`Vue.js`的设计思想以及代码实现的相关逻辑，所以我们暂不去关心类型检测、单元测试以及特定平台运行等相关逻辑实现，仅关注它的核心代码，即`src/core`和`src/complier`这两个目录下的代码，并且接下来后续的学习也都是只在这两个目录的范围之内。

## 2.2 学习路线

在学习之前，我们需要先制定一个学习路线，循序渐进的学习，这样不至于一头雾水，无处下手。后面的学习路线如下：

1. 变化侦测篇

   学习`Vue`中如何实现数据的响应式系统，从而达到数据驱动视图。

2. 虚拟DOM篇

   学习什么是虚拟DOM，以及`Vue`中的`DOM-Diff`原理

3. 模板编译篇

   学习`Vue`内部是怎么把`template`模板编译成虚拟`DOM`,从而渲染出真实`DOM`

4. 实例方法篇

   学习`Vue`中所有实例方法(即所有以`$`开头的方法)的实现原理

5. 全局API篇

   学习`Vue`中所有全局`API`的实现原理

6. 生命周期篇

   学习`Vue`中组件的生命周期实现原理

7. 指令篇

   学习`Vue`中所有指令的实现原理

8. 过滤器篇

   学习`Vue`中所有过滤器的实现原理

9. 内置组件篇

   学习`Vue`中所有内置组件的实现原理

## 2.3 学习输出

通过一步步的学习，博主打算在学习过程中输出以下三个东西：

- 以文字形式记录学习过程，在线阅读地址：https://nlrx-wjc.github.io/Learn-Vue-Source-Code/
- 为`clone`下来的`Vue`源码添加尽可能详细的注释；
- 做一份思维导图，以宏观角度总览源码；

# 3. 那就开始吧

写作是一件十分枯燥的事情，如果我写的这些文字对你有些许帮助的话，还请赏个star哈~~


