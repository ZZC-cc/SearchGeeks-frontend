# SearchGeeks - 极客搜 聚合搜索平台

> 前后端分离项目  By程序员Chic
>
>
> 一行代码，无限可能！欢迎探索我的项目，喜欢请Star⭐！
>

## 项目介绍

🔍 基于 Spring Boot + Elastic Stack + Vue3 的一站式信息聚合搜索平台 。

👨🏻‍🚀 用户可以在同一页面集中搜索出不同来源、不同类型的内容，比如：文 章、图片、用户、ChatGPT的回复等，提升搜索体验。

👨🏻‍💻 企业也可以直接将项目的数据源接入搜索平台，复用同一套搜索后端，提升开发效率、降低系统维护成本。

> 线上地址：https://xxxxxx.com(暂未上线)
>
>
> 前端项目地址：[https://github.com/ZZC-cc/SearchGeeks-frontend](https://github.com/ZZC-cc/SearchGeeks-frontend)
>
> 后端项目地址：[https://github.com/ZZC-cc/SearchGeeks-backend](https://github.com/ZZC-cc/SearchGeeks-backend)
>

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01-2post.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01-2post.png?raw=true)

## 项目架构

> 一图胜千言~
>

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/00project.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/00project.png?raw=true)

## 技术栈

### 前端

- Vue3
- Ant Design Vue
- 页面状态同步

### 后端

- SpringBoot2.7框架 + springboot-init脚手架
- MySQL数据库（8.x版本）
- Elastic Stack
- ElasticSearch搜索引擎（重点）
- Logstash数据管道
- Kibana数据可视化
- 数据抓取（jsoup、HttpClient爬虫）
    - 离线
    - 实时
- 设计模式
    - 门面模式
    - 适配器模式
    - 注册器模式
- 数据同步
    - 定时
    - 双写
    - Logstash
    - Canal
- JMeter压力测试
## 效果演示

### 文章搜索

（1）没有搜索词则显示全部文章列表

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01-2post.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01-2post.png?raw=true)

（2）输入搜索词搜索

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01post.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/01post.png?raw=true)

### 图片搜索

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/02pircture.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/02pircture.png?raw=true)

### 用户搜索

（1）没有搜索词则显示全部用户列表

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/03user.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/03user.png?raw=true)

（2）搜索用户

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/03-2user.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/03-2user.png?raw=true)

### ChatGPT搜索

![https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/04chat.png?raw=true](https://github.com/ZZC-cc/SearchGeeks-backend/blob/master/doc/04chat.png?raw=true)

## 快速上手

### 安装依赖

```java
npm install
```

### 启动服务

```java
npm run serve
```

### 启动完成：

```java
App running at:
  - Local:   http://localhost:8080/
  - Network: http://192.168.2.9:8080/
```

## 致谢

感谢[鱼皮](https://github.com/liyupi)大佬的指导