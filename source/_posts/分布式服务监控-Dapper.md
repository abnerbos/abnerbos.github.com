---
title: 分布式服务监控--Dapper
date: 2017-12-13 19:31:48
tags: Dapper,Zipkin
categories: code
---



> [Dapper, a Large-Scale Distributed Systems Tracing Infrastructure](https://research.google.com/pubs/pub36356.html)



学习了大神的论文，再结合网上大家的解析，大概明白了整个流程：

- 在分布式框架上调整，服务调用时会透传traceId parentSpanId，并将这些信息记录到日志中
- 异步拉取日志，结合traceId 和 spanId 分析调用线路，以及分析消耗时间
- 打印的信息为 Annotation，一组Annotation为Span，一组Span 为trace



已经 相应的实现框架

> Zipkin 是 Twitter 的一个开源项目，允许开发者收集 Twitter 各个服务上的监控数据，并提供查询接口

[zipkin简单介绍及环境搭建](https://mykite.github.io/2017/04/21/zipkin简单介绍及环境搭建（一）)



