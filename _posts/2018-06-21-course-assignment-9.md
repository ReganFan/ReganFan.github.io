---
layout: post
title: 系统分析与设计-Lesson-16-作业
date: 2018-06-21 23:00:00+08:00
categories: 作业
tags: 博客
---

# 系统分析与设计 Lesson 16

## · 使用ECB实现make reservation用例的详细设计(包含用例简介，顺序图，类图)。

### 准备

#### 用例图

![make reservation use case diagram](/assets/2018-06-21-course-assignment-9-diagram/make-reservation-use-case-diagram.png)

#### 界面原型

参照文档[Asg_RH](/assets/2018-06-21-course-assignment-9-diagram/Asg_RH.pdf)说明。

#### 领域模型

![domain model](/assets/2018-06-21-course-assignment-9-diagram/domain-model.png)

#### 数据库设计(ER 逻辑模型)

![E-R model](/assets/2018-06-21-course-assignment-9-diagram/E-R.PNG)

### 识别类

#### 用例简介

**make reservation** 用例包括的子用例有**search hotels**、**choose hotel**、**choose room type**和**confirm reservation**，其中**confirm reservation**中还包括了**provide personal info**、**add reservation to basket**和**make payment**子用例。

结合用例图、界面原型和领域模型，能够识别出以下类：

##### Boundary

`SearchHotelsWindow`  `ChooseHotelWidnow`  `ChooseRoomWindow` `ConfirmReservationWindow`  `MakePaymentWindow`

##### Controller

`MakeReservationController`：执行**make reservation**用例时的一个控制类

##### Entity

`Hotel`  `Location`  `Room`  `Reservation`  `Payment`  `Customer`  `CreditCard`

### 动态图设计

#### 顺序图

![sequence-diagram](/assets/2018-06-21-course-assignment-9-diagram/sequence-diagram.png)

### 静态图设计

#### 类图

![class-diagram](/assets/2018-06-21-course-assignment-9-diagram/class-diagram.png)

## · 将逻辑设计类图映射到实际项目框架的包图。用树形结构表述实现的包和类。

![package diagram](/assets/2018-06-21-course-assignment-9-diagram/package-diagram.png)