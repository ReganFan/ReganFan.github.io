---
layout: post
title: 系统分析与设计-Lesson-6-作业
date: 2018-04-22 23:00:00+08:00
categories: 作业
tags: 博客
---

# 系统分析与设计 Lesson 6

## 1. 用例建模

### a. 阅读Asg_RH文档，绘制用例图。按Task1要求，请使用工具UMLet，截图格式务必是png并控制尺寸

　　如下UML图：

![task 1 uml](/assets/2018-04-22-course-assignment-4-diagram/task-1-reserve-hotel-uml.png)

### b. 选择你熟悉的订旅馆在线服务系统（或移动APP），如绘制用例图。并满足以下要求：<br/>- 对比Asg_RH用例图，请用色彩标注出创新用例或子用例<br/>- 尽可能识别外部系统，并用色彩标注新的外部系统和服务

　　本次个人选择的是去哪儿网站中的订旅馆在线服务系统进行用例分析。

#### 去哪儿网站订旅馆基本流程：

　　下面提供了个人在未登录状态下使用去哪儿网站订旅馆过程的截图，其中将与Asg_RH中例子区别的主要创新用例或子用例用红框框出。

##### 搜索旅馆：

　　这部分的创新用例包括了选择境内外酒店、高级搜索酒店、地图搜索以及根据每日酒店推荐搜索。

![search hotels](/assets/2018-04-22-course-assignment-4-diagram/qunar-search-hotels.PNG)

##### 选择旅馆：

　　这里额外提供了按条件筛选酒店的功能。

![choose hotel](/assets/2018-04-22-course-assignment-4-diagram/qunar-choose-hotel.PNG)

##### 选择房间：

　　增加了用户点评、酒店设施概况、酒店位置交通、多个预订网站选择等等功能。

![choose room](/assets/2018-04-22-course-assignment-4-diagram/qunar-choose-room-type.PNG)

##### 确认订单：

![confirm reservation](/assets/2018-04-22-course-assignment-4-diagram/qunar-confirm-reservation.PNG)

　　下面是预定完成后的预定信息，可以进一步选择取消订单或打印：

![view reservation info](/assets/2018-04-22-course-assignment-4-diagram/qunar-view-reservation-info.PNG)

##### 支付：

　　支付方式有多种类型。

![pay](/assets/2018-04-22-course-assignment-4-diagram/qunar-pay.PNG)

#### 用例图

　　其中红色用例表示创新用例或子用例，绿色外部Actors表示新的外部系统或服务，黄色注释也是与Asg_RH中网站所包括的不同点。另外，需要强调的是，去哪儿网站已经发展非常成熟，因而与文档中的旧网站相比，有更多的功能和服务，也就有更多的用例，用例图更加复杂。下列用例图也只是选择了主要的用例，尽可能地详细绘制，但实际上也有相当多的用例被选择忽略，因而请阅者体谅。

![qunar reserve hotel use case diagram](/assets/2018-04-22-course-assignment-4-diagram/qunar-reserve-hotel.png)

### c. 对比两个时代、不同地区产品的用例图，总结在项目早期，发现创新的思路与方法

　　通过比较两个产品的用例图，可以发现出两个产品之间的异同点，首先是相同点：

1. 两个产品用例图的主要用例是一致的，比如两者均包含预订酒店用例，同时该用例的子用例也是相同，有搜索酒店、选择酒店、选择房间和确认订单，还有支付用例等等，因为这些均是在线预订酒店平台所必须具备的基本功能。
2. 上述提到的基本用例的扩展点是类似的，比如两者的选择酒店用例的扩展点都有搜索酒店，就是允许客户在选择酒店时重新搜索酒店；选择酒店时也同样可以选择进行酒店排序。
3. 主要的外部系统是相同的，比如都有基本的网上信用卡支付系统的支持。

　　两者的不同点在于：

1. 新时代的去哪儿预订酒店产品的基本用例更加简单，比如搜索酒店用例，只需要选择目的地、入住和退房时间，并不需要亲自输入目的地或者选择输入留宿天数；在提供预订房间数量的时候，也不需要过多地说明旅客人数和是否是成人或者小孩；同时，在未登录状态下，支付阶段也不需要额外进行添加购物车流程。
2. 两者的某些用例的具体场景并不完全相同，即相同业务的流程不一样，比如旧系统的在选择房间类型时就需确定房间数量，而新系统将这一步骤设置成确定订单的一步；取消订单的流程也从在购物车中取消改成在确认订单过程中就可取消，对用户更加友好。另外，同样用例的注释内容也不完全相同。
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

![backlog](/assets/2018-04-22-course-assignment-4-diagram/backlog.PNG)

## 2. 业务建模

### a. 在（任务b）基础上，用活动图建模找酒店用例。简述利用流程图发现子用例的方法。

　　如下所示，即是去哪儿网站中预订酒店平台的找酒店用例的活动图建模。需要注意的是，该活动图只是选取了主要的业务流程。可以知道的是，通过分析流程图中的重要操作能够获取子用例，尤其是需要实现额外功能的操作。比如，该找酒店用例，就有选择酒店范围以及以某种搜索方式搜索酒店这两个操作需要再进行扩展设计的，对比用例图，能够发现这些操作就是找酒店用例的子用例，而且是创新用例。

![search hotels uml activity](/assets/2018-04-22-course-assignment-4-diagram/search-hotels.png)

### b. 选择你身边的银行ATM，用活动图描绘取款业务流程。

　　选择建设银行的ATM进行分析，取款业务流程的活动图如下所示：

![withdraw money](/assets/2018-04-22-course-assignment-4-diagram/withdraw-money.png)

### c. 查找淘宝退货业务官方文档，使用多泳道图，表达客户、淘宝网、淘宝商家服务系统、商家等用户和系统协同完成退货业务的过程。分析客户要完成退货业务，在淘宝网上需要实现哪些系统用例

　　通过浏览[淘宝开放平台](http://open.taobao.com/)提供的API文档，可以发现[退款退货业务的多泳道活动图](http://open.taobao.com/doc.htm?spm=a219a.7386653.1.21.cYxzrQ#?treeId=477&docId=102594&docType=1)（忽略API接口信息），如下所示：

![taobao refund uml activity](/assets/2018-04-22-course-assignment-4-diagram/taobao-refund.png)

　　可以发现，客户要完成退货业务，淘宝网需要实现的系统用例（考虑成功退货的主要用例）包括有：生成退款单、同意退货处理、变更退款单状态以及同意退款处理。

## 3. 用例文本编写

### · 在大作业基础上，分析三种用例文本的优点和缺点

#### Brief（high level）

　　用例描述是一段简洁的概括性文字，通常描述用例主要的参与者以及主要的成功场景。

##### 优点：

　　在早期的需求分析阶段，可以帮助团队成员快速理解用例主题和范围。同时设计方便，编写只需要几分钟时间。

##### 缺点：

　　因为描述比较概括，所以不太利于开发时的功能细节设计与实现。

#### Casual

　　用例描述使用非正式的段落格式。使用多个段落来较为详细地描述各种场景。

##### 优点：

　　比brief格式更加详细地描述用例场景，同时还提供了更多的场景描述，对开发时的功能实现过程有所帮助。同时这部分的设计对与客户需求交流也有所帮助。

##### 缺点：

　　因为使用非正式的段落格式，所以往往会对功能细节的描述仍有所遗漏，并不能帮助达成开发目标。

#### Fully

　　详细描述用例的所有场景、场景步骤以及其他相关信息，包括前置条件和成功保证支持。通常在团队识别大多数用例并完成brief用例设计后，在第一次需求分析会议中，选择最重要的、最有价值的那几个用例进行详细编写。

##### 优点：

　　用例描述详尽，很好地帮助开发过程的功能设计与实现，能够引导开发人员解决开发时遇到的功能细节问题，同时也能够帮助达成开发目标。

##### 缺点：

　　描述用例的所有信息所需的编写时间花费很大，对于敏捷开发团队来说，不太适合投入太多的时间。实际上，项目团队也不可能完全描述出用例的所有相关信息。所以，存在的矛盾也非常明显。