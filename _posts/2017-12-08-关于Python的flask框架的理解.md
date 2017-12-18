---
layout: post
category: "python"
title:  "关于Python的flask框架的理解和实践"
tags: [python,框架]
---
Markdown是一款标记语言，能够减轻在排版上的工作量。

<!-- more -->

### 
第一部分 Flask简介
第1章 安装
[Flask的安装可以参照](./2017-11-25-关于Flask的一个简单的应用及Restful服务)
第2章 程序的基本结构
2.1 初始化 
```

```
2.2 路由和视图函数
```
@app.route('/')
def index():
	return '<h1>hello world</h1>'

```
2.3 启动服务器
```
from flask import Flask
app = Flask(_name_)
@app.route('/')
def index():
	return '<h1>hello world</h1>'
if _name_ == '_main_':
	app.run(debug=True)
	
```
2.4 一个完整的程序
2.5 请求一响应循环
2.5.1 程序和请求上下文
2.5.2 请求调度
2.5.3 请求钩子
2.5.4 响应
2.6 Flask扩展
第3章 模板
3.1 Jinja2模板引擎
3.1.u1 渲染模板
3.1.2 变量
3.1.3 控制结构
3.2 使用Flask—Bootstrap集成Twitter Bootstrap
3.3 自定义错误页面
3.4 链接
3.5 静态文件
3.6 使用：Flask—Moment本地化日期和时间
第4章 web表单
4.1 跨站请求伪造保护
4.2 表单类
4.3 把表单渲染成HTML
4.4 在视图函数中处理表单
4.5 重定向和用户会话
4.6 Flash消息
第5章 数据库
5.1 SQL数据库
5.2 NoSQL数据库
5.3 使用SQL还是NoSQL
5.4 Python数据库框架
5.5 使用FlaskSQLAlchemy管理数据库
5.6 定义模型
5.7 关系
5.8 数据库操作
5.8.1 创建表
5.8.2 插入行
5.8.3 修改行
5.8.4 册除行
5.8.5 查询行
5.9 在视图函数中操作数据库
5.10 集成Python shell
5.11 使用FlaskMigrate实现数据库迁移
5.11.1 创建迁移仓库
5.11.2 创建迁移脚本
5.11.3 更新数据库
……
第6章 电子邮件
第7章 大型程序的结构

第二部分 实例：社会化博客程序
第8章 用户认证
第9章 用户角色
第10章 用户资料
第11章 博客文章
第12章 关注者
第13章 用户评论
第14章 程序编程接口
第三部分 成功在望
第15章 测试
第16章 性能
第17章 部署
第18章 其他资源