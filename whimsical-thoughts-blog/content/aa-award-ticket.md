---
title: '用Python追踪AA里程票Availability'
date: 2024-08-01T18:09:02-04:00
description: "还没写细节呢"
tags: [AA]
featured_image: "/images/DSC07301.jpg"
categories: 航空
comment : false
hidden: false
---
- 取aa award calendar api 
- postman取api返回的json示例
- postman生成python调用api的code
- 用gpt按照json示例生成筛选可用性的代码
- 合并上两步的代码-修改Postman生成的代码和gpt生成的代码
- 本地试运行
- 自动运行：
	O1 - python脚本里面加个循环无限运行
	O2 - win上部署有定时任务可以用，linux上一般就是cronjob，另外python还有很多包可以实现定时任务，比如apscheduler这种。（每段时间运行一次code）
	O3 - 部署到狗云，把python script 部署到cloud function 查票，然后结果上传到数据库 (Bigquery), 然后用looker studio 做一个简单的图表。cloud scheduler & pubsub 设置每个小时就自动查一次。数据量小，所以都是免费的。想看到时候，我自己点到 lookerstudio 网站看就行。
- 查到票显示链接
- cf 可以自动发邮件 or slack msg 给自己。


可选：
代理池

其他：
api可以做到1min一次 ip被ban半分钟复活