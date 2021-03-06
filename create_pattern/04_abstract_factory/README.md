# 抽象工厂模式

工厂方法模式只考虑生产同等级的产品，但是在现实生活中许多工厂是综合型的工厂，能生产多等级（种类） 的产品。

将同一个具体工厂所生产的位于不同等级的一组产品称为一个产品族。

## 1、抽象工厂模式定义

是一种为访问类**提供一个创建一组相关或相互依赖对象的接口**，且访问类无须指定所要产品的具体类就能得到同族的不同等级的产品的模式结构。

抽象工厂模式是工厂方法模式的升级版本，工厂方法模式只生产一个等级的产品，而抽象工厂模式可生产多个等级的产品。

## 2、抽象工厂模式的特点

使用抽象工厂模式一般满足以下条件：

> 系统中有**多个产品族**，每个具体工厂创建同一族但属于不同等级结构的产品。
>
> 系统一次只可能消费其中某一族产品，即同族的产品一起使用
>

抽象工厂模式除具有工厂模式的的优点外。还有以下优点：

> 可以在类的内部对产品族中相关联的多等级产品共同管理，而不必专门引入多个新的类来进行管理。
> 
> 当需要产品族时，抽象工厂可以保证客户端始终只使用同一个产品的产品组。
> 
> 抽象工厂增强了程序的可扩展性，当增加一个新的产品族时，不需要修改原代码，满足开闭原则。
> 

抽象工厂模式的缺点是：

> 当产品族中需要增加一个新的产品时，所有的工厂类都需要进行修改。增加了系统的抽象性和理解难度
> 

应用场景

> 当需要创建的对象是**一系列相互关联或相互依赖的产品族时**，如电器工厂中的电视机、洗衣机、空调等。
>
> 系统中**有多个产品族，但每次只使用其中的某一族产品**。如有人只喜欢穿某一个品牌的衣服和鞋。
>
> 系统中**提供了产品的类库**，且所有产品的接口相同，客户端不依赖产品实例的创建细节和内部结构。
>

## 3、抽象工厂模式实现

抽象工厂模式包含以下主要角色

> **抽象工厂类（AbstractFactory）**：提供了创建产品的接口，调用者通过它访问具体抽象工厂的抽象工厂方法 newProduct() 来创建产品，可以创建多个不同等级的产品。
>
> **具体工厂类（ConcreteFactory）**：主要是实现抽象抽象工厂中的抽象方法，完成具体产品的创建。
>
> **抽象产品（AbstractProduct）**：定义了产品的规范，描述了产品的主要特性和功能，抽象工厂模式有多个抽象产品。
>
> **具体产品（ConcreteProduct）**：实现了抽象产品角色所定义的接口，由具体抽象工厂来创建，，它同具体工厂之间是多对一的关系。

