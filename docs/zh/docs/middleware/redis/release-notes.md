---
hide:
  - navigation
---

# Redis 缓存服务 Release Notes

本页列出 Redis 缓存服务的 Release Notes，便于您了解各版本的演进路径和特性变化。

*[mcamel-redis]: mcamel 是 DaoCloud 所有中间件的开发代号，redis 是提供内存数据库缓存服务的中间件

## 2025-02-28

### v0.27.0

- **新增** 支持创建 `7.2.7` 版本的 `Redis` 实例

## 2024-11-30

### v0.24.0

- **优化** 支持部署 7.2.6 版本的 Redis 实例
- **优化** Redis 哨兵模式支持支持设置非动态参数
- **修复** Redis 哨兵模式重启后无法启动的问题

## 2024-09-30

### v0.22.0

- **修复** 选择工作空间查询 Redis 列表时权限泄漏的问题
- **修复** 部分操作无审计日志的问题

## 2024-08-31

### v0.21.0

- **优化** 创建实例时不可选择异常的集群

## 2024-07-31

### v0.20.0

- **新增** 支持纳管 Redis 实例

## 2024-06-30

### v0.19.0

- **优化** 创建 Redis 实例时支持配置固定  IP
- **优化** 参数模板增加 ****maxclients 等常用参数

## 2024-05-31

### v0.18.0

- **新增** 删除任务时可以不删除远程备份
- **新增** 参数模板导入功能
- **优化** 支持批量修改实例参数

## 2024-04-30

### v0.17.0

- **新增** Redis 实例拓扑
- **优化** 增加命名空间配额的提示
- **优化** 删除备份的时候，可以选择删除在 s3 里的备份数据

## 2024-03-31

### v0.16.0

- **新增** Redis 慢查询
- **优化** Redis 哨兵模式支持开启 hostnetwork
- **优化** 当用户权限不足时无法读取 redis 的密码
- **优化** 升级 Redis 哨兵模式的 Operator
- **修复** Redis 哨兵模式无法创建副本数大于 3 的问题（需升级 Operator）
- **修复** Redis 哨兵模式宕机 Master 后用户侧有概率不可用的问题（需升级 Operator）
- **修复** 备份路径默认为 name.rdb
- **修复** Redis 哨兵模式监控面板内存使用率有误的问题

## 2024-01-31

### v0.15.0

- **优化** Redis Operator 升级版本至 6.2.12
- **优化** 在全局管理中增加 Redis 版本展示
- **修复** Redis 集群模式扩容不生效问题（需升级 Operator）
- **修复** Redis 集群模式支持 NodePort 访问（需升级 Operator）

## 2023-12-31

### v0.14.0

- **新增** Redis 内置告警规则
- **优化** Redis 哨兵模式下 NodePort 模式时返回多个哨兵的 NodePort 地址
- **修复** 创建实例时部分输入框填写特殊字符的校验未生效的问题

## 2023-11-30

### v0.13.0

- **新增** 支持记录操作审计日志
- **优化** 实例列表未获取到列表信息时的提示
- **优化** Mcamel-Redis 监控 Dashboard 的中英文展示

## 2023-10-31

### v0.12.0

- **新增** 离线升级
- **新增** 实例重启功能
- **新增** 参数模板功能
- **新增** 跨集群恢复实例
- **优化** 主从延迟的计算方式
- **修复** cloudshell 权限问题

## 2023-08-31

### v0.11.0

- **优化** KindBase 语法兼容
- **优化** operator 创建过程的页面展示

## 2023-07-31

### v0.10.0

- **新增** __mcamel-redis__  访问白名单配置
- **优化** __mcamel-redis__  创建实例对话框添加默认反亲和标签值，简化配置过程
- **优化** __mcamel-redis__  数据恢复界面
- **优化** __mcamel-redis__  前端界面权限展示信息
- **修复** __mcamel-redis__  关闭节点亲和性失败

## 2023-06-30

### v0.9.0

- **新增** __mcamel-redis__  不同命名空间下无法创建同名 Redis
- **新增** __mcamel-redis__  非 MCamel 纳管的 Redis 可能被误操作的问题
- **优化** __mcamel-redis__  备份管理页面结构样式展示
- **优化** __mcamel-redis__  备份 Job 中的密码展示问题
- **优化** __mcamel-redis__  监控图表，去除干扰元素并新增时间范围选择
- **优化** __mcamel-redis__  ServiceMonitor 闭环安装

## 2023-05-30

### v0.8.0

- **新增** __mcamel-redis__  可配置实例反亲和性
- **新增** __mcamel-redis__  对接全局管理审计日志模块
- **修复** __mcamel-redis__  删除 Redis 后，备份相关内容残留
- **修复** __mcamel-redis__  哨兵集群的 Service 地址展示错误

## 2023-04-27

### v0.7.1

- **新增** __mcamel-redis__  详情页面展示相关的事件
- **新增** __mcamel-redis__  列表接口支持 Cluster 与 Namespace 字段过滤
- **新增** __mcamel-redis__  自定义角色
- **修复** __mcamel-redis__  优化 调度策略增加滑动按钮

## 2023-03-29

### v0.6.2

- **新增** __mcamel-redis__  支持自动化备份恢复
- **修复** 没有导出备份恢复的离线镜像
- **修复** __mcamel-redis__  没有导出备份恢复的离线镜像
- **修复** __mcamel-redis__  修复了若干已知问题，提升了系统稳定性和安全性
- **新增** 新增备份功能使用文档

## 2023-02-23

### v0.5.0

- **新增** __mcamel-redis__  helm-docs 模板文件
- **新增** __mcamel-redis__  应用商店中的 Operator 只能安装在 mcamel-system
- **新增** __mcamel-redis__  支持 cloud shell
- **新增** __mcamel-redis__  支持导航栏单独注册
- **新增** __mcamel-redis__  支持查看日志
- **新增** __mcamel-redis__  更新单例/集群模式 Operator 的版本
- **新增** __mcamel-redis__  展示 common Redis 集群
- **新增** __mcamel-redis__  Operator 对接 chart-syncer
- **修复** __mcamel-redis__  实例名太长导致自定义资源无法创建的问题
- **修复** __mcamel-redis__  工作空间 Editor 用户无法查看实例密码
- **修复** __mcamel-redis__  不能解析出正确的 Redis 版本号
- **修复** __mcamel-redis__  无法修改 Port 的问题
- **升级** __mcamel-redis__  升级离线镜像检测脚本  
- **新增** 日志查看操作说明，支持自定义查询、导出等功能

## 2022-12-25

### v0.4.0

- **新增** __mcamel-redis__  NodePort 端口冲突提前检测
- **新增** __mcamel-redis__  节点亲和性配置
- **修复** __mcamel-redis__  单例和集群设置 nodeport 无效的问题
- **修复** __mcamel-redis__  集群模式下，从节点不可以设置为 0 的问题

## 2022-11-28

### v0.2.6

- **修复** 更新 Redis 时校验部分字段错误
- **改进** 密码校验调整为 MCamel 低等密码强度
- **改进** 提升哨兵模式的版本依赖，v1.1.1=>v1.2.2，重要变更为支持 k8s 1.25+
- **新增** 支持在 ARM 环境安装主备模式的 Redis 集群
- **新增** sc 扩容提示
- **新增** 返回列表或者详情时的公共字段
- **新增** 增加返回告警列表
- **新增** 校验 Service 注释
- **修复** 服务地址展示错误

## 2022-10-26

### v0.2.2

- **新增** 获取用户列表接口
- **新增** 支持 arm 架构
- **新增** redis 实例全生命周期的管理
- **新增** redis 实例的监控部署
- **新增** 支持 redis 哨兵，单例和集群一键部署
- **新增** 支持 ws 权限隔离
- **新增** 支持在线动态扩容
- **升级** release notes 脚本
