---
layout: post
title: 系统分析与设计-Lesson-4-作业
date: 2018-04-22 23:00:00+08:00
categories: 作业
tags: 博客
---

# 系统分析与设计 Lesson 4

## 1. 用例建模

### a. 阅读Asg_RH文档，绘制用例图。按Task1要求，请使用工具UMLet，截图格式务必是png并控制尺寸

如下UML图，其中关于外部系统"hotel database"的使用其实与"search hotels"以及"choose hotel"两个用例均有关，但在Use case上只是与一些具体子用例相关联：

![task 1 uml](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\task-1-reserve-hotel-uml.png)

### b. 选择你熟悉的订旅馆在线服务系统（或移动APP），如绘制用例图。并满足以下要求：<br/>- 对比Asg_RH用例图，请用色彩标注出创新用例或子用例<br/>- 尽可能识别外部系统，并用色彩标注新的外部系统和服务

　　本次个人选择的是去哪儿网站中的订旅馆在线服务系统进行用例分析。

#### 去哪儿网站订旅馆基本流程：

　　下面提供了个人在未登录状态下使用去哪儿网站订旅馆过程的截图，其中将与Asg_RH中例子区别的主要创新用例或子用例用红框框出。

##### 搜索旅馆：

　　这部分的创新用例包括了选择境内外酒店、高级搜索酒店、地图搜索以及根据每日酒店推荐搜索。

![search hotels](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-search-hotels.PNG)

##### 选择旅馆：

　　这里额外提供了按条件筛选酒店的功能。

![choose hotel](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-choose-hotel.PNG)

##### 选择房间：

　　增加了用户点评、酒店设施概况、酒店位置交通、多个预订网站选择等等功能。

![choose room](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-choose-room-type.PNG)

##### 确认订单：

![confirm reservation](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-confirm-reservation.PNG)

　　下面是预定完成后的预定信息，可以进一步选择取消订单或打印：

![view reservation info](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-view-reservation-info.PNG)

##### 支付：

　　支付方式有多种类型。

![pay](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-pay.PNG)

#### 用例图

　　其中红色用例表示创新用例或子用例，绿色外部Actors表示新的外部系统或服务，黄色注释也是与Asg_RH中网站所包括的不同点。另外，需要强调的是，去哪儿网站已经发展非常成熟，因而与文档中的旧网站相比，有更多的功能和服务，也就有更多的用例，用例图更加复杂。下列用例图也只是选择了主要的用例，尽可能地详细绘制，但实际上也有相当多的用例被选择忽略，因而请阅者体谅。

![qunar reserve hotel use case diagram](D:\Programming\GitHub Desktop\ReganFan.github.io\assets\2018-04-22-course-assignment-4-diagram\qunar-reserve-hotel.png)

### c. 对比两个时代、不同地区产品的用例图，总结在项目早期，发现创新的思路与方法

　　通过比较两个产品的用例图，可以发现出两个产品之间的异同点，首先是相同点：

1. 两个产品用例图的主要用例是一致的，比如两者均包含预订酒店用例，同时该用例的子用例也是相同，有搜索酒店、选择酒店、选择房间和确认订单，还有支付用例等等，因为这些均是在线预订酒店平台所必须具备的基本功能。
2. 上述提到的基本用例的扩展点是类似的，比如两者的选择酒店用例的扩展点都有搜索酒店，就是允许客户在选择酒店时重新搜索酒店；选择酒店时也同样可以选择进行酒店排序。
3. 主要的外部系统是相同的，比如都有酒店数据库以及信用卡支付系统的支持。

　　两者的不同点在于：

1. 新时代的去哪儿预订酒店产品的基本用例更加简单，比如搜索酒店用例，只需要选择目的地、入住和退房时间，并不需要亲自输入目的地或者选择输入留宿天数；在提供预订房间数量的时候，也不需要过多地说明旅客人数和是否是成人或者小孩；同时，在未登录状态下，支付阶段也不需要额外进行添加购物车流程。
2. 两者的某些用例的子用例并不完全相同，即相同业务的流程不一样，比如旧系统的在选择房间类型时就需确定房间数量，而新系统这个子用例被设置成确定订单的子用例；取消订单的流程也从在购物车中取消改成在确认订单过程中就可取消，对用户更加友好。另外，同样用例的注释内容也不完全相同。
3. 新系统的在每个基本用例上都添加了创新用例，比如搜索酒店中新增了境内境外酒店选择、地图搜索、高级搜索、酒店推荐等等，选择酒店新增了筛选条件选择，选择房间类型新增了用户评论、酒店交通和设施介绍，确定订单中新增了打印订单，支付的方式也明显增加。
4. 新系统的外部系统支持更多，同时还有和同类竞争者合作。

　　分析上面两个产品的异同点，可以总结出项目早期，发现创新的思路与方法：

1. 在模仿前辈产品的基本业务的前提上，调整某个业务的操作流程，使得用户使用更加方便，比如把取消订单改为在确定订单的流程中。
2. 对前辈产品的基本业务进行简化，将额外冗余的功能进行筛选删除，使得新产品使用更加简单快捷，比如删除冗余的购物车流程。
3. 扩大或者缩小产品的目标市场范围，比如上述旧系统只是针对国内市场，而新系统则面向国内和国外市场。
4. 在单个业务或者多个业务流程中，考虑添加新的功能或者对相同的扩展点进行修改，比如在相同的对酒店排序扩展点上，旧系统是根据星级、价格、喜好以及字典顺序排列，而新系统则选择是根据星级、价格以及用户评分来排序；又例如在搜索酒店时添加高级搜索或者酒店推荐功能。
5. 考虑寻找更多的外部系统支持，并在这基础上进行扩展。比如在支付上，除了信用卡支付，考虑还有各个支付平台的存在，可以向这些平台寻求合作，为用户提供更多便利。
6. 与竞争对手合作，可以考虑和竞争对手共享数据资源（这里主要指是酒店信息等大数据，并不是指用户私人信息）或者利用前辈产品的渠道进行扩展合作。比如在线预订酒店平台项目早期，可以寻求前辈产品（或者国外同类平台）的合作来利用它的数据库资源，同时自身为前辈产品提供一个推广渠道，这其实是一个互惠共利的思路方法。

### d. 请使用Scrum方法，在（任务b）用例图基础上，编制某订旅馆开发的需求（backlog）

　　绘制backlog的方法可见[Learning-Scrum-and-XP](https://reganfan.github.io/Learning-Scrum-and-XP/)，下列backlog使用的排序方法是按需求组织的形式进行排序，并非按照重要性排序，同时，下列故事条目只是选取了主要故事以及每个主要故事的一个扩展点作为例子。另外，初始估算是假设开发团队为6人时进行的人-天估算（每个故事安排2人），并且一个迭代周期假设为三个星期工作日（15天）。最后，下列backlog并没有How to demo条目，主要是因为篇幅太大，所以被省去，请阅者体谅。

|ID|Name|Imp|Est|Iter|Notes|
| :- | :- | :- | :- | :- | :- |
|1|search hotels|120|10|1||
|2|search by map|60|2|2|Using Baidu Map|
|3|choose hotel|110|10|1||
|4|select filter conditions|50|4|1||
|5|choose room type|100|10|1||
|6|view customer comment|40|4|2||
|7|confirm reservation|90|10|1||
|8|make payment|80|8|2||

## 2. 业务建模

