# Yao

[![UnitTest](https://github.com/YaoApp/yao/actions/workflows/unit-test.yml/badge.svg)](https://github.com/YaoApp/yao/actions/workflows/unit-test.yml)
[![codecov](https://codecov.io/gh/YaoApp/yao/branch/main/graph/badge.svg?token=294Y05U71J)](https://codecov.io/gh/YaoApp/yao)

![intro](docs/1.intro.png)

Yao 是一款支持快速创建 Web 服务和管理后台的开源低代码应用引擎。

[English](README.md)

官网: [https://yaoapps.com](https://yaoapps.com)

文档: [https://yaoapps.com/doc](https://yaoapps.com/doc)

## 演示

### 客户管理系统

使用 Yao 搭建的一套通用 CRM 管理系统。

[https://demo-crm.yaoapps.com](https://demo-crm.yaoapps.com/xiang/login/admin?autoLogin=true)

### 智能仓库管理系统

使用 Yao 搭建的云+边物联网应用，支持人脸识别、RFID 的无人值守智能仓库管理系统。

[https://demo-wms.yaoapps.com](https://demo-crm.yaoapps.com/xiang/login/admin?autoLogin=true)

## 介绍

Yao 是一个只需使用 JSON 即可创建数据库模型、编写 API 接口、描述管理后台界面的低代码引擎，使用 Yao 构建的应用可运行在云端或物联网设备上。 开发者不需要写一行代码，就可以拥有 10 倍生产力。

Yao 基于 **flow-based** 编程思想，采用 **Go** 语言开发，支持多种方式扩展数据流处理器。这使得 Yao 具有极好的**通用性**，大部分场景下可以代替编程语言, 在复用性和编码效率上是传统编程语言的 **10 倍**；应用性能和资源占比上优于 **PHP**, **JAVA** 等语言。

Yao 内置了一套数据管理系统，通过编写 **JSON** 描述界面布局，即可实现 90% 常见界面交互功能，特别适合快速制作各类管理后台、CRM、ERP 等企业内部系统。对于特殊交互功能亦可通过编写扩展组件或 HTML 页面的方式实现。内置管理系统与 Yao 并不耦合，亦可采用 **VUE**, **React** 等任意前端技术实现管理界面。

## Install

在终端下运行脚本: ( MacOS / Linux )

```bash
curl -fsSL https://website.yaoapps.com/install.sh | bash
```

Windows 用户请参考安装调试章节: [安装调试](https://yaoapps.com/doc/a.介绍/b.安装调试)

## 入门指南

### Step 1: 创建项目

新建一个项目目录，进入项目目录，运行 `yao init` 命令，创建一个空白的 Yao 应用。

```bash
mkdir -p /data/crm  # 创建项目目录
cd /data/crm  # 进入项目目录
yao init # 运行初始化程序
```

命令运行成功后，将创建 `app.json文件` , `db`, `ui` , `data` 等目录

```bash
├── data        # 用于存放应用产生的文件，如图片,PDF等
├── db          # 用于存放 SQLite 数据库文件
│   └── yao.db
└── ui          # 静态文件服务器文件目录，可以放置自定义前端制品，该目录下文件可通过 http://host:port/文件名称 访问。
└── app.json    # 应用配置文件, 用来定义应用名称等
```

### Step 2: Create the data table

使用 `yao migrate` 命令创建数据表，打开命令行终端，**在项目根录下运行**:

```bash
yao migrate
```

初始化菜单

```bash
yao run flows.setmenu
```

### Step 3: Start the service

打开命令行终端，**在项目根录下运行**:

```bash
yao start
```

1. 打开浏览器, 访问 `https://127.0.0.1:5099/xiang/login/admin`，

2. 输入默认用户名: `xiang@iqka.com`， 密码: `A123456p+`

## 关于 Yao

Yao 的名字源于汉字**爻(yáo)**，是构成八卦的基本符号。八卦，是上古大神伏羲观测总结自然规律后，创造的一个可以指代万事万物的符号体系。爻，有阴阳两种状态，就像 0 和 1。爻的阴阳转换，驱动八卦更替，以此来总结记录事物的发展规律。
