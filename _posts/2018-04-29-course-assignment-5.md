---
layout: post
title: 系统分析与设计-Lesson-5-作业
date: 2018-04-29 23:00:00+08:00
categories: 作业
tags: 博客
---

# 系统分析与设计 Lesson 5

## 1. 领域建模

### a. 阅读Asg_RH文档，**按用例**构建领域模型。

#### 根据Task2的要求，使用工具UMLet绘制“Reserve Hotel”的领域模型图如下：

![domain-model](/assets/2018-04-29-course-assignment-5-diagram/domain-model.png)

### b. 数据建模(E-R 模型)

#### - 按 Task 3 要求，给出系统的 E-R 模型（数据逻辑模型）

![E-R model](/assets/2018-04-29-course-assignment-5-diagram/E-R.PNG)

#### - 导出 Mysql 物理数据库脚本

这里使用的数据库系统为**MySQL 4.0**：

```sql
drop table if exists City;

drop index Owns_FK on CreditCard;

drop index "Paid-with_FK" on CreditCard;

drop table if exists CreditCard;

drop table if exists Customer;

drop index "Is-in_FK" on Hotel;

drop table if exists Hotel;

drop index "Paid-by_FK" on Payment;

drop index "Paid-with2_FK" on Payment;

drop table if exists Payment;

drop index Reserves_FK on Reservation;

drop index "Made-by_FK" on Reservation;

drop index "Paid-by2_FK" on Reservation;

drop table if exists Reservation;

drop index Has_FK on Room;

drop table if exists Room;

/*==============================================================*/
/* Table: City                                                  */
/*==============================================================*/
create table City
(
   cityName                       varchar(50)                    not null,
   primary key (cityName)
)
type = InnoDB;

/*==============================================================*/
/* Table: CreditCard                                            */
/*==============================================================*/
create table CreditCard
(
   cardType                       varchar(50)                    not null,
   cardNumber                     numeric(50,0)                  not null,
   paymentID                      int,
   emailAddress                   varchar(50)                    not null,
   securityCode                   numeric(3,0)                   not null,
   expiryDate                     datetime                       not null,
   primary key (cardNumber)
)
type = InnoDB;

/*==============================================================*/
/* Index: "Paid-with_FK"                                        */
/*==============================================================*/
create index "Paid-with_FK" on CreditCard
(
   paymentID
);

/*==============================================================*/
/* Index: Owns_FK                                               */
/*==============================================================*/
create index Owns_FK on CreditCard
(
   emailAddress
);

/*==============================================================*/
/* Table: Customer                                              */
/*==============================================================*/
create table Customer
(
   fullName                       varchar(50)                    not null,
   emailAddress                   varchar(50)                    not null,
   primary key (emailAddress)
)
type = InnoDB;

/*==============================================================*/
/* Table: Hotel                                                 */
/*==============================================================*/
create table Hotel
(
   hotelName                      varchar(50)                    not null,
   cityName                       varchar(50)                    not null,
   starRating                     int,
   lowestPrice                    float(50,0),
   favourites                     int,
   primary key (hotelName)
)
type = InnoDB;

/*==============================================================*/
/* Index: "Is-in_FK"                                            */
/*==============================================================*/
create index "Is-in_FK" on Hotel
(
   cityName
);

/*==============================================================*/
/* Table: Payment                                               */
/*==============================================================*/
create table Payment
(
   amount                         float(8,2)                     not null,
   paymentID                      int                            not null,
   cardNumber                     numeric(50,0)                  not null,
   ReservationID                  int                            not null,
   primary key (paymentID)
)
type = InnoDB;

/*==============================================================*/
/* Index: "Paid-with2_FK"                                       */
/*==============================================================*/
create index "Paid-with2_FK" on Payment
(
   cardNumber
);

/*==============================================================*/
/* Index: "Paid-by_FK"                                          */
/*==============================================================*/
create index "Paid-by_FK" on Payment
(
   ReservationID
);

/*==============================================================*/
/* Table: Reservation                                           */
/*==============================================================*/
create table Reservation
(
   ReservationID                  int                            not null,
   hotelName                      varchar(50)                    not null,
   emailAddress                   varchar(50)                    not null,
   paymentID                      int,
   checkInDate                    datetime                       not null,
   checkOutDate                   datetime                       not null,
   primary key (ReservationID)
)
type = InnoDB;

/*==============================================================*/
/* Index: "Paid-by2_FK"                                         */
/*==============================================================*/
create index "Paid-by2_FK" on Reservation
(
   paymentID
);

/*==============================================================*/
/* Index: "Made-by_FK"                                          */
/*==============================================================*/
create index "Made-by_FK" on Reservation
(
   emailAddress
);

/*==============================================================*/
/* Index: Reserves_FK                                           */
/*==============================================================*/
create index Reserves_FK on Reservation
(
   hotelName
);

/*==============================================================*/
/* Table: Room                                                  */
/*==============================================================*/
create table Room
(
   roomType                       varchar(50)                    not null,
   roomPrice                      float(50,0)                    not null,
   adultsNumber                   numeric(8,0),
   childrenNumber                 numeric(8,0),
   RoomNo                         int                            not null,
   hotelName                      varchar(50)                    not null,
   primary key (RoomNo)
)
type = InnoDB;

/*==============================================================*/
/* Index: Has_FK                                                */
/*==============================================================*/
create index Has_FK on Room
(
   hotelName
);

alter table CreditCard add constraint FK_Owns foreign key (emailAddress)
      references Customer (emailAddress) on delete restrict on update restrict;

alter table CreditCard add constraint "FK_Paid-with" foreign key (paymentID)
      references Payment (paymentID) on delete restrict on update restrict;

alter table Hotel add constraint "FK_Is-in" foreign key (cityName)
      references City (cityName) on delete restrict on update restrict;

alter table Payment add constraint "FK_Paid-by" foreign key (ReservationID)
      references Reservation (ReservationID) on delete restrict on update restrict;

alter table Payment add constraint "FK_Paid-with2" foreign key (cardNumber)
      references CreditCard (cardNumber) on delete restrict on update restrict;

alter table Reservation add constraint "FK_Made-by" foreign key (emailAddress)
      references Customer (emailAddress) on delete restrict on update restrict;

alter table Reservation add constraint "FK_Paid-by2" foreign key (paymentID)
      references Payment (paymentID) on delete restrict on update restrict;

alter table Reservation add constraint FK_Reserves foreign key (hotelName)
      references Hotel (hotelName) on delete restrict on update restrict;

alter table Room add constraint FK_Has foreign key (hotelName)
      references Hotel (hotelName) on delete restrict on update restrict;

```

#### - 简单叙说 数据库逻辑模型 与 领域模型 的异同

**相同点：**

1. 领域模型的实体类、类属性以及联系依次对应数据库逻辑模型的实体、实体属性和关系，它们有相同的名字以及相同的数据类型，这些都是与数据库的构建有关。

**不同点：**

1. 领域模型中包含有中介实体，而与数据库相关密切的数据库逻辑模型中是不存在中介实体的。
2. 数据库逻辑模型最主要应用在数据库构建方面，而领域模型除了数据库构建，还能用于描述其他模型架构。
3. 数据库逻辑模型能够转换为物理模型，进而转换成具体的数据库对象，原来的“实体-关系”转换成“表-外键”，实体的属性转换为表的列，同时每个列的数据类型转换为对应的DBMS中支持的数据类型，因此E-R模型中会存在领域模型中没有的主键、外键等概念。