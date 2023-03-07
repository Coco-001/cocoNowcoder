<img src="https://uploadfiles.nowcoder.com/images/20200918/63_1600411072844_22E9FCAB3FDEAC64452DAA8AD9CBD14C#pic_center" style="width:20%;" />

​	  ![](https://img.shields.io/badge/SpringBoot-2.1.5.RELEASE-brightgreen)![](https://img.shields.io/badge/SpringSecurity-5.4.5-brightgreen)![](https://img.shields.io/badge/JDK-1.8-brightgreen)![](https://img.shields.io/badge/MySql-8.0.15-brightgreen)![](https://img.shields.io/badge/Redis-5.0.14-brightgreen)

​	![](https://img.shields.io/badge/Mybatis-3.5.1-brightgreen)![](https://img.shields.io/badge/fastjson-1.2.58-brightgreen)![](https://img.shields.io/badge/Quartz-2.3.2-brightgreen)![](https://img.shields.io/badge/maven-3.6.3-brightgreen)![](https://img.shields.io/badge/kafka-2.2.6-brightgreen)![](https://img.shields.io/badge/elasticsearch-6.3.0-brightgreen)

## 项目简介

仿牛客网的论坛，实现了论坛的注册、登录、发帖、评论、回复、私信等功能，使用前缀树实现敏感词过滤；使用 Spring Security 做权限控制；使用Quartz定时更新热门帖子；使用 Redis 实现点赞、关注与发帖限流；使用 Kafka 处理发送评论、点赞和关注等系统通知；使用 Elasticsearch 实现全文搜索。

## 前端

![首页](./images/readme/image-20220307154506982.png)

![消息](./images/readme/image-20220307154626348.png)

![通知](./images/readme/image-20220307154751687.png)

![注册](./images/readme/image-20220307154709573.png)

## 后端

后端学习参照牛客网官方课程：https://www.nowcoder.com/study/live/246/intro
