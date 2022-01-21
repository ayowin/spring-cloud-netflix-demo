[toc]

# spring-cloud-netflix-demo
spring cloud netflix版本的demo，整个工程为一个多模块maven工程，以下对各模块逐一介绍。

---

## config-server
* 配置中心，为所有节点提供配置管理
* 配置仓库：https://gitee.com/ayowin/spring-cloud-netflix-demo-config
* 启动模块，生产时需要独立启动

---

## eureka-server
* 注册与发现中心，为节点提供注册、监控、发现
* 启动模块，生产时需要独立启动

---

## common
* springboot工程。
* 公共模块。所有可重用的代码在本模块中编写，供所有节点调用。
* 依赖模块，生产时无需独立启动，仅作为编码时启动。

---

## dao
* springboot工程。
* dao(data access object)模块。对mysql、redis等数据的增删改查等操作在本模块中编码，供所有节点调用。
* 依赖模块，生产时无需独立启动，仅作为编码时启动。

---

## zuul
* springboot工程
* 网关模块。提供网关服务。
* 启动模块，生产时需要独立启动。

---

## producer
* springboot工程
* 生产者模块。提供生产服务。
* 启动模块，生产时需要独立启动。  

**接口说明**
```shell
url: /product/produce
method: post
request:
    {
        "id": 1,
        "quantity": 5
    }
response:
    {
        "result": "success"
    }
```

---

## consumer
* springboot工程
* 消费者模块。提供消费服务。
* 启动模块，生产时需要独立启动。  

**接口说明**
```shell
url: /product/consume
method: post
request:
    {
        "id": 1,
        "quantity": 5
    }
response:
    {
        "result": "success"
    }
```

---

## ui
* 传统前端工程/vue/react/angular工程均可，按需搭建
* 前端模块
* 启动模块，生产时需要独立启动。