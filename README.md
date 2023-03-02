# 基于Flask的电商销售数据采集预测与可视化系统


## 一、**项目简介**

20世纪以来，信息技术飞速发展。中国赶上了信息时代的浪潮，在这期间发展了很多规模较大的互联网电商平台。例如拼多多、淘宝、京东、苏宁易购、唯品会等等都有着自己的电商平台软件。

本项目主要通过浏览器爬虫技术，粗略的爬取淘宝热卖网的大致销量数据以及商品基础数据进行数据分析。学习和初步使用爬虫技术、可视化技术、机器学习技术是本课题的意义，并不是数据，所以这里数据相对来说比较粗略不具备商业价值。当然如果技术炉火纯青，可以获取更深层次的数据就具备很高的价值了。

本课题初步实现了【爬虫爬取淘宝热卖数据存入数据库】、【可视化展示分析】、【后台数据管理】、【机器学习算法预测】等核心模块。

## 二、**项目获取**

项目下载地址：http://www.shiyuncode.com/details?id=48

## 三、**开发环境**

运行环境：推荐Python3.6及以上；

开发工具：PyChram（推荐）；

操作系统：windows 10 8G内存以上（其他windows以及macOS支持，但不推荐）；

浏览器：Firefox(推荐)、Google Chrome(推荐)、Edge;

数据库：MySQL8.0(推荐)及其他版本（支持，但容易异常尤其MySQL5.7（不含）以下版本）；

数据库可视化工具：Navicat Premium 15（推荐）以及其他Navicat版本

## 四、**项目技术**

后端：Flask、PyMySql、selenium、Mysql

前端：HTML、Jquery、Ajax、LayUI、Echarts

## 五、**功能结构**

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps1.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps2.jpg) 

## 六、**运行截图**

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps3.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps4.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps5.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps6.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps7.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps8.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps9.jpg) 

![img](https://github.com/UserXiaohu/sales_analysis/blob/main/img/wps10.jpg) 

## 七、**数据库设计**

表名：category

| 字段名  | 数据类型 | 长度 | 允许为空 | 默认值 | 描述   |
| ------- | -------- | ---- | -------- | ------ | ------ |
| content | varchar  | 255  | YES      | None   | 类型   |
| id      | int      | None | NO       | None   | 编号ID |

 

表名：goods

| 字段名 | 数据类型 | 长度 | 允许为空 | 默认值 | 描述     |
| ------ | -------- | ---- | -------- | ------ | -------- |
| id     | int      | None | NO       | None   | 编号ID   |
| ...    | ...      | ...  | ...      | ...    | ...      |
| title  | varchar  | 255  | YES      | None   | 商品标题 |

 

表名：goods_train

| 字段名 | 数据类型 | 长度 | 允许为空 | 默认值 | 描述     |
| ------ | -------- | ---- | -------- | ------ | -------- |
| id     | int      | None | NO       | None   | 编号ID   |
| ...    | ...      | ...  | ...      | ...    | ...      |
| title  | varchar  | 255  | YES      | None   | 商品标题 |

 

表名：notice

| 字段名      | 数据类型 | 长度 | 允许为空 | 默认值 | 描述     |
| ----------- | -------- | ---- | -------- | ------ | -------- |
| content     | varchar  | 255  | YES      | None   | 公告内容 |
| create_time | datetime | None | YES      | None   | 发布时间 |
| id          | int      | None | NO       | None   | 公告     |
| title       | varchar  | 255  | YES      | None   | 公告标题 |
| user_name   | varchar  | 255  | YES      | None   | 发布人   |

 

表名：slog

| 字段名      | 数据类型 | 长度 | 允许为空 | 默认值 | 描述   |
| ----------- | -------- | ---- | -------- | ------ | ------ |
| create_time | datetime | None | YES      | None   | 时间   |
| id          | int      | None | NO       | None   | 编号ID |
| log         | varchar  | 255  | YES      | None   | 内容   |

 

表名：sys_version

| 字段名      | 数据类型 | 长度 | 允许为空 | 默认值 | 描述     |
| ----------- | -------- | ---- | -------- | ------ | -------- |
| id          | int      | None | NO       | None   | 系统版本 |
| sys_name    | varchar  | 255  | YES      | None   | 名称     |
| sys_version | varchar  | 255  | YES      | None   | 描述     |

 

表名：user

| 字段名   | 数据类型 | 长度 | 允许为空 | 默认值 | 描述                   |
| -------- | -------- | ---- | -------- | ------ | ---------------------- |
| account  | varchar  | 255  | YES      | None   | 用户账号               |
| company  | varchar  | 255  | YES      | None   | 企业名称               |
| id       | int      | None | NO       | None   | 编号ID                 |
| mail     | varchar  | 255  | YES      | None   | 邮箱                   |
| name     | varchar  | 255  | YES      | None   | 用户名称（供应商名称） |
| password | varchar  | 255  | YES      | None   | 用户密码               |
| phone    | varchar  | 255  | YES      | None   | 电话号码               |
| status   | int      | None | YES      | None   | 0禁用1启用             |
| type     | int      | None | YES      | None   | 0管理员，1普通用户     |
