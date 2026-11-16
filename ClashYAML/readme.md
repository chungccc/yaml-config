# Mihomo Configuration

一个基于 Mihomo 内核的个人代理配置模板，支持多机场订阅、地区节点筛选、自动测速、应用分流及自定义规则。

## Features

- 多机场订阅管理
- 香港、新加坡、日本节点自动测速
- PRM / BSC 节点筛选
- 常用应用独立策略组
- Fake-IP DNS 分流
- IPv4 / IPv6 双栈支持
- 多来源规则集自动更新
- 自定义规则及节点管理

## Proxy Providers

| Provider | Prefix | Suffix |
|---|---|---|
| 订阅1 | `SUF-` | `-PRM` |
| 订阅2 | `LXY-` | `-BSC` |


## Usage

1. 下载 `Clash.yaml`。
2. 填写机场订阅地址。
3. 根据需要调整节点筛选条件。
4. 将配置导入 Mihomo 或兼容客户端。

## Disclaimer

本项目仅供个人学习与交流使用。

配置中引用的第三方规则集、图标及相关资源版权归原作者所有，请遵守相关项目的使用协议及所在地法律法规。
