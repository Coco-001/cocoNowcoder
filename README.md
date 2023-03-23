<p align="center">
	<a href="https://cocospace.top/" target="_blank">
		<img src="https://uploadfiles.nowcoder.com/images/20200918/63_1600411072844_22E9FCAB3FDEAC64452DAA8AD9CBD14C" style="width: 200px; height: 200px">
	</a>
</p>
<p align="center">
	<img src="https://img.shields.io/badge/SpringBoot-2.1.5.RELEASE-brightgreen">
	<img src="https://img.shields.io/badge/SpringSecurity-5.4.5-brightgreen">
	<img src="https://img.shields.io/badge/MyBatis-3.5.5-brightgreen">
	<img src="https://img.shields.io/badge/JDK-1.8-brightgreen">
	<img src="https://img.shields.io/badge/MySql-8.0.15-brightgreen">
  <img src="https://img.shields.io/badge/Redis-5.0.14-brightgreen">
</p>
<p align="center">
	<img src="https://img.shields.io/badge/fastjson-1.2.58-brightgreen">
	<img src="https://img.shields.io/badge/Quartz-2.3.2-brightgreen">
	<img src="https://img.shields.io/badge/maven-3.6.3-brightgreen">
	<img src="https://img.shields.io/badge/kafka-2.2.6-brightgreen">
  <img src="https://img.shields.io/badge/elasticsearch-6.3.0-brightgreen">
</p>

# 仿牛客网社区

## 项目简介

这是一个仿照牛客网实现的讨论区，不仅实现了基本的注册、登录、发帖、评论、回复、私信等功能，同时使用前缀树实现敏感词过滤；使用 Redis 实现点赞与关注；使用 Kafka 处理发送评论、点赞和关注等系统通知；使用 Elasticsearch 实现全文搜索，关键词高亮显示；并将用户头像等信息存于七牛云服务器。

## 功能简介

- 使用 Redis 的 set 实现点赞，zset 实现关注，并使用 Redis 存储登录ticket和验证码，解决分布式 Session 问题，计划使用 Redis 的高级数据类型 HyperLogLog 统计 UV (Unique Visitor)，使用 Bitmap 统计 DAU (Daily Active User)（未实现）。
- 使用Redis Cell模块对用户发帖进行限流，防止恶意灌水。
- 使用 Kafka 处理发送评论、点赞、关注等系统通知、将新发布的帖子异步传输至Elasticsearch服务器，并使用事件进行封装，构建了强大的异步消息系统。
- 使用Elasticsearch做全局搜索，增加关键词高亮显示等功能。
- 使用 Quartz 定时更新热帖排行。
- 使用 Spring Security 做权限控制，替代拦截器的拦截控制，并使用自己的认证方案替代 Security 认证流程，使权限认证和控制更加方便灵活。

## 系统架构

![](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/%E6%9E%B6%E6%9E%84%E5%9B%BE.png)

## 数据库初始化

```sql
create database community;
use community;
source /path/to/sql/init_schema.sql;
source /path/to/sql/init_data.sql;
source /path/to/sql/tables_mysql_innodb.sql;
```

## 运行

1. 安装JDK，Maven

2. 克隆代码到本地

3. 配置mysql、七牛云、kafka、ElasticSearch

4. 启动zookeeper

5. 启动Kafka

6. 启动Elasticsearch

7. 启动项目


## 运行效果展示

#### 发帖

![image-20210331105217867](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210331105217867.png)

#### 帖子详情、评论

![image-20210331105241026](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210331105241026.png)

#### 私信

![image-20210331105316546](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210331105316546.png)

#### 系统通知

![image-20210331105333140](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210331105333140.png)

#### 搜索

![image-20210331105404130](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210331105404130.png)

#### 限流

![image-20210427152933772](https://cdn.jsdelivr.net/gh/Coco-001/coco/images/image-20210427152933772.png)
