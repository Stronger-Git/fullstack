* [Summary](#summary)
* [MySQL常用命令](#mysql%E5%B8%B8%E7%94%A8%E5%91%BD%E4%BB%A4)
  * [MySQL使用](#mysql%E4%BD%BF%E7%94%A8)
  * [SQL命令](#sql%E5%91%BD%E4%BB%A4)
  * [数据类型相关命令](#%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E7%9B%B8%E5%85%B3%E5%91%BD%E4%BB%A4)
  * [show create](#show-create)
* [第一部分 基础篇](#%E7%AC%AC%E4%B8%80%E9%83%A8%E5%88%86-%E5%9F%BA%E7%A1%80%E7%AF%87)
* [1\. MySQL的安装与配置](#1-mysql%E7%9A%84%E5%AE%89%E8%A3%85%E4%B8%8E%E9%85%8D%E7%BD%AE)
  * [1\.1 Windows系统](#11-windows%E7%B3%BB%E7%BB%9F)
  * [1\.2 Linux系统](#12-linux%E7%B3%BB%E7%BB%9F)
* [2\. SQL基础](#2-sql%E5%9F%BA%E7%A1%80)
  * [2\.1 DDL语句](#21-ddl%E8%AF%AD%E5%8F%A5)
  * [2\.2 DML语句](#22-dml%E8%AF%AD%E5%8F%A5)
  * [2\.3 DCL语句](#23-dcl%E8%AF%AD%E5%8F%A5)
  * [2\.4 帮助的使用](#24-%E5%B8%AE%E5%8A%A9%E7%9A%84%E4%BD%BF%E7%94%A8)
* [3\. MySQL支持的数据类型](#3-mysql%E6%94%AF%E6%8C%81%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
  * [3\.1 数值类型](#31-%E6%95%B0%E5%80%BC%E7%B1%BB%E5%9E%8B)
    * [3\.1\.1 整数类型](#311-%E6%95%B4%E6%95%B0%E7%B1%BB%E5%9E%8B)
    * [3\.1\.2 小数类型](#312-%E5%B0%8F%E6%95%B0%E7%B1%BB%E5%9E%8B)
    * [3\.1\.3 BIT(位)类型](#313-bit%E4%BD%8D%E7%B1%BB%E5%9E%8B)
  * [3\.2 字符串](#32-%E5%AD%97%E7%AC%A6%E4%B8%B2)
  * [3\.3 日期和时间类型](#33-%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4%E7%B1%BB%E5%9E%8B)
* [4\. MySQL中的运算符](#4-mysql%E4%B8%AD%E7%9A%84%E8%BF%90%E7%AE%97%E7%AC%A6)
  * [4\.1 算数运算符](#41-%E7%AE%97%E6%95%B0%E8%BF%90%E7%AE%97%E7%AC%A6)
  * [4\.2 比较运算符](#42-%E6%AF%94%E8%BE%83%E8%BF%90%E7%AE%97%E7%AC%A6)
  * [4\.3 逻辑运算符](#43-%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97%E7%AC%A6)
  * [4\.4 位运算符](#44-%E4%BD%8D%E8%BF%90%E7%AE%97%E7%AC%A6)
* [5\. 常用函数](#5-%E5%B8%B8%E7%94%A8%E5%87%BD%E6%95%B0)
  * [5\.1 字符串函数](#51-%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%87%BD%E6%95%B0)
  * [5\.2 数值函数](#52-%E6%95%B0%E5%80%BC%E5%87%BD%E6%95%B0)
  * [5\.3 日期和时间函数](#53-%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4%E5%87%BD%E6%95%B0)
  * [5\.4 流程函数](#54-%E6%B5%81%E7%A8%8B%E5%87%BD%E6%95%B0)
  * [5\.5 其他常用函数](#55-%E5%85%B6%E4%BB%96%E5%B8%B8%E7%94%A8%E5%87%BD%E6%95%B0)
* [6\. 图形化工具的使用](#6-%E5%9B%BE%E5%BD%A2%E5%8C%96%E5%B7%A5%E5%85%B7%E7%9A%84%E4%BD%BF%E7%94%A8)
* [第二部分 开发篇](#%E7%AC%AC%E4%BA%8C%E9%83%A8%E5%88%86-%E5%BC%80%E5%8F%91%E7%AF%87)
* [7\. 表类型(存储引擎)的选择](#7-%E8%A1%A8%E7%B1%BB%E5%9E%8B%E5%AD%98%E5%82%A8%E5%BC%95%E6%93%8E%E7%9A%84%E9%80%89%E6%8B%A9)
  * [7\.1 MySQL存储引擎概述](#71-mysql%E5%AD%98%E5%82%A8%E5%BC%95%E6%93%8E%E6%A6%82%E8%BF%B0)
  * [7\.2 各种存储引擎的特性](#72-%E5%90%84%E7%A7%8D%E5%AD%98%E5%82%A8%E5%BC%95%E6%93%8E%E7%9A%84%E7%89%B9%E6%80%A7)
    * [7\.2\.1 MyISAM](#721-myisam)
    * [7\.2\.2 InnoDB](#722-innodb)
    * [7\.2\.3 MEMORY](#723-memory)
    * [7\.2\.4 MERGE](#724-merge)
  * [7\.3 status和variables](#73-status%E5%92%8Cvariables)
* [8\. 选择合适的数据类型](#8-%E9%80%89%E6%8B%A9%E5%90%88%E9%80%82%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
  * [8\.1 CHAR与VARCHAR](#81-char%E4%B8%8Evarchar)
  * [8\.2 TEXT与BLOB](#82-text%E4%B8%8Eblob)
  * [8\.3 浮点数与定点数](#83-%E6%B5%AE%E7%82%B9%E6%95%B0%E4%B8%8E%E5%AE%9A%E7%82%B9%E6%95%B0)
  * [8\.4 日期类型选择](#84-%E6%97%A5%E6%9C%9F%E7%B1%BB%E5%9E%8B%E9%80%89%E6%8B%A9)
* [9\. 字符集](#9-%E5%AD%97%E7%AC%A6%E9%9B%86)
  * [9\.1\. MySQL支持的字符集](#91-mysql%E6%94%AF%E6%8C%81%E7%9A%84%E5%AD%97%E7%AC%A6%E9%9B%86)
  * [9\.2 MySQL字符集的设置](#92-mysql%E5%AD%97%E7%AC%A6%E9%9B%86%E7%9A%84%E8%AE%BE%E7%BD%AE)
    * [9\.2\.1 服务器字符集和校对规则](#921-%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%AD%97%E7%AC%A6%E9%9B%86%E5%92%8C%E6%A0%A1%E5%AF%B9%E8%A7%84%E5%88%99)
    * [9\.2\.2 数据库字符集和校对规则](#922-%E6%95%B0%E6%8D%AE%E5%BA%93%E5%AD%97%E7%AC%A6%E9%9B%86%E5%92%8C%E6%A0%A1%E5%AF%B9%E8%A7%84%E5%88%99)
    * [9\.2\.3 表级别的字符集和校对规则](#923-%E8%A1%A8%E7%BA%A7%E5%88%AB%E7%9A%84%E5%AD%97%E7%AC%A6%E9%9B%86%E5%92%8C%E6%A0%A1%E5%AF%B9%E8%A7%84%E5%88%99)
    * [9\.2\.4 列字符集和校对规则](#924-%E5%88%97%E5%AD%97%E7%AC%A6%E9%9B%86%E5%92%8C%E6%A0%A1%E5%AF%B9%E8%A7%84%E5%88%99)
    * [9\.2\.4 连接字符集和校对规则](#924-%E8%BF%9E%E6%8E%A5%E5%AD%97%E7%AC%A6%E9%9B%86%E5%92%8C%E6%A0%A1%E5%AF%B9%E8%A7%84%E5%88%99)
  * [3\. 字符集的修改步骤](#3-%E5%AD%97%E7%AC%A6%E9%9B%86%E7%9A%84%E4%BF%AE%E6%94%B9%E6%AD%A5%E9%AA%A4)
* [10\. 索引的设计和使用](#10-%E7%B4%A2%E5%BC%95%E7%9A%84%E8%AE%BE%E8%AE%A1%E5%92%8C%E4%BD%BF%E7%94%A8)
  * [10\.1 索引概述](#101-%E7%B4%A2%E5%BC%95%E6%A6%82%E8%BF%B0)
  * [10\.2 数据库索引的分类](#102-%E6%95%B0%E6%8D%AE%E5%BA%93%E7%B4%A2%E5%BC%95%E7%9A%84%E5%88%86%E7%B1%BB)
  * [聚集索引和非聚集索引](#%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95%E5%92%8C%E9%9D%9E%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95)
    * [聚集索引](#%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95)
    * [非聚集索引](#%E9%9D%9E%E8%81%9A%E9%9B%86%E7%B4%A2%E5%BC%95)
  * [10\.3 索引的设计原则](#103-%E7%B4%A2%E5%BC%95%E7%9A%84%E8%AE%BE%E8%AE%A1%E5%8E%9F%E5%88%99)
  * [10\.4 索引的使用](#104-%E7%B4%A2%E5%BC%95%E7%9A%84%E4%BD%BF%E7%94%A8)
  * [10\.5 索引命中](#105-%E7%B4%A2%E5%BC%95%E5%91%BD%E4%B8%AD)
  * [10\.6 最左匹配原则的解释](#106-%E6%9C%80%E5%B7%A6%E5%8C%B9%E9%85%8D%E5%8E%9F%E5%88%99%E7%9A%84%E8%A7%A3%E9%87%8A)
* [11\. 视图](#11-%E8%A7%86%E5%9B%BE)
  * [11\.1 什么是视图](#111-%E4%BB%80%E4%B9%88%E6%98%AF%E8%A7%86%E5%9B%BE)
  * [11\.2 视图操作](#112-%E8%A7%86%E5%9B%BE%E6%93%8D%E4%BD%9C)
    * [11\.2\.1 创建或者修改视图](#1121-%E5%88%9B%E5%BB%BA%E6%88%96%E8%80%85%E4%BF%AE%E6%94%B9%E8%A7%86%E5%9B%BE)
    * [11\.2\.2 删除视图](#1122-%E5%88%A0%E9%99%A4%E8%A7%86%E5%9B%BE)
    * [11\.2\.3 查看视图](#1123-%E6%9F%A5%E7%9C%8B%E8%A7%86%E5%9B%BE)
* [12\. 存储过程和函数](#12-%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E5%92%8C%E5%87%BD%E6%95%B0)
  * [12\.1 什么是存储过程和函数](#121-%E4%BB%80%E4%B9%88%E6%98%AF%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E5%92%8C%E5%87%BD%E6%95%B0)
  * [12\.2 存储过程和函数的相关操作](#122-%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E5%92%8C%E5%87%BD%E6%95%B0%E7%9A%84%E7%9B%B8%E5%85%B3%E6%93%8D%E4%BD%9C)
    * [12\.2\.1 存储过程或函数创建](#1221-%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E6%88%96%E5%87%BD%E6%95%B0%E5%88%9B%E5%BB%BA)
    * [12\.2\.2 删除存储过程或者函数](#1222-%E5%88%A0%E9%99%A4%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E6%88%96%E8%80%85%E5%87%BD%E6%95%B0)
    * [12\.2\.3 查看存储过程或者函数](#1223-%E6%9F%A5%E7%9C%8B%E5%AD%98%E5%82%A8%E8%BF%87%E7%A8%8B%E6%88%96%E8%80%85%E5%87%BD%E6%95%B0)
    * [12\.2\.4 变量的声明及使用](#1224-%E5%8F%98%E9%87%8F%E7%9A%84%E5%A3%B0%E6%98%8E%E5%8F%8A%E4%BD%BF%E7%94%A8)
    * [12\.2\.5 定义条件和处理](#1225-%E5%AE%9A%E4%B9%89%E6%9D%A1%E4%BB%B6%E5%92%8C%E5%A4%84%E7%90%86)
    * [12\.2\.6 光标的使用](#1226-%E5%85%89%E6%A0%87%E7%9A%84%E4%BD%BF%E7%94%A8)
    * [12\.2\.7 流程控制](#1227-%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6)
* [13\. 触发器](#13-%E8%A7%A6%E5%8F%91%E5%99%A8)
  * [13\.1 创建触发器](#131-%E5%88%9B%E5%BB%BA%E8%A7%A6%E5%8F%91%E5%99%A8)
  * [13\.2 删除触发器](#132-%E5%88%A0%E9%99%A4%E8%A7%A6%E5%8F%91%E5%99%A8)
  * [13\.3 查看触发器](#133-%E6%9F%A5%E7%9C%8B%E8%A7%A6%E5%8F%91%E5%99%A8)
* [14\. 数据库事务](#14-%E6%95%B0%E6%8D%AE%E5%BA%93%E4%BA%8B%E5%8A%A1)
  * [14\.1 事务基础](#141-%E4%BA%8B%E5%8A%A1%E5%9F%BA%E7%A1%80)
  * [14\.2 分布式事务](#142-%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1)
    * [14\.2\.1 本地事务](#1421-%E6%9C%AC%E5%9C%B0%E4%BA%8B%E5%8A%A1)
    * [14\.2\.2 分布式事务](#1422-%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1)
  * [14\.3 分布式事务的解决方案](#143-%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%E7%9A%84%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
    * [14\.3\.1 X/Open XA协议](#1431-xopen-xa%E5%8D%8F%E8%AE%AE)
    * [14\.3\.2 TCC模型](#1432-tcc%E6%A8%A1%E5%9E%8B)
  * [14\.4 MySQL分布式事务](#144-mysql%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1)
* [第三部分 优化篇](#%E7%AC%AC%E4%B8%89%E9%83%A8%E5%88%86-%E4%BC%98%E5%8C%96%E7%AF%87)
* [17\. 常用SQL技巧和常见问题](#17-%E5%B8%B8%E7%94%A8sql%E6%8A%80%E5%B7%A7%E5%92%8C%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)
  * [17\.1 正则表达式的使用](#171-%E6%AD%A3%E5%88%99%E8%A1%A8%E8%BE%BE%E5%BC%8F%E7%9A%84%E4%BD%BF%E7%94%A8)
  * [17\.2 巧用RAND()提取随机行](#172-%E5%B7%A7%E7%94%A8rand%E6%8F%90%E5%8F%96%E9%9A%8F%E6%9C%BA%E8%A1%8C)
  * [17\.3 用BIT GROUP FUNCTIONS做统计](#173-%E7%94%A8bit-group-functions%E5%81%9A%E7%BB%9F%E8%AE%A1)
  * [17\.4 小结](#174-%E5%B0%8F%E7%BB%93)
* [18\. SQL优化](#18-sql%E4%BC%98%E5%8C%96)
  * [18\.1 优化SQL语句的一般步骤](#181-%E4%BC%98%E5%8C%96sql%E8%AF%AD%E5%8F%A5%E7%9A%84%E4%B8%80%E8%88%AC%E6%AD%A5%E9%AA%A4)
    * [18\.1\.1 通过 show status命令了解各种SQL的执行频率](#1811-%E9%80%9A%E8%BF%87-show-status%E5%91%BD%E4%BB%A4%E4%BA%86%E8%A7%A3%E5%90%84%E7%A7%8Dsql%E7%9A%84%E6%89%A7%E8%A1%8C%E9%A2%91%E7%8E%87)
    * [18\.1\.2 定位执行效率低的SQL语句](#1812-%E5%AE%9A%E4%BD%8D%E6%89%A7%E8%A1%8C%E6%95%88%E7%8E%87%E4%BD%8E%E7%9A%84sql%E8%AF%AD%E5%8F%A5)
    * [18\.1\.3 通过EXPLAIN分析低效率SQL的执行计划](#1813-%E9%80%9A%E8%BF%87explain%E5%88%86%E6%9E%90%E4%BD%8E%E6%95%88%E7%8E%87sql%E7%9A%84%E6%89%A7%E8%A1%8C%E8%AE%A1%E5%88%92)
    * [18\.1\.4 确定问题并采取相应的优化措施](#1814-%E7%A1%AE%E5%AE%9A%E9%97%AE%E9%A2%98%E5%B9%B6%E9%87%87%E5%8F%96%E7%9B%B8%E5%BA%94%E7%9A%84%E4%BC%98%E5%8C%96%E6%8E%AA%E6%96%BD)
  * [18\.2 索引问题](#182-%E7%B4%A2%E5%BC%95%E9%97%AE%E9%A2%98)
    * [18\.2\.1 索引的存储分类](#1821-%E7%B4%A2%E5%BC%95%E7%9A%84%E5%AD%98%E5%82%A8%E5%88%86%E7%B1%BB)
    * [18\.2\.2 MySQL如何使用索引](#1822-mysql%E5%A6%82%E4%BD%95%E4%BD%BF%E7%94%A8%E7%B4%A2%E5%BC%95)
    * [18\.2\.3 查看索引使用情况](#1823-%E6%9F%A5%E7%9C%8B%E7%B4%A2%E5%BC%95%E4%BD%BF%E7%94%A8%E6%83%85%E5%86%B5)
  * [18\.3 两个简单实用的优化方法](#183-%E4%B8%A4%E4%B8%AA%E7%AE%80%E5%8D%95%E5%AE%9E%E7%94%A8%E7%9A%84%E4%BC%98%E5%8C%96%E6%96%B9%E6%B3%95)
    * [18\.3\.1 定期分析表和检查表](#1831-%E5%AE%9A%E6%9C%9F%E5%88%86%E6%9E%90%E8%A1%A8%E5%92%8C%E6%A3%80%E6%9F%A5%E8%A1%A8)
    * [18\.3\.2 定期优化表](#1832-%E5%AE%9A%E6%9C%9F%E4%BC%98%E5%8C%96%E8%A1%A8)
  * [18\.4 常用SQL的优化](#184-%E5%B8%B8%E7%94%A8sql%E7%9A%84%E4%BC%98%E5%8C%96)
* [19\. 优化数据库对象](#19-%E4%BC%98%E5%8C%96%E6%95%B0%E6%8D%AE%E5%BA%93%E5%AF%B9%E8%B1%A1)
  * [19\.1 优化表的数据类型](#191-%E4%BC%98%E5%8C%96%E8%A1%A8%E7%9A%84%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B)
  * [19\.2 通过拆分提高表的访问效率](#192-%E9%80%9A%E8%BF%87%E6%8B%86%E5%88%86%E6%8F%90%E9%AB%98%E8%A1%A8%E7%9A%84%E8%AE%BF%E9%97%AE%E6%95%88%E7%8E%87)
  * [19\.3 逆规范化](#193-%E9%80%86%E8%A7%84%E8%8C%83%E5%8C%96)
  * [19\.4 使用中间表提高统计查询速度](#194-%E4%BD%BF%E7%94%A8%E4%B8%AD%E9%97%B4%E8%A1%A8%E6%8F%90%E9%AB%98%E7%BB%9F%E8%AE%A1%E6%9F%A5%E8%AF%A2%E9%80%9F%E5%BA%A6)
* [20\. 锁问题](#20-%E9%94%81%E9%97%AE%E9%A2%98)
  * [20\.1 MySQL锁概述](#201-mysql%E9%94%81%E6%A6%82%E8%BF%B0)
  * [20\.2 MyISAM表锁](#202-myisam%E8%A1%A8%E9%94%81)
    * [20\.2\.1 MySQL表级锁的锁模式](#2021-mysql%E8%A1%A8%E7%BA%A7%E9%94%81%E7%9A%84%E9%94%81%E6%A8%A1%E5%BC%8F)
    * [20\.2\.2 如何加表锁](#2022-%E5%A6%82%E4%BD%95%E5%8A%A0%E8%A1%A8%E9%94%81)
    * [20\.2\.3 并发插入(Concurrent Inserts)](#2023-%E5%B9%B6%E5%8F%91%E6%8F%92%E5%85%A5concurrent-inserts)
    * [20\.2\.4 MyISAM的锁调度](#2024-myisam%E7%9A%84%E9%94%81%E8%B0%83%E5%BA%A6)
  * [20\.3 InnoDB锁问题](#203-innodb%E9%94%81%E9%97%AE%E9%A2%98)
    * [20\.3\.1 事务基础](#2031-%E4%BA%8B%E5%8A%A1%E5%9F%BA%E7%A1%80)
    * [20\.3\.2 InnoDB的行锁模式及加锁方法](#2032-innodb%E7%9A%84%E8%A1%8C%E9%94%81%E6%A8%A1%E5%BC%8F%E5%8F%8A%E5%8A%A0%E9%94%81%E6%96%B9%E6%B3%95)
    * [20\.3\.3 InnoDB行锁实现方式](#2033-innodb%E8%A1%8C%E9%94%81%E5%AE%9E%E7%8E%B0%E6%96%B9%E5%BC%8F)
    * [20\.3\.4 间隙锁（Next\-Key锁）](#2034-%E9%97%B4%E9%9A%99%E9%94%81next-key%E9%94%81)
    * [20\.3\.5 恢复和复制的需要，对 InnoDB 锁机制的影响](#2035-%E6%81%A2%E5%A4%8D%E5%92%8C%E5%A4%8D%E5%88%B6%E7%9A%84%E9%9C%80%E8%A6%81%E5%AF%B9-innodb-%E9%94%81%E6%9C%BA%E5%88%B6%E7%9A%84%E5%BD%B1%E5%93%8D)
* [21\. 优化MySQL Server](#21-%E4%BC%98%E5%8C%96mysql-server)
  * [21\.1MySQL体系结构](#211mysql%E4%BD%93%E7%B3%BB%E7%BB%93%E6%9E%84)
  * [21\.2 查看MySQL Server参数](#212-%E6%9F%A5%E7%9C%8Bmysql-server%E5%8F%82%E6%95%B0)
  * [21\.3 MyISAM内存优化](#213-myisam%E5%86%85%E5%AD%98%E4%BC%98%E5%8C%96)
    * [21\.3\.1 索引缓存](#2131-%E7%B4%A2%E5%BC%95%E7%BC%93%E5%AD%98)
    * [21\.3 table\_cache](#213-table_cache)
  * [21\.4 InnoDB内存优化](#214-innodb%E5%86%85%E5%AD%98%E4%BC%98%E5%8C%96)
    * [21\.4\.1 innodb\_buffer\_pool\_size的设置](#2141-innodb_buffer_pool_size%E7%9A%84%E8%AE%BE%E7%BD%AE)
    * [21\.4\.2 InnoDB日志优化](#2142-innodb%E6%97%A5%E5%BF%97%E4%BC%98%E5%8C%96)
    * [21\.4\.3 其他参数](#2143-%E5%85%B6%E4%BB%96%E5%8F%82%E6%95%B0)
  * [21\.5 MySQL并发相关参数](#215-mysql%E5%B9%B6%E5%8F%91%E7%9B%B8%E5%85%B3%E5%8F%82%E6%95%B0)
* [22\. 磁盘I/O问题](#22-%E7%A3%81%E7%9B%98io%E9%97%AE%E9%A2%98)
  * [22\.1 使用磁盘阵列](#221-%E4%BD%BF%E7%94%A8%E7%A3%81%E7%9B%98%E9%98%B5%E5%88%97)
  * [22\.2 使用Symbolic Links分布I/O](#222-%E4%BD%BF%E7%94%A8symbolic-links%E5%88%86%E5%B8%83io)
  * [22\.3 禁止操作系统更新文件的atime属性](#223-%E7%A6%81%E6%AD%A2%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E6%9B%B4%E6%96%B0%E6%96%87%E4%BB%B6%E7%9A%84atime%E5%B1%9E%E6%80%A7)
  * [22\.4 用裸设备(Raw Device)存放InnoDB的共享表空间](#224-%E7%94%A8%E8%A3%B8%E8%AE%BE%E5%A4%87raw-device%E5%AD%98%E6%94%BEinnodb%E7%9A%84%E5%85%B1%E4%BA%AB%E8%A1%A8%E7%A9%BA%E9%97%B4)
* [23\. 应用优化](#23-%E5%BA%94%E7%94%A8%E4%BC%98%E5%8C%96)
  * [23\.1 使用连接池](#231-%E4%BD%BF%E7%94%A8%E8%BF%9E%E6%8E%A5%E6%B1%A0)
  * [23\.2 减少对MySQL的访问](#232-%E5%87%8F%E5%B0%91%E5%AF%B9mysql%E7%9A%84%E8%AE%BF%E9%97%AE)
    * [23\.2\.1 避免对同一数据做重复检索](#2321-%E9%81%BF%E5%85%8D%E5%AF%B9%E5%90%8C%E4%B8%80%E6%95%B0%E6%8D%AE%E5%81%9A%E9%87%8D%E5%A4%8D%E6%A3%80%E7%B4%A2)
    * [23\.2\.2 使用查询缓存](#2322-%E4%BD%BF%E7%94%A8%E6%9F%A5%E8%AF%A2%E7%BC%93%E5%AD%98)
    * [23\.2\.3 增加 CACHE 层](#2323-%E5%A2%9E%E5%8A%A0-cache-%E5%B1%82)
  * [23\.3 负载均衡](#233-%E8%B4%9F%E8%BD%BD%E5%9D%87%E8%A1%A1)
    * [23\.3\.1 利用 MySQL 复制分流查询操作](#2331-%E5%88%A9%E7%94%A8-mysql-%E5%A4%8D%E5%88%B6%E5%88%86%E6%B5%81%E6%9F%A5%E8%AF%A2%E6%93%8D%E4%BD%9C)
    * [23\.3\.2 采用分布式数据库架构](#2332-%E9%87%87%E7%94%A8%E5%88%86%E5%B8%83%E5%BC%8F%E6%95%B0%E6%8D%AE%E5%BA%93%E6%9E%B6%E6%9E%84)

# Summary

解决不了的问题，有闲暇时间还是看官网文档！

书籍:books: 数据库原理与技术

# MySQL常用命令

## MySQL使用

登录退出

```mysql
mysql -uroot -proot -hip -p port
exit
```

win启动关闭服务&linux启动关闭服务

```mysql
#win
net start 服务名
net stop 服务名
#linux
service start mysql
service restart mysql
service stop mysql
```

## SQL命令

DCL：创建用户，查看用户，删除用户，更改密码，创建用户的同时授权，查看权限，授予权限，撤销权限

```mysql
###################用户相关###################
create user 'username'@'ip' identified by 'password';
select * from mysql.user; # 常关注 user,host这两个字段的值
drop user username@'ip';
# 老版本
alter user 'username'@'ip' identified by 'new_password'
# 新版本
update mysql.user set authentication_string=PASSWORD('new_password') where user='username'
###################权限相关###################
# 及时刷新权限
flush privileges;
grant pri1,pri2,...prin on {DB_NAME.*|*.*} to username @'ip' identified by 'password';
grant pri1,pri2,...prin on {DB_NAME.*|*.*} to username;
show grants for username@'ip';
revoke pri1,pri2,.. from username@'ip';
```

DDL：创建数据库，删除数据库，更改数据库，查询数据库，表的定义，查询，删除

```mysql
# 库相关
create database DB_NAME;
show databases;
use DB_NAME;
drop database DB_NAME;
rename OLD_DB_NAME to NEW_DB_NAME;
# 表相关
create table tb_name(col_name_1 col_type_1 constraints,col_name_2 col_type_2 constraints,...,col_name_n col_type_n constraints)
show tables;
desc tb_name;
show create table tb_name \G;#"\G"选项使记录能够按照字段竖着排列。
drop table tb_name;
alter table old_tb_name rename [TO] new_tb_name;
# 字段相关
alter table tb_name MODIFY|ADD|DROP|CHANGE [column] column_definition [FIRST | AFTER col_name;
alter table tb_name engine=innodb;
alter table tb_name add  [UNIQUE | FULLTEXT | SPATIAL]  INDEX | KEY  [索引名] (字段名1 [(长度)] [ASC | DESC]) [USING 索引方法];
drop index 索引名 on tb_name;
alter table tb_name drop index 索引名;
```

DML：表的增删改查

```mysql
# 插入记录
insert into tb_name(field1,field2,...,fieldn) values(value1,value2,...,valuen);
#　指定字段名
insert into emp(ename,hiredate,sal,deptno) values('Long','2020-07-11',5000,1);
# 不指定字段名，但是values的顺序必须和表中的字段排列顺序一致
insert into emp values('Ming', '2020-07-11',5050, 2);
# 对于含可空字段、非空但是含有默认值的字段、自增字段，可以不用再insert后的字段列表里面出现，
# values后面直接跟对应字段的名称value
insert into emp (ename,sal) values('Ting', 5000);
# 批量插入(Mysql特性)
insert into tb_name (field1,field2,...,fieldn) values
(record1_value1,record1_value2,...,record1_valuen),
(record2_value1,record2_value2,...,record2_valuen),
...
(recordn_value1,recordn_value2,...,recordn_valuen);

# 更新记录
update tb_name set field1=value1,field2=value2,...,fieldn =valuen [WHERE CONDITION];
# 删除记录
delete from tb_name [WHERE CONDITION];
#　查询记录
# [WHERE CONDITION]条件查询，where后面的条件可以使用比较运算符(>,<,>=,<=,!=...)，
# 多个条件之间可以用and、or等逻辑运算符进行多条件联合查询
select * from tb_name [WHERE CONDITION];
select field1,field2,..,fieldn from tb_name [WHERE CONDITION];
# 查询不重复记录[去重] distinct
select distinct field from tb_name [WHERE CONDITION];
# 排序和限制
# ORDER BY后跟排序字段，可以跟多个；DESC|ASC是排序关键字，不写此关键字默认是升序排列。
# 如果排序字段的值一样，则值相同的字段按照第二个排序字段进行排序，以此类推。如果只有一个
# 排序字段，则这些字段相同的记录会无序排列。
select * from tb_name [WHERE CONDITION] [ORDER BY field1 [DESC|ASC],field2 [DESC|ASC],...fieldn [DESC|ASC]]
# 限制或分页查询
# offset_start表示记录的起始偏移量，row_count表示显示的行数
# 默认情况下，起始偏移量为0，只需要写记录行数就可以，这时候显示的实际就是前n条记录
select ...[LIMIT offset_start,row_count]
# 聚合
# 很多情况下，我们需要进行一些汇总操作，比如统计整个公司的人数或者统计每个部门的人数，
# 这时候就需要用到SQL的聚合操作。
select [field1,field2,...fieldn] fun_name
from tb_name
[WHERE where_condition]
[GROUP BY field1,field2,...fieldn]
[WITH ROLLUP]
[HAVING where_condition]
# 参数说明
# fun_name 表示要做的聚合操作，也就是聚合函数，常用的有sum、count(*)、max、min。
# GROUP BY关键字表示要进行分类聚合的字段。
# WITH ROLLUP是可选语法，表示是否对分类聚合后的结果进行在汇总。
# HAVING关键字表示对分类后的结果在进行条件的过滤。
#注意：having是对聚合后的记过进行条件的过滤，where是在聚合之前就对记录进行过滤。
#如果逻辑允许，我们尽可能用where先过滤记录，之后再根据逻辑看是否用having再过滤。

# with rollup表示对聚合后的结果求总数
select deptno,count(1) number from emp group by deptno with rollup;

# 统计人数大于1的部门
mysql> select deptno,count(1) from emp group by deptno having count(1) > 1; 

# 统计员工薪水
mysql> select max(sal),min(sal),avg(sal) from emp;

# 按部门号排序[默认asc]
mysql> select * from emp order by deptno;

# 按部门号排序，部门号相同的则按sal降序排序
mysql> select * from emp order by deptno, sal desc;

# 连接查询
# 表连接分为内连接和外连接，他们之间的主要区别是内连接仅选出两张表中互相匹配的记录，
# 而外连接会选出其他不匹配的记录。常用内连接。
mysql> select ename,deptname from emp,dept where emp.deptno = dept.deptno;

# 外连接又分为左外连接和右外连接
# 左连接：包含所有的左边表中的记录甚至是右边表中没有和它匹配的记录
# 右连接：包含所有的右边表中的记录甚至是左边表中没有和它匹配的记录
mysql> select ename,deptname from emp left join dept on emp.deptno = dept.deptno;

mysql> select deptname,ename from emp right join dept on emp.deptno = dept.deptno;

# 子查询：查询的条件是另外一个select语句的结果
# 子查询的关键字包括：in、not in、=、!=、exists、not exists等
mysql> select * from emp where deptno in (select deptno from dept);
# 如果子查询记录数唯一，可以用=代替in
# 某些情况下，子查询可以转化为表连接

# 记录联合（不常用）
# 将两表的数据按照一定的查询条件查询出来后，将结果合并到一起显示出来。就需要使用union和union all关键字。
# UNION ALL：将所有结果集直接合并在一起
# UNION：将UNION ALL后的结果进行一次DISTINCT，去除重复记录后的结果
select * from t1
UNION|UNION ALL
select * from t2
...
UNION|UNION ALL
select * from tn;
```

## 数据类型相关命令

```mysql
1. now()函数：以年月日时分秒的形式显示当前时间
示例：
mysql> select now();
+---------------------+
| now()               |
+---------------------+
| 2020-09-09 09:36:47 |
+---------------------+

2. bin(field):将bit(M)类型的字段以二进制显示，
默认select显示不加操作是查询不到数据的
mysql> select bin(5);
+--------+
| bin(5) |
+--------+
| 101    |
+--------+

3. concat(a, b)：将字符a与b相互连接
mysql> select concat('a', 'b');
+------------------+
| concat('a', 'b') |
+------------------+
| ab               |
+------------------+

4. length(field)：查看某字段的长度值
mysql> select length('abc');
+---------------+
| length('abc') |
+---------------+
|             3 |
+---------------+

```

## show create

```mysql
# show命令相关
1. 查询表和数据库
show create tables|databases;
2. 查看数据库表结构
show create table|database  db_name|tb_name [\g];
3. 查看用户所授予权限
show grants for username@'ip';
4. 查看运行SQL语句时的warning
show warnings;

5. 查看MySQL系统变量及常用变量查询
show variables;
show variables like 'pattern'|where expr;
5.1 查看mysql客户端相关字符集
show variables like 'character_set_client';
=等同于
show variables where Variable_name='character_set_client';
5.2 查看时区
show variables like 'time_zone';
5.3 查看外键关联状态，主要用于导入其他数据库时，在存在外键关联，
且未知其关联性(谁先关联谁的情况下)，我们可以将外键关联暂时关闭。
show variables like '%FOREIGN_KEY_CHECKS%';
5.4 查看运行时的SQLMode
show variables like '%mode%';

6. 查看当前模式
select @@sql_mode;
show variables like '%mode%';
```

# 数据库原理与技术（新增章节）2020-10

## 基本概念

数据库（DB）：是按照一定结构组织并长期存储在计算机内的、可共享的大量数据的有机集合。

解释：

1）数据库中的数据是按照一定的结构**数据模型**来进行组织的，即数据间有一定的联系以及数据有语义解释。

数据模型：数据库系统的核心和基础，是关于描述数据与数据之间的联系、数据的语义、一致性约束的概念性工具的集合。

数据模型的分类：

* 三种基本数据模型：层次模型、**关系模型**（重点掌握）、网状模型。
* 面向对象数据模型
* 谓词模型（逻辑模型）
* XML数据模型
* 非SQL数据模型
* 扩充的数据模型

数据模型通常是由：**数据结构、数据操作和完整性约束**组成。

* 数据结构：系统静态特征的描述，描述对象包含的数据类型、内容、性质和数据之间的相互关系。
* 数据操作：系统动态特征的描述，是对数据库各种对象实例的操作。
* 完整性约束：定义了给定数据模型中数据及联系所具有的制约和依存关系。

数据库管理系统（DBMS）：管理和维护数据库的**系统软件**，是数据库和用户之间的一个接口。

数据库系统（DBS）：实现有组织地、动态地存储大量关联数据、方便多用户访问的计算机软件、硬件和人组成的系统。

> 计算机系统中引入数据库技术后形成数据库系统，也可以说数据库系统是具有管理数据库功能的计算机系统。

关系：DBS=计算机系统（硬件、软件平台、人）+ DBMS + DB

![](https://gitee.com/git_wjx/picture_bed/raw/master/20201015132230.png)

<div align="center"><font color="gray">DB、DBMS、DBS之间的关系
## 关系数据库

关系模型数据结构：行和列组成的二维表结构。

**1.笛卡尔积**（数据库）

笛卡尔积是在域上的一种运算。域是一组具有相同数据类型的值集合。域用来表明定义属性的取值范围。

给定一组域D<sub>1</sub>,D<sub>2</sub>,...,D<sub>n</sub>，则D<sub>1</sub>,D<sub>2</sub>,...,D<sub>n</sub>的笛卡尔积为

D<sub>1</sub> X D<sub>2</sub> X ... X D<sub>n</sub> = {(d<sub>1</sub>,d<sub>2</sub>,...,d<sub>n</sub>) | d<sub>i</sub> ∈ D<sub>i</sub>, i=1,2,...,n }

在数学中，两个集合X和Y的笛卡尓积（Cartesian product），又称直积，表示为X × Y，第一个对象是X的成员而第二个对象是Y的所有可能有序对的其中一个成员。

**简单说就是两集合中，每一项与另一集合中每一项的乘积。**

![](https://gitee.com/git_wjx/picture_bed/raw/master/20201015132229.png)

**2.关系**

关系中基本术语：

（1）元组与属性

（2）候选键

（3）主键

（4）外键

**3.关系的完整性约束**

关系型数据库的完整性约束：实体完整性、参照完整性、用户自定义

实体完整性：主键

参照完整性：外键

用户自定义：字段非空、取值范围要求

## 关系代数

​	关系代数是一种抽象语言，它通过对关系的运算来表达查询。关系代数以关系为运算对象，通过对关系进行“组合”或“分割”，得到所需的数据集合—一个新的关系。

关系代数可分为：

1）集合运算（并交差、广义笛卡尔积）

2）关系运算（投影、选择、连接和除运算）

3）扩充的关系运算（广义投影、外连接、半连接、聚集等）

:bookmark: :new:

========================================================================================================================未完待续

# 查询

SQL写法顺序和执行顺序

```
写法顺序：select--from--where--group by--having--order by 
执行顺序：from--where--group by [having]--select--order by
就是select要放后面，如果有order by，则order by放最后，因为order by 是对结果进行排序
```

**用GROUP BY关键字分组查询**

通过GROUP BY子句可以将数据划分到不同的组中，实现对记录进行分组查询。在查询时，**所查询的列必须包含在分组中**。

执行如下sql,发现能正常执行,而且groupby后默认取每组第一条数据。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20201015144624.png)

当同时含有where子句、group by 子句 、having子句及聚集函数时，执行顺序如下：
--执行where子句查找符合条件的数据；
--使用group by 子句对数据进行分组；对group by 子句形成的组运行聚集函数计算每一组的值；最后用having 子句去掉不符合条件的组。
--having 子句中的每一个元素也必须出现在select列表中。有些数据库例外，如oracle.
--having子句和where子句都可以用来设定限制条件以使查询结果满足一定的条件限制。
--having子句限制的是组，而不是行。where子句中不能使用聚集函数，而having子句中可以。

# 第一部分 基础篇

# 1. MySQL的安装与配置

## 1.1 Windows系统

Win下安装MySQL整体来说没什么难度，基本都是傻白甜操作。

步骤：

* 官网下载MySQL安装包
* 安装，安装过程有很多配置，都很简单，next
* 安装成功后，可以通过MySQL command命令窗口进行操作

注意点：

配置MySQL环境变量，在dos下就能够执行MySQL相关命令，具体就是exe路径配置到PATH里面即可。

常用命令：**启动关闭``mysql``服务必须以管理员身份运行 **

```mysql
# 必须以管理员身份运行 
# 注意这里是你自己的MySQL服务名
net start mysql56 
net stop mysql56
# mysql登录
mysql -uUSERNAME [-hIP] -pPASSWORD
# 本地登录
mysql -uroot -proot
# 远程登录（前提是远程登录被授权）
mysql -uroot -h39.97.181.76 -proot;
```

**Skill Points:** win下mysql配置文件为 my.in，Linux系统下mysql配置文件为my.cnf

```markdown
# win下查看mysql默认文件路劲（baseDir）
mysql> select @@baseDir;
--> C:\Program Files (x86)\MySQL\MySQL Server 5.6\
# linux
whereis my.cnf
```

mysql的配置文件简单介绍：

port = 3306：指定了Mysql开放的端口；

basedir = /usr/local/mysql：指定Mysql安装的绝对路径；

datadir = /data/mysql_db_data：指定Mysql数据存放的绝对路径；

socket = /tmp/mysql.sock：套接字文件

...

## 1.2 Linux系统

Linux系统安装mysql有二进制包编译安装和rpm包安装，rpm相对于二进制包来说，安装方便，不需要手动配置。这里主要讲解二进制包编译安装。

```bash
#1.清除工作
#首先查看linux是否已经安装过mysql相关的软件和配置 清除配置，防止安装失败
#查看是否有mysql相关rpm包
rpm -qa | grep mysql
#如果存在则删除 --nodeps忽略依赖关系
rpm -e --nodeps mysql-xxx-xxx
#搜索mysql命令所在目录及信息
whereis mysql
#搜索mysql相关目录 find命令支持通配符 * ?
find / -name mysql 
#清除目录或命令
rm -rf xxx

#2.准备工作
#检查mysql用户组用户是否存在，如果没有，则创建
cat /etc/group | grep mysql
# 添加mysql用户和用户组
groupadd mysql
useradd -r -g mysql mysql
#下载Linux的Mysql安装包
wget https://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.26-linux-glibc2.12-x86_64.tar.gz
#解压缩 移动 重命名文件或者建立软链接
#解压缩
tar -zxvf mysql-5.7.26-linux-glibc2.12-x86_64.tar.gz
#将解压缩后的文件重命名
cp|mv mysql-5.7.26-linux-glibc2.12-x86_64 mysql
#移动位置
mv mysql /usr/local/
#创建mysql数据目录并给予mysql读写权限
mkdir /usr/local/mysql/data
chown -R mysql:mysql /usr/local/mysql
chmod -R 755 /usr/local/mysql
# 更改完毕之后 可以ls -l 查看一下mysql所属用户和组用户是否变更为mysql

#3.安装 配置
#编译安装mysql /usr/local/mysql/bin目录下执行！！！
./mysqld --initialize --user=mysql --datadir=/usr/local/mysql/data --basedir=/usr/local/mysql
# 安装过程中如果出现了libaio.so.1相关错误，可能是该依赖没有安装，需要手动安装
bin/mysqld: error while loading shared libraries: libaio.so.1: cannot open shared object file: No such file or directory
解决方法：yum install -y libaio  //安装后在初始化就OK了）

#编辑配置文件my.cnf
vim /etc/my.cnf
#添加 注：[mysqld]不要省略
[mysqld]
basedir=/usr/local/mysql
datadir=/usr/local/mysql/data
bind-address=0.0.0.0
port=3306
user=mysql
socket=/tmp/mysql.sock
#character config
character_set_server=utf8mb4
symbolic-links=0

#4.测试启动mysql
/usr/local/mysql/support-files/mysql.server start
# 启动报错，没有该文件夹或文件
# 解决：创建改文件，并赋予mysql权限
/usr/local/mysql/support-files/mysql.server start
Starting MySQL.2020-10-03T02:23:26.745432Z mysqld_safe error: log-error set to '/var/log/mariadb/mariadb.log', however file don't exists. Create writable for user 'mysql'.
The server quit without updating PID file (/usr/local/mysql[FAILED]2zehjjhi300kynwdk13iz.pid).

[root@iz2zehjjhi300kynwdk13iz mysql]# mkdir /var/log/mariadb
[root@iz2zehjjhi300kynwdk13iz mysql]# touch /var/log/mariadb/mariadb.log
[root@iz2zehjjhi300kynwdk13iz mysql]# chown -R mysql:mysql /var/log/mariadb/
# 重启
[root@iz2zehjjhi300kynwdk13iz mysql]# /usr/local/mysql/support-files/mysql.server start

#添加软链接，重启mysql服务
ln -s /usr/local/mysql/support-files/mysql.server /etc/init.d/mysql 
ln -s /usr/local/mysql/bin/mysql /usr/bin/mysql
service mysql restart
#查看mysql初始密码
grep ‘temporary password’ /var/log/mysqld.log
#根据初始密码登录即可

# 启动和关闭服务
service mysql restart
# 查看mysql服务状态
netstat -nlp | grep mysql
```

[参考一](https://blog.csdn.net/weixin_38003389/article/details/90696337)  [参考二](https://www.jianshu.com/p/276d59cbc529)

# 2. SQL基础

## 2.1 DDL语句

```mysql
# 库命令相关
# 创建数据库
create database DB_NAME;
# 查看数据库
show databases;
# 选择数据库
use DB_NAME;
# 删除数据库
drop database DB_NAME;
# 更改数据库名(不支持)
rename OLD_DB_NAME to NEW_DB_NAME;

# 表命令相关
# 创建表
create table tb_name(col_name_1 col_type_1 constraints,col_name_2 col_type_2 constraints,...,col_name_n col_type_n constraints)
#注：mysql的表名是以目录的形式存在于磁盘上，所以表名的字符可以用任何目录名允许的字符。col_name是列名，
#col_type是数据类型，constraints是约束条件。
#示例
create table emp(ename varchar(10), hiredate date,sal decimal(10,2),deptno int(2));
# 查看数据库中的表
show tables;
# 查看表结构
desc tb_name;
show create table tb_name \G;#"\G"选项使记录能够按照字段竖着排列。
# 删除表
drop table tb_name;
# 修改表名
alter table old_tb_name rename [TO] new_tb_name;
# 修改表字段
alter table tb_name MODIFY|ADD|DROP|CHANGE [column] column_definition [FIRST | AFTER col_name]
mysql> desc emp;
+----------+---------------+------+-----+---------+-------+
| Field    | Type          | Null | Key | Default | Extra |
+----------+---------------+------+-----+---------+-------+
| ename    | varchar(10)   | YES  |     | NULL    |       |
| hiredate | date          | YES  |     | NULL    |       |
| sal      | decimal(10,2) | YES  |     | NULL    |       |
| deptno   | int(2)        | YES  |     | NULL    |       |
+----------+---------------+------+-----+---------+-------+
#修改列字段类型
alter table emp modify ename varchar(20);
#增加表字段
alter table emp add age int(3);
#增加到指定位置
alter table emp add birth date after ename;
#删除表字段
alter table emp drop ename;
#字段改名
alter table emp change sal salary decimal(10,2);
```

## 2.2 DML语句

```mysql
+----------+---------------+------+-----+---------+-------+
| Field    | Type          | Null | Key | Default | Extra |
+----------+---------------+------+-----+---------+-------+
| ename    | varchar(20)   | YES  |     | NULL    |       |
| hiredate | date          | YES  |     | NULL    |       |
| sal      | decimal(10,2) | YES  |     | NULL    |       |
| deptno   | int(2)        | YES  |     | NULL    |       |
+----------+---------------+------+-----+---------+-------+

# 插入记录
insert into tb_name(field1,field2,...,fieldn) values(value1,value2,...,valuen);
#　指定字段名
insert into emp(ename,hiredate,sal,deptno) values('Long','2020-07-11',5000,1);
# 不指定字段名，但是values的顺序必须和表中的字段排列顺序一致
insert into emp values('Ming', '2020-07-11',5050, 2);
# 对于含可空字段、非空但是含有默认值的字段、自增字段，可以不用再insert后的字段列表里面出现，
# values后面直接跟对应字段的名称value
insert into emp (ename,sal) values('Ting', 5000);
# 批量插入(Mysql特性)
insert into tb_name (field1,field2,...,fieldn) values
(record1_value1,record1_value2,...,record1_valuen),
(record2_value1,record2_value2,...,record2_valuen),
...
(recordn_value1,recordn_value2,...,recordn_valuen);

# 更新记录
update tb_name set field1=value1,field2=value2,...,fieldn =valuen [WHERE CONDITION];

# 删除记录
delete from tb_name [WHERE CONDITION];

#　查询记录
# [WHERE CONDITION]条件查询，where后面的条件可以使用比较运算符(>,<,>=,<=,!=...)，
# 多个条件之间可以用and、or等逻辑运算符进行多条件联合查询
select * from tb_name [WHERE CONDITION];
select field1,field2,..,fieldn from tb_name [WHERE CONDITION];
# 查询不重复记录[去重] distinct
select distinct field from tb_name [WHERE CONDITION];
# 排序和限制
# ORDER BY后跟排序字段，可以跟多个；DESC|ASC是排序关键字，不写此关键字默认是升序排列。
# 如果排序字段的值一样，则值相同的字段按照第二个排序字段进行排序，以此类推。如果只有一个
# 排序字段，则这些字段相同的记录会无序排列。
select * from tb_name [WHERE CONDITION] [ORDER BY field1 [DESC|ASC],field2 [DESC|ASC],...fieldn [DESC|ASC]]
# 限制或分页查询
# offset_start表示记录的起始偏移量，row_count表示显示的行数
# 默认情况下，起始偏移量为0，只需要写记录行数就可以，这时候显示的实际就是前n条记录
select ...[LIMIT offset_start,row_count]
# 聚合
# 很多情况下，我们需要进行一些汇总操作，比如统计整个公司的人数或者统计每个部门的人数，
# 这时候就需要用到SQL的聚合操作。
select [field1,field2,...fieldn] fun_name
from tb_name
[WHERE where_condition]
[GROUP BY field1,field2,...fieldn]
[WITH ROLLUP]
[HAVING where_condition]
# 参数说明
# fun_name 表示要做的聚合操作，也就是聚合函数，常用的有sum、count(*)、max、min。
# GROUP BY关键字表示要进行分类聚合的字段。
# WITH ROLLUP是可选语法，表示是否对分类聚合后的结果进行在汇总。
# HAVING关键字表示对分类后的结果在进行条件的过滤。
#注意：having是对聚合后的记过进行条件的过滤，where是在聚合之前就对记录进行过滤。
#如果逻辑允许，我们尽可能用where先过滤记录，之后再根据螺距看是否用having再过滤。
mysql> select * from emp;
+-------+------------+---------+--------+
| ename | hiredate   | sal     | deptno |
+-------+------------+---------+--------+
| Long  | 2020-07-11 | 6001.00 |      1 |
| Xiu   | 2020-07-11 | 5001.00 |      2 |
| Dong  | NULL       | 2000.00 |   NULL |
| Ting  | 2020-07-10 | 3000.00 |      5 |
| Lin   | 2020-07-10 | 3000.00 |      1 |
| Bi    | 2020-07-10 | 3200.00 |      1 |
| Au    | 2020-07-10 | 3300.00 |      2 |
+-------+------------+---------+--------+
# with rollup表示对聚合后的结果求总数
select deptno,count(1) number from emp group by deptno with rollup;
+--------+--------+
| deptno | number |
+--------+--------+
|   NULL |      1 |
|      1 |      3 |
|      2 |      2 |
|      5 |      1 |
|   NULL |      7 |
+--------+--------+
# 统计人数大于1的部门
mysql> select deptno,count(1) from emp group by deptno having count(1) > 1; 
+--------+----------+
| deptno | count(1) |
+--------+----------+
|      1 |        3 |
|      2 |        2 |
+--------+----------+
# 统计员工薪水
mysql> select max(sal),min(sal),avg(sal) from emp;
+----------+----------+-------------+
| max(sal) | min(sal) | avg(sal)    |
+----------+----------+-------------+
|  6001.00 |  2000.00 | 3643.142857 |
+----------+----------+-------------+
# 按部门号排序[默认asc]
mysql> select * from emp order by deptno;
+-------+------------+---------+--------+
| ename | hiredate   | sal     | deptno |
+-------+------------+---------+--------+
| Dong  | NULL       | 2000.00 |   NULL |
| Long  | 2020-07-11 | 6001.00 |      1 |
| Lin   | 2020-07-10 | 3000.00 |      1 |
| Bi    | 2020-07-10 | 3200.00 |      1 |
| Xiu   | 2020-07-11 | 5001.00 |      2 |
| Au    | 2020-07-10 | 3300.00 |      2 |
| Ting  | 2020-07-10 | 3000.00 |      5 |
+-------+------------+---------+--------+
# 按部门号排序，部门号相同的则按sal降序排序
mysql> select * from emp order by deptno, sal desc;
+-------+------------+---------+--------+
| ename | hiredate   | sal     | deptno |
+-------+------------+---------+--------+
| Dong  | NULL       | 2000.00 |   NULL |
| Long  | 2020-07-11 | 6001.00 |      1 |
| Bi    | 2020-07-10 | 3200.00 |      1 |
| Lin   | 2020-07-10 | 3000.00 |      1 |
| Xiu   | 2020-07-11 | 5001.00 |      2 |
| Au    | 2020-07-10 | 3300.00 |      2 |
| Ting  | 2020-07-10 | 3000.00 |      5 |
+-------+------------+---------+--------+
# 连接查询
# 表连接分为内连接和外连接，他们之间的主要区别是内连接仅选出两张表中互相匹配的记录，
# 而外连接会选出其他不匹配的记录。常用内连接。
mysql> select * from dept; 
+--------+----------+
| deptno | deptname |
+--------+----------+
|      1 | tech     |
|      2 | sale     |
|      3 | hr       |
+--------+----------+
mysql> select ename,deptname from emp,dept where emp.deptno = dept.deptno;
+-------+----------+
| ename | deptname |
+-------+----------+
| Long  | tech     |
| Xiu   | sale     |
| Lin   | tech     |
| Bi    | tech     |
| Au    | sale     |
+-------+----------+
# 外连接又分为左外连接和右外连接
# 左连接：包含所有的左边表中的记录甚至是右边表中没有和它匹配的记录
# 右连接：包含所有的右边表中的记录甚至是左边表中没有和它匹配的记录
mysql> select ename,deptname from emp left join dept on emp.deptno = dept.deptno;
+-------+----------+
| ename | deptname |
+-------+----------+
| Long  | tech     |
| Lin   | tech     |
| Bi    | tech     |
| Xiu   | sale     |
| Au    | sale     |
| Dong  | NULL     |
| Ting  | NULL     |
+-------+----------+
mysql> select deptname,ename from emp right join dept on emp.deptno = dept.deptno;
+----------+-------+
| deptname | ename |
+----------+-------+
| tech     | Long  |
| sale     | Xiu   |
| tech     | Lin   |
| tech     | Bi    |
| sale     | Au    |
| hr       | NULL  |
+----------+-------+
# 子查询：查询的条件是另外一个select语句的结果
# 子查询的关键字包括：in、not in、=、!=、exists、not exists等
mysql> select * from emp where deptno in (select deptno from dept);
+-------+------------+---------+--------+
| ename | hiredate   | sal     | deptno |
+-------+------------+---------+--------+
| Long  | 2020-07-11 | 6001.00 |      1 |
| Xiu   | 2020-07-11 | 5001.00 |      2 |
| Lin   | 2020-07-10 | 3000.00 |      1 |
| Bi    | 2020-07-10 | 3200.00 |      1 |
| Au    | 2020-07-10 | 3300.00 |      2 |
+-------+------------+---------+--------+
# 如果子查询记录数唯一，可以用=代替in
# 某些情况下，子查询可以转化为表连接

# 记录联合（不常用）
# 将两表的数据按照一定的查询条件查询出来后，将结果合并到一起显示出来。就需要使用union和union all关键字。
# UNION ALL：将所有结果集直接合并在一起
# UNION：将UNION ALL后的结果进行一次DISTINCT，去除重复记录后的结果
select * from t1
UNION|UNION ALL
select * from t2
...
UNION|UNION ALL
select * from tn;
mysql> select deptno from emp union all select deptno from dept;
+--------+
| deptno |
+--------+
|      1 |
|      2 |
|   NULL |
|      5 |
|      1 |
|      1 |
|      2 |
|      1 |
|      2 |
|      3 |
+--------+
10 rows in set (0.00 sec)

mysql> select deptno from emp union select deptno from dept;                  
+--------+
| deptno |
+--------+
|      1 |
|      2 |
|   NULL |
|      5 |
|      3 |
+--------+
```

## 2.3 DCL语句

```mysql
# 创建用户 
# ip字段：(1)localhost (2)公网ip(指定ip段的话使用'%') (3)% 所有ip,username不加引号可以，password必须加引号
create user 'username'@'ip' identified by 'password';
# 删除用户
drop user username @'ip'；
# 修改用户密码
alter user 'username'@'ip' identified by 'new_password';
# 刷新权限，否则可能会导致更改密码无效
flush privileges;
# 利用DML更改用户密码
use mysql;
update user set authentication_string=PASSWORD('new_password') where user='用户名';
flush privileges;//刷新权限，否则可能会导致更改密码无效 

# 用户授权
grant pri1,pri2,...prin on {DB_NAME.*|*.*} to username @'ip';
# 授权的同时创建用户
grant pri1,pri2,...prin on {DB_NAME.*|*.*} to username @'ip' identified by 'password';
#注：支持通配符，‘*’代表所有；授予所有的权限可用 all 或 all privileges
# 单用户授予多库权限，多个grant分开授予
# 撤销权限
revoke pri1,pri2...prin on {DB_NAME.*|*.*} from username@'ip'
# 查看用户权限
show grants for username@'ip';

# 总结：对用户相关的权限、密码、配置等信息的都是修改的mysql下的user表，所以说，我们通过DCL创建用户，实际就是想mysql.user下插入了一条记录，换言之，我们也可以通过DML直接向表中插入，这是可以的，更改用户密码也可以通过update等操作实现，但通常我们不这样做。而是通过DCL来操作。因为DBA控制着DB的运转。

# 下面进行实操 云服务器
mysql> use mysql;
Database changed
mysql> select user,host from user;
+---------------+-----------+
| user          | host      |
+---------------+-----------+
| mysql.session | localhost |
| mysql.sys     | localhost |
| root          | localhost |
+---------------+-----------+
# 创建远端登录用户(指定IP)，并授予权限【也可以设置IP段 112.38.%.%】
mysql> grant all on test.* to stronger@'112.38.54.240' identified by '123';
mysql> select user,host from user;
+---------------+---------------+
| user          | host          |
+---------------+---------------+
| stronger      | 112.38.54.240 |
| mysql.session | localhost     |
| mysql.sys     | localhost     |
| root          | localhost     |
+---------------+---------------+
# 防止创建不能及时生效
mysql> flush privileges;
# 本地登录测试
/user/dos>mysql -ustronger -h39.97.181.76 -p
/user/dos>Enter password: ***
# 上述操作报错的解决方案（可参考）
# whereis my.cnf 定位到my.cnf所在文件，查看my.cnf是否有bind-address=127.0.0.1,将其注释或删去或者改为bind-address=0.0.0.0。
```

## 2.4 帮助的使用

mysql命令和虽不及linux命令多，但是全部都记住是...，在而mysql上使用帮助，不单单是查看这个命令怎么用，也可以查看当前版本下的mysql支持哪些函数和功能或者在该版本上某些命令是否还支持。

```mysql
# 显示可供查询的分类，然后可以继续？选择某个分类查看
mysql> ? contents

# 关键字快速查询
mysql> ? keyword
# 查询create命令的相关使用
mysql> ? create
Many help items for your request exist.
To make a more specific request, please type 'help <item>',
where <item> is one of the following
topics:
   CREATE DATABASE
   CREATE EVENT
   CREATE FUNCTION
   CREATE FUNCTION UDF
   CREATE INDEX
   CREATE LOGFILE GROUP
   CREATE PROCEDURE
   CREATE SERVER
   CREATE TABLE
   CREATE TABLESPACE
   CREATE TRIGGER
   CREATE USER
   CREATE VIEW
   SHOW
   SHOW CREATE DATABASE
   SHOW CREATE EVENT
   SHOW CREATE FUNCTION
   SHOW CREATE PROCEDURE
   SHOW CREATE TABLE
   SPATIAL

```

# 3. MySQL支持的数据类型

## 3.1 数值类型

MySQL支持所有标准SQL中的数值类型，主要有**整数、浮点数、定点数、位类型**。表3-1列出了MySQL5.0中支持的所有数值类型。关键字INT是INTEGER的同名词，DEC是DECIMAL的同名词。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192409.png)

### 3.1.1 整数类型

(1) 对于整型数据，MySQL支持在类型名称后面的小括号内指定显示宽度。如果不显示指定宽度则默认为int(11)。一般配合zerofill使用，zerofill就是用"0"填充的意思，就是在数字位数不够的空间用字符"0"填满。

设置了宽度限制后，如果插入大于宽度限制的值，不会有任何影响，只不过宽度格式已经失去了它本来的意义。

(2)可选属性``UNSIGNED``、``AUTO_INCREMENT``。

``UNSIGNED``保存无符号数（非负数）可设置此选项。

``AUTO_INCREMENT``产生唯一标识符或顺序值，**一个表中只能有一个``AUTO_INCREMENT``列。**对于任何想要使用``AUTO_INCREMENT``的列，应该定义为``NOT NULL``，并定义为``PRIMARY KEY``或定义为``UNIQUE``键。

```mysql
# 创建表t1
mysql> create table t1 (id1 int,id2 int(5));
Query OK, 0 rows affected (0.02 sec)

mysql> desc t1;
+-------+---------+------+-----+---------+-------+
| Field | Type    | Null | Key | Default | Extra |
+-------+---------+------+-----+---------+-------+
| id1   | int(11) | YES  |     | NULL    |       |
| id2   | int(5)  | YES  |     | NULL    |       |
+-------+---------+------+-----+---------+-------+
2 rows in set (0.00 sec)

mysql> insert into t1 values(128,128);
Query OK, 1 row affected (0.00 sec)

mysql> select * from t1;
+------+------+
| id1  | id2  |
+------+------+
|  128 |  128 |
+------+------+
1 row in set (0.00 sec)
# 修改表字段属性为zerofill
mysql> alter table t1 modify id1 int zerofill;
Query OK, 1 row affected (0.05 sec)
Records: 1  Duplicates: 0  Warnings: 0

mysql> alter table t1 modify id2 int(5) zerofill;
Query OK, 1 row affected (0.05 sec)
Records: 1  Duplicates: 0  Warnings: 0
# 不满足宽度0填充
mysql> select * from t1;
+------------+-------+
| id1        | id2   |
+------------+-------+
| 0000000128 | 00128 |
+------------+-------+
1 row in set (0.00 sec)
# 插入大于宽度值的数据对于存储没有影响
mysql> insert into t1 values(128, 1280001);
Query OK, 1 row affected (0.00 sec)

mysql> select * from t1;
+------------+---------+
| id1        | id2     |
+------------+---------+
| 0000000128 |   00128 |
| 0000000128 | 1280001 |
+------------+---------+
2 rows in set (0.00 sec)
# 更改表字段属性为UNSIGNED
mysql> mysql> alter table t1 add id3 tinyint UNSIGNED;   
Query OK, 0 rows affected (0.06 sec)
Records: 0  Duplicates: 0  Warnings: 0
# MySQL自动为zerofill列添加unsigned属性
mysql> desc t1;
+-------+---------------------------+------+-----+---------+-------+
| Field | Type                      | Null | Key | Default | Extra |
+-------+---------------------------+------+-----+---------+-------+
| id1   | int(10) unsigned zerofill | YES  |     | NULL    |       |
| id2   | int(5) unsigned zerofill  | YES  |     | NULL    |       |
| id3   | tinyint(3) unsigned       | YES  |     | NULL    |       |
+-------+---------------------------+------+-----+---------+-------+
3 rows in set (0.00 sec)
# 插入负数提示值越界
mysql> insert into t1 values(-1,-1,-1);
ERROR 1264 (22003): Out of range value for column 'id1' at row 1

# 定义AUTO_INCREMENT列的方式
CREATE TABLE A1(ID INT AUTO_INCREMENT NOT NULL PRIMARY KEY);
CREATE TABLE A1(ID INT NOT NULL,PRIMARY KEY(ID));
CREATE TABLE A1(ID INT AUTO_INCREMENT NOT NULL,UNIQUE(ID));
```

### 3.1.2 小数类型

MySQL小数类型分为**浮点数(float,double)和定点数(decimal)**。定点数在MySQL内部以字符串形式存放，比浮点数更精确，适合用来表示货币等精度高的数据。

(1)浮点数和定点数都可以用**类型名称后加"(M,D)"**的方式来进行表示。表示该值一共显示M位(整数位+小数位)，其中D位位于小数点后面，支持四舍五入，一般浮点数不这样指定，非标准用法。而decimal在不指定精度时，默认的整数位为10，默认的小数位为0。

```mysql
# 类型名称加(M,D)|(精度,标度) 
定义一个float(7,4)的列可以显示-999.9999;如果插入999.00005，近似结果为999.0001;
```

(2)浮点数如果不写精度和标度，则会按照实际精度值显示，如果有精度和标度，则会自动将四舍五入后的结果插入，系统不会报错；定点数如果不写精度和标度，则按照默认值decimal(10,0)来进行操作，并且如果数据超越了精度和标度值，小数位会截断，并按四舍五入处理。

```mysql

mysql> create table t1(id1 float(3,2),id2 double(3,2),id3 decimal(3,2));
Query OK, 0 rows affected (0.02 sec)
# double类型的id2字段插入的数据超出标度 小数位截断四舍五入
mysql> insert into t1 values(2.55,2.555,2.55);
mysql> select * from t1;
+------+------+------+
| id1  | id2  | id3  |
+------+------+------+
| 2.55 | 2.56 | 2.55 |
+------+------+------+
1 row in set (0.00 sec)
# decimal类型的id3字段插入的数据超出标度 会给出警告提示
mysql> insert into t1 values(2.55,2.55,2.555); 
Query OK, 1 row affected, 1 warning (0.01 sec)
# 提示id3字段的数据被截断处理
mysql> show warnings;
+-------+------+------------------------------------------+
| Level | Code | Message                                  |
+-------+------+------------------------------------------+
| Note  | 1265 | Data truncated for column 'id3' at row 1 |
+-------+------+------------------------------------------+
1 row in set (0.00 sec)

mysql> select * from t1;
+------+------+------+
| id1  | id2  | id3  |
+------+------+------+
| 2.55 | 2.56 | 2.55 |
| 2.55 | 2.55 | 2.56 |
+------+------+------+
2 rows in set (0.00 sec)
# 更改数据类型，省略精度和标度
mysql> alter table t1 modify id1 float;
mysql> alter table t1 modify id2 double;
mysql> alter table t1 modify id3 decimal; 
# float,double省略精度和标度则会按照实际精度值显示 decimal省略后精度标度默认为(10,0)
mysql> desc t1;
+-------+---------------+------+-----+---------+-------+
| Field | Type          | Null | Key | Default | Extra |
+-------+---------------+------+-----+---------+-------+
| id1   | float         | YES  |     | NULL    |       |
| id2   | double        | YES  |     | NULL    |       |
| id3   | decimal(10,0) | YES  |     | NULL    |       |
+-------+---------------+------+-----+---------+-------+
3 rows in set (0.00 sec)
# 插入数据
mysql> insert into t1 values(2.555,2.555,2.555);
Query OK, 1 row affected, 1 warning (0.00 sec)

mysql> show warnings;
+-------+------+------------------------------------------+
| Level | Code | Message                                  |
+-------+------+------------------------------------------+
| Note  | 1265 | Data truncated for column 'id3' at row 1 |
+-------+------+------------------------------------------+
1 row in set (0.00 sec)
# float和double类型的字段值没有发生影响，decimal类型的字段发生截断处理
mysql> select * from t1;
+-------+-------+------+
| id1   | id2   | id3  |
+-------+-------+------+
|  2.55 |  2.56 |    3 |
|  2.55 |  2.55 |    3 |
| 2.555 | 2.555 |    3 |
+-------+-------+------+
```

### 3.1.3 BIT(位)类型

(1)用于存放位字段值，BIT(M)可以用来存放多位二进制数，M范围从1~64，如果不写则默认为1位。对于位字段，直接使用``SELECT``命令将不会看到结果，可以用``bin() （显示为二进制格式）或者hex()``函数进行读取。

(2)数据以十进制进行插入，首先转化为二进制，如果转化后的位数小于实际定义的位数，则插入失败。

```mysql

# 省略插入的位数默认为1位
mysql> create table t1(id1 BIT);
Query OK, 0 rows affected (0.02 sec)
# 插入十进制5,会被mysql转化为101进行插入
mysql> insert into t1 values(5);
# 二进制数据位数101大于定义的BIT位数范围，报错
ERROR 1406 (22001): Data too long for column 'id1' at row 1
# 修改BIT位数
mysql> alter table t1 modify id1 BIT(4);
# 再次插入数据5
mysql> insert into t1 values(5);
# 直接使用SELECT默认看不到结果
mysql> select * from t1;
+------+
| id1  |
+------+
|     |
+------+

mysql> select bin(id1) from t1;
+----------+
| bin(id1) |
+----------+
| 101      |
+----------+

mysql> insert into t1 values(12);
mysql> select bin(id1) from t1;
+----------+
| bin(id1) |
+----------+
| 101      |
| 1100     |
+----------+
```

## 3.2 字符串

MySQL中的字符串包括``CHAR、VARCHAR、BINARY、VARBINARY、BLOB、TEXT、ENUM和SET``等字符串类型。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192634.png)

(1)char和varchar，常用来保存较短的字符串，两者的主要区别在于存储方式的不同：char列的长度固定为创建表时声明的长度，即一旦定义后及时存储数据长度不满足也会(空字符填充)占定义的长度空间；而varchar列中的值为可变字符串，存储长度根据字符串的长度变化。另外，在检索的时候，char列删除了尾部的空格，而varchar则保留这些空格。

```mysql
mysql> create table vc(v varchar(4),c char(4)); 
# 插入'ab '
mysql> insert into vc values('ab ','ab ');
# char类型字段删除了尾部的空格
mysql> select *,length(v),length(c) from vc;
+------+------+-----------+-----------+
| v    | c    | length(v) | length(c) |
+------+------+-----------+-----------+
| ab   | ab   |         3 |         2 |
+------+------+-----------+-----------+

mysql> select concat(v,'+'),concat(c,'+'),length(v),length(c) from vc; 
+---------------+---------------+-----------+-----------+
| concat(v,'+') | concat(c,'+') | length(v) | length(c) |
+---------------+---------------+-----------+-----------+
| ab +          | ab+           |         3 |         2 |
+---------------+---------------+-----------+-----------+
```

(2)ENUM类型插入数据的时候是忽略大小写的，对于插入的数据不再ENUM指定范围内的值时，会报错。

```mysql
# 可以看出枚举量下标从1开始
mysql> alter table t add gender enum('M','F');

mysql> insert into t values(10, 2);

mysql> select * from t;
+------+--------+
| id   | gender |
+------+--------+
|   20 | NULL   |
|   10 | F      |
+------+--------+
2 rows in set (0.00 sec)

mysql> insert into t values(30, 1);
Query OK, 1 row affected (0.00 sec)

mysql> select * from t;
+------+--------+
| id   | gender |
+------+--------+
|   20 | NULL   |
|   10 | F      |
|   30 | M      |
+------+--------+
```

## 3.3 日期和时间类型

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192400.png)

这些类型的主要区别如下：

* 表示年月日，通常用DATE表示。
* 年月日时分秒，通常用DATETIME表示。
* 只用来表示时分秒，通常用TIME表示。
* 如果要经常插入或者更新日期为当前系统时间，则通常使用TIMESTAMP表示。
* 如果只表示年份，可以用YEAR来表示，它比DATE占用更少的空间。YEAR有2位或4位格式的年。默认是4位格式。在两位格式中允许的值是70~69（1970~2069）。MySQL以YYYY格式显示YEAR值。

从上表可以看出，每种日期时间类型都有一个有效值范围，如果超出这个范围，在默认的SQLMode下，系统会进行错误提示，并将以零值来进行存储。

(1)``TIMESTAMP``相关特性

* MySQL会给表中的**第一个**``TIMESTAMP``类型的字段设置默认值为系统日期，如果有第二个TIMESTAMP类型，则默认值设置为0值
* ``TIMESTAMP``和在不同的时区下显示的时间也是不同的。
* ``TIMESTAMP``支持的事件范围较小，如果插入的时间范围超出，则会报错。
* 如果在一个``TIMESTAMP``列中插入NULL，则该列值自动设置为当前的日期和时间。在插入或更新一行但不明确给TIMESTAMP列赋值时也会自动设置该列的值为当前的日期和时间。

```mysql

mysql> create table t1(d date,t time,dt datetime);
mysql> desc t1;
+-------+----------+------+-----+---------+-------+
| Field | Type     | Null | Key | Default | Extra |
+-------+----------+------+-----+---------+-------+
| d     | date     | YES  |     | NULL    |       |
| t     | time     | YES  |     | NULL    |       |
| dt    | datetime | YES  |     | NULL    |       |
+-------+----------+------+-----+---------+-------+
# 使用now函数插入当前系统时间
mysql> insert into t1 values(now(),now(),now());
#　datetime是date和time的结合体，所以根据实际需要设置相应字段类型
mysql> select * from t1;
+------------+----------+---------------------+
| d          | t        | dt                  |
+------------+----------+---------------------+
| 2020-07-17 | 20:01:33 | 2020-07-17 20:01:33 |
+------------+----------+---------------------+

# timestamp相关知识讲解
mysql> create table t(ts timestamp);

mysql> show create table t\G;
*************************** 1. row ***************************
       Table: t
Create Table: CREATE TABLE `t` (
  `ts` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
) ENGINE=InnoDB DEFAULT CHARSET=latin1
1 row in set (0.00 sec)
# 增加同类型字段
mysql> alter table t add ts1 timestamp;
Query OK, 0 rows affected (0.03 sec)
Records: 0  Duplicates: 0  Warnings: 0
# MySQL只会为第一个timestamp设置默认值
mysql> desc t;
+-------+-----------+------+-----+---------------------+-----------------------------+
| Field | Type      | Null | Key | Default             | Extra                       |
+-------+-----------+------+-----+---------------------+-----------------------------+
| ts    | timestamp | NO   |     | CURRENT_TIMESTAMP   | on update CURRENT_TIMESTAMP |
| ts1   | timestamp | NO   |     | 0000-00-00 00:00:00 |                             |
+-------+-----------+------+-----+---------------------+-----------------------------+

# 查看当前时区 中国默认东八区
mysql> show variables like 'time_zone';
+---------------+--------+
| Variable_name | Value  |
+---------------+--------+
| time_zone     | SYSTEM |
+---------------+--------+

mysql> insert into t values(now(),now());

mysql> select * from t;
+---------------------+---------------------+
| ts                  | ts1                 |
+---------------------+---------------------+
| 2020-07-17 20:11:28 | 2020-07-17 20:11:28 |
+---------------------+---------------------+

mysql> set time_zone='+9:00';
mysql> show variables like 'time_zone';
+---------------+--------+
| Variable_name | Value  |
+---------------+--------+
| time_zone     | +09:00 |
+---------------+--------+
# 时间自动发生了变化
mysql> select * from t;
+---------------------+---------------------+
| ts                  | ts1                 |
+---------------------+---------------------+
| 2020-07-17 21:11:28 | 2020-07-17 21:11:28 |
+---------------------+---------------------+

# 插入时间范围大于TIMESTAMP的范围会报错
mysql> insert into t(t) values('2099-09-09 21:00:00');
ERROR 1054 (42S22): Unknown column 't' in 'field list'

#插入NULL值，则该列值自动设置为当前的日期和时间
mysql> insert into t values(NULL,NULL);
mysql> select * from t;
+---------------------+---------------------+
| ts                  | ts1                 |
+---------------------+---------------------+
| 2020-07-17 21:45:32 | 2020-07-17 21:45:32 |
| 2020-07-17 21:47:25 | 2020-07-17 21:47:25 |
+---------------------+---------------------+
```

(2)``datetime``相关特性

*  ``YYYY-MM-DD HH:MM:SS或YY-MM-DD HH:MM:SS``格式的字符串。允许“不严格”语法：任何标点符都可以用做日期部分或时间部分之间的分隔符。
* ``YYYYMMDDHHMMSS或YYMMDDHHMMSS``格式的没有间隔符的字符串或**数字**，假定字符串或数字对于日期类型是有意义的，则会自动被解释为相应的时间。
* 函数返回的结果，其值适合``DATETIME、DATE或者TIMESTAMP``上下文，例如``NOW()或CURRENT_DATE``。

```mysql
mysql> create table t6(dt datetime);

mysql> insert into t6 values('2020-07-17 20:20:20');

mysql> insert into t6 values('2020/07/17 20*20*20');    

mysql> insert into t6 values('20200717202020');      

mysql> insert into t6 values(20200717202020); 

mysql> select * from t6;
+---------------------+
| dt                  |
+---------------------+
| 2020-07-17 20:20:20 |
| 2020-07-17 20:20:20 |
| 2020-07-17 20:20:20 |
| 2020-07-17 20:20:20 |
+---------------------+
```

# 4. MySQL中的运算符

MySQL支持多种类型的运算符，来连接表达式的项。这些类型主要包括**算数运算符、比较运算符、逻辑运算符和位运算符**。

## 4.1 算数运算符

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192354.png)

(1) “/”为实数除，结果有小数位，“div”为整数除，结果不存在小数位，不会四舍五入。

```mysql
# 无需选择数据库就可以进行表达式的操作查询
mysql> select 3.1+0.04,3.1-0.04,2*3,1/2,12%8;
+----------+----------+-----+--------+------+
| 3.1+0.04 | 3.1-0.04 | 2*3 | 1/2    | 12%8 |
+----------+----------+-----+--------+------+
|     3.14 |     3.06 |   6 | 0.5000 |    4 |
+----------+----------+-----+--------+------+

# 除法运算和模运算中，如果除数为0，将是非法除数，返回结果为NULL
mysql> select 1/0;
+------+
| 1/0  |
+------+
| NULL |
+------+
1 row in set (0.00 sec)

# div整数除，结果不会四舍五入，mod函数可以实现%同样的效果
mysql> select 3 div 2,mod(12,8);
+---------+-----------+
| 3 div 2 | mod(12,8) |
+---------+-----------+
|       1 |         4 |
+---------+-----------+
```

## 4.2 比较运算符

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192350.png)

(1)MySQL允许用户对表达式左右两边的操作数进行比较，**比较结果为真，则返回1，为假则返回0，比较结果不确定则返回NULL**。

(2)**比较运算符可以用于比较数字、字符串和表达式。数字作为浮点数比较，而字符串以不区分大小写的方式比较。**

==MySQL字符串四则运算的注意点：==

对MySQL中的字符串进行四则运算的时候，会转化为相应的数值类型进行运算。即使运算符两侧的字符串没有数值类型，也能参与运算。转化规则等同于比较的规则。

字符串与数值类型的比较

* MySQL字符串和数字比较时，会自动地把字符串类型转化为数字类型，从首字母开始，遇到非数字类型终止。
* 对于数字开头的字符串，转成数字后会自动丢弃后面的字母部分，只留下纯数字进行比较。
* 对于没有数字开头的字符串与数值类型比较时，只会转化为0和其他数值进行比较。

同理，MySQL会将字符串转化为数字，所以当将字符串和数值进行四则运算时原理，也是同上，会被截断转化为相应的数值类型。

```mysql
#对于开头部分不能截取出数字的字符串来说，转换的结果自然就是0了。就只剩下0去和其他数值进行比较
mysql> select 'a'=0;
+-------+
| 'a'=0 |
+-------+
|     1 |
+-------+
1 row in set, 1 warning (0.00 sec)

mysql> select 'aa1' < 2;
+-----------+
| 'aa1' < 2 |
+-----------+
|         1 |
+-----------+
1 row in set, 1 warning (0.00 sec)

#对于数据开头的字符串，转成数字后会自动丢弃后面的字母部分，只留下纯数字进行比较。
mysql> select '23aa' < 3;
+------------+
| '23aa' < 3 |
+------------+
|          0 |
+------------+
1 row in set, 1 warning (0.00 sec)

#字符串与数字相加
# 转化为 0+3
mysql> select 'a'+3;
+-------+
| 'a'+3 |
+-------+
|     3 |
+-------+
1 row in set, 1 warning (0.00 sec)
# 转化为1+3
mysql> select '1a'+3;
+--------+
| '1a'+3 |
+--------+
|      4 |
+--------+
# 转化为2*3
mysql> select '2a'*3;
+--------+
| '2a'*3 |
+--------+
|      6 |
+--------+
1 row in set, 1 warning (0.00 sec)
#字符串相加
mysql> select '3a'+'2b';
+-----------+
| '3a'+'2b' |
+-----------+
|         5 |
+-----------+
#可以看到截断警告的提示
mysql> show warnings;
+---------+------+----------------------------------------+
| Level   | Code | Message                                |
+---------+------+----------------------------------------+
| Warning | 1292 | Truncated incorrect DOUBLE value: '2a' |
+---------+------+----------------------------------------+
1 row in set (0.00 sec)
```



```mysql
# NULL不可比较返回NULL
mysql> select 1=0,1=1,NULL=0,NULL=NULL;
+-----+-----+--------+-----------+
| 1=0 | 1=1 | NULL=0 | NULL=NULL |
+-----+-----+--------+-----------+
|   0 |   1 |   NULL |      NULL |
+-----+-----+--------+-----------+

mysql> select 'ab'='ab','a'<'d',1<=1;
+-----------+---------+------+
| 'ab'='ab' | 'a'<'d' | 1<=1 |
+-----------+---------+------+
|         1 |       1 |    1 |
+-----------+---------+------+
# 字符串比较不区分大小写
mysql> select 'ab'='AB';
+-----------+
| 'ab'='AB' |
+-----------+
|         1 |
+-----------+

```

(3)**BETWEEN**运算符的使用格式为 ``a BETWEEN min and max``，包括min和max边界值；当操作数a、min、max类型相同时，此表达式等价于``a>=min and a<=max)``，当操作数类型不同时，比较时会遵循类型转化原则进行转化后，在进行比较运算。

(4)**IN**运算符的使用格式为``a IN(value1,value2,...)``

(5)**IS NULL和IS NOT NULL**判断值是否为NULL或者不为NULL

(6)**LIKE**运算符常用模糊查询，**%代表0个或多个字符，下划线"_"代表一个字符**，使用格式为“a LIKE %xxx%”

(7)**REGEXP**正则匹配运算符，使用格式“str REGEXP str_pat”,当str字符串中含有str_pat相匹配的字符串时，返回1，否则返回0.

```mysql

mysql> select 10 between 10 and 20,9 between 10 and 20;
+----------------------+---------------------+
| 10 between 10 and 20 | 9 between 10 and 20 |
+----------------------+---------------------+
|                    1 |                   0 |
+----------------------+---------------------+

mysql> select 0 is null,0 is not null,null is null,null is not null;
+-----------+---------------+--------------+------------------+
| 0 is null | 0 is not null | null is null | null is not null |
+-----------+---------------+--------------+------------------+
|         0 |             1 |            1 |                0 |
+-----------+---------------+--------------+------------------+

mysql> select 'a' in ('a','ab');
+-------------------+
| 'a' in ('a','ab') |
+-------------------+
|                 1 |
+-------------------+

mysql> select 'abc' regexp 'ab', 'aabbc' regexp 'bc';
+-------------------+---------------------+
| 'abc' regexp 'ab' | 'aabbc' regexp 'bc' |
+-------------------+---------------------+
|                 1 |                   1 |
+-------------------+---------------------+
1 row in set (0.00 sec)
```

## 4.3 逻辑运算符

​	逻辑运算符又称为布尔运算符，用来确认表达式的真和假。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192658.png)

(1) NOT NULL的返回值为NULL

(2)逻辑与运算，一个或多个操作数为0时，所得结果为0，操作数中有任何一个为NULL则返回值为NULL。

(3)逻辑或功能不再赘述，逻辑异或，操作数逻辑真假值相异为1，相同为0

```mysql
mysql> select not 0, !0, not null;
+-------+----+----------+
| not 0 | !0 | not null |
+-------+----+----------+
|     1 |  1 |     NULL |
+-------+----+----------+

mysql> select not 0, !1, not null; 
+-------+----+----------+
| not 0 | !1 | not null |
+-------+----+----------+
|     1 |  0 |     NULL |
+-------+----+----------+

mysql> select (1 and 2),(0 && 5),(1 and NULL);
+-----------+----------+--------------+
| (1 and 2) | (0 && 5) | (1 and NULL) |
+-----------+----------+--------------+
|         1 |        0 |         NULL |
+-----------+----------+--------------+

mysql> select (1 or 0),(0 || 0),(NULL or NULL);
+----------+----------+----------------+
| (1 or 0) | (0 || 0) | (NULL or NULL) |
+----------+----------+----------------+
|        1 |        0 |           NULL |
+----------+----------+----------------+

mysql> select 1 xor 0, 1 xor 1,null xor 1;
+---------+---------+------------+
| 1 xor 0 | 1 xor 1 | null xor 1 |
+---------+---------+------------+
|       1 |       0 |       NULL |
+---------+---------+------------+
```

## 4.4 位运算符

​	位运算是将给定的操作数转化为二进制后，对各个操作数每一位都进行指定的逻辑运算，得到的二进制结果转化为十进制数后就是位运算的结果。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192342.png)

```mysql
mysql> select 2&&3;
+------+
| 2&&3 |
+------+
|    1 |
+------+

mysql> select 2|3;
+-----+
| 2|3 |
+-----+
|   3 |
+-----+
# 位相异为1，相同为0
mysql> select 2^3;
+-----+
| 2^3 |
+-----+
|   1 |
+-----+
# 1的取反为什么会是这么大的数字？
# 在MySQL中，常量数字默认会以8字节来表示，8字节就是64位，常量1的二进制表示为63个0加1个1，位取反后就是63个1
#加一个0.
mysql> select ~1,~18446744073709551614;
+----------------------+-----------------------+
| ~1                   | ~18446744073709551614 |
+----------------------+-----------------------+
| 18446744073709551614 |                     1 |
+----------------------+-----------------------+
mysql> select bin(18446744073709551614);
+------------------------------------------------------------------+
| bin(18446744073709551614)                                        |
+------------------------------------------------------------------+
| 1111111111111111111111111111111111111111111111111111111111111110 |
+------------------------------------------------------------------+

# 位右移n位，相当于除以2^n
mysql> select 100>>3,100 div 8;
+--------+-----------+
| 100>>3 | 100 div 8 |
+--------+-----------+
|     12 |        12 |
+--------+-----------+

mysql> select 100<<3;
+--------+
| 100<<3 |
+--------+
|    800 |
+--------+
```

# 5. 常用函数

​	MySQL常用函数包括字符串函数、 数值函数、日期和时间函数、流程函数等。也许在Java开发中并不需要全都掌握，但是了解总比是个愣头青强吧！况且如果结合业务场景选择合适的函数来简化sql的查询处理，往往能事半功倍。

MySQL中的函数格式基本都是函数名加括号加形参组成，不只是MySQL，其他语言的函数名称构成也差不多，所以说我们在使用MySQL时，函数名括号不能省略。MySQL中的字符串函数，不用刻意去记忆，比如求子串，字符串替换等，函数的第一个操作数必定是字符串本身，其他参数就结合函数的功能去填写。

## 5.1 字符串函数

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192338.png)

(1)CONCAT(s1,s2,...sn)函数：把传入的参数连接成一个字符串。任何字符串与NULL连接的结果都将是NULL。

```mysql
mysql> select concat("hello"," world!");
+---------------------------+
| concat("hello"," world!") |
+---------------------------+
| hello world!              |
+---------------------------+

mysql> select insert("hello world!",7,6,"mysql!");
+-------------------------------------+
| insert("hello world!",7,6,"mysql!") |
+-------------------------------------+
| hello mysql!                        |
+-------------------------------------+

mysql> select upper("hello mysql!");
+-----------------------+
| upper("hello mysql!") |
+-----------------------+
| HELLO MYSQL!          |
+-----------------------+

mysql> select left("hello mysql!",5);
+------------------------+
| left("hello mysql!",5) |
+------------------------+
| hello                  |
+------------------------+

mysql> select lpad(" mysql!",12,"hello");  
+----------------------------+
| lpad(" mysql!",12,"hello") |
+----------------------------+
| hello mysql!               |
+----------------------------+

mysql> select ltrim("  mysql");
+------------------+
| ltrim("  mysql") |
+------------------+
| mysql            |
+------------------+

mysql> select replace("hello world!","world","mysql");
+-----------------------------------------+
| replace("hello world!","world","mysql") |
+-----------------------------------------+
| hello mysql!                            |
+-----------------------------------------+
# 字符串的比较是按照ASCII码值进行比较的，如果第一个字符就能确定大小，则不会在往后比较
# strcmp函数：比较字符串s1和s2的ASCII码值的大小。如果s1比s2小，那么返回-1；如果s1与s2相等，那么返回0；如果s1比s2大，那么返回1
mysql> select strcmp('a','b'), strcmp('A','A'),strcmp('C','b');
+-----------------+-----------------+-----------------+
| strcmp('a','b') | strcmp('A','A') | strcmp('C','b') |
+-----------------+-----------------+-----------------+
|              -1 |               0 |               1 |
+-----------------+-----------------+-----------------+
mysql> select '18'<'2';
+----------+
| '18'<'2' |
+----------+
|        1 |
+----------+
mysql> select 'abc' > '123';
+---------------+
| 'abc' > '123' |
+---------------+
|             1 |
+---------------+

mysql> select substring("hello mysql!",7,5);
+-------------------------------+
| substring("hello mysql!",7,5) |
+-------------------------------+
| mysql                         |
+-------------------------------+
```

## 5.2 数值函数

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192334.png)

```mysql
mysql> select abs(-0.1),abs(0.1);
+-----------+----------+
| abs(-0.1) | abs(0.1) |
+-----------+----------+
|       0.1 |      0.1 |
+-----------+----------+

mysql> select ceil(-0.8),ceil(0.8);
+------------+-----------+
| ceil(-0.8) | ceil(0.8) |
+------------+-----------+
|          0 |         1 |
+------------+-----------+

mysql> select floor(-0.8),floor(0.8);        
+-------------+------------+
| floor(-0.8) | floor(0.8) |
+-------------+------------+
|          -1 |          0 |
+-------------+------------+
# 模数和被模数任何一个为NULL结果都为NULL
mysql> select mod(15,10),mod(1,11),mod(NULL,10); 
+------------+-----------+--------------+
| mod(15,10) | mod(1,11) | mod(NULL,10) |
+------------+-----------+--------------+
|          5 |         1 |         NULL |
+------------+-----------+--------------+
# rand函数返回0-1内的随机值，边界值取不到
mysql> select RAND();
+--------------------+
| RAND()             |
+--------------------+
| 0.5434079063529222 |
+--------------------+
# 产生0-100以内的随机整数
mysql> select ceil(100*rand());
+------------------+
| ceil(100*rand()) |
+------------------+
|               52 |
+------------------+
1 row in set (0.00 sec)

#round返回参数x的四舍五入的有y位小数的值，truncate不会四舍五入，仅仅截断y位小数
mysql> select round(5.125,2),truncate(5.125,2);
+----------------+-------------------+
| round(5.125,2) | truncate(5.125,2) |
+----------------+-------------------+
|           5.13 |              5.12 |
+----------------+-------------------+
```

## 5.3 日期和时间函数

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192330.png)

```mysql
#CURDATE():返回当前日期，只包含年月日
mysql> select CURDATE();
+------------+
| CURDATE()  |
+------------+
| 2020-07-20 |
+------------+
#CUETIME():返回当前时间，只包含时分秒
mysql> select CURTIME();
+-----------+
| CURTIME() |
+-----------+
| 15:16:52  |
+-----------+
#NOW():返回当前的时间，年月日时分秒
mysql> select NOW();
+---------------------+
| NOW()               |
+---------------------+
| 2020-07-20 15:17:03 |
+---------------------+
#UNIX_TIMESTAMP(date):返回日期date的UNIX时间戳 可通过该函数进行日期类型的比较
#FROM_UNIXTIME(unixtime):返回UNIXTIME时间戳的日期值，和UNIXTIMESTAMP(date)互为逆操作
mysql> select UNIX_TIMESTAMP(now());
+-----------------------+
| UNIX_TIMESTAMP(now()) |
+-----------------------+
|            1595229496 |
+-----------------------+

mysql> select FROM_UNIXTIME(1595229496);
+---------------------------+
| FROM_UNIXTIME(1595229496) |
+---------------------------+
| 2020-07-20 15:18:16       |
+---------------------------+
#WEEK(date)和YEAR(date)函数：前者返回所给的日期是一年中的第几周，后者返回所给的日期是哪一年
mysql> select WEEK(CURDATE()),YEAR(CURDATE());
+-----------------+-----------------+
| WEEK(CURDATE()) | YEAR(CURDATE()) |
+-----------------+-----------------+
|              29 |            2020 |
+-----------------+-----------------+
#HOUR(time)和MINUTE(time)函数：前者返回所给时间的小时，后者返回所给时间的分钟。
mysql> select HOUR(CURTIME()),MINUTE(CURTIME());
+-----------------+-------------------+
| HOUR(CURTIME()) | MINUTE(CURTIME()) |
+-----------------+-------------------+
|              15 |                27 |
+-----------------+-------------------+
#MONTHNAME(date):返回date的英文月份名称
mysql> select MONTHNAME(CURDATE());
+----------------------+
| MONTHNAME(CURDATE()) |
+----------------------+
| July                 |
+----------------------+
#【了解】
#DATE_FORMAT(date,fmt):按字符串fmt格式化日期值，MySQL中的日期时间格式如表5-4
#DATE_ADD(date,INTERVAL expr type)：返回与所给日期date相差INTERVAL时间段的日期。INTERVAL是间隔类型关键字，expr是一个表达式，type表示间隔类型，type间隔类型如表5-5
#DATEDIFF(date1,date2):用来计算两个日期之间相差的天数
mysql> select DATE_FORMAT(NOW(),"%Y %M %D"); 
+-------------------------------+
| DATE_FORMAT(NOW(),"%Y %M %D") |
+-------------------------------+
| 2020 July 20th                |
+-------------------------------+

mysql>  select now() current,date_add(now(),INTERVAL 31 day) after31days,date_add(now(),INTERVAL '1_2' year_month) after_oneyear_twomonth;
+---------------------+---------------------+------------------------+
| current             | after31days         | after_oneyear_twomonth |
+---------------------+---------------------+------------------------+
| 2020-07-20 15:41:56 | 2020-08-20 15:41:56 | 2021-09-20 15:41:56    |
+---------------------+---------------------+------------------------+
1 row in set (0.00 sec)
# 可以用负数让它返回之前的某个日期时间
mysql>  select now() current,date_add(now(),INTERVAL -31 day) before31days,date_add(now(),INTERVAL '-1_-2' year_month) before_oneyear_twomonth;
+---------------------+---------------------+-------------------------+
| current             | before31days        | before_oneyear_twomonth |
+---------------------+---------------------+-------------------------+
| 2020-07-20 15:42:04 | 2020-06-19 15:42:04 | 2019-05-20 15:42:04     |
+---------------------+---------------------+-------------------------+
1 row in set (0.00 sec)
# 距离新年还有多少天 希望再次看到的话，努力没有白费！
mysql> select DATEDIFF('2021-01-01',CURDATE());  
+----------------------------------+
| DATEDIFF('2021-01-01',CURDATE()) |
+----------------------------------+
|                              165 |
+----------------------------------+
```

> 什么是时间戳？
>
> 时间戳是指格林威治时间1970年01月01日00时00分00秒(北京du时间1970年01月01日08时00分00秒)起至现在的总秒数。通俗的讲， 时间戳是一份能够表示一份数据在一个特定时间点已经存在的完整的可验证的数据。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192324.png)

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192320.png)

## 5.4 流程函数

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192320.png)

下面以模拟对职员薪水进行分类为例：

```mysql
mysql> create table salary(userid int,salary decimal(9,2));
mysql> insert into salary values(1,100),(2,2000),(3,3000),(4,4000),(5,5000),(1,NULL);
mysql> select * from salary;
+--------+---------+
| userid | salary  |
+--------+---------+
|      1 | 1000.00 |
|      2 | 2000.00 |
|      3 | 3000.00 |
|      4 | 4000.00 |
|      5 | 5000.00 |
|      1 |    NULL |
+--------+---------+
# 月薪在2000元以上的职员用“high”表示
mysql> select if(salary>2000,'high','low') from salary;
+------------------------------+
| if(salary>2000,'high','low') |
+------------------------------+
| low                          |
| low                          |
| high                         |
| high                         |
| high                         |
| low                          |
+------------------------------+
6 rows in set (0.00 sec)
# NULL值不能参与数值运算，下面将NULL值替换
mysql> select ifnull(salary,0) from salary;
+------------------+
| ifnull(salary,0) |
+------------------+
|          1000.00 |
|          2000.00 |
|          3000.00 |
|          4000.00 |
|          5000.00 |
|             0.00 |
+------------------+
6 rows in set (0.00 sec)

mysql> select case when salary<=2000 then 'low' else 'high' end from salary;
+---------------------------------------------------+
| case when salary<=2000 then 'low' else 'high' end |
+---------------------------------------------------+
| low                                               |
| low                                               |
| high                                              |
| high                                              |
| high                                              |
| high                                              |
+---------------------------------------------------+
6 rows in set (0.00 sec)
# 多个when...then联合使用
mysql> select case salary when 1000 then 'low' when 2000 then 'mid' else 'high' end from salary;
+-----------------------------------------------------------------------+
| case salary when 1000 then 'low' when 2000 then 'mid' else 'high' end |
+-----------------------------------------------------------------------+
| low                                                                   |
| mid                                                                   |
| high                                                                  |
| high                                                                  |
| high                                                                  |
| high                                                                  |
+-----------------------------------------------------------------------+
```

## 5.5 其他常用函数

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192316.png)

示例：

```mysql
# 查看当前操作数据库
mysql> select database();
+------------+
| database() |
+------------+
| test       |
+------------+
# 查看mysql版本
mysql> select version();
+-----------+
| version() |
+-----------+
| 5.7.26    |
+-----------+
# 查看当前用户
mysql> select user();
+----------------+
| user()         |
+----------------+
| root@localhost |
+----------------+
#INET_ATON(IP):返回IP地址的网络字节序表示
mysql> select inet_aton('192.168.8.1');
+--------------------------+
| inet_aton('192.168.8.1') |
+--------------------------+
|               3232237569 |
+--------------------------+
#INET_NTOA(num):返回网络字节序代表的IP地址
mysql> select inet_ntoa(3232237569);
+-----------------------+
| inet_ntoa(3232237569) |
+-----------------------+
| 192.168.8.1           |
+-----------------------+
```
INET_ATON(IP)和INET_NTOA(num)函数的主要用途是将字符串的IP地址转换为数字表示的网络字节序，这样可以很方便地进行**IP或者网段的比较**。比如在下面的表t中，要想知道在192.168.1.3-192.168.1.20 一共有多少个IP地址：
```mysql
mysql> select * from t;
+--------------+
| ip           |
+--------------+
| 192.168.1.1  |
| 192.168.1.3  |
| 192.168.1.6  |
| 192.168.1.10 |
| 192.168.1.20 |
| 192.168.1.30 |
+--------------+

#正常思维来想的话，肯定是字符串比较，但是不出乎意料，结果为空。字符串比较是一个一个字符比较的，当对应字符相同时候，比较下一个，知道遇到能区分大小的字符，就停止比较，后面的字符也将忽略。因为字符"3"比“2”大，而不能用我们日常的思维3<20，所以比“3”大比“2”小的结果为空。
mysql> select * from t where ip>='192.168.1.3' and ip<='192.168.1.20';

# 要想实现上面的功能，就可用INET_ATON函数将IP转化为字节序后在比较，如下所示：
mysql> select * from t where inet_aton(ip)>=inet_aton('192.168.1.3')&&inet_aton(ip)<=inet_aton('192.168.1.20');
+--------------+
| ip           |
+--------------+
| 192.168.1.3  |
| 192.168.1.6  |
| 192.168.1.10 |
| 192.168.1.20 |
+--------------+
```

# 6. 图形化工具的使用

原书中介绍的工具都比较老了，这一部分自行阅读吧！

# 第二部分 开发篇

# 7. 表类型(存储引擎)的选择

MySQL中存储引擎针的概念，**针对不同的存储需求选择最优的存储引擎**。提高数据的存取读取效率。

## 7.1 MySQL存储引擎概述

MySQL支持的存储引擎包括MyISAM、InnoDB、MEMORY、MERGE、BDB等(前两种常用，后两种了解即可)。**其中InnoDB和BDB提事务安全表，其他存储引擎都是非事务安全表**。

MySQLv5.1之后默认的存储引擎为InnoDB，之前是MyISAM。

1· 查看mysql支持哪些引擎：``show engines \G;``

engine:引擎名称;support:显示是否支持，default显示当前默认存储引擎;comment:简单描述;transactions:是否支持事务

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192312.png)

2· 修改默认存储引擎： ``set default_storage_engine=innodb;``

修改后只是本次会话有效，其他会话无效，可通过``global``选项设置全局会话有效，无论本次会话还是全局会话都有效，但是重启后都会失效。

3· 创建新表的时候，通过增加``engine``关键字则设置新表的存储引擎，也可以使用``alter table tb_name engine=innodb``修改表的存储引擎。

```mysql
mysql> create table t (
    -> id int(10) not null auto_increment,
    -> primary key(id)
    -> )ENGINE=MyISAM DEFAULT CHARSET=UTF8;
Query OK, 0 rows affected (0.00 sec)

mysql> show create table t;
+-------+------------------------------+
| Table | Create Table                                                                                                         |
+-------+------------------------------+
| t     | CREATE TABLE `t` (
  `id` int(10) NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM DEFAULT CHARSET=utf8 |
+-------+------------------------------+


mysql> alter table t engine=InnoDB;
mysql> show create table t;
+-------+------------------------------+
| Table | Create Table                                                                                                         |
+-------+------------------------------+
| t     | CREATE TABLE `t` (
  `id` int(10) NOT NULL AUTO_INCREMENT,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 |
+-------+------------------------------+
```

## 7.2 各种存储引擎的特性

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192308.png)

### 7.2.1 MyISAM

​	MySQL5.1之前的默认存储引擎。**不支持事务、表级锁、不支持外键，优点是访问速度快**。**对事务完整性没有要求或者以SELECT、INSERT为主的应用可以使用这个引擎来创建表**。

1· 每个MyISAM在磁盘上存储成3个文件，其文件名和表名相同，但扩展名分别是：

* .frm（存储表定义）
* .MYD（MYData，存储数据）
* .MYI (MYIndex，存储索引)

数据文件和索引文件可以放置在不同的目录，**平均分布IO，获得更快的速度**。

==2有误==

<del>2· MyISAM的表支持3种不同的存储格式，分别是</del>

* <del>静态（固定长度）表</del>

  默认的存储格式，表中字段都是固定长度，如果列不满足定义的列宽则空格填充。

  优点：访问速度快

  缺点：占用空间

* <del>动态表</del>

  存储的字段变长

  优点：占用空间少。

  缺点：容易产生碎片。

* <del>压缩表</del>

mysql并没有什么静态、动态、压缩表，但是有静态动态压缩行，静态和动态是针对具体行中定义的数据类型，当保存具体的数据时所呈现的结果是什么样的。详情参考

https://dev.mysql.com/doc/refman/5.7/en/innodb-row-format.html

**varchar类型的对末尾空格不做处理，char类型的字段会去掉末尾空格**

```mysql
# varchar类型的对末尾空格不做处理，char类型的字段会去掉末尾空格
mysql> insert into t values(1,'abc'),(3,'abc  '),(4,'   abc');
mysql> select name,length(name) from t;
+--------+--------------+
| name   | length(name) |
+--------+--------------+
| abc    |            3 |
| abc    |            5 |
|    abc |            6 |
+--------+--------------+
3 rows in set (0.00 sec)

mysql> show create table t;
+-------+------+
| Table | Create Table                                                                   
+-------+---+
| t     | CREATE TABLE `t` (
  `id` int(10) NOT NULL AUTO_INCREMENT,
  `name` varchar(10) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=MyISAM AUTO_INCREMENT=5 DEFAULT CHARSET=utf8 |
+-------+-------+
1 row in set (0.00 sec)

mysql> alter table t modify name char(10);      

mysql> select name,length(name) from t;
+--------+--------------+
| name   | length(name) |
+--------+--------------+
| abc    |            3 |
| abc    |            3 |
|    abc |            6 |
+--------+--------------+
#插入记录后面的空格都被去掉了，前面的空格保留。
```

### 7.2.2 InnoDB

​	MySQL5.1之后默认的存储引擎，InnoDB 存储引擎提供了具有**提交、回滚和崩溃恢复能力的事务安全，支持外键**。但是对比 MyISAM的存储引擎，InnoDB **写的处理效率差一些**并且会占用更多的磁盘空间以保留数据和索引。

应用场景：如果应用对事务的**完整性**有比较高大要求，要求在并发条件下要求数据的**一致性**，，数据操作除了插入和查询以外，还包括很多的更新、删除操作，那么 InnoDB 存储引擎应该是比较合适的选择。

**1. 自动增长列**

* InnoDB 表的自动增长列可以手工插入，但是插入的值如果是空或者 0，则实际插入的将是自动增长后的值。
* 对于 InnoDB 表，**自动增长列必须是索引**。如果是组合索引，也必须是组合索引的第一列，但是对于 MyISAM 表，自动增长列可以是组合索引的其他列，这样插入记录后，自动增长列是按照组合索引的前面几列进行排序后递增的。
* 可以通过**alter table tb_name auto_increment = n;**设置自动增长列的初始值。只适用于本次回话（重启失效）。可以使用**LAST_INSERT_ID()**查询当前线程最后插入记录使用的值。

示例：

```mysql
mysql> create table autoincre_demo (
    -> i smallint not null auto_increment,
    -> name varchar(10),primary key(i));

mysql> insert into autoincre_demo values(1,'1'),(0,'2'),(null,'3');
mysql> select * from autoincre_demo;
+---+------+
| i | name |
+---+------+
| 1 | 1    |
| 2 | 2    |
| 3 | 3    |
+---+------+

```

**2. 外键约束**

**MySQL 支持外键的存储引擎只有 InnoDB，在创建外键的时候，要求父表必须有对应的索引，子表在创建外键的时候也会自动创建对应的索引。**

 外键的使用需要满足下列的条件：

1. 两张表必须都是InnoDB表，并且它们没有临时表。

2. 建立外键关系的对应列必须具有相似的InnoDB内部数据类型。

3. 建立外键关系的对应列必须建立了索引。

(1)在创建索引的时候，可以指定在删除、更新父表时，对子表进行的相应操作，包 RESTRICT、CASCADE、SET NULL 和 NO ACTION。**其中 RESTRICT 和 NO ACTION 相同，是指限制在子表有关联记录的情况下父表不能更新**；**CASCADE 表示父表在更新或者删除时，更新或者删除子表对应记录**；SET NULL 则表示父表在更新或者删除的时候，子表的对应字段被 SET NULL。选择后两种方式的时候要谨慎，可能会因为错误的操作导致数据的丢失。 

1. CASCADE: 父表中删除或更新对应的行，同时自动的删除或更新自表中匹配的行。ON DELETE CANSCADE和ON UPDATE CANSCADE都被InnoDB所支持。

2. SET NULL: 父表中删除或更新对应的行，同时将子表中的外键列设为空。注意，这些在外键列没有被设为NOT NULL时才有效。ON DELETE SET NULL和ON UPDATE SET SET NULL都被InnoDB所支持。

3. NO ACTION: InnoDB拒绝删除或者更新父表。

4. RESTRICT: 拒绝删除或者更新父表。指定RESTRICT（或者NO ACTION）和忽略ON DELETE或者ON UPDATE选项的效果是一样的。

 外键约束使用最多的两种情况无外乎：

 1）**父表更新时子表也更新，父表删除时如果子表有匹配的项，删除失败**；

```mysql
ON UPDATE CASCADE ON DELETE RESTRICT
```

 2）**父表更新时子表也更新，父表删除时子表匹配的项也删除**。

```mysql
ON UPDATE CASCADE ON DELETE CASCADE
```

(2)当某个表被其他表创建了外键参照，那么该表的对应索引或者主键禁止被删除。 
在导入多个表的数据时，如果需要忽略表之前的导入顺序，可以暂时关闭外键的检查；
同样，在执行 LOAD DATA 和 ALTER TABLE 操作的时候，可以通过暂时关闭外键约束来加快处理的速度，关闭的命令是``SET FOREIGN_KEY_CHECKS = 0;``，执行完成之后，通过执行``SET FOREIGN_KEY_CHECKS = 1;``语句改回原状态。 

例如对下面创建的两个表，子表的外键指定是 ON DELETE RESTRICT ON UPDATE CACADE

```mysql
mysql> CREATE TABLE country ( 
    ->   country_id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT, 
    ->   country VARCHAR(50) NOT NULL, 
    ->   last_update TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP, 
    ->   PRIMARY KEY  (country_id) 
    -> )ENGINE=InnoDB DEFAULT CHARSET=utf8;
Query OK, 0 rows affected (0.02 sec)

mysql> CREATE TABLE city ( 
    ->   city_id SMALLINT UNSIGNED NOT NULL AUTO_INCREMENT, 
    ->   city VARCHAR(50) NOT NULL, 
    ->   country_id SMALLINT UNSIGNED NOT NULL, 
    ->   last_update TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP, 
    ->   PRIMARY KEY  (city_id), 
    ->   KEY idx_fk_country_id (country_id), 
    ->   CONSTRAINT `fk_city_country` FOREIGN KEY (country_id) REFERENCES country (country_id) ON 
    -> DELETE RESTRICT ON UPDATE CASCADE 
    -> )ENGINE=InnoDB DEFAULT CHARSET=utf8;
Query OK, 0 rows affected (0.03 sec)

mysql> insert into country(country_id,country) values(1,'ShanDong');
Query OK, 1 row affected (0.00 sec)

mysql> select * from country;
+------------+----------+---------------------+
| country_id | country  | last_update         |
+------------+----------+---------------------+
|          1 | ShanDong | 2020-07-21 10:21:48 |
+------------+----------+---------------------+

mysql> insert into city(city_id,city,country_id) values(111,'QingDao',1);

mysql> select * from city;
+---------+---------+------------+---------------------+
| city_id | city    | country_id | last_update         |
+---------+---------+------------+---------------------+
|     111 | QingDao |          1 | 2020-07-21 10:22:53 |
+---------+---------+------------+---------------------+
# 删除主表中一条被子表关联的一条记录，报错
mysql> delete from country where country_id=1;
ERROR 1451 (23000): Cannot delete or update a parent row: a foreign key constraint fails (`test`.`city`, CONSTRAINT `fk_city_country` FOREIGN KEY (`country_id`) REFERENCES `country` (`country_id`) ON UPDATE CASCADE)
# 更新主表中的记录，子表有对应记录也会跟新
mysql> update country set country_id=1000 where country_id=1;

mysql> select * from city;
+---------+---------+------------+---------------------+
| city_id | city    | country_id | last_update         |
+---------+---------+------------+---------------------+
|     111 | QingDao |       1000 | 2020-07-21 10:22:53 |
+---------+---------+------------+---------------------+

mysql> select * from country;
+------------+----------+---------------------+
| country_id | country  | last_update         |
+------------+----------+---------------------+
|       1000 | ShanDong | 2020-07-21 10:23:48 |
+------------+----------+---------------------+

#上面已经演示了，当删除一条被其他表的外键关联字段时会报错，我们可以通过将外键约束禁止掉，就可以删除了
#默认外键约束开启
mysql> show variables like '%FOREIGN_KEY_CHECKS%';       
+--------------------+-------+
| Variable_name      | Value |
+--------------------+-------+
| foreign_key_checks | ON    |
+--------------------+-------+

mysql> set foreign_key_checks=off;
mysql> show variables like '%FOREIGN_KEY_CHECKS%';
+--------------------+-------+
| Variable_name      | Value |
+--------------------+-------+
| foreign_key_checks | OFF   |
+--------------------+-------+
# 成功删除
mysql> delete from country where country_id=1000;

mysql> select * from country;
Empty set (0.00 sec)
```

**3. 存储方式**

innoDB存储数据和索引有**共享表空间存储和独占表空间存储**两种方式，通过参数innodb_file_per_table控制，0表示共享空间，也是默认的，1表示独占空间。两种方式的表结构（描述）都保存在.frm文件中。

共享表空间：

每一个数据库的所有表的数据、索引都保存在一个文件中，默认在data目录下，名为ibdata1，大小为10M的文件，可以通过参数innodn_data_file_path=/data/ibdata1:2000M来指定存储路径。

优点：

（1）可以将表空间分为多个文件放在不同的磁盘上，**分布IO**，提高性能。采用共享空间存储，存储空间的大小不受文件系统下文件大小的限制了，而取决于自身的限制，官方文档显示，表空间的最大限制是64TB。

（2）表数据和表结构放在一起，方便管理

缺点：由于所有的数据和索引都是在一个文件中混合存储，这样的话对一个表做了大量的删除操作后，表空间中会产生大量的空隙

独占表空间存储：

每一张表都有自己独立的表空间，表的结构依然在.frm文件中，还有一个后缀为.ibd的文件，保存了这张表的数据和索引。

优点：

每张表都有自己独立的表空间，可实现单表在不同数据库中移动空间可回收。drop table会自动回收；删除数据后，通过alter table emp engine=innodb也可回收不用的表空间，效率和性能会好一些。
缺点：由于每个表的数据都是以一个单独的文件来存放，所以会受到文件系统的大小限制

### 7.2.3 MEMORY

​	MEMORY 存储引擎使用**存在内存中**的内容来创建表。每个 MEMORY 表只实际对应一个磁盘文件，格式是.frm。MEMORY 类型的表**访问非常得快**，因为它的数据是放在内存中的，并且默认使用 HASH 索引，但是一旦服务关闭，表中的数据就会丢失掉。

MEMORY：将所有数据保存在 RAM 中，在需要快速定位记录和其他类似数据的环境下，可提供极快的访问。MEMORY 的缺陷是对表的大小有限制，太大的表无法 CACHE 在内存中，其次是要确保表的数据可以恢复，数据库异常终止后表中的数据是可以恢复的。MEMORY 表通常用于更新不太频繁的小表，用以快速得到访问结果。

### 7.2.4 MERGE

MERGE 存储引擎是一组 MyISAM 表的组合，这些 MyISAM 表必须结构完全相同，MERGE表本身并没有数据，对 MERGE 类型的表可以进行查询、更新、删除的操作，这些操作实际上是对内部的实际的 MyISAM 表进行的。

MERGE：用于将一系列等同的 MyISAM 表以逻辑方式组合在一起，并作为一个对象引用它们。MERGE 表的优点在于可以突破对单个 MyISAM 表大小的限制，并且通过将不同的表分布在多个磁盘上，可以有效地改善MERGE表的访问效率。这对于诸如数据仓储等VLDB环境十分适合。

## 7.3 status和variables

**show status**:  查看系统运行的实时状态，便于dba查看mysql当前运行的状态，做出相应优化，动态的，不可人为进行修改，只能系统自动update。

**show variables** : 查看系统参数，系统默认设置或者dba调整优化后的参数，静态的。可以通过set或者修改my.cnf配置文件修改。

首先可以通过下属两个命令来查看mysql的相应的系统参数

```mysql
# 支持模糊查询
show status like '%abc%';
show variables like '%abc%';
```

参考:[mysql之status和variables区别及用法详解](https://blog.csdn.net/andyzhaojianhui/article/details/50052117)

系统变量又分global和session，特别是当用show variables like 'character_set%';不选中数据库和选中数据库时是不一样的

# 8. 选择合适的数据类型

## 8.1 CHAR与VARCHAR

​	CHAR 和 VARCHAR 类型类似，都用来存储字符串，但它们保存和检索的方式不同。CHAR 属于固定长度的字符类型，而 VARCHAR 属于可变长度的字符类型。当char定义一定宽度的格式时，数据末尾的空格会被处理掉。char是固定长度的，处理速度比varchar块，但缺点是浪费空间。

**char和varchar如何选择？**

在 MySQL 中，不同的存储引擎对 CHAR 和 VARCHAR 的使用原则有所不同，这里简单概括如下。 

* MyISAM 存储引擎：**建议使用固定长度的数据列代替可变长度的数据列。** 
*  MEMORY 存储引擎：目前都使用固定长度的数据行存储，因此无论使用 CHAR 或VARCHAR 列都没有关系。两者都是作为 CHAR  类型处理。 
*  InnoDB 存储引擎：**建议使用 VARCHAR 类型**。对于 InnoDB 数据表，**内部的行存储格式没有区分固定长度和可变长度列（所有数据行都使用指向数据列值的头指针）**，因此在本质上，使用固定长度的 CHAR 列不一定比使用可变长度 VARCHAR 列性能要好。因而，主要的性能因素是数据行使用的存储总量。**由于 CHAR 平均占用的空间多于 VARCHAR，因此使用 VARCHAR 来最小化需要处理的数据行的存储总量和磁盘 I/O 是比较好的。**

## 8.2 TEXT与BLOB

​	char或者varchar适用于保存少量字符串，如果保存较大文本是，通常会选择使用TEXT和BLOB。

**BLOB：**用来保存二进制数据，比如照片。

**TEXT：**只能保存字符数据，比如一篇文章和日记。

TEXT 和 BLOB 中又分别包括TEXT、MEDIUMTEXT、LONGTEXT 和 BLOB、MEDIUMBLOB、LONGBLOB3 种不同的类型。

(1)BLOB 和 TEXT 值会引起一些性能问题，特别是在执行了大量的删除操作时。 删除操作会在数据表中留下很大的**“空洞”**，以后填入这些“空洞”的记录在插入的性能上会有影响。为了提高性能，建议定期使用 **OPTIMIZE TABLE** 功能对这类表进行碎片整理，避免因为“空洞”导致性能问题。

(2)可以使用**合成的（Synthetic）索引**来**提高大文本字段（BLOB 或 TEXT）的查询性能。**

简单来说，合成索引就是根据大文本字段的内容建立一个散列值，并把这个值存储在单独的数据列中，接下来就可以通过检索散列值找到数据行了。但是，要注意这种技术只能用于精确匹配的查询（散列值对于类似<或>=等范围搜索操作符是没有用处的）。

```mysql
mysql>  create table t (id varchar(100),context  blob,hash_value varchar(40)); 
Query OK, 0 rows affected (0.02 sec)

mysql> insert into t values(1,repeat('beijing',2),md5(context));
Query OK, 1 row affected (0.01 sec)

mysql>  insert into t values(2,repeat('beijing',2),md5(context));
Query OK, 1 row affected (0.01 sec)

mysql> insert into t values(3,repeat('beijing 2008',2),md5(context));
Query OK, 1 row affected (0.00 sec)

mysql>  select * from t;
+------+--------------------------+----------------------------------+
| id   | context                  | hash_value                       |
+------+--------------------------+----------------------------------+
| 1    | beijingbeijing           | 09746eef633dbbccb7997dfd795cff17 |
| 2    | beijingbeijing           | 09746eef633dbbccb7997dfd795cff17 |
| 3    | beijing 2008beijing 2008 | 1c0ddb82cca9ed63e1cacbddd3f74082 |
+------+--------------------------+----------------------------------+
3 rows in set (0.00 sec)

mysql> select * from t where hash_value=md5(repeat('beijing 2008',2));
+------+--------------------------+----------------------------------+
| id   | context                  | hash_value                       |
+------+--------------------------+----------------------------------+
| 3    | beijing 2008beijing 2008 | 1c0ddb82cca9ed63e1cacbddd3f74082 |
+------+--------------------------+----------------------------------+
```

(3)对 BLOB 或者 CLOB 字段进行模糊查询，MySQL 提供了**前缀索引**，也就是只为字段的前 n 列创建索引。

```

mysql> create index idx_blob on t(context(100));
Query OK, 0 rows affected (0.02 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc select * from t where context like 'beijing%' \G;
*************************** 1. row ***************************
           id: 1
  select_type: SIMPLE
        table: t
   partitions: NULL
         type: ALL
possible_keys: idx_blob
          key: NULL
      key_len: NULL
          ref: NULL
         rows: 3
     filtered: 100.00
        Extra: Using where
1 row in set, 1 warning (0.00 sec)
# 请注意，这里的查询条件中，“%”不能放在最前面，否则索引将不会被使用。
```

(4)在不必要的时候避免检索大型的 BLOB 或 TEXT 值。

(5)把 BLOB 或 TEXT 列分离到单独的表中。

## 8.3 浮点数与定点数

浮点数一般用于表示含有小数部分的数值。插入数据超出实际精度，则插入值会被四舍五入到实际定义的精度值，然后插入，四舍五入的过程不会报错。在 MySQL 中 float、double（或 real）用来表示浮点数。

定点数实际上是以字符串形式存放的，定点数可以更加精确的保存数据。如果实际插入的数值精度大于实际定义的精度，则 MySQL 会进行警告（默认的 SQLMode 下），但是数据按照实际精度四舍五入后插入；如果 SQLMode 是在 TRADITIONAL传统模式下，则系统会直接报错，导致数据无法插入。在 MySQL 中,decimal（或 hnumberic）用来表示定点数。

注意：在今后关于浮点数和定点数的应用中，用户要考虑到以下几个原则： 

* 浮点数存在误差问题； 
*  对货币等对精度敏感的数据，应该用定点数表示或存储； 
*   在编程中，如果用到浮点数，要特别注意误差问题，**并尽量避免做浮点数比较**； 
*  要注意浮点数中一些特殊值的处理。

## 8.4 日期类型选择

选择日期类型的原则：

* 如果只需要记录年份，只需要用一个字节的``YEAR``类型完全可以满足，而不需要四个字节的``DATE``类型。
* 如果要记录年月日时分秒，并且记录年份比较久远，那么最好使用``DATETIME``。
* 如果要记录的日期要让不同时区的用户使用，那么最好使用``TIMESTAMP``。

> 延展阅读

**mysql的严格模式和宽松模式**

mysql支持的sql_mode模式：ANSI、TRADITIONAL、STRICT_ALL_TABLES和STRICT_TRANS_TABLES。 

**ANSI模式**：宽松模式，对插入数据进行校验，如果不符合定义类型或长度，对数据类型调整或截断保存，报warning警告。

**TRADITIONAL模式**：严格模式，当向mysql数据库插入数据时，进行数据的严格校验，保证错误数据不能插入，报error错误。用于事务时，会进行事务的回滚。

**STRICT_TRANS_TABLES模式**：严格模式，进行数据的严格校验，错误数据不能插入，报error错误。只对支持事务的表有效。

**STRICT_ALL_TABLES模式**：严格模式，进行数据的严格校验，错误数据不能插入，报error错误。对所有表都有效。

```mysql
# 查看当前模式
select @@sql_mode;
show variables like '%mode%';
# 更改模式值:(1)命令行 (2)配置文件 更多详情见官网
# 有时候当像数据库插入一个date类型为空或者不允许插入的字符的时候，可以通过设置sql_mode来允许操作
# 清空模式值[局部]
set [global | session] sql_mode = "";
```

# 9. 字符集

## 9.1. MySQL支持的字符集

MySQL 服务器可以支持多种字符集，在同一台服务器、同一个数据库、甚至同一个表的不同字段都可以指定使用不同的字符集，相比 Oracle 等其他数据库管理系统，在同一个数据库只能使用相同的字符集，MySQL 明显存在更大的灵活性。

(1)查看所有可用的字符集命令：``show character set;``

```mysql
mysql> show character set;
+----------+---------------------------------+---------------------+--------+
| Charset  | Description                     | Default collation   | Maxlen |
+----------+---------------------------------+---------------------+--------+
| big5     | Big5 Traditional Chinese        | big5_chinese_ci     |      2 |
....
#Charset:字符集名称 Description:描述 Default collation:默认校对规则 Maxlen:最大长度
```

(2)MySQL 的字符集包括**字符集（CHARACTER）和校对规则（COLLATION）两个概念**。**字符集是用来定义 MySQL 存储字符串的方式，校对规则则是定义了字符串的比较方式，排列规则**。字符集和校对规则是一对多的关系。

校对格则命名约定：以相关的字符集名开始，并以``_ci``(大小写不敏感)、``_cs``(大小写敏感)、``_bin``(基于字符编码的值比较)。

> ci是case insensitive的缩写，cs是case sensitive的缩写

```mysql
# show collation like '字符名';查看字符集的校对规则
mysql> show collation like 'gbk%';
+----------------+---------+----+---------+----------+---------+
| Collation      | Charset | Id | Default | Compiled | Sortlen |
+----------------+---------+----+---------+----------+---------+
| gbk_chinese_ci | gbk     | 28 | Yes     | Yes      |       1 |
| gbk_bin        | gbk     | 87 |         | Yes      |       1 |
+----------------+---------+----+---------+----------+---------+
2 rows in set (0.00 sec)
```

## 9.2 MySQL字符集的设置

MySQL字符集和校对规则有4个级别的默认设置：**服务器级、数据库级、表级和字段级。**

### 9.2.1 服务器字符集和校对规则

服务器字符集和校对，在MySQL服务启动的时候确定。可以在my.cnf中设置，或者启动MySQL服务的时候指定。

```mysql
# my.cnf添加
[mysqld]
character-set-server=utf8
# 启动项中指定
mysqld -character-set-server=utf8
```

如果没有特别的指定服务器字符集，默认使用 latin1 作为服务器字符集。

查询当前服务器的字符集和校对规则。

```mysql
show variables like 'character_set_server';
```

### 9.2.2 数据库字符集和校对规则

数据库的字符集和校对规则在创建数据库的时候指定，也可以在创建完数据库后通过“alter database”命令进行修改。需要注意的是，如果数据库里已经存在数据，因为修改字符集并不能将已有的数据按照新的字符集进行存放，所以不能通过修改数据库的字符集直接修改数据的内容。

### 9.2.3 表级别的字符集和校对规则

```mysql
# 创建数据表的时候指定字符集和校对规则
create table tb_name (...) default character set=utf8 collate=utf8_bin;
```

### 9.2.4 列字符集和校对规则

列字符集和校对规则的定义可以在创建表时指定，或者在修改表时调整，如果在创建表的时候没有特别指定字符集和校对规则，则默认使用表的字符集和校对规则。

```mysql
# 查看表字段的字符集
show full columns from col_name;
```

**小结：**对于字符集的设置有如下规律

* 如果在指定了字符集和校对规则，使用指定的字符集和校对规则； 
*  如果指定了字符集没有指定校对规则，使用指定字符集的默认校对规则； 
* 如果没有指定字符集和校对规则，对于server来说，默认为latin1，对于服务器来说，继承server字符集，对表字段也是一样的，默认继承上层的字符集设置。

### 9.2.4 连接字符集和校对规则

上面 4 种设置方式，确定的是数据保存的字符集和校对规则，对于实际的应用访问来说，还存在客户端和服务器之间交互的字符集和校对规则的设置。 对于客户端和服务器的交互操作，MylSQL 提供了 3 个不同的参数：character_set_client、character_set_connection 和 character_set_results，分别代表客户端、连接和返回结果的字符集，通常情况下，这 3 个字符集应该是相同的，才可以确保用户写入的数据可以正确地读出，特别是对于中文字符，不同的写入字符集和返回结果字符集将导致写入的记录不能正确读出。

## 3. 字符集的修改步骤

如果在应用开始阶段没有正确的设置字符集，在运行一段时间以后才发现存在不能满足要求需要调整，又不想丢弃这段时间的数据，那么就需要进行字符集的修改。字符集的修改不能直接通过`alter database character set `或者`alter table tablename character set`命令进行，这两个命令都没有更新已有记录的字符集，而只是对新创建的表或者记录生效。已有记录的字符集调整，需要先将数据导出，经过适当的调整重新导入后才可完成。

> TODO Linux下mysqld命令找不到

# 10. 索引的设计和使用

## 10.1 索引概述

**数据库索引：**是数据库管理系统中一个排序的数据结构，以协助快速查询、更新数据表中数据。索引的实现通常使用B树及其变种B+树。

MySQL索引：索引用于**快速查找具有特定列值的行**。没有索引，MySQL必须从第一行开始，然后通读整个表以找到相关的行。

**索引的优点**

* 通过创建唯一性索引，可以保证数据库表中每一行数据的唯一性。
* **加快数据的检索速度。**
* **减少磁盘I/O次数**
* **加速表和表之间的连接。**
* **在使用分组和排序子句进行数据检索时，同样可以显著减少查询中分组和排序的时间。**
* 通过使用索引，可以在查询的过程中，使用优化隐藏器，提高系统的性能。

索引并不是万金油，增加索引也有许多不利的方面。

* 创建索引和维护索引要耗费时间，这种时间随着数据量的增加而增加。
* **索引需要占物理空间**，除了数据表占数据空间之外，每一个索引还要占一定的物理空间，如果要建立聚簇索引，那么需要的空间就会更大。
* **对表中的数据进行增删改的时候，索引也需要动态的维护，降低写操作性能，减缓表的修改速度**。

## 10.2 数据库索引的分类

可以在数据库设计器中创建五种类型的索引：**主键索引、唯一索引、普通索引、复合索引、全文索引**。其中主键索引也可以叫做聚集索引，非主键索引称为非聚集索引。

**主键索引**

数据库表经常有一列或列组合，其值唯一标识表中的每一行。该列称为表的主键。

在数据库关系图中为表定义主键将自动创建主键索引，主键索引是唯一索引的特定类型。该索引要求主键中的每个值都唯一。当在查询中使用主键索引时，它还允许对数据的快速访问。

**唯一索引** 

唯一索引是不允许其中任何两行具有相同索引值的索引，==唯一性，可以为空==。

当现有数据中存在重复的键值时，大多数数据库不允许将新创建的唯一索引与表一起保存。数据库还可能防止添加将在表中创建重复键值的新数据。例如，如果在employee表中职员的姓(name)上创建了唯一索引，则任何两个员工都不能同姓。

**普通索引**

用表中的普通列构建的索引，没有任何限制

**复合索引**

用多个列组合构建的索引，这多个列中的值**不允许有空值**，遵循最**左匹配原则**。如组合索引index(col1,col2,col3),使用col2和col3的查询是不会使用索引的。

**全文索引**

主要用于大文本信息建立索引

## 聚集索引和非聚集索引

**索引的理解：**

我对索引的的理解是这样的：

如果一个表没有加索引，数据按顺序一条一条的在磁盘上按插入顺序存储着。

如果一张表一旦加了索引，比如加了自增主键，那么表中的数据在磁盘中就不是按顺序排列的，而是变成了树状结构，也就是我们常说的平衡树，换句话说就是整个表都变成了一个索引树，也就是所谓的聚簇索引。这也是为什么一个表中只有一个主键（可以是多个字段，联合主键），因为自增主键的根就是根据一定算法把表的数据按照一定格式转换成**平衡树**存放在磁盘上的。

聚集索引：**表数据存放的物理顺序与索引顺序一致**。

非聚集索引：**表数据存放的物理顺序与索引顺序不一致**

> 相当于顺序表和链表之间的差异。
>
> 根本区别是表记录的排列顺序和与索引的排列顺序是否一致。

### 聚集索引

* 聚集索引的叶子结点就是数据结点。
* 聚簇索引的**数据表和主键索引存储在一起**。

**聚集索引中表记录的排列顺序和索引的排列顺序保持一致**，所以查询效率相当快。只要找到第一个索引记录的值，其余的连续性的记录也一定是连续存放的。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192243.jpeg)

假设执行一个`SQL`为`select * from where id=50`，查找流程就是平衡树关键字的查找

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192243.jpeg)

很多存储引擎在B+Tree的基础上进行了优化，==添加了指向相邻叶节点的指针==，形成了带有顺序访问指针的B+Tree，这样做是为了==提高区间查找的效率==，只要找到第一个值那么就可以顺序的查找后面的值。

下面更好的解释了这个概念

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192243.jpeg)

### 非聚集索引

* 非聚簇索引的叶节点仍然是索引节点，只不过有一个指针指向对应的数据块。

* 非聚簇索引的**数据表和索引表是分开存储**的。

非聚集索引这棵树中所有的节点都来自于表中二级索引（非聚集索引）字段。假如给user表的name字段加上索引 ， 那么索引就是由name字段中的值构成，在数据改变时， DBMS需要一直维护索引结构的正确性。如果给表中多个字段加上索引 ，那么就会出现**多个独立的索引结构**，每个索引（非聚集索引）互相之间不存在关联。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192243.jpeg)

**每次给字段建一个新索引，字段中的数据就会被复制一份出来，用于生成索引**。因此，给表添加索引，会增加表的体积，占用磁盘存储空间。

非聚集索引和聚集索引的区别在于，**通过聚集索引可以查到需要查找的数据，而通过非聚集索引可以查到记录对应的主键值 ，再使用主键的值通过聚集索引查找到需要的数据**（==回表查询==），如下图

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192243.jpeg)

> 聚集和非聚集索引不管以任何方式查询表，最终都会利用主键通过聚集索引来定位到数据，聚集索引（主键）是通往真实数据所在的唯一路径。

不过，有一种例外可以不使用聚集索引就能查询出所需要的数据这种非主流的方法称之为==覆盖索引==查询，也就是平时所说的**复合索引或者多字段索引查询**。



> 索引参考：
>
> * https://baijiahao.baidu.com/s?id=1645514817836645220&wfr=spider&for=pc
> * https://blog.csdn.net/mysteryhaohao/article/details/51719871
> * https://blog.csdn.net/tongdanping/article/details/79878302

## 10.3 索引的设计原则

(1) 在经常搜索的列上建立索引，可以加快搜索的速度。  搜索的索引列，不一定是所要选择的列。换句话说，**最适合索引的列是出现在 WHERE 子句中的列，或连接子句中指定的列，而不是出现在 SELECT 关键字后的选择列表中的列。**

(2) 使用唯一索引

(3) 使用段索引。如果对字符串列进行索引，应该指定一个前缀长度，只要有可能就应该这样做。例如，如果有一个 CHAR(200)列，如果在前 10 个或 20 个字符内，多数值是惟一的，那么就不要对整个列进行索引。对前10个或20个字符进行索引能够节省大量索引空间，也可能会使查询更快。较小的索引涉及的磁盘 IO 较少，较短的值比较起来更快。

(3) 利用最左前缀匹配原则

(4) 不要过度索引。不要以为索引“越多越好”，什么东西都用索引是错误的。每个额外的索引都要占用额外的磁盘空间，并降低写操作的性能。在修改表的内容时，索引必须进行更新，有时可能需要重构，因此，索引越多，所花的时间越长。

## 10.4 索引的使用

**1、建表时创建索引**

```mysql
create table tb_name (
	col_name 数据类型 [完整性约束条件],
	...,
	[unique | fulltext | spatial] index|key [索引名](字段名1[(长度)] [ASC]|[DESC]) [using 索		引方法]
);
```

参数：

* unique：唯一性索引
* fulltext：全文索引
* spatial：空间索引
* index和key：用于指定字段为索引，两者作用是一样的，二选一。
* 索引名：可选，创建索引时指定名称。
* 字段名1:指定索引对应的字段的名称，该字段必须是前面定义好的字段。

- 长度:可选。指索引的长度，必须是字符串类型才可以使用。
- ASC:可选。表示升序排列。
- DESC:可选。表示降序排列。

索引示例：

```mysql

mysql> create table t (
    -> id int comment 'ID标识',
    -> name varchar(20) comment '姓名',
    -> age int comment '年龄',
    -> addr varchar(100),
    -> primary key PK_ID (id),
    -> index index_name (name)
    -> );
```

**2、建表后创建约束**

```mysql
alter table tb_name add  [UNIQUE | FULLTEXT | SPATIAL]  INDEX | KEY  [索引名] (字段名1 [(长度)] [ASC | DESC]) [USING 索引方法];
或者
CREATE  [UNIQUE | FULLTEXT | SPATIAL]  INDEX  索引名 ON  表名(字段名) [USING 索引方法]；
```

示例：

```mysql
mysql>  alter table t add unique index (addr);
```

**3、查看已创建的索引**

```mysql
show index from tb_name;
```

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192237.png)

【注】索引默认是BTREE索引

**4、索引的删除**

```mysql
drop index 索引名 on tb_name;
alter table tb_name drop index 索引名;
```

**5、查看SQL语句对索引的使用情况**

**select语句之前添加explain即可**

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192234.png)

请注意第二个和第三个查询，一个用到了索引，一个没有用到索引。

> BTREE索引触发原则：
>
> 当使用 >、<、>= 、BETWEEN、!=、<>或者LIKE ’pattern'(**其中patter不以通配符开始**)操作符时，都可以使用相关列上的索引。 

explain查询参数：

**id：**SELECT识别符。这是SELECT的查询序列号。

**select_type：**SELECT类型。

1. SIMPLE： 简单SELECT(不使用UNION或子查询)
2. PRIMARY： 最外面的SELECT
3. UNION：UNION中的第二个或后面的SELECT语句
4. DEPENDENT UNION：UNION中的第二个或后面的SELECT语句，取决于外面的查询
5. UNION RESULT：UNION的结果
6. SUBQUERY：子查询中的第一个SELECT
7. DEPENDENT SUBQUERY：子查询中的第一个SELECT，取决于外面的查询
8. DERIVED：导出表的SELECT(FROM子句的子查询)

**table：**表名

**type：**联接类型。是SQL性能的非常重要的一个指标，结果值从好到坏依次是：

```bash
system > const > eq_ref > ref > fulltext > ref_or_null > index_merge > unique_subquery > index_subquery > range > index > ALL。
```

一般来说，得保证查询至少达到range级别。

1. system：表仅有一行(=系统表)。这是const联接类型的一个特例。
2. const：表最多有一个匹配行，它将在查询开始时被读取。因为仅有一行，在这行的列值可被优化器剩余部分认为是常数。const用于用常数值比较PRIMARY KEY或UNIQUE索引的所有部分时。
3. eq_ref：对于每个来自于前面的表的行组合，从该表中读取一行。这可能是最好的联接类型，除了const类型。它用在一个索引的所有部分被联接使用并且索引是UNIQUE或PRIMARY KEY。eq_ref可以用于使用= 操作符比较的带索引的列。比较值可以为常量或一个使用在该表前面所读取的表的列的表达式。
4. ref：对于每个来自于前面的表的行组合，所有有匹配索引值的行将从这张表中读取。如果联接只使用键的最左边的前缀，或如果键不是UNIQUE或PRIMARY KEY(换句话说，如果联接不能基于关键字选择单个行的话)，则使用ref。如果使用的键仅仅匹配少量行，该联接类型是不错的。ref可以用于使用=或<=>操作符的带索引的列。
5. ref_or_null：该联接类型如同ref，但是添加了MySQL可以专门搜索包含NULL值的行。在解决子查询中经常使用该联接类型的优化。
6. index_merge：该联接类型表示使用了索引合并优化方法。在这种情况下，key列包含了使用的索引的清单，key_len包含了使用的索引的最长的关键元素。
7. unique_subquery：该类型替换了下面形式的IN子查询的ref：value IN (SELECT primary_key FROMsingle_table WHERE some_expr);unique_subquery是一个索引查找函数，可以完全替换子查询，效率更高。
8. index_subquery：该联接类型类似于unique_subquery。可以替换IN子查询，但只适合下列形式的子查询中的非唯一索引：value IN (SELECT key_column FROM single_table WHERE some_expr)
9. range：只检索给定范围的行，使用一个索引来选择行。key列显示使用了哪个索引。key_len包含所使用索引的最长关键元素。在该类型中ref列为NULL。当使用=、<>、>、>=、<、<=、IS NULL、<=>、BETWEEN或者IN操作符，用常量比较关键字列时，可以使用range
10. index：该联接类型与ALL相同，除了只有索引树被扫描。这通常比ALL快，因为索引文件通常比数据文件小。
11. all：对于每个来自于先前的表的行组合，进行完整的表扫描。如果表是第一个没标记const的表，这通常不好，并且通常在它情况下很差。通常可以增加更多的索引而不要使用ALL，使得行能基于前面的表中的常数值或列值被检索出。

**possible_keys：**possible_keys列指出MySQL能使用哪个索引在该表中找到行。注意，该列完全独立于EXPLAIN输出所示的表的次序。这意味着在possible_keys中的某些键实际上不能按生成的表次序使用。

**key：**key列显示MySQL实际决定使用的键(索引)。如果没有选择索引，键是NULL。要想强制MySQL使用或忽视possible_keys列中的索引，在查询中使用FORCE INDEX、USE INDEX或者IGNORE INDEX。

**key_len：**key_len列显示MySQL决定使用的键长度。如果键是NULL，则长度为NULL。注意通过key_len值我们可以确定MySQL将实际使用一个多部关键字的几个部分。

**ref：**ref列显示使用哪个列或常数与key一起从表中选择行。

**rows：**rows列显示MySQL认为它执行查询时必须检查的行数。

**Extra：**该列包含MySQL解决查询的详细信息。

[explain命令解释](https://www.cnblogs.com/gomysql/p/3720123.html)

## 10.5 索引命中

**1、通配符在前，模糊查询不使用索引**

**2、union、in、or 都能够命中索引，建议使用 in**

**3、联合索引最左前缀原则（又叫最左侧查询）**

如果在(a,b,c)三个字段上建立联合索引，那么它能够加快 a | (a,b) | (a,b,c) 三组查询速度。

**4、范围列可以用到索引**

- 范围条件有：<、<=、>、>=、between等。
- 范围列可以用到索引（联合索引必须是最左前缀），但是**范围列后面的列无法用到索引**，**索引最多用于一个范围列，如果查询条件中有两个范围列则无法全用到索引**。

如有索引 `(a,b,c,d)`，查询条件 `a=1 and b=2 and c>3 and d=4`，则会在每个节点依次命中a、b、c，无法命中d。(c已经是范围查询了，d肯定是排不了序了)

==范围查询不一定用到索引==

如果索引列数据量大的情况下，那么即使索引列查询，也有可能用不到索引。

## 10.6 最左匹配原则的解释

创建表

```mysql
create` `table` `test(
a ``int` `,
b ``int``,
c ``int``,
d ``int``,
key` `index_abc(a,b,c)
)engine=InnoDB ``default` `charset=utf8;
```

插入10000条数据，当我在执行的时候，以为会很快执行，但没想到这10000条数据往磁盘写花费了接近2min，

不明白为什么？

```mysql
DROP` `PROCEDURE` `IF EXISTS proc_initData;
DELIMITER $
CREATE` `PROCEDURE` `proc_initData()
BEGIN
DECLARE` `i ``INT` `DEFAULT` `1;
WHILE i<=10000 DO
  ``INSERT` `INTO` `test(a,b,c,d) ``VALUES``(i,i,i,i);
  ``SET` `i = i+1;
END` `WHILE;
END` `$
CALL proc_initData();
```

explain select * from test where a<10 ;

explain select * from test where a<10 and b <10;

explain select * from test where a<10 and b <10 and c<10;

上述查询都显示用到了组合索引，但是考虑下面这种情况：

explain select * from test where b<10 and a <10;

explain select * from test where b<10 and a <10 and c<10;

explain显示查询也用到了索引，不是最左匹配吗？

**mysql会自动优化这些条件的顺序，以匹配尽可能多的索引列。**

其实，mysql查询优化器帮我们解析纠正这条语句以什么样的顺序执行效率最高，有点自动校正的意思。

但是如果执行

explain select * from test where b<10 and c <10;

explain select * from test where a<10 and c <10;

会发现**b<10 and c <10,没有用到索引？而 a<10 and c <10用到了？**

因为B+树的数据项是复合的数据结构，比如建立组合索引(name,age,sex),B+树是从左到右来建立搜索树的，比如查询(张三,20,F)，b+树会**优先比较name来确定下一步的所搜方向**，如果name相同再依次比较age和sex，最后得到检索的数据；但当(20,F)这样的没有name的数据的时候，b+树就不知道下一步该查哪个节点，因为建立搜索树的时候name就是第一个比较因子，必须要先根据name来搜索才能知道下一步去哪里查询。比如当(张三,F)这样的数据来检索时，b+树可以用name来指定搜索方向，但下一个字段age的缺失，所以只能把名字等于张三的数据都找到，然后再匹配性别是F的数据了， 这个是非常重要的性质，即索引的最左匹配特性。

# 11. 视图

## 11.1 什么是视图

​	视图是一种**虚拟存在**的表，并**不在数据库中实际存在**，对用户透明，行列数据来自定义视图的查询中使用的表，并且在使用的过程中动态生成的。

视图相对于普通表的优势主要包括：

* 简单：使用视图的用户无需关心查询的数据后面对应的表结构、关联条件等。用户透明。对用户来说是已经过滤好的符合条件的结果集。
* 安全：使用视图的用户只能访问他们被允许查询的结果集。
* 数据独立：对原表增加列并不会影响视图，原表修改列名，可以通过修改视图来修改结构，不会造成对访问者的影响。

## 11.2 视图操作

### 11.2.1 创建或者修改视图

创建视图的语法：

```mysql
create [or replace][algorithm={undefined|merge|temptable}]
		view view_name [(column_list)]
		as select_statement
		[with [cascaded|local] check option];
```

修改视图的语法：

```mysql
alter [or replace][algorithm={undefined|merge|temptable}]
		view view_name [(column_list)]
		as select_statement
		[with [cascaded|local] check option];
```

新增员工表和地址表，地址表的address_id是员工表的外键。

```mysql
CREATE TABLE "address" (
  "address_id" int(11) NOT NULL,
  "address" varchar(100) DEFAULT NULL,
  PRIMARY KEY ("address_id")
);

CREATE TABLE "staff" (
  "staff_id" int(11) NOT NULL AUTO_INCREMENT,
  "address_id" int(11) DEFAULT NULL,
  "first_name" varchar(20) DEFAULT NULL,
  "last_name" varchar(20) DEFAULT NULL,
  PRIMARY KEY ("staff_id"),
  KEY "address_id" ("address_id"),
  CONSTRAINT "staff_ibfk_1" FOREIGN KEY ("address_id") REFERENCES "address" ("address_id")
);

# 创建视图
create or replace view staff_list_view
as 
select s.staff_id,s.first_name,s.last_name,a.address
from staff as s, address a
where s.address_id = a.address_id;
```

视图的可更新性和视图中查询的定义有关系，以下类型的视图是不可更新的。

*  包含以下关键字的 SQL 语句：聚合函数（SUM、MIN、MAX、COUNT 等）、DISTINCT、GROUP BY、HAVING、UNION 或者 UNION ALL。 
* 常量视图。 
*   SELECT 中包含子查询。 
*  JOIN。 
*  FROM 一个不能更新的视图。 
*  WHERE 字句的子查询引用了 FROM 字句中的表

``WITH [CASCADED | LOCAL] CHECK OPTION ``决定了是否允许更新数据使记录不再满足视图的条
件。这个选项与 Oracle 数据库中的选项是类似的，其中： 

* LOCAL 是只要满足本视图的条件就可以更新； 
*  CASCADED 则是必须满足所有针对该视图的所有视图的条件才可以更新。

如果没有明确是 LOCAL 还是 CASCADED，则默认是 CASCADED。

```mysql
create or replace view payment_view as 
select payment_id,amount from payment  
where amount < 10 WITH CHECK OPTION;

create or replace view payment_view1 as 
select payment_id,amount from payment_view  
where amount > 5 WITH LOCAL CHECK OPTION;

create or replace view payment_view2 as 
select payment_id,amount from payment_view  
 where amount > 5 WITH CASCADED CHECK OPTION;
 
 # 按书中来说，下面应该更新成功
 update payment_view1 set amount=11
  where payment_id = 1;
 # 这句应该更新失败
 update payment_view2 set amount=11
  where payment_id = 1;
```

> 实际在MySQL5.6测试时，建立在payment_view上面的两层视图，无论哪个都是都是失败的！

### 11.2.2 删除视图

```mysql
drop view [if exists] view_name [, view_name] ... [restrict | cascade];
```

### 11.2.3 查看视图

```mysql
show create view view_name
```

# 12. 存储过程和函数

MySQL官方文档有**存储例程**(Store routines)一说，它的两种类型就是存储过程和函数。

## 12.1 什么是存储过程和函数

存储过程和函数是事先经过编译并存储在数据库中的**一段SQL语句的集合**。可以把一些复杂的数据处理逻辑封装在存储过程和函数，这样就减轻了后端人员编写SQL语句的负担，提高了数据处理的效率。

**存储过程和函数的区别：**

* 函数必须有返回值，而存储过程没有。
* 存储过程的参数可以使用IN、OUT、INOUT类型，函数的参数只能是IN类型。省略则默认参数类型为IN。

## 12.2 存储过程和函数的相关操作

对存储过程和函数操作时，需要用户有相应的权限。创建存储过程或者函数需要 CREATE ROUTINE 权限，修改或者删除存储过程或者函数需要 ALTER ROUTINE 权限，执行存储过程或者函数需要 EXECUTE 权限。

>**通常begin-end用于定义一组语句块，在各大数据库中的客户端工具中可直接调用，但在mysql中不可用。**
>
>**begin-end、流程控制语句、局部变量只能用于函数、存储过程内部、游标、触发器的定义内部。**

### 12.2.1 存储过程或函数创建

```mysql
CREATE
    [DEFINER = user]
    PROCEDURE sp_name ([proc_parameter[,...]])
    [characteristic ...] routine_body

CREATE
    [DEFINER = user]
    FUNCTION sp_name ([func_parameter[,...]])
    RETURNS type
    [characteristic ...] routine_body

proc_parameter:
    [ IN | OUT | INOUT ] param_name type

func_parameter:
    param_name type

type:
    Any valid MySQL data type

characteristic: {
    COMMENT 'string'
  | LANGUAGE SQL
  | [NOT] DETERMINISTIC
  | { CONTAINS SQL | NO SQL | READS SQL DATA | MODIFIES SQL DATA }
  | SQL SECURITY { DEFINER | INVOKER }
}

routine_body:
    Valid SQL routine statement
```

调用存储过程和函数

```mysql
# 存储过程
call proc_name(...);
# 函数：直接在表达式中引用即可，和调用SQL内部函数一样
func_name();
```

下面的示例显示了一个简单的存储过程，该存储过程给定了国家（地区）代码，计算了出现在国家表中相同国家代码的城市数。使用IN参数传递国家/地区代码，并使用OUT参数返回城市计数：

```mysql
CREATE TABLE "country" (
  "country_code" varchar(11) DEFAULT NULL,
  "city" varchar(11) DEFAULT NULL
);

# 修改定界符,防止mysql在遇到“;”被解释为结束符, code是mysql保留的关键字
delimiter //;
CREATE PROCEDURE citycount(in ccode varchar(11), out cities varchar(11))
begin
select count(*) into cities from country
where country_code=ccode;
end
//
# 将结束定界符复原
delimiter ;
# 调用存储过程,这里的@cities相当于一个全局变量，在执行完毕之后，可以通过
# select @cities;查看结果
call citycount('CN', @cities);

```

定界符因需选择，比如下面存储函数就没有使用，因为就只有单条语句。

```mysql
mysql> create function hello(s char(20))
    -> returns char(50) deterministic
    -> return concat('hello, ',s,'!');

mysql> select hello('world');
+----------------+
| hello('world') |
+----------------+
| hello, world!  |
+----------------+
```

> 关于characteristic特征值的说明这里不再记录，详情可以看书或者官方文档。

### 12.2.2 删除存储过程或者函数

```mysql
DROP {PROCEDURE | FUNCTION} [IF EXISTS] sp_name;
```

### 12.2.3 查看存储过程或者函数

```mysql
show create {PROCEDURE | FUNCTION} sp_name;

show {PROCEDURE | FUNCTION} status like \G;

# ...具体就是结果不同
# show create 查询的是 某结构的 定义
# show status 查询的是 某结构的 状态
```

### 12.2.4 变量的声明及使用

**MySQL变量的分类**

 MySQL变量分为：**局部变量、用户变量、会话变量和全局变量。**全局变量和会话变量又称为**系统变量**。

(1)局部变量

一般用于sql语句块，比如store_routines的begin/end。作用域仅限于该语句块，生命周期随语句块而存活。

一般用法：**declare声明，set或者select ...into 赋值**。

(2)用户变量

``@var_name``形式的变量为用户变量，用户变量的生命周期与本次连接（session）有关，当本次会话结束，连接中所有定义的用户变量都会消失，且各个连接中的用户变量互不可见。

一般用法：**set @var_name=value; set @var_name:=value;或者 select @var_name:=value;select @num:=字段名 from 表名 where ……**

用户变量不需要声明，赋初值的过程即声明和定义，一起做了。**声明及定义然后再赋值**

(3)会话变量和全局变量

session和globall。

**1、变量的定义**

格式：``DECLARE var_name[,...] type [DEFAULT value]``

通过 DECLARE 可以定义一个局部变量，**该变量的作用范围只能在 BEGIN…END 块中**，可以用在嵌套的块中。变量的定义必须写在复合语句的开头，并且在任何其他语句的前面。可以一次声明多个相同类型的变量。如果需要，可以使用 DEFAULT 赋默认值。

**2、变量的赋值**

**变量可以直接赋值，或者通过查询赋值**

格式：

```mysql
# set赋值可以是常量或者表达式
set var_name = expr [,var name = expr]...

# 查询赋值，要求查询返回的结果必须只有一行
select col_name[,...] into var_name[,...] table_expr;
```

> declare 声明变量，set或者select...into为变量赋值。

```mysql
# set方式赋值
delimiter //
create function addSum(a int,b int)
returns int
begin
declare sum int;
set sum = a + b;
return sum;
end
//
# 查询赋值
delimiter //
create function addSum(a int,b int)
returns int
begin
declare sum int;
select a+b into sum;
return sum;
end
//
```

### 12.2.5 定义条件和处理

条件的定义和处理可以用来定义在处理过程中遇到问题时相应的处理步骤。

**1、条件的定义**

```mysql
DECLARE condition_name CONDITION FOR condition_value

condition_value: {
    mysql_error_code
  | SQLSTATE [VALUE] sqlstate_value
}

# mysql_error_code: An integer literal indicating a MySQL error code.
# SQLSTATE [VALUE] sqlstate_value: A 5-character string literal indicating an SQLSTATE value.
```

**2、条件的处理**

```mysql
DECLARE handler_action HANDLER
    FOR condition_value [, condition_value] ...
    statement
handler_action: {
    CONTINUE
  | EXIT
  | UNDO
}

condition_value: {
    mysql_error_code
  | SQLSTATE [VALUE] sqlstate_value
  | condition_name
  | SQLWARNING
  | NOT FOUND
  | SQLEXCEPTION
}
```

当调用存储过程执行其中的SQL时发生内部错误时，如果使用了条件处理，那么就会触发条件处理的action，它有三个值分别代表：

* CONTINUE 表示继续执行下面的语句
* EXIT 则表示执行终止
* UNDO 现在还不支持

condition_value 的值可以是通过 DECLARE 定义的 condition_name，可以是 SQLSTATE 的值或者 mysql-error-code 的值或者 SQLWARNING、NOT FOUND、SQLEXCEPTION，这 3 个值是 3 种定义好的错误类别，分别代表不同的含义。 

* SQLWARNING 是对所有以 01 开头的 SQLSTATE 代码的速记。 
* NOT FOUND 是对所有以 02 开头的 SQLSTATE 代码的速记。 
* SQLEXCEPTION 是对所有没有被 SQLWARNING 或 NOT FOUND 捕获的 SQLSTATE 代码的速记。

向staff表中插入重复主键的记录，如果没有异常处理，x=3就不会执行，我们希望异常发生后，继续往后执行，这时就需要异常处理。

```mysql
CREATE DEFINER="stronger"@"%" PROCEDURE "staff_insert"()
BEGIN
	declare continue handler for sqlstate '23000' set @x2=1;
	set @x = 1;
	insert into staff values(2, 1, 'Qing','Q');
	set @x = 2;
	insert into staff values(1, 1, 'Long','L');
	set @x = 3;
END
```

### 12.2.6 光标的使用 

在存储过程和函数中可以使用光标对结果集进行循环的处理。光标的使用包括光标的声明、OPEN、FETCH 和 CLOSE。

* 声明光标

  ```mysql
  declare cursor_name cursor for select statement;
  ```

* 打开光标

  ```mysql
  open cursor_name;
  ```

* fetch光标，循环遍历

  ```mysql
  fetch cursor_name into var_name [, var_name]...
  ```

  作用：将遍历的每条记录赋值到var_name

* 关闭光标

  ```mysql
  close cursor_name;
  ```

例：统计账单金额大于100的账单数量，判断循环结束的条件是捕获NOT FOUND的条件，当FETCH光标找不到下一条记录的时候，就会关闭光标然后退出过程。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192216.png)

```mysql

drop PROCEDURE payment_proc;
delimiter //
create procedure payment_proc()
begin
	# 一定不要定义和fetch捕获的列同名的变量比如declare amount int;
	declare i_amount int;
	declare amount_cur cursor for select amount from payment;

	declare exit handler for not found close amount_cur;
	
	set @count = 0;
	# 打开光标
	open amount_cur;
	REPEAT
		# 使用光标
		fetch amount_cur into i_amount;
			if i_amount>100 then
				set @count = @count + 1;# 注意赋值必须加set
			end if;
	UNTIL 0 END REPEAT;
	
	# 关闭光标
	close amount_cur;

end
//

call payment_proc();
select @count;
```

【注】

* navicate中定义存储过程一定要通过``delimiter //``改变定界符，不然会报错。
* fetch游标将参数赋值给之前定义的变量，需要注意定义的变量不要和游标中捕获的参数同名。
* 变量、条件、处理程序、光标都是通过 DECLARE 定义的，它们之间是有先后顺序的要求的。变量和条件必须在最前面声明，然后才能是光标的声明，最后才可以是处理程序的声明。

### 12.2.7 流程控制

**1、IF语句**

语法：

```mysql
if condition then statement_list
	[elseif condition then statement_list]...s
	[else statement_list]
endif;
```

**2、CASE语句**

CASE 实现比 IF 更复杂一些的条件构造，具体语法如下：

```mysql
case case_value
	when when_value then statement_list
	[when when_value then statement_list]...
	[else statement_list]
end case
or:
case 
	when search_condition then statement_list
	[when search_condition then statement_list]...
	[else statement_list]
end case;
```

**3、LEAVE和ITERATE**

(1)LEAVE

用于退出具有给定标签的流控制构造。如果标签用于最外面存储的程序块，则LEAVE退出程序。

LEAVE可以在BEGIN ... END或循环构造（LOOP，REPEAT，WHILE）中使用。

```mysql
#格式
LEAVE label;
```

(2)ITERATE 

ITERATE 语句必须用在循环中，作用是跳过当前循环的剩下的语句，直接进入下一轮循环。

```mysql
#格式
ITERATE label;

# 循环向表中插入值，如果是偶数跳过当前循环，奇数则插入
create procedure test()
begin
	declare i int default 10;
	ins: loop
		set i = i + 1;
		if i > 20 then
			leave ins;
		elseif mod(i,2)=0 then
			iterate ins;
		else 
			insert into t values(i);
		end if;
		#set i = i + 1;刚开始把这句放后面了，导致死循环
	end loop;
end
//
```

**4、循环**

MySQL中循环的定义有``while``、``repeat``、``loop``。

(1)while

```mysql
#格式
[begin_label:] WHILE search_condition DO
    statement_list
END WHILE [end_label]

delimiter //
# 存储过程括号一定不要忘记加
create procedure test()
begin
	declare i int default 1;
	while i <= 10 do
		insert into t values(i);
		set i = i + 1;
	end while;
end
//
delimiter ;
call test();
```

(2)repeat

```mysql
# 格式
[begin_label:] REPEAT
    statement_list
UNTIL search_condition # 注意它的意思，是直到满足什么条件才跳出，有点像do...while
END REPEAT [end_label]

create procedure test()
begin
	declare i int default 1;
	repeat
		insert into t values(i);
		set i = i + 1;
	until i > 10 end repeat;
end
```

(3)loop

通常loop配合leave，循环的终止需要leave，或者如果在存储函数中也可以通过return终止循环。

```mysql
# 格式
[begin_label:] LOOP
    statement_list
END LOOP [end_label]

create procedure test()
begin
	declare i int default 1;
	lp: loop
		if i > 10 then
			leave lp;
		end if;
		insert into t values(i);
		set i = i + 1;
	end loop;
end
//
```

# 13. 触发器

触发器是与表有关的数据库对象，**在满足定义条件时触发，并执行触发器中定义的语句集合**。触发器的这种特性可以协助应用在数据库端确保数据的完整性。

## 13.1 创建触发器

```mysql
CREATE
    [DEFINER = user]
    TRIGGER trigger_name
    trigger_time trigger_event
    ON tbl_name FOR EACH ROW
    [trigger_order]
    trigger_body

trigger_time: { BEFORE | AFTER }

trigger_event: { INSERT | UPDATE | DELETE }

trigger_order: { FOLLOWS | PRECEDES } other_trigger_name
```

>触发器只能创建在永久表（Permanent Table）上，不能对临时表（Temporary Table）或试图创建
>触发器。

 在触发器主体内，您可以使用别名OLD和NEW来引用主题表（与触发器关联的表）中的列。OLD.col_name在**更新或删除之前**引用现有行的列。NEW.col_name指向**要插入的新行或更新后**的现有行的列。换句话说，**在INSERT触发器中，只能使用NEW.col_name**。没有旧的行。**在DELETE触发器中，只能使用OLD.col_name**。没有新行。在UPDATE触发器中，可以使用OLD.col_name来引用更新前的行的列，并可以使用NEW.col_name来引用更新后的行的列。

示例：创建一个insert动作相关的触发器与表关联，在向账户表插入数据前，累加金额。

```mysql
create table account(acct_num int, amount decimal(10,2));

# 定义触发器，在向表account插入数据时，累计金额
create trigger ins_sum before insert on account
for each row set @sum = @sum + NEW.amount;

set @sum=0;

INSERT INTO account VALUES(137,14.98),(141,1937.50),(97,-100.00);
SELECT @sum AS 'Total amount inserted';
+-----------------------+
| Total amount inserted |
+-----------------------+
|               1852.48 |
+-----------------------+
```

从MySQL5.7.2开始，可以为给定表定义具有相同触发事件和动作事件的多个触发，这在之前是不允许的，只能通过``begin...end``复合块来执行多个动作。例如，一个表可以有两个BEFORE UPDATE触发器。**默认情况下，具有相同触发事件和动作时间的触发将按照其创建顺序进行激活**。要影响触发顺序，请在FOR EACH ROW之后指定一个子句，该子句指示FOLLOWS或PRECEDES，以及一个现有触发器的名称，该触发器也具有相同的触发器事件和动作时间。使用FOLLOWS，新触发器将在现有触发器之后激活。使用PRECEDES，新触发器将在现有触发器之前激活。

例如，在表account的基础上在定义*before insert*的触发器

```mysql
set @depositis=0;
set @withdraw=0;
create trigger ins_transaction before insert on account
for each row precedes ins_sum
set
@depositis = @depositis + if(NEW.amount>0,New.amount,0),
@withdraw = @withdraw + if(NEW.amount<0,-NEW.amount,0);

select @depositis '存款', @withdraw '取款', @sum '总额';

+-----------------------+
| 存款	 | 取款 | 总额	|
+-----------------------+
| 1952.48 | 100	|1852.48|
+-----------------------+
```

此触发器ins_transaction与ins_sum类似，但分别存储存款和取款。它有一个PRECEDES子句，使它在ins_sum之前激活；如果没有该子句，它将在ins_sum之后激活，因为它是在ins_sum之后创建的。

以OLD命名的列是只读的。您可以引用它（如果您具有SELECT特权），但不能对其进行修改。如果您具有使用SELECT特权，则可以引用以NEW命名的列。在BEFORE触发器中，如果您具有UPDATE(insert、update)特权，也可以使用SET NEW.col_name = value更改其值。这意味着您可以使用触发器来修改要插入到新行中或用于更新行的值。（这种SET语句在AFTER触发器中无效，因为行更改已经发生。）

示例：在更新account表时检查账户入账金额。

```mysql
delimiter //
create trigger upd_check before update on account
for each row
begin
	if NEW.amount < 0 then
		set NEW.amount = 0;
	elseif NEW.amount > 100 then
		set NEW.amount = 100;
	end if;
end
//
```

优势：分别定义存储过程，然后使用简单的CALL语句从触发器调用存储过程会更容易。如果要在多个触发器中执行相同的代码，这也将非常有利。

## 13.2 删除触发器

 ```mysql
drop trigger trigger_name;
 ```

> If you drop a table, any triggers for the table are also dropped.

## 13.3 查看触发器

```mysql
SHOW TRIGGERS
    [{FROM | IN} db_name]
    [LIKE 'pattern' | WHERE expr];

show triggers from db
 like 'acc%'; # like后是表名
```



# 14. 数据库事务

## 14.1 事务基础

## 14.2 分布式事务

### 14.2.1 本地事务

**本地事务**：支持事务的参与者、服务器、资源管理器（RM）和事务管理器（TM）位于单机之上，仅限对单一数据库资源的访问控制。就是表和数据库位于一个服务器上，事务的操作都在这一个服务器上进行。

起初，事务仅限于对单一数据资源的访问控制：

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192206.png)

而我们的本地事务由资源管理器进行管理：

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192203.png)

事务的ACID是通过InnoDB日志和锁来保证。事务的隔离性是通过事务的锁机制实现的，持久性通过redo log(重做日志)来实现，原子性和一致性通过Undo log来实现。UndoLog的原理很简单，为了满足事务的原子性，在操作任何数据之前，首先将数据备份到一个地方（这个存储数据备份的地方称为UndoLog）。然后进行数据的修改。如果出现了错误或者用户执行了ROLLBACK语句，系统可以利用Undo Log中的备份将数据恢复到事务开始之前的状态。 和Undo Log相反，RedoLog记录的是新数据的备份。在事务提交前，只要将RedoLog持久化即可，不需要将数据持久化。当系统崩溃时，虽然数据没有持久化，但是RedoLog已经持久化。系统可以根据RedoLog的内容，将所有数据恢复到最新的状态。

本地事务主要限制在单个会话内，不涉及多个数据库资源。但是在基于 **SOA（Service-Oriented Architecture，面向服务架构）**的分布式应用环境下，越来越多的应用要求对多个数据库资源，多个服务的访问都能纳入到同一个事务当中，分布式事务应运而生。

### 14.2.2 分布式事务

​	在开发中，为了降低单机的压力，通常会进行分表分库，将表分布在不同的数据库中（数据库有可能分布在不同的机器上），但是一个业务场景可能会处理不同库中的表，事务的提交就不能在像单机那样处理，因为涉及到多个服务器的控制，要考虑服务器之间的通信是否正常、网络延时带宽等因素，这些在单机上并没有太大的影响。所以说多服务器之间事务的控制变得相对复杂，分布式事务也就相应的出现。

比如原来单机支撑了整个电商网站，现在对整个网站进行拆解，分离出了订单中心、用户中心、库存中心等,对于订单中心，有专门的数据库存储订单信息，用户中心也有专门的数据库存储用户信息，库存中心也会有专门的数据库存储库存信息,如果要同时对订单和库存进行操作，那么就会涉及到订单数据库和库存数据库，为了保证数据一致性，就需要用到分布式事务。

**分布式事务**：分布式事务就是指事务的参与者、支持事务的服务器、资源服务器以及事务管理器分别位于不同的分布式系统的不同节点之上。简单的说，就是一次大的操作由不同的小操作组成，这些小的操作分布在不同的服务器上，且属于不同的应用，分布式事务需要保证这些小操作要么全部成功，要么全部失败。本质上来说，分布式事务就是为了保证不同数据库的数据一致性。

最早的分布式事务应用架构*不涉及服务之间的访问调用*，仅仅是服务内操作涉及对多个数据库资源的访问。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192200.png)

当一个服务操作访问不同的数据库资源，又希望对它们的访问具有事务特性时，就需要采用分布式事务来协调所有的事务参与者。

在上面的分布式事务应用架构中，尽管一个服务操作会访问多个数据库资源，但是毕竟整个事务还是控制在单一服务的内部。如果一个服务操作需要调用另外一个服务，这时的事务就需要**跨越**多个**服务**了。**在这种情况下，起始于某个服务的事务在调用另外一个服务的时候，需要以某种机制流转到另外一个服务**，从而使被调用的服务访问的资源也自动加入到该事务当中来。下图反映了这样一个跨越多个服务的分布式事务：

 ![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192705.png)

如果将上面这两种场景（一个服务可以调用多个数据库资源，也可以调用其他服务）结合在一起，对此进行延伸，整个分布式事务的参与者将会组成如下图所示的树形拓扑结构。在一个跨服务的分布式事务中，事务的发起者和提交均系同一个，它可以是整个调用的客户端，也可以是客户端最先调用的那个服务。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192155.png)

## 14.3 分布式事务的解决方案

分布式事务是最核心的还是其ACID特性。研究分布式事务本质上还是研究其是如何保证ACID的。事务模型为分布式事务提供了理论基础，像2PC、3PC协议则是实现分布式事务的设计方案。

### 14.3.1 X/Open XA协议

**DTP模型（ X/Open Distributed Transaction）**：最早的分布式事务模型，是由 X/Open 国际联盟提出的，也就是X/Open XA协议，简称XA协议。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192153.png)



DTP模型包含**一个全局事务管理器**（TM Transaction Manager）和**多个资源管理器**（RM Resource Manager）。全局事务管理器**负责管理全局事务状态与参与的资源，协同资源一起提交或回滚**；资源管理器负责具体的资源操作。

XA协议描述了TM与RM之间的接口，允许多个资源在同一分布式事务中访问。

**TM：Transaction Manager 事务管理器**

- 分布式事务的实现由事务管理器来完成，它会提供分布式事务的操作接口供我们的业务系统调用。这些接口称为TX接口。
- 事务管理器还管理着所有的资源管理器，通过它们提供的XA接口来统一调度这些资源管理器，以实现分布式事务。
- **DTP只是一套实现分布式事务的规范，并没有定义具体如何实现分布式事务，TM可以采用2PC、3PC、Paxos等协议实现分布式事务。**

**RM：Resource Manager 资源管理器**

- 能够提供数据服务的对象都可以是资源管理器，比如：数据库、消息中间件、缓存等。大部分场景下，数据库即为分布式事务中的资源管理器。
- 资源管理器能够提供单数据库的事务能力，它们通过XA接口，将本数据库的提交、回滚等能力提供给事务管理器调用，以帮助事务管理器实现分布式的事务管理。
- **XA是DTP模型定义的接口，用于向事务管理器提供该资源管理器(该数据库)的提交、回滚等能力**。XA协议实现通常在RM层。
- **DTP只是一套实现分布式事务的规范，RM具体的实现是由数据库厂商来完成的。**


**基于 DTP 模型的分布式事务流程大致如下：**

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192151.png)

1. 应用程序（AP）向TM申请开始一个事务
2. 针对要操作的 RM，AP 会先向 TM 注册（TM 负责记录 AP 操作过哪些 RM，即**分支事务**），TM 通过 XA 接口函数通知相应 RM 开启分布式事务的子事务，接着 AP 就可以对该 RM 管理的资源进行操作。
3. 当 AP 对所有 RM 操作完毕后，AP 根据执行情况通知 TM 提交或回滚该全局事务，TM 通过 XA 接口函数通知各 RM 完成操作。TM 会先要求各个 RM 做预提交，所有 RM 返回成功后，再要求各 RM 做正式提交，XA 协议要求，一旦 RM 预提交成功，则后续的正式提交也必须能成功；如果任意一个 RM 预提交失败，则 TM 通知各 RM 回滚。

4. 所有 RM 提交或回滚完成后，全局事务结束。

**1、原子性**

XA协议使用2PC（Two Phase Commit 两阶段提交）原子提交协议来保证分布式事务原子性。

两阶段提交是指将提交过程分为两个阶段：**准备阶段**（投票阶段）和**提交阶段**（执行阶段）。

* 准备阶段 

  TM向每个RM发送准备消息。如果 RM 的本地事务操作执行成功，则返回成功；如果 RM 的本地事务操作执行失败，则返回失败。

* 提交阶段

  如果 TM 收到了所有 RM 回复的成功消息，则向每个 RM 发送提交消息；否则发送回滚消息；RM 根据 TM 的指令执行提交或者回滚本地事务操作，释放所有事务处理过程中使用的锁资源。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192148.png)

存在的问题：

**同步阻塞**：当参与事务者存在占用公共资源的情况，其中一个占用了资源，其他事务参与者就只能阻塞等待资源释放，处于阻塞状态。并发性差。

**单点故障**：一旦事务管理器出现故障，整个系统不可用

**数据不一致**：在阶段二，如果事务管理器只发送了部分 commit 消息，此时网络发生异常，那么只有部分参与者接收到 commit 消息，也就是说只有部分参与者提交了事务，使得系统数据不一致。

**2、隔离性**

XA 协议中没有描述如何实现分布式事务的隔离性，但是 XA 协议要求 DTP 模型中的每个 RM 都要实现本地事务，也就是说，基于 XA 协议实现的分布式事务的隔离性是由每个 RM 本地事务的隔离性来保证的，当一个分布式事务的所有子事务都是隔离的，那么这个分布式事务天然的就实现了隔离性。

以 MySQL 来举例，MySQL 使用 2PL（Two-Phase Locking，两阶段锁）机制来控制本地事务的并发，保证隔离性。2PL 与 2PC 类似，也是将锁操作分为加锁和解锁两个阶段，并且保证两个阶段完全不相交。加锁阶段，只加锁，不放锁。解锁阶段，只放锁，不加锁。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192145.png)

如上图所示，在一个本地事务中，每执行一条更新操作之前，都会先获取对应的锁资源，只有获取锁资源成功才会执行该操作，并且一旦获取了锁资源就会持有该锁资源直到本事务执行结束。

MySQL 通过这种 2PL 机制，可以保证在本地事务执行过程中，其他并发事务不能操作相同资源，从而实现了事务隔离。

**3、一致性**

前面提到一致性有两层语义，一层是确保事务执行结束后，数据库从一个一致状态转变为另一个一致状态。另一层语义是事务执行过程中的中间状态不能被观察到。

### 14.3.2 TCC模型

TCC（Try-Confirm-Cancel）分布式事务模型相对于 XA 等传统模型，其特征在于它不依赖资源管理器（RM）对分布式事务的支持，而是通过对业务逻辑的分解来实现分布式事务。

TCC 模型认为对于业务系统中一个特定的业务逻辑，其对外提供服务时，必须接受一些不确定性，即对业务逻辑初步操作的调用仅是一个临时性操作，调用它的主业务服务保留了后续的取消权。如果主业务服务认为全局事务应该回滚，它会要求取消之前的临时性操作，这就对应从业务服务的取消操作。而当主业务服务认为全局事务应该提交时，它会放弃之前临时性操作的取消权，这对应从业务服务的确认操作。每一个初步操作，最终都会被确认或取消。

TCC事务机制相比于上面介绍的XA，解决了其几个缺点: 

1. 解决了协调者单点，由主业务方发起并完成这个业务活动。业务活动管理器也变成多点，引入集群。 

2. 同步阻塞:引入超时，超时后进行补偿，并且不会锁定整个资源，将资源转换为业务逻辑形式，粒度变小。 

3. 数据一致性，有了补偿机制之后，由业务活动管理器控制一致性

## 14.4 MySQL分布式事务

MySQL 的 InnoDB 引擎其实能够支持分布式事务，也就是我们经常说的 XA 事务；XA 事务就是用了我们在上一节中提到的两阶段提交协议实现分布式事务，其中事务管理器为协调者，而资源管理器就是分布式事务的参与者。

参考

* [再有人问你分布式事务，把这篇扔给他](https://juejin.im/post/6844903647197806605)
* [常用的分布式事务解决方案](https://juejin.im/post/6844903573667446797#heading-5)
* [一篇文章带你学习分布式事务](https://www.infoq.cn/article/g1avP9FUA6CDOYRAlv4R)
* [分布式事务,这一篇就够了](https://xiaomi-info.github.io/2020/01/02/distributed-transaction/)
* [分布式事务的实现原理](https://draveness.me/distributed-transaction-principle/)

# 第三部分 优化篇

# 17. 常用SQL技巧和常见问题

## 17.1 正则表达式的使用

正则表达式（Regular Expression），是指一个用来描述或者匹配一系列符合某个句法规则的字符串的单个字符串。

MySQL中可以使用的模式序列如表：

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192142.png)

**正则表达式操作符**

```mysql
expr REGEXP pat
expr NOT REGEXP pat
```

如果字符串expr与模式pat指定的正则表达式匹配，则返回1，否则返回0。如果expr或pat为NULL，则返回值为NULL。

```markdown
# 匹配以特定字符开头特定字符结尾
select 'abcdgjk123' regexp '^a[a-w]*3$';
```

## 17.2 巧用RAND()提取随机行

在MySQL中，产生随机数的方法是RAND()函数。可以利用这个函数与ORDER BY子句一起完成随机抽取某些行的功能。它的原理其实就是ORDER BY RAND()能够把数据随机排序。

例如，可按照随机顺序检索数据行：

```mysql
mysql> select * from sales2 order by rand() limit 5; 
+------+------------+--------+------+ 
| id   | company_id | moneys | year | 
+------+------------+--------+------+ 
| 876  | 876        | 876    | 0000 | 
| 283  | 283        | 283    | 0000 | 
| 442  | 442        | 442    | 0000 | 
| 874  | 874        | 874    | 0000 | 
| 849  | 849        | 849    | 0000 | 
+------+------------+--------+------+ 
5 rows in set (0.00 sec);
```

> 随机抽取样本常用于对总体的统计。

## 17.3 用BIT GROUP FUNCTIONS做统计

使用 GROUP BY 语句和` BIT_AND	`、`BIT_OR` 函数完成统计工作。这两个函数的一般用途就是做数值之间的逻辑位运算，但是，当把它们与 GROUP BY 子句联合使用的时候就可以做一些其他的任务。

假设现在有这样一个任务：一个超市需要记录每个用户每次来超市都购买了哪些商品。为了将问题简单化，假设该超市只有面包、牛奶、饼干、啤酒 4 种商品。那么通常该怎么做呢？
一般先建立一个购物单表，里面记录购物发生的时间、顾客信息等；然后再建立一个购物单明细表，里面记录该顾客所购买的商品。这样设计表结构的优点是顾客所购买的商品的详细信息可以记录下来，比如数量、单价等。但是上述设计存在相应的缺点是数据库设计复杂，如果用户一次购买商品比较多的话，需要很大的存储空间。

可以采用下面一种新的解决办法，用一个数值型字段来表示用户的物品。该字段存储一个十进制数字，当它转换成二进制的时候，那么每一位代表一种商品，而且如果所在位是“1”那么表示顾客购买了该种商品，“0”表示没有购买该种商品。比如数值的第 1 位代表面包（规定从右向左开始计算）、第 2 位代表牛奶、第 3 位代表饼干、第 4 位代表啤酒，这样如果一个用户购物单的商品列的数值为 5，那么二进制表示为 0101，这样从右向左第 1 位和第 3 位是 1，那么就可以知道这个用户购买了面包和饼干，而如果这个客户有多个这样的购物单（在数据库中就是有多条记录），把这些购物单按用户分组做 BIT_OR()操作就可以知道这个用户都购买过什么商品。

```mysql
mysql> create table order_rab (id int,customer_id int,kind int); 
Query OK, 0 rows affected (0.05 sec)  
mysql> insert into order_rab values (1,1,5),(2,1,4); 
Query OK, 2 rows affected (0.00 sec)  
mysql> insert into order_rab values (3,2,3),(4,2,4); 
Query OK, 2 rows affected (0.00 sec) 
mysql> select * from order_rab; 
+------+-------------+------+ 
| id   | customer_id | kind | 
+------+-------------+------+ 
| 1    | 1           | 5    | 
| 2    | 1           | 4    | 
| 3    | 2           | 3    | 
| 4    | 2           | 4    | 
+------+-------------+------+
```

其中 customerid 是顾客编号，kind 是所购买的商品，初始化了两个顾客 1 和 2 的数据，他们每人购物两次，前者购买的商品数值是 5 和 4，转化为二进制分别为 0101、0100，表示这个顾客第一次购买了牛奶和啤酒，第二次购买了牛奶；后者购买的商品数值是 3 和 4，转化为二进制分别为 0011、0100，表示这个顾客第一次购买了饼干和啤酒，第二次购买了牛奶。 
下面用 BIT_OR()函数与 GROUP BY 子句联合起来，统计一下这两个顾客在这个超市一共都购买过什么商品，如下例:

```mysql
mysql> select customer_id,bit_or(kind) from order_rab group by customer_id; 
+-------------+--------------+ 
| customer_id | bit_or(kind) | 
+-------------+--------------+ 
| 1           | 5            | 
| 2           | 7            | 
+-------------+--------------+
```

可以看到顾客 1 的 BIT_OR()结果是 5 即 0101，表示这个顾客在本超市购买过牛奶和啤酒；顾客 2 的 BIT_OR()结果是 7 即 0111，表示这个顾客在本超市购买过牛奶、饼干、啤酒。

## 17.4 小结 

本章讲述了在数据库开发时会用到的一些 SQL 小技巧和需要注意的问题。 

* 应用正则表达式可以使用户能够在一段很大的字符串中找到符合自己规则的一些
  语句，这个功能在进行匹配查找的时候非常有用。  
*  RAND()函数与 ORDER BY 字句的配合使用能够实现随机抽取样本的功能，这个技巧
  在进行数据统计的时候很方便。 
* GROUP BY 的 WITH ROLLUP 字句能够实现类似于 OLAP 的查询。 
* BIT 函数与 GROUP BY 子句的联合使用在某些应用场合可以大大降低存储量，提高
  统计查询效率。 
* MySQL 数据库名和表名的大小写与操作系统对大小写的敏感性关系密切，因此需
  要格外引起用户的注意。 
* MySQL 的外键功能仅对 InnoDB 存储引擎的表有作用，其他类型存储引擎的表虽然
  可以建立外键，但是并不能起到外键的作用。

# 18. SQL优化

## 18.1 优化SQL语句的一般步骤

### 18.1.1 通过 show status命令了解各种SQL的执行频率

​	MySQL客户端连接成功后，通过`show[session|global]status`命令可以提供服务器状态信息

```mysql
# 所有存储引擎的表统计信息
show status like 'Com_%';
# InnoDB相关的表统计信息
show status like 'Innodb_%';
# 查看数据库基本情况
# Connections：试图连接 MySQL 服务器的次数。 
# Uptime：服务器工作时间。 
# Slow_queries：慢查询的次数。
show status like 'Connections|Uptime|Slow_queries';
```

Com_xxx 表示每个 xxx 语句执行的次数，我们通常比较关心的是以下几个统计参数。 

* Com_select：执行 select 操作的次数，一次查询只累加 1。 
* Com_insert：执行 INSERT 操作的次数，对于批量插入的 INSERT 操作，只累加一次。 
* Com_update：执行 UPDATE 操作的次数。 
* Com_delete：执行 DELETE 操作的次数。

### 18.1.2 定位执行效率低的SQL语句

### 18.1.3 通过EXPLAIN分析低效率SQL的执行计划

 通过 EXPLAIN 或者 DESC 命令获取 MySQL如何执行 SELECT 语句的信息，包括在 SELECT 语句执行过程中表如何连接和连接的顺序。

### 18.1.4 确定问题并采取相应的优化措施

如果经过上述步骤已经分析出问题出现的原因，此时用户可以根据情况进行相应的优化。

比如全表扫描导致查询效率低可以考虑添加索引。

## 18.2 索引问题

### 18.2.1 索引的存储分类

MyISAM 存储引擎的表的数据和索引是自动分开存储的，各自是独立的一个文件；InnoDB存储引擎的表的数据和索引是存储在同一个表空间里面，但可以有多个文件组成。

MySQL 中索引的存储类型目前只有两种（BTREE 和 HASH），具体和表的存储引擎相关：**MyISAM 和 InnoDB 存储引擎都只支持 BTREE 索引；MEMORY/HEAP 存储引擎可以支持 HASH和 BTREE 索引**。

### 18.2.2 MySQL如何使用索引

**1、使用索引**

(1)多列索引，最左原则，查询的条件中用到了最左边的列，索引一般就会使用。

(2)like查询，后面如果是常量并且**只有%号不在第一个字符**，索引才可能被使用。

(3)如果对大的文本进行搜索，使用全文索引而不用使用 like ‘%…%’。

**2、存在索引但不使用索引**

(1)如果 MySQL 估计使用索引比全表扫描更慢，则不使用索引。例如如果列key_part1 均匀分布在 1 和 100 之间，下列查询中使用索引就不是很好：

```mysql
SELECT * FROM table_name where key_part1 > 1 and key_part1 < 90;
```

(2)or分割开的条件，如果or前的条件的列中有索引，而后面的列中没有索引，那么涉及到的索引都不会被用到。

(3)like后面的值以%开头

(4)如果列类型是字符串，那么一定记得在 where 条件中把字符常量值用引号引起来，否则的话即便这个列上有索引，MySQL 也不会用到的。

### 18.2.3 查看索引使用情况

如果索引正在工作，Handler_read_key 的值将很高，这个值代表了一个行被索引值读的次数，很低的值表明增加索引得到的性能改善不高，因为索引并不经常使用。 Handler_read_rnd_next 的值高则意味着查询运行低效，并且应该建立索引补救。这个值的含义是在数据文件中读下一行的请求数。如果正进行大量的表扫描，`Handler_read_rnd_next`的值较高，则通常说明表索引不正确或写入的查询没有利用索引，具体如下。

```mysql
mysql> show status like 'Handler_read%'; 
+-----------------------+-------+ 
| Variable_name         | Value | 
+-----------------------+-------+ 
| Handler_read_first    | 0     | 
| Handler_read_key      | 5     | 
| Handler_read_next     | 0     | 
| Handler_read_prev     | 0     | 
| Handler_read_rnd      | 0     | 
| Handler_read_rnd_next | 2055  | 
+-----------------------+-------+
```

## 18.3 两个简单实用的优化方法

### 18.3.1 定期分析表和检查表

```mysql
analyze table tb1_name[,tb2_name]...
check table tb_name...;
```

### 18.3.2 定期优化表

优化表的语法如下：

```mysql
OPTIMIZE [LOCAL | NO_WRITE_TO_BINLOG] TABLE tbl_name [, tbl_name] ...
```

如果已经删除了表的一大部分，或者如果已经对含有可变长度行的表（含有 VARCHAR、BLOB 或 TEXT 列的表）进行了很多更改，则应使用 OPTIMIZE TABLE 命令来进行表优化。这个命令可以将表中的空间碎片进行合并，并且可以消除由于删除或者更新造成的空间浪费，但OPTIMIZE TABLE 命令只对 MyISAM、BDB 和 InnoDB 表起作用。

>ANALYZE、CHECK、OPTIMIZE 执行期间将对表进行锁定，因此一定注意要在数据库不繁忙的时候执行相关的操作。

## 18.4 常用SQL的优化

搜索资料了解，

```mysql
USE INDEX(index_name...);
IGGNORE INDEX(index_name...);
FORCE INDEX(index_name...);
```

# 19. 优化数据库对象

## 19.1 优化表的数据类型

在MySQL中，可以使用PROCEDURE ANALYSE()对当前应用的表进行分析，该函数可以对数据表列的数据类型提出优化建议，用户可以根据应用的实际情况酌情考虑是否实施优化。

使用方法：

```mysql
select * from tb_name procedure analyse();
# 不为那些包含的值多于16个或者256字节的ENUM类型提出建议
select * from tb_name procedure analyse(16,256);
```

## 19.2 通过拆分提高表的访问效率

这里所说的**“拆分”，是指对数据表进行拆分**。如果针对 **MyISAM** 类型的表进行拆分，那么有两种拆分方法。

(1)垂直拆分

将表中的包含的列部分拆开，转移到另一个表。垂直拆分可以按以下原则进行：

* 把不常用的字段单独存放到一个表中
* 把大字段独立存放到一个表中
* 把经常一起使用的字段放一起

(2)水平拆分

表的水平拆分是为了解决单表的数据量过大的问题，水平拆分的表每一个表的结构都是一致的。

## 19.3 逆规范化

规范化越高，那么产生的关系就越多，关系过多的直接结果就是导致表之间的连接操作越频繁，而表之间的连接操作是性能较低的操作，直接影响到查询的速度，所以对于查询较多的应用就需要根据实际情况运用逆规范化对数据进行设计，通过逆规范化来提高查询的性能。 
反规范的好处是降低连接操作的需求、降低外码和索引的数目，还可能减少表的数目，相应带来的问题是可能出现数据的完整性问题。

常用的反规范技术有：**增加冗余列**、增加派生列、重新组表和分割表。

（1）增加冗余列：指在多个表中具有相同的列，它常用来在查询时避免连接操作。

（2）增加派生列：指增加的列来自其他表中的数据，由其他表中的数据经过计算生成。增加的派生列其作用是在查询时减少连接操作，避免使用集函数。

（3）重新组表：指如果许多用户需要查看两个表连接出来的结果数据，则把这两个表重新组成一个表来减少连接而提高性能。

（4）分割表：根据需求将一个表分割成多个表存储。

逆规范技术需要维护数据的完整性。无论使用何种反规范技术，都需要一定的管理来维护数据的完整性，常用的方法是批处理维护、应用逻辑和触发器。

（1）批处理维护：指对复制列或派生列的修改积累一定的时间后，运行一批处理作业或存储过程对复制或派生列进行修改，这只能在对实时性要求不高的情况下使用。

（2）数据的完整性也可由应用逻辑来实现，这就要求必须在同一事务中对所有涉及的表进行增、删、改操作。用应用逻辑来实现数据的完整性风险较大，因为同一逻辑必须在所有的应用中使用和维护，容易遗漏，特别是在需求变化时，不易于维护。

（3）另一种方式就是使用触发器，对数据的任何修改立即触发对复制列或派生列的相应修改。触发器是实时的，而且相应的处理逻辑只在一个地方出现，易于维护。一般来说，是解决这类问题比较好的办法。逆规范技术需要维护数据的完整性。无论使用何种反规范技术，都需要一定的管理来维护数据的完整性，常用的方法是批处理维护、应用逻辑和触发器。

（1）批处理维护：指对复制列或派生列的修改积累一定的时间后，运行一批处理作业或存储过程对复制或派生列进行修改，这只能在对实时性要求不高的情况下使用。

（2）数据的完整性也可由应用逻辑来实现，这就要求必须在同一事务中对所有涉及的表进行增、删、改操作。用应用逻辑来实现数据的完整性风险较大，因为同一逻辑必须在所有的应用中使用和维护，容易遗漏，特别是在需求变化时，不易于维护。

（3）另一种方式就是使用触发器，对数据的任何修改立即触发对复制列或派生列的相应修改。触发器是实时的，而且相应的处理逻辑只在一个地方出现，易于维护。一般来说，是解决这类问题比较好的办法。

## 19.4 使用中间表提高统计查询速度

对于数据量较大的表，在其上进行统计查询通常会效率很低，并且还要考虑统计查询是否会对在线的应用产生负面影响。通常在这种情况下，使用中间表可以提高统计查询的效率。

中间表在统计查询中经常会用到，其优点如下: 

* 中间表复制源表部分数据，并且与源表相“隔离”，在中间表上做统计查询不会对在线应用产生负面影响。
* 中间表上可以灵活的添加索引或增加临时用的新字段,从而达到提高统计查询效率和辅助统计查询作用。

# 20. 锁问题

锁时计算机协调多个进程或线程并发访问某一资源的机制，并发访问控制的基础。

## 20.1 MySQL锁概述

MySQL不同的存储引擎支持不同的所机制。比如，MyISAM和MEMORY使用的是表级锁(table-level locking);BDB存储引擎采用的是页面锁（page-level locking），但也支持表级锁；InnoDB存储引擎既支持行级锁(row-level locking)，也支持表级锁，默认情况下采用的是行级锁。

MySQL锁的特性

* 表级锁：开销小，加锁快，**无死锁**，锁定粒度大，锁冲突概率最高，并发度最低
* 行级锁：开销大，加锁慢，**存在死锁**，锁定粒度小，锁冲突概率最小，并发度最高
* 页面锁：特点介于行级锁和表级锁之间

> MyISAM不支持事务，所以对其设置 `set autocommit = 0`无效，只有对支持事务的存储引擎（InnoDB）才生效。

## 20.2 MyISAM表锁

MyISAM 存储引擎只支持表锁，如果对并发要求不高，并且主要以查询为主的业务，可以采用MyISAM。

### 20.2.1 MySQL表级锁的锁模式

MySQL 的表级锁有两种模式：**表共享读锁**（Table Read Lock）和**表独占写锁**（Table Write Lock）。

锁模式的兼容性如下：

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192132.png)

根据上图，对于存储引擎为MyISAM的表，不会阻塞其他用户对表加读锁，**可以对表加多个读锁**，但会阻塞对同一表加多个写锁；对 MyISAM 表的写操作，则会阻塞其他用户对同一表的读和写操作；**MyISAM 表的读操作与写操作之间，以及写操作之间是串行的**！

> 对表加读锁，会话都可读，不可写，但是加锁的会话不能读其它未加锁的表。
>
> 对表加写锁，只有加锁的会话能读写表，其余会话不可读写表。

表级锁的加锁和解锁语句：

```mysql
LOCK TABLES
    tbl_name [[AS] alias] lock_type
    [, tbl_name [[AS] alias] lock_type] ...

lock_type: {
    READ [LOCAL]
  | [LOW_PRIORITY] WRITE
}

UNLOCK TABLES;
```

下面演示了当一个线程获得对一个表的写锁后，只有持有锁的线程可以对表进行更新操作。其他线程的读、写操作都会等待，直到锁被释放为止。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192126.png)

### 20.2.2 如何加表锁

**MyISAM 在执行查询语句（SELECT）前，会自动给涉及的所有表加读锁，在执行更新操作（UPDATE、DELETE、INSERT 等）前，会自动给涉及的表加写锁**，这个过程并不需要用户干预，因此，用户一般不需要直接用 LOCK TABLE 命令给 MyISAM 表显式加锁。

给 MyISAM 表显示加锁，一般是为了在一定程度模拟事务操作，实现对某一时间点多个表的一致性读取。

在用 LOCK TABLES 给表显式加表锁时，必须同时取得所有涉及到表的锁，并且 MySQL 不支持锁升级。也就是说，**在执行 LOCK TABLES 后，只能访问显式加锁的这些表，不能访问未加锁的表**；同时，**如果加的是读锁，那么只能执行查询操作，而不能执行更新操作**。其实，在自动加锁的情况下也基本如此，MyISAM 总是一次获得 SQL 语句所需要的全部锁。这也正是 MyISAM 表不会出现死锁（Deadlock Free）的原因。

一个 session 使用 LOCK TABLE 命令给表 film_text 加了读锁，**这个 session 可以查询锁定表中的记录，但更新或访问其他表都会提示错误**；同时，另外一个session 可以查询表中的记录，但更新就会出现锁等待。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192122.png)

### 20.2.3 并发插入(Concurrent Inserts)

上文提到过 MyISAM 表的读和写是串行的，但这是就总体而言的。在一定条件下，MyISAM表也支持查询和插入操作的并发进行，在对表读操作的同时，进行更新操作。

MyISAM存储引擎有一个系统变量concurrent_insert，专门用以控制其并发插入的行为，其值分别可以为0、1或2。 

* 当concurrent_insert设置为0时，不允许并发插入。 
* 当concurrent_insert设置为1时，如果MyISAM表中没有空洞（即表的中间没有被删除的行），MyISAM允许在一个进程读表的同时，另一个进程从表尾插入记录。这也是MySQL的默认设置。 
* 当concurrent_insert设置为2时，无论MyISAM表中有没有空洞，都允许在表尾并发插入
  记录。

### 20.2.4 MyISAM的锁调度

MyISAM存储引擎的读锁和写锁是互斥的，读写操作是串行的。那么，一个进程请求某个 MyISAM 表的读锁，同时另一个进程也请求同一表的写锁，MySQL 如何处理呢？
答案是**写进程先获得锁**。即使读请求先到锁等待队列，写请求后到，写锁也会插到读锁请求之前！这是因为MySQL 认为写请求一般比读请求要重要。这也正是 MyISAM 表不太适合于有大量更新操作和查询操作应用的原因，因为大量的更新操作会造成查询操作很难获得读锁，从而可能永远阻塞。这种情况有时可能会变得非常糟糕！幸好我们可以通过一些设置来调节 MyISAM 的调度行为。

* 通过指定启动参数low-priority-updates，使MyISAM引擎默认给予读请求以优先的权利。 
* 通过执行命令SET LOW_PRIORITY_UPDATES=1，使该连接发出的更新请求优先级降低。 
* 通过指定INSERT、UPDATE、DELETE语句的LOW_PRIORITY属性，降低该语句的优先级。

## 20.3 InnoDB锁问题

InnoDB与MyISAM的最大不同有两点：一是支持事务（TRANSACTIONS）；而是采用了行级锁。

### 20.3.1 事务基础

**1、事务及其ACID属性**

不在阐述。

**2、并发事务处理带来的问题**

相对于串行处理，并发事务处理能大大增加数据库资源的利用率，提高数据库系统的事务吞吐量。但并发事务处理也会带来一些问题，主要有：**更新丢失、脏读、不可重复读、幻读**。

> 更新丢失属于应用层面，不属于数据库系统的管理范畴。

**3、事务隔离级别**

“脏读”、“不可重复读”和“幻读”，其实都是数据库读一致性问题，必须由数据库提供一定的事务隔离机制来解决。

数据库实现事务隔离的方式，基本上可分为以下两种。 

* 一种是在读取数据前，对其加锁，阻止其他事务对数据进行修改。 
* 另一种是不用加任何锁，通过一定机制生成一个数据请求时间点的一致性数据快照（Snapshot)，并用这个快照来提供一定级别（语句级或事务级）的一致性读取。从用户的角度来看，好象是数据库可以提供同一数据的多个版本，因此，这种技术叫做数据多版本并发控制（MultiVersion Concurrency Control，简称 MVCC 或MCC），也经常称为多版本数据库。 

**数据库的事务隔离越严格，并发副作用越小，但付出的代价也就越大**，因为事务隔离实质上就是使事务在一定程度上“串行化”进行，这显然与“并发”是矛盾的。

### 20.3.2 InnoDB的行锁模式及加锁方法

InnoDB实现标准的行级锁定，其中有两种类型的锁定：

* **共享（S）锁**：允许持有该锁的事务读取一行。

* **排他（X）锁定**：允许持有该锁的事务更新或删除行。

如果事务T1在行r上持有一个共享（S）锁，那么来自某些不同事务T2的对行r上的锁的请求将按以下方式处理：

* T2可以请求S锁可以立即获得，T1和T2都在r上保持了S锁
* T2不能立即授予X锁请求。

如果事务T1在行r上拥有排他（X）锁，则不能立即批准某个不同事务T2对r上任一类型的锁的请求。相反，事务T2必须等待事务T1释放对行r的锁定。

InnoDB为了支持多种粒度锁定，允许行锁和表锁并存。

InnoDB 还有两种内部使用的意向锁（Intention Locks）意向锁是**表级锁**，指示事务稍后对表中的行需要哪种类型的锁（共享锁或排他锁）。有两种类型的意图锁：

* 意向共享锁（IS）：事务打算给数据行加行共享锁，事务在给一个数据行加共享锁前必须先取得该表的 IS 锁。 
* 意向排他锁（IX）：事务打算给数据行加行排他锁，事务在给一个数据行加排他锁前必须先取得该表的 IX 锁。

InnoDB行锁模式兼容性列表：

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192117.png)

如果一个事务请求的锁模式与当前的锁兼容，InnoDB 就将请求的锁授予该事务；反之，如果两者不兼容，该事务就要等待锁释放。

> 意向锁除了全表请求（例如LOCK TABLES ... WRITE）以外，不阻止任何其他内容。意图锁定的主要目的是表明有人正在锁定表中的行，或者打算锁定表中的行。

**意向锁是InnoDB自动加的，不需要用户干预。对于 UPDATE、DELETE 和 INSERT 语句，InnoDB会自动给涉及数据集加排他锁（X)；对于普通 SELECT 语句，InnoDB 不会加任何锁**；事务可以通过以下语句显示给记录集加共享锁或排他锁。 

* 共享锁（S）：`SELECT * FROM table_name WHERE ... LOCK IN SHARE MODE` 
*  排他锁（X)：`SELECT * FROM table_name WHERE ... FOR UPDATE` 

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192114.png)

当使用SELECT...FOR UPDATE加锁后再更新记录，出现如表20-8所示的情况。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921192110.png)

### 20.3.3 InnoDB行锁实现方式

InnoDB**行锁**是通过给索引上的**索引项加锁**来实现的。**只有通过索引条件检索数据，InnoDB才使用行级锁，否则，InnoDB将使用表锁**！

(1)在不通过索引条件查询的时候，InnoDB使用的是表锁，而不是行锁。

> 加锁是给索引项加锁。现在T1会话通过索引查询并加锁，那么此会话中获得行锁，如果T2会话也通过索引查询并加锁，若不是同一条记录则不会BLOCK，否则BLOCK，若获得锁也是行锁；若果T2会话不是通过索引查询，如果加锁肯定是加表锁，但是此时T1会话持有IS锁或者IX锁，根据意向锁的性质，不能再次为其加表锁，所以此时会话就会出现等待。

(2)由于 MySQL 的行锁是针对索引加的锁，不是针对记录加的锁，所以虽然是访问不同行的记录，但是如果是使用相同的索引键，是会出现锁冲突的。

> 演示时，一定要关闭自动提交模式

(3)当表有多个索引的时候，不同的事务可以使用不同的索引锁定不同的行，另外，不论是使用主键索引、唯一索引或普通索引，InnoDB 都会使用行锁来对数据加锁。

![](https://gitee.com/git_wjx/picture_bed/raw/master/20200921191911.png)

### 20.3.4 间隙锁（Next-Key锁）

> 这地方，我感觉树中讲解的不是很好，大家可以网上看官方文档，或者搜索资料。

InnoDB 存储引擎有三种行锁的算法，其分别是：

- Record Lock: 单个行记录上的锁
- Gap Lock: 间隙锁，锁定一个范围，但不包含记录本身
- Next-Key 锁: Gap Lock + Record Lock，锁定一个范围，并且会锁定记录本身

<hr>

当我们用**范围条件而不是相等条件检索数据**，并请求共享或排他锁时，InnoDB 会给符合条件的**已有数据记录的索引项**加锁；对于键值在条件范围内但并不存在的记录，叫做“间隙（GAP)”，InnoDB 也会对这个“间隙”加锁，这种锁机制就是所谓的间隙锁（Next-Key 锁）。

假如 emp 表中只有 101 条记录，其 empid 的值分别是 1,2,...,100,101，下面的 SQL：

```mysql
Select * from  emp where empid > 100 for update;
```

是一个范围条件的检索，InnoDB 不仅会对符合条件的 empid 值为 101 的记录加锁，也会对empid 大于 101（这些记录并不存在）的“间隙”加锁。

InnoDB **使用间隙锁的目的**，**一方面是为了防止幻读**，以满足相关隔离级别的要求，对于上面的例子，要是不使用间隙锁，如果其他事务插入了 empid 大于 100 的任何记录，那么本事务如果再次执行上述语句，就会发生幻读；另外一方面，是为了满足其恢复和复制的需要。

>InnoDB 除了通过范围条件加锁时使用间隙锁外，如果使用相等条件请求给一个不存在的记录加锁，InnoDB 也会使用间隙锁！

### 20.3.5 恢复和复制的需要，对 InnoDB 锁机制的影响

MySQL 通过 **BINLOG** 录执行成功的 INSERT、UPDATE、DELETE 等更新数据的 SQL 语句，并由此实现 MySQL 数据库的恢复和主从复制。

MySQL恢复机制的特点：

1. MySQL 的恢复是 SQL 语句级的，也就是重新执行 BINLOG 中的 SQL 语句。
2.  MySQL 的 Binlog 是按照事务提交的先后顺序记录的，恢复也是按这个顺序进行的。

MySQL 的恢复机制要求：**在一个事务未提交前，其他并发事务不能插入满足其锁定条件的任何记录，也就是不允许出现幻读**，这已经超过了 ISO/ANSI SQL92“可重复读”隔离级别的要求，实际上是要求事务要串行化。

# 21. 优化MySQL Server

之前提到过，MySQL的优化，从基础层面有SQL语句的优化，表字段数据库对象的优化。另外MySQL还有本节将要介绍的Server层面上的优化。

为什么要优化？

通常一个应用的吞吐量瓶颈往往出现在数据库中的处理速度上，随着应用的使用，数据库数据逐渐增多，数据库处理压力逐渐增大，关系型数据库的数据是存放在磁盘上的，IO速度远远小于ROM。所以说通过优化，减少系统瓶颈和资源的占用，提高系统反应速度。

例如：

1. 通过优化文件系统，来提高磁盘I/O的独写速度；
2. 通过优化操作系统的调度策略，提高MySQL在高负荷情况下的负载能力；
3. 通过优化表结构、索引、查询语句等使得查询响应更快。

## 21.1MySQL体系结构

MySQL实例由一组后台线程、一些内存块和若干服务线程组成。

后台线程包括：

- 主线程：主要负责将脏缓存页刷新到数据文件，执行purge操作，触发检查点，合并插入缓冲区等。
- IO线程：
  - insert buffer线程：主要负责插入缓冲区的合并操作。
  - read线程：负责数据库读操作，可配置多个读线程。
  - write线程：负责数据库写操作，可配置多个写线程。
  - log线程：将重做日志刷新到logfile中。
- 锁线程：负责锁控制和死锁检测。
- 错误监控线程：主要负责错误监控和错误处理。
- purge线程：MySQL5.5之后用单独的线程执行purge操作。

可通过`SHOW ENGINE INNODB STATUS`查看线程的状态。

## 21.2 查看MySQL Server参数

* `show variables:`：查看MySQL服务器静态参数值。数据库启动会不会动态更改的值，比如buffer_size、character_set、数据文件名称等。

* `show status`：查看MySQL服务器动态运行状态信息。如锁等待、当前连接数等。

内存优化原则：

- 将尽量多的内存分配给MySQL做缓存，但要给操作系统和其他应用程序的运行预留足够的内存，否则如果产生SWAP页交换，将严重影响系统性能。
- MyISAM的数据文件读取依赖于操作系统自身的IO缓存，因此，如果有MyISAM表，就要预留更多的内存给操作系统做IO缓存。
- 排序区、连接区等缓存是分配给每个数据库会话专用的，其默认值的设置要根据最大连接数合理分配，如果设置太大，不但浪费内存资源，而且在并发连接较高时会导致物理内存耗尽。

## 21.3 MyISAM内存优化

MyISAM存储引擎使用**索引缓存（key buffer）缓存索引块**，对于数据块没有特别的缓存机制，完全依赖于操作系统的IO缓存。

### 21.3.1 索引缓存

**key_buffer_size设置**

key_buffer_size决定MyISAM索引缓存区的大小，它直接影响MyISAM表的存取效率。建议至少分配1/4可用物理内存。

通过检查系统状态变量可评估MyISAM缓存的效率：

* 读比率：key_reads/key_read_requests，一般应小于0.01。
* 写比率：key_writes/key_write_requests，对于更新和删除特别多的应用可能接近1，对于每次更新很多行的应用就会比较小。
* 使用率：1-(key_blocks_unused*key_cache_block_size/key_buffer_size)，一般在0.8左右比较合适。

```mysql
mysql> show variables like 'key_%';
+--------------------------+---------+
| Variable_name            | Value   |
+--------------------------+---------+
| key_buffer_size          | 8388608 |
| key_cache_age_threshold  | 300     |
| key_cache_block_size     | 1024    |
| key_cache_division_limit | 100     |
+--------------------------+---------+
4 rows in set (0.00 sec)

mysql> show status like 'key_%';
+------------------------+-------+
| Variable_name          | Value |
+------------------------+-------+
| Key_blocks_not_flushed | 0     |
| Key_blocks_unused      | 7173  |
| Key_blocks_used        | 2     |
| Key_read_requests      | 8     |
| Key_reads              | 4     |
| Key_write_requests     | 0     |
| Key_writes             | 0     |
+------------------------+-------+
```

**使用多索引缓存**

多索引缓存机制，可以**将不同的表索引缓存存放到不同的key buffer中**，减少session键对key buffer的竞争导致数据被淘汰。

```mysql
# 创建新的索引缓存：
set global key_buffer_name.key_buffer_size = n;
# 删除索引缓存：
# 注意：不能删除默认key_bufffer
set global key_buffer_name.key_buffer_size = 0;
# 指定表的索引缓存（不指定则使用默认索引缓存）
cache index tb_name[,...] in key_buffer_name;
# 将索引预装到默认key_buffer中
load index into cache tb_name[,...];
```

### 21.3 table_cache

每个连接进来，都会至少打开一个表缓存。因此，table_cache 与 max_connections 有关，例如，对于 200 个并行运行的连接，应该让表的缓存至少有 200×N，这里 N 是可以执行的查询的一个联接中表的最大数量。

可以通过检查mysqld的状态变量open_tables和opened_tables确定这个参数是否过小;

* `open_tables`：表示当前session打开的表缓存数，值不会随每次查询累加。
* `opened_tables`：表示曾经打开的表缓存数。值会随每次查询累加。

```mysql
mysql> show status like 'open_tables';
+---------------+-------+
| Variable_name | Value |
+---------------+-------+
| Open_tables   | 1     |
+---------------+-------+
1 row in set (0.00 sec)

mysql> show status like 'opened_tables';
+---------------+-------+
| Variable_name | Value |
+---------------+-------+
| Opened_tables | 2     |
+---------------+-------+
```

## 21.4 InnoDB内存优化

### 21.4.1 innodb_buffer_pool_size的设置

这个参数定义了 InnoDB 存储引擎的表数据和索引数据的最大内存缓冲区大小。和MyISAM 存储引擎不同，MyISAM 的 key_buffer_size 只缓存索引键，而 **innodb_buffer_pool_size却是同时为数据块和索引块做缓存**，这个特性和 Oracle 是一样的。这个**值设得越高**，访问表中数据需要的**磁盘 I/O 就越少**。在专用数据库服务器上，可分配80%的物理内存。

可通过`SHOW STATUS LIKE 'innodb_buffer_pool%'`查看缓存池的使用情况。

InnoDB缓存池命中率：1-innodb_buffer_pool_reads/innodb_buffer_pool_read_request。

```mysql
mysql> show status like 'innodb_buffer_pool%';
+---------------------------------------+-------------+
| Variable_name                         | Value       |
+---------------------------------------+-------------+
| Innodb_buffer_pool_dump_status        | not started |
| Innodb_buffer_pool_load_status        | not started |
| Innodb_buffer_pool_pages_data         | 470         |
| Innodb_buffer_pool_bytes_data         | 7700480     |
| Innodb_buffer_pool_pages_dirty        | 0           |
| Innodb_buffer_pool_bytes_dirty        | 0           |
| Innodb_buffer_pool_pages_flushed      | 20          |
| Innodb_buffer_pool_pages_free         | 1961        |
| Innodb_buffer_pool_pages_misc         | 1           |
| Innodb_buffer_pool_pages_total        | 2432        |
| Innodb_buffer_pool_read_ahead_rnd     | 0           |
| Innodb_buffer_pool_read_ahead         | 0           |
| Innodb_buffer_pool_read_ahead_evicted | 0           |
| Innodb_buffer_pool_read_requests      | 20445       |
| Innodb_buffer_pool_reads              | 470         |
| Innodb_buffer_pool_wait_free          | 0           |
| Innodb_buffer_pool_write_requests     | 28          |
+---------------------------------------+-------------+
```

### 21.4.2 InnoDB日志优化

当更新数据时，InnoDB内部的操作流程大致是：

1. 将数据写入缓存池，并对相关记录加独占锁。
2. 将UNDO信息写入undo表空间的回滚段中。
3. 更新缓存页中的数据，并将更新记录写入重做日志缓存池（另一个redo buffer）中。
4. 提交时，根据innodb_flush_log_at_trx_commit的设置，用不同的方式将重做日志缓存池中的更新记录刷新到重做日志文件中，然后释放独占锁。
5. 后台IO线程根据需要择机将缓存中更新过的数据刷新到磁盘文件中。

**innodb_flush_log_at_trx_commit设置**

- 值为0：在事务提交时，不会立即将缓存中的redo日志写到磁盘文件，而是每秒触发一次，并调用操作系统fsync刷新IO缓存。如果数据库崩溃，数据就会丢失。
- 值为1（默认值）：事务提交时，立即将缓存中的redo日志回写到磁盘文件，并调用操作系统fsync刷新IO缓存。
- 值为2：事务提交时，立即将缓存中的redo日志回写到磁盘文件，但并不马上调用fsync刷新IO缓存，而是每秒触发一次。如果数据库崩溃，只要操作系统没有崩溃，数据就不会丢失。

### 21.4.3 其他参数

innodb_lock_wait_timeout：MySQL 可以自动地监测行锁导致的死锁并进行相应的处理，但是对于表锁导致的死锁不能自动的监测，所以该参数主要被用于在出现类似情况的时候等待指定的时间后回滚。系统默认值是 50 秒，用户可以根据应用的需要进行调整。

innodb_log_buffer_size决定InnoDB重做日志缓存池的大小，默认是8MB。

## 21.5 MySQL并发相关参数

**max_connections设置**

max_connections控制允许连接到MySQL数据库的最大数量，默认是151。

如果状态变量connection_errors_max_connections不为0且一直增长，说明不断有连接请求因数据库连接数已达到最大允许值而失败。

 **table_open_cache设置**

table_open_cache控制所有SQL执行线程可打开的表缓存数量。该值应设置为：max_connections*N，N为每个连接执行关联查询时所涉及到的表的最大个数。

**thread_cache_size设置**

thread_cache_size控制MySQL缓存可供重用的客户服务线程的数量。

可以通过线程cache的失效率threads_created/connections来衡量tread_cache_size的设置是否合适。

**innodb_lock_wait_timeout设置**

innodb_lock_wait_timeout可以控制InnoDB事务等待行锁的时间，默认为50ms。

# 22. 磁盘I/O问题

作为应用系统的持久化层，不管数据库采取了什么样的 Cache 机制，但数据库最终总是要将数据储存到可以长久保存的I/O设备──磁盘上，但磁盘的存取速度显然要比CPU、RAM 的速度慢很多，因此，对于比较大的数据库，磁盘 I/O 一般总会成为数据库的一个性能瓶颈！

我们前面提到的 SQL 优化、数据库对象优化、数据库参数优化，以及应用程序优化等，**大部分都是想通过减少或延缓磁盘读写来减轻磁盘 I/O 的压力及其对性能的影响**。解决磁盘 I/O 问题，减少或延缓磁盘操作肯定是一个重要方面，但磁盘 I/O 是不可避免的，因此，增强磁盘 I/O 本身的性能和吞吐量也是一个重要方面。

## 22.1 使用磁盘阵列

## 22.2 使用Symbolic Links分布I/O

MySQL 的数据库名和表名是与文件系统的目录名和文件名对应的，默认情况下，创建的数据库和表都存放在参数 datadir 定义的目录下。这样如果不使用 RAID 或逻辑卷，所有的表都存放在一个磁盘设备上，无法发挥多磁盘并行读写的优势！在这种情况下，我们就可以利用操作系统的符号连接（Symbolic Links）将不同的数据库或表、索引指向不同的物理磁盘，从而达到分**布磁盘 I/O** 的目的。

（1）将一个数据库指向其他物理磁盘

（2）将MyISAM（其他存储引擎的表不支持）表的数据文件或索引文件指向其他物理磁盘。

（3）在Windows下使用符号连接。

## 22.3 禁止操作系统更新文件的atime属性

atime 是 Linux/UNIX 系统下的一个文件属性，每当读取文件时，操作系统都会将读操作发生的时间回写到磁盘上。对于读写频繁的数据库文件来说，记录文件的访问时间一般没有任何用处，却会增加磁盘系统的负担，影响 I/O 的性能！因此，可以通过设置文件系统的 mount属性，阻止操作系统写 atime 信息，以减轻磁盘 I/O 的负担。

## 22.4 用裸设备(Raw Device)存放InnoDB的共享表空间

MyISAM 存储引擎有自己的索引缓存机制，但数据文件的读写完全依赖于操作系统，操作系统磁盘 I/O 缓存对 MyISAM 表的存取很重要。但 InnoDB 存储引擎与 MyISAM 不同，它采用类似 Oracle 的数据缓存机制来 Cache 索引和数据，操作系统的磁盘 I/O 缓存对其性能不仅没有帮助，甚至还有反作用。因此，在 InnoDB 缓存充足的情况下，可以考虑使用 Raw Device 来存放 InnoDB 共享表空间。

# 23. 应用优化

## 23.1 使用连接池

对于访问数据库来说，建立连接的代价比较昂贵，因此，可以通过建立“连接池”提高访问的性能。

连接池：**把连接当做对象或者设备，统一放在一个“池子”中，，以前需要直接访问数据库的地方，现在都改为从这个“池子”里面获取连接来使用**。因为“池子”中的连接都已经预先创建好，可以直接分配给应用使用，因此大大减少了创建新连接所耗费的资源。

## 23.2 减少对MySQL的访问

### 23.2.1 避免对同一数据做重复检索

应用中需要理清对数据库的访问逻辑。能够一次连接就能够提取出所有结果的，就不用两次连接，这样可以大大减少对数据库无谓的重复访问。

> 编写SQL代码的逻辑问题

### 23.2.2 使用查询缓存

MySQL 的查询缓存（MySQL Query Cache）是在 4.1 版本以后新增的功能，它的作用是存储 SELECT 查询的文本以及相应结果。如果随后收到一个相同的查询，服务器会从查询缓存中重新得到查询结果，而不再需要解析和执行查询。 

**查询缓存的适用对象是更新不频繁的表，当表更改（包括表结构和表数据）后，查询缓存值的相关条目被清空。** 

### 23.2.3 增加 CACHE 层

在应用中，我们可以在应用端加 CACHE 层来达到减轻数据库的负担的目的。CACHE 层有很多种，也有很多种实现的方式，只要能达到降低数据库的负担，又能满足应用就可以，这就需要根据应用的实际情况进行特殊处理。 
比如，可以把部分数据从数据库中抽取出来放到应用端以文本方式存储，然后有查询需求的话，可以直接从这个“CACHE”中检索。或者可以在应用端建立一个二级数据库，将访问高频数据放在二级库上，然后设定一个机制与主数据库进行同步。可以大大降低主数据库的压力。

## 23.3 负载均衡

负载均衡（Load Balance）是实际应用中使用非常普遍的一种优化方法，它的机制就是利用某种均衡算法，将固定的负载量分布到不同的服务器上，以此来减轻单台服务器的负载，达到优化的目的。**负载均衡可以用在系统中的各个层面中，从前台的 Web 服务器到中间层的应用服务器，最后到数据层的数据库服务器，都可以使用。**

### 23.3.1 利用 MySQL 复制分流查询操作

**主从复制**：具体的实现是一个主服务器承担更新操作，而多台从服务器承担查询操作，主从之间通过复制实现数据的同步。多台从服务器一方面用来确保可用性，一方面可以创建不同的索引以满足不同查询的需要。

### 23.3.2 采用分布式数据库架构

**集群**（Cluster）

分布式的数据库架构适合大数据量、负载高的情况，它具有良好的扩展性和高可用性。