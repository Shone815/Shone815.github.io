---
layout: post
title: "设计模式"
subtitle: "基于C++的设计模式基础（李建忠）"
author: "Shone815"
header-img: "img/2024-05-31_design_mode_header.jpg"
catalog: true
tags:
  - C++
  - 设计模式
  - 计算机
---

> [在线练习网站](https://refactoringguru.cn/design-patterns)

> 推荐：《重构——改善既有代码的设计》、《重构与模式》

![img](/img/2024-05-31_design_mode.png)

## 一. 简介

### 1. 目标

理解**松耦合**设计思想，掌握**面向对象**设计原则，掌握`重构`技法改善设计，<b>掌握```GOF```核心设计模式。</b>

### 2. 从面向对象谈起

#### 1）底层思维：向下，如何把握机器底层从微观理解对象构造

(1) 语言构造

(2) 编译转换

(3) 内存模型

(4) 运行时机制

#### 2) 抽象思维：向上，如何将我们的周围世界抽象为程序代码

(1) 面向对象

(2) 组件封装

(3) 设计模式

(4) 架构模式

### 3. 深入理解面向对象

#### 1) 向下：深入理解三大面向对象机制

(1) 封装：隐藏内部实现

(2) 继承：复用现有代码

(3) 多态：改写对象行为

#### 2) 向上：深刻把握面向对象机制所带来的抽象意义，理解如何使用这些机制来表达现实世界，掌握什么是”好的面向对象设计“

### 4. 软件设计复杂的根本原因

#### 1) 变化

(1) 客户需求的变化

(2) 技术平台的变化

(3) 开发团队的变化

(4) 市场环境的变化

### 5. 如何解决复杂性

#### 1) 分解

分而治之，将大问题分解为多个小问题，将复杂问题分解为多个简单问题。

#### 2) 抽象

更高层次来讲，人们处理复杂性有一个通用的技术，即抽象。由于不能掌握全部的复杂对象，我们选择忽视它的非本质细节，而去处理泛化和理想化了的对象模型。

### 6. 软件设计的目标

金科玉律：`复用`！！！深刻理解稳定和变化。

#### 1) 有人说设计模式是为了弥补编程语言的不足而产生的。

## 二. 面向对象设计原则

### 1. 变化是复用的天敌！面向对象设计最大的优势在于：抵御变化！

### 2. 重新认识面向对象 - 抽象思维

#### 1) 理解隔离变化：从宏观层面来看，面向对象的构建方式更能适应软件的变化，能将变化所带来的影响减为最小

#### 2) 各司其职

(1) 从微观层面来看，面向对象的方式更强调各个类的“责任”

(2) 由于需求变化导致的新增类型不应该影响原来类型的实现——是所谓各负其责

#### 3) 对象是什么

(1) 从语言实现层面来看，对象封装了代码和数据。

(2) 从规格层面讲，对象是一系列可被使用的公共接口。

(3) 从概念层面讲，对象是某种拥有责任的抽象。

### 3. 面向对象设计原则 - 比设计模式更重要！！！

> 注：（维基百科）流行的原则是SOLID原则，单一功能、开闭原则、里氏替换、接口隔离、依赖反转。

#### 1) 依赖倒置原则（DIP，Dependence Inversion Principle） -> 隔离变化

(1) 高层模块(稳定)不应该依赖于低层模块(变化)，二者都应该依赖于抽象(稳定) 。

(2) 抽象(稳定)不应该依赖于实现细节(变化) ，实现细节应该依赖于抽象(稳定)。

#### 2) 开放封闭原则（OCP，Open Closed Principle）

(1) 对扩展开放，对更改关闭。

(2) 类模块应该是可扩展的，但是不可修改。

#### 3) 单一职责原则（SRP，Single Responsibility Principle）

(1) 一个类应该仅有一个引起它变化的原因。

(2) 变化的方向隐含着类的责任。

#### 4) Liskov替换原则（LSP，Liskov Substitution Principle）

(1) 子类必须能够替换它们的基类（is-a）。

(2) 继承表达类型抽象。

#### 5) 接口隔离原则（ISP，Interface Segregation Principle）

(1) 不应该强迫客户程序依赖它们不用的方法。（不要无节制使用public）

(2) 接口应该小而完备

#### 6) 优先使用对象组合，而不是继承（Composite Reuse Principle）

(1) 类继承通常为“白箱复用”，对象组合通常为“黑箱复用”。

(2) 继承在某种程度上破坏了封装性，子类父类耦合度高。

(3) 而对象组合则只要求被组合的对象具有良好定义的接口，耦合度低。

#### 7) 封装变化点

(1) 使用封装来创建对象之间的分界层，让设计者可以在分界层的一侧进行修改，而不会对另一侧产生不良的影响，从而实现层次间的松耦合。

#### 8) 针对接口编程，而不是针对实现编程

(1) 不将变量类型声明为某个特定的具体类，而是声明为某个接口。

(2) 客户程序无需获知对象的具体类型，只需要知道对象所具有的接口。

(3) 减少系统中各部分的依赖关系，从而实现“高内聚、松耦合”的类型设计方案。

### 4. 产业强盛的标志：接口标准化！！

### 5. 将设计原则提升为设计经验

#### 1) 设计习语 Design Idioms

(1) Design Idioms 描述与特定编程语言相关的低层模式，技巧，惯用法。

#### 2) 设计模式 Design Patterns

(1) Design Patterns主要描述的是“类与相互通信的对象之间的组织关系，包括它们的角色、职责、协作方式等方面。

#### 3) 架构模式 Architectural Patterns

(1) Architectural Patterns描述系统中与基本结构组织关系密切的高层模式，包括子系统划分，职责，以及如何组织它们之间关系的规则。

### 6. 设计模式分类

#### 1) 从目的来看

(1) 创建型模式（5种）：将对象的部分创建工作延迟到子类或者其他对象，从而应对需求变化为对象创建时具体类型实现引来的冲击。

> a) 工厂方法模式、抽象工厂模式、单例模式、建造者模式、原型模式。（抽单建工原）

(2) 结构型模式（7种）：通过类继承或者对象组合获得更灵活的结构，从而应对需求变化为对象的结构带来的冲击。

> a) 适配器模式、装饰器模式、代理模式、外观模式、桥接模式、组合模式、享元模式。（适代外组装享桥）

(3) 行为型模式（11种）：通过类继承或者对象组合来划分类与对象间的职责，从而应对需求变化为多个交互的对象带来的冲击。

> a) 策略模式、模板方法模式、观察者模式、迭代子模式、责任链模式、命令模式、备忘录模式、状态模式、访问者模式、中介者模式、解释器模式。（责备中模访，状观迭 解命策）

#### 2) 从范围来看

(1) 类模式处理类与子类的静态关系

(2) 对象模式处理对象间的动态关系

#### 3) 从封装变化角度对模式分类

(1) 组件协作

> a) Template Method模板方法模式

> b) Observer/Event观察者模式

> c) Strategy策略模式

(2) 单一职责

> a) Decorator装饰器模式

> b) Bridge桥接模式

(3) 对象创建

> a) Factory Method工厂方法模式

> b) Abstract Factory抽象工厂模式

> c) Prototype原型模式

> d) Builder建造者模式

(4) 对象性能

> a) Singleton单例模式

> b) Flyweight享元模式

(5) 接口隔离

> a) Facade外观模式

> b) Proxy代理模式

> c) Mediator中介者模式

> d) Adapter适配器模式

(6) 状态变化

> a) Memento备忘录模式

> b) State状态模式

(7) 数据结构

> a) Composite组合模式

> b) Iterator迭代子模式

> c) Chain of Resposibility责任链模式

(8) 行为变化

> a) Command命令模式

> b) Visitor访问者模式

(9) 领域问题

> a) Interpreter解释器模式

### 7. 重构获得模式 Refactoring to Patterns

#### 1) 面向对象设计模式是“好的面向对象设计”，是指可以满足“应对变化，提高复用”的设计

#### 2) 现代软件设计的特征是“需求的频繁变化”。设计模式的要点是“寻找变化点，然后在变化点处应用设计模式，从而来更好地应对需求的变化”。“什么时候，什么地点应用设计模式”比“理解设计模式结构本身”更为重要。

#### 3) 设计模式的应用不宜先入为主，一上来就使用设计模式是对设计模式的最大误用。没有一步到位的设计模式。敏捷软件开发实践提倡的“Refactoring to Patterns”是目前普遍公认的最好的使用设计模式的方法。

### 8. 重构关键技法

#### 1) 静态 -> 动态

#### 2) 早绑定 -> 晚绑定

(1) C++可由virtual实现晚绑定。

#### 3) 继承 -> 组合

(1) 组合优于继承

#### 4) 编译时依赖 -> 运行时依赖

#### 5) 紧耦合 -> 松耦合

## 三. 组件协作模式

> 现代软件专业分工之后的第一个结果是“框架与应用程序的划分”，“组件协作”模式通过晚期绑定，来实现框架与应用程序之间的松耦合，是二者之间协作时常用的模式。

### 1. Template method模板方法（复杂度：*，流行度**）

#### 1) 动机

在软件构建过程中，对于某一项任务，它常常有稳定的整体操作结构，但各个子步骤却有很多改变的需求，或者由于固有的原因（比如框架与应用之间的关系）而无法和任务的整体结构同时实现。

#### 2) 模式定义

定义一个操作中的算法的骨架（稳定），而将一些步骤延迟（变化）到子类中。Template Method使得子类可以不改变（复用）一个算法的结构即和重定义（override 重写）该算法的某些特定步骤。

#### 3) 注意

(1) 当你只希望客户端扩展某个特定算法步骤， 而不是整个算法或其结构时， 可使用模板方法模式。

(2) 算法骨架必须是稳定不变的，可以将可能引起变化的小模块通过virtual多态特性在子类中overwrite实现。若骨架不够稳定，那么可能template method不太适合。

(3) 当多个类的算法除一些细微不同之外几乎完全一样时， 你可使用该模式。 但其后果就是， 只要算法发生变化， 你就可能需要修改所有的类。

#### 4) 要点总结

(1) Template Method模式是一种非常基础性的设计模式，在面向对象系统中有着大量的应用。它用最简洁的机制（虚函数的多态性）为很多应用程序框架提供了灵活的扩展点，是代码复用方面的基本实现结构。

(2) 除了可以灵活应对子步骤的变化外，“不要调用我，让我来调用你”的反向控制结构是Template Method的典型应用。

(3) 在具体实现方面，被Template Method调用的虚方法可以具有实现，也可以没有任何实现（抽象方法、纯虚方法），但一般推荐将它们设置为protected方法。

#### 5) 优点

(1) 你可仅允许客户端重写一个大型算法中的特定部分， 使得算法其他部分修改对其所造成的影响减小。

(2) 你可将重复代码提取到一个基类中。

#### 6) 缺点

(1) 部分客户端可能会受到算法框架的限制。

(2) 通过子类抑制默认步骤实现可能会导致违反_里氏替换原则_。

(3) 模板方法中的步骤越多， 其维护工作就可能会越困难。

### 2. strategy策略模式（复杂度：*，流行度***）

#### 1) 动机

在软件构建过程中，某些对象使用的算法可能多种多样，经常改变，如果将这些算法都编码到对象中，将会使对象变得异常复杂；而且有时候支持不使用的算法也是一个性能负担。

#### 2) 模式定义

定义一系列算法，把它们一个个封装起来，并且使它们可互相替换（变化）。该模式使得算法可独立于使用它的客户程序(稳定)而变化（扩展，子类化） 。

#### 3) 要点总结

> if-else 或者switch-case的改进版（绝对稳定不变情况下使用if-else问题不大）

(1) Strategy及其子类为组件提供了一系列可重用的算法，从而可以使得类型在运行时方便地根据需要在各个算法之间进行切换。

(2) Strategy模式提供了用条件判断语句以外的另一种选择，消除条件判断语句，就是在解耦合。含有许多条件判断语句的代码通常都需要Strategy模式。

(3) 如果Strategy对象没有实例变量，那么各个上下文可以共享同一个Strategy对象，从而节省对象开销。

#### 4) 优点

(1) 你可以在运行时切换对象内的算法。

(2) 你可以将算法的实现和使用算法的代码隔离开来。

(3) 你可以使用组合来代替继承。

(4) 开闭原则。 你无需对上下文进行修改就能够引入新的策略。

#### 5) 缺点

(1) 如果你的算法极少发生改变， 那么没有任何理由引入新的类和接口。 使用该模式只会让程序过于复杂。

(2) 客户端必须知晓策略间的不同——它需要选择合适的策略。

(3) 许多现代编程语言支持函数类型功能， 允许你在一组匿名函数中实现不同版本的算法。 这样， 你使用这些函数的方式就和使用策略对象时完全相同， 无需借助额外的类和接口来保持代码简洁。

### 3. 观察者模式（复杂度：**，流行度***）

#### 1) 动机

(1) 在软件构建过程中，我们需要为某些对象建立一种“通知依赖关系” ——一个对象（目标对象）的状态发生改变，所有的依赖对象（观察者对象）都将得到通知。如果这样的依赖关系过于紧密，将使软件不能很好地抵御变化。

(2) 使用面向对象技术，可以将这种依赖关系弱化，并形成一种稳定的依赖关系。从而实现软件体系结构的松耦合。

#### 2) 模式定义

定义对象间的一种一对多（变化）的依赖关系，以便当一个对象(Subject)的状态发生改变时，所有依赖于它的对象都得到通知并自动更新。

#### 3) 要点总结

(1) 使用面向对象的抽象， Observer模式使得我们可以独立地改变目标与观察者，从而使二者之间的依赖关系达到松耦合。

(2) 目标发送通知时，无需指定观察者，通知（可以携带通知信息作为参数）会自动传播。

(3) 观察者自己决定是否需要订阅通知，目标对象对此一无所知。

(4) Observer模式是基于事件的UI框架中非常常用的设计模式，也是MVC模式的一个重要组成部分。

#### 4) 优点

(1) 开闭原则。 你无需修改发布者代码就能引入新的订阅者类 （如果是发布者接口则可轻松引入发布者类）。

(2) 你可以在运行时建立对象之间的联系。

#### 5) 缺点

(1) 订阅者的通知顺序是随机的。

## 四. 单一职责模式

> 在软件组件的设计中，如果责任划分不清晰，使用继承得到的结果往往是随着需求的变化，子类急剧膨胀，同时充斥着重复代码，这时候的关键是划清责任。

### 1. Decorator 装饰模式（复杂度：**，流行度**）

#### 1) 动机

(1) 在某些情况下我们可能会“过度地使用继承来扩展对象的功能”，由于继承为类型引入的静态特质，使得这种扩展方式缺乏灵活性；并且随着子类的增多（扩展功能的增多），各种子类的组合（扩展功能的组合）会导致更多子类的膨胀。

(2) 如何使“对象功能的扩展”能够根据需要来动态地实现？同时避免“扩展功能的增多”带来的子类膨胀问题？从而使得任何“功能扩展变化”所导致的影响将为最低？

#### 2) 模式定义

动态（组合）地给一个对象增加一些额外的职责。就增加功能而言，Decorator模式比生成子类（继承）更为灵活（消除重复代码 & 减少子类个数）。组合优于继承的典型体现。

(1) 继承的缺点

> a) 继承是静态的，无法在运行时改变对象的行为。只能使用由不同子类创建对象来替代当前整个对象。

> b) 子类只能有一个父类。大部分编程语言不允许一个类同时继承多个父类。

#### 3) 要点总结

(1) 通过采用组合而非继承的手法， Decorator模式实现了在运行时动态扩展对象功能的能力，而且可以根据需要扩展多个功能。避免了使用继承带来的“灵活性差”和“多子类衍生问题”。

(2) Decorator类在接口上表现为is-a Component的继承关系，即Decorator类继承了Component类所具有的接口。但在实现上又表现为has-a Component的组合关系，即Decorator类又使用了另外一个Component类。

> a) 继承于某个基类，但同时实现里又有这个基类的指针实例。

(3) Decorator模式的目的并非解决“多子类衍生的多继承”问题，Decorator模式应用的要点在于解决“主体类在多个方向上的扩展功能”——是为“装饰”的含义。

#### 4) 优点

(1) 你无需创建新子类即可扩展对象的行为。

(2) 你可以在运行时添加或删除对象的功能。

(3) 你可以用多个装饰封装对象来组合几种行为。

(4) 单一职责原则。 你可以将实现了许多不同行为的一个大类拆分为多个较小的类。

#### 5) 缺点

(1) 在封装器栈中删除特定封装器比较困难。

(2) 实现行为不受装饰栈顺序影响的装饰比较困难。

(3) 各层的初始化配置代码看上去可能会很糟糕。

### 2. Bridge桥模式（复杂度：***，流行度*）

#### 1) 动机

(1) 由于某些类型的固有的实现逻辑，使得它们具有两个变化的维度（如形状和颜色），乃至多个纬度的变化。

(2) 如何应对这种“多维度的变化”？如何利用面向对象技术来使得类型可以轻松地沿着两个乃至多个方向变化，而不引入额外的复杂度？

#### 2) 模式定义

将抽象部分(业务功能)与实现部分(平台实现)分离，使它们都可以独立地变化。

#### 3) 要点总结

(1) Bridge模式使用“对象间的组合关系”解耦了抽象和实现之间固有的绑定关系，使得抽象和实现可以沿着各自的维度来变化。所谓抽象和实现沿着各自纬度的变化，即“子类化”它们。

(2) Bridge模式有时候类似于多继承方案，但是多继承方案往往违背单一职责原则（即一个类只有一个变化的原因），复用性比较差。Bridge模式是比多继承方案更好的解决方法。

(3) Bridge模式的应用一般在“两个非常强的变化维度”，有时一个类也有多于两个的变化维度，这时可以使用Bridge的扩展模式

#### 4) 优点

(1)  你可以创建与平台无关的类和程序。

(2)  客户端代码仅与高层抽象部分进行互动， 不会接触到平台的详细信息。

(3)  开闭原则。 你可以新增抽象部分和实现部分， 且它们之间不会相互影响。

(4)  单一职责原则。 抽象部分专注于处理高层逻辑， 实现部分处理平台细节。

#### 5) 缺点

(1) 对高内聚的类使用该模式可能会让代码更加复杂。

## 五. “对象创建“模式

> 通过“对象创建” 模式绕开new，来避免对象创建（new）过程中所导致的紧耦合（依赖具体类），从而支持对象创建的稳定。它是接口抽象之后的第一步工作。

### 1. Factory Method工厂模式（复杂度：*，流行度***）

#### 1) 动机

(1) 在软件系统中，经常面临着创建对象的工作；由于需求的变化，需要创建的对象的具体类型经常变化。

(2) 如何应对这种变化？如何绕过常规的对象创建方法(new)，提供一种“封装机制”来避免客户程序和这种“具体对象创建工作”的紧耦合？

#### 2) 模式定义

定义一个用于创建对象的接口，让子类决定实例化哪一个类。Factory Method使得一个类的实例化延迟（目的：解耦，手段：虚函数）到子类。

#### 3) 要点总结

(1) Factory Method模式用于隔离类对象的使用者和具体类型之间的耦合关系。面对一个经常变化的具体类型，紧耦合关系(new)会导致软件的脆弱。

(2) Factory Method模式通过面向对象的手法，将所要创建的具体对象工作延迟到子类，从而实现一种扩展（而非更改）的策略，较好地解决了这种紧耦合关系。

(3) Factory Method模式解决“单个对象”的需求变化。缺点在于要求创建方法/参数相同。

#### 4) 优点

(1) 你可以避免创建者和具体产品之间的紧密耦合。

(2) 单一职责原则。 你可以将产品创建代码放在程序的单一位置， 从而使得代码更容易维护。

(3) 开闭原则。 无需更改现有客户端代码， 你就可以在程序中引入新的产品类型。

#### 5) 缺点

(1) 应用工厂方法模式需要引入许多新的子类， 代码可能会因此变得更复杂。 最好的情况是将该模式引入创建者类的现有层次结构中。

#### 6) 应用

在许多设计工作的初期都会使用工厂方法模式 （较为简单， 而且可以更方便地通过子类进行定制）， 随后演化为使用抽象工厂模式、 原型模式或生成器模式 （更灵活但更加复杂）。

### 2. Abstract Factory抽象工厂模式（复杂度：**，流行度***）

#### 1) 动机

(1) 在软件系统中，经常面临着“一系列相互依赖的对象”的创建工作；同时，由于需求的变化，往往存在更多系列对象的创建工作

#### 2) 模式定义

提供一个接口，让该接口负责创建一系列“相关或者相互依赖的对象”，无需指定它们具体的类。

(1) 有相关性的类可以考虑合在一起。

#### 3) 要点总结

(1) 如果没有应对“多系列对象构建”的需求变化，则没有必要使用Abstract Factory模式，这时候使用简单的工厂完全可以。

(2) ”系列对象”指的是在某一特定系列下的对象之间有相互依赖、或作用的关系。不同系列的对象之间不能相互依赖。

(3) Abstract Factory模式主要在于应对“新系列”的需求变动。其缺点在于难以应对“新对象”的需求变动

#### 4) 优点

(1) 你可以确保同一工厂生成的产品相互匹配。

(2) 你可以避免客户端和具体产品代码的耦合。

(3) 单一职责原则。 你可以将产品生成代码抽取到同一位置， 使得代码易于维护。

(4) 开闭原则。 向应用程序中引入新产品变体时， 你无需修改客户端代码。

#### 5) 缺点

(1) 由于采用该模式需要向应用中引入众多接口和类， 代码可能会比之前更加复杂。

### 3. Prototype原型模式（复杂度：*，流行度**），通过clone或copy等识别

#### 1) 动机

在软件系统中，经常面临着“某些结构复杂的对象”的创建工作；由于需求的变化，这些对象经常面临着剧烈的变化，但是它们却拥有比较稳定一致的接口。如何隔离“这些易变的对象”？

#### 2) 模式定义

使用原型实例指定创建对象的种类，然后通过拷贝这些原型来创建新的对象。

#### 3) 要点总结

(1) Prototype模式同样用于隔离类对象的使用者和具体类型（易变类）之间的耦合关系，它同样要求这些“易变类”拥有“稳定的接口”

(2) Prototype模式对于“如何创建易变类的实体对象”采用“原型克隆”的方法来做，它使得我们可以非常灵活地动态创建“拥有某些稳定接口”的新对象——所需工作仅仅时注册一个新类对象（即原型），然后在任何需要的地方clone。

(3) Prototype模式中的Clone方法可以利用某些框架中的序列化来实现深拷贝。

#### 4) 优点

(1) 你可以克隆对象， 而无需与它们所属的具体类相耦合。

(2) 你可以克隆预生成原型， 避免反复运行初始化代码。

(3) 你可以更方便地生成复杂对象。

(4) 你可以用继承以外的方式来处理复杂对象的不同配置。

#### 5) 缺点

(1) 克隆包含循环引用的复杂对象可能会非常麻烦。

### 4. Builder建造者模式（复杂度：**，流行度***）

#### 1) 动机

(1) 在软件系统中，有时候面临着“一个复杂对象”的创建工作，其通常由各个部分的子对象用一定的算法构成；由于需求的变化，这个复杂对象的各个部分经常面临着剧烈的变化，但是将它们组合在一起的算法却相对稳定。

(2) 如何应对这种变化？如何提供一种“封装机制”来隔离出“复杂对象的各个部分”的变化，从而保持系统中的“稳定构建算法”不随着需求改变而改变？

#### 2) 模式定义

将一个复杂对象的构建与其表示相分离，使得同样的构建过程(稳定)可以创建不同的表示(变化)。

#### 3) 要点总结

(1) Builder 模式主要用于“分步骤构建一个复杂的对象”。在这其中“分步骤”是一个稳定的算法，而复杂对象的各个部分则经常变化。

(2) 变化点在哪里，封装哪里—— Builder模式主要在于应对“复杂对象各个部分”的频繁需求变动。其缺点在于难以应对“分步骤构建算法”的需求变动。

(3) 在Builder模式中，要注意不同语言中构造器内调用虚函数的差别（C++ vs. C#) 。

#### 4) 优点

(1) 你可以分步创建对象， 暂缓创建步骤或递归运行创建步骤。

(2) 生成不同形式的产品时， 你可以复用相同的制造代码。

(3) 单一职责原则。 你可以将复杂构造代码从产品的业务逻辑中分离出来。

#### 5) 缺点

(1) 由于该模式需要新增多个类， 因此代码整体复杂程度会有所增加。

## 六. 对象性能

> 面向对象很好地的解决了”抽象“的问题，但是必不可避免地要付出一定地代价。对于通常情况来讲，面向对象的成本大都可以忽略不计。但是某些情况，面向对象所带来的成本必须谨慎处理。

### 1. Singleton单例模式（复杂度：*，流行度**）

#### 1) 动机

(1) 在软件系统中，经常有这样的一些特殊的类，必须保证它们在系统中只存在一个实例，才能确保它们的逻辑正确性、以及良好的效率。

(2) 如何绕过常规的构造器，提供一种机制来保证一个类只有一个实例？

(3) 这应该是类设计者的责任，而不是使用者的责任。

#### 2) 模式定义

保证一个类仅有一个实例，并提供一个该实例的全局访问点。

#### 3) 要点总结

(1) Singleton模式中的实例构造器可以设置为protected以允许子类派生。

(2) Singleton模式一般不要支持拷贝构造函数和clone接口，因为这有可能导致多个对象实例，与singleton模式的初衷违背。

(3) 如何实现多线程环境下安全的singleton？注意对双检查锁得正确实现。

#### 4) 优点

(1) 你可以保证一个类只有一个实例。

(2) 你获得了一个指向该实例的全局访问节点。

(3) 仅在首次请求单例对象时对其进行初始化。

#### 5) 缺点

(1) 违反了“单一职责原则”。 该模式同时解决了两个问题：保证一个类只有一个实例；提供一个全局访问节点。

(2) 单例模式可能掩盖不良设计， 比如程序各组件之间相互了解过多等。

(3) 该模式在多线程环境下需要进行特殊处理， 避免多个线程多次创建单例对象。

(4) 单例的客户端代码单元测试可能会比较困难， 因为许多测试框架以基于继承的方式创建模拟对象。 由于单例类的构造函数是私有的， 而且绝大部分语言无法重写静态方法， 所以你需要想出仔细考虑模拟单例的方法。 要么干脆不编写测试代码， 或者不使用单例模式。

### 2. Flyweight享元模式（复杂度：***，流行度*）

#### 1) 动机

(1) 在软件系统采用纯粹对象方案的问题在于大量细粒度的对象会很快充斥在系统中，从而带来很高的运行时代价——主要指内存需求方面的代价。

(2) 如何在避免大量细粒度对象问题的同时，让外部客户程序仍然能够透明地使用面向对象的方式来进行操作？

#### 2) 模式定义

运用共享技术有效地支持大量细粒度的对象。

#### 3) 要点总结

(1) 面向对象很好地解决了抽象性的问题，但是作为一个运行在机器中的程序实体，我们需要考虑对象的代价问题。Flyweight主要解决面向对象的代价问题，一般不触及面向对象的抽象性问题。

(2) Flyweight采用对象共享的做法来降低系统中对象的个数，从而降低细粒度对象给系统带来的内存压力。在具体实现方面，要注意对象状态的处理。

(3) 对象的数量太大从而导致对象内存开销加大——什么样的数量才算大？这需要我们仔细的根据具体应用情况进行评估，而不能凭空臆断。

#### 4) 优点

(1) 如果程序中有很多相似对象， 那么你将可以节省大量内存。

#### 5) 缺点

(1) 你可能需要牺牲执行速度来换取内存， 因为他人每次调用享元方法时都需要重新计算部分情景数据。

(2) 代码会变得更加复杂。 团队中的新成员总是会问：“为什么要像这样拆分一个实体的状态？”。

## 七. 接口隔离

> 在组件构建过程中，某些接口之间直接的依赖常常会带来很多问题、甚至根本无法实现。采用添加一层间接（稳定）接口，来隔离本来互相紧密关联的接口是一种常见的解决方案。

### 1. Facade外观模式（复杂度：*，流行度**）

#### 1) 动机

(1) 组件客户和组件中各种复杂的子系统有过多的耦合，会随着外部客户程序和各子系统的演化，这种过多的耦合面临很多变化的挑战。

(2) 如何简化外部客户程序和系统件的交互接口？如何将外部客户程序的演化和内部子系统的变化之间的依赖相互解耦？

#### 2) 模式定义

为子系统中的一组接口提供一个一致（稳定）的界面，Facade模式定义了一个高层接口，这个接口使得这以子系统更加容易使用（复用）。

#### 3) 要点总结

(1) 从客户程序的角度来看，Facade模式简化了整个组件系统的接口，对于组件内部与外部客户程序来说，达到了一种“解耦”的效果——内部子系统的任何变化不会影响到Facade接口的变化。

(2) Facade设计模式更注重从架构的层次去看整个系统，而不是单个类的层次。Facade很多时候更是一种架构设计模式。

(3) Facade设计模式并非一个集装箱，可以任意地放进任何多个对象。Facade模式中组件的内部应该是“相互耦合关系比较大的一系列组件”，而不是一个简单的功能集合。

#### 4) 优点

(1) 你可以让自己的代码独立于复杂子系统。

#### 5) 缺点

(1) 外观可能成为与程序中所有类都耦合的上帝对象。

### 2. Proxy代理模式（复杂度：**，流行度*）

#### 1) 动机

(1) 在面向对象系统中，有些对象由于某种原因（比如对象创建的开销很大，或者某些操作需要安全控制，或者需要进程外的访问等）直接访问会给使用者、或者系统结构带来很多麻烦。

(2) 如何在不失去透明操作对象的同时来管理/控制这些对象特有的复杂性？增加一层间接层是软件开发中常见的解决方式。

#### 2) 模式定义

为其他对象提供一种代理以控制（隔离，使用接口）对这个对象的访问。

#### 3) 要点总结

(1) “增加一层间接层”是软件系统中对许多复杂问题的一种常见解决方法。在面向对象系统中，直接使用某些对象会带来很多问题，作为间接层的proxy对象便是解决这一问题的常用手段。

(2) 具体proxy设计模式的实现方法、实现粒度都相差很大，有些可能对单个对象做细粒度的控制，如copy-on-write技术，有些可能对组件模块提供抽象代理层，在架构层次对对象做proxy。

(3) proxy并不一定要求保持接口完整的一致性，只要能够实现间接控制，有时候损及一些透明性是可以接受的。

#### 4) 优点

(1) 你可以在客户端毫无察觉的情况下控制服务对象。

(2) 如果客户端对服务对象的生命周期没有特殊要求， 你可以对生命周期进行管理。

(3) 即使服务对象还未准备好或不存在， 代理也可以正常工作。

(4) 开闭原则。 你可以在不对服务或客户端做出修改的情况下创建新代理。

#### 5) 缺点

(1) 代码可能会变得复杂， 因为需要新建许多类。

(2) 服务响应可能会延迟。

### 3. Mediator中介者模式（复杂度：**，流行度**）

#### 1) 动机

(1) 在软件构建过程中，经常会出现多个对象互相关联交互的情况，对象之间常常会维持一种复杂的引用关系，如果遇到一些需求的更改，这种直接的引用关系将面临不断的变化。

(2) 在这种情况下，我们可使用一个“中介对象”来管理对象间的关联关系，避免相互交互的对象之间的紧耦合关系，从而更好地抵御变化。

#### 2) 模式定义

用一个中介对象来封装（封装变化）一系列的对象交互。中介者使各对象不需要显式的相互引用（编译时依赖->运行时依赖），从而使其耦合松散（管理变化），而且可以独立地改变它们之间的交互。

#### 3) 要点总结

(1) 将多个对象间复杂的关联关系解耦，Mediator模式将多个对象间的控制逻辑进行集中管理，变“多个对象互相关联”为“多个对象和一个中介者关联”，简化了系统的维护，抵御了可能的变化。

(2) 随着控制逻辑的复杂化，Mediator具体对象的实现可能相当复杂。这时候可以对Mediator对象进行分解处理。

(3) Facade模式是解耦系统间（单向）的对象关联关系；Mediator模式是解耦系统内各个对象之间（双向）的关联关系。

#### 4) 优点

(1) 单一职责原则。 你可以将多个组件间的交流抽取到同一位置， 使其更易于理解和维护。

(2) 开闭原则。 你无需修改实际组件就能增加新的中介者。

(3) 你可以减轻应用中多个组件间的耦合情况。

(4) 你可以更方便地复用各个组件。

#### 5) 缺点

(1) 一段时间后， 中介者可能会演化成为上帝对象。

### 4. Adapter适配器模式（复杂度：*，流行度***）

#### 1) 动机

(1) 在软件系统中，由于应用环境的变化，常常需要将“一些现存的对象”放在新的环境中应用，但是新环境要求的接口是这些现存对象所不满足的。

(2) 如何应对这种“迁移的变化”？如何既能利用现有对象的良好实现，同时又能满足新的应用环境所要求的接口？

#### 2) 模式定义

将一个类的接口转换成客户希望的另一个接口。Adapter模式使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。

#### 3) 要点总结

(1) Adapter模式主要用于“希望复用一些现存的类，但是接口又与复用环境要求不一致的情况”，在遗留代码复用、类库迁移等方面非常有用。

(2) Gof23定义了两种Adapter模式的实现结构：对象适配器和类适配器。但类适配器采用“多继承”的实现方式，一般不推荐使用。对象适配器采用“对象组合”的方式，更符合松耦合精神。

(3) Adapter模式可以实现的非常灵活，不必拘泥于GoF23中定义的两种结构。例如：完全可以将Adapter模式中的“现存对象”作为新的接口方法参数，来达到适配器的目的。

#### 4) 优点

(1) 单一职责原则_你可以将接口或数据转换代码从程序主要业务逻辑中分离。

(2) 开闭原则。 只要客户端代码通过客户端接口与适配器进行交互， 你就能在不修改现有客户端代码的情况下在程序中添加新类型的适配器。

#### 5) 缺点

(1) 代码整体复杂度增加， 因为你需要新增一系列接口和类。 有时直接更改服务类使其与其他代码兼容会更简单。

## 八. 状态变化

> 在组件构建过程中，某些对象的状态经常面临变化，如何对这些变化进行有效的管理？同时又维持高层模块的稳定？“状态变化”模式为这一问题提供了一种解决方案。

### 1. Memento备忘录模式（复杂度：***，流行度*）

#### 1) 动机

(1) 在软件构建过程中，某些对象的状态在转换过程中，可能由于某种需要，要求程序能够回溯到对象之前处于某个点时的状态。如果使用一些共有接口来让其他对象得到对象的状态，便会暴露对象的细节实现。

(2) 如何实现对象状态的良好保存与恢复？但同时又不会因此而破坏对象本身的封装性。

#### 2) 模式定义

在不破坏封装性的前提下，捕获一个对象的内部状态，并在该对象之外保存这个状态。这样以后就可以将该对象恢复到原先保存的状态。

#### 3) 要点总结

(1) 备忘录（Memento）存储原发器（Originator）对象的内部状态，在需要时恢复原发器状态。

(2) Memento模式的核心是信息隐藏，即Originator需要向外界隐藏信息，保持其封装性。但同时有需要将状态保持到外界。

(3) 由于现代语言运行时都具有相当的对象序列化支持，因此往往采用效率较高、有较容易正确实现的序列化方案来实现Memento模式。

#### 4) 优点

(1) 你可以在不破坏对象封装情况的前提下创建对象状态快照。

(2) 你可以通过让负责人维护原发器状态历史记录来简化原发器代码。

#### 5) 缺点

(1) 如果客户端过于频繁地创建备忘录， 程序将消耗大量内存。

(2) 负责人必须完整跟踪原发器的生命周期， 这样才能销毁弃用的备忘录。

(3) 绝大部分动态编程语言 （例如 PHP、 Python 和 JavaScript） 不能确保备忘录中的状态不被修改。

### 2. State状态模式（复杂度：*，流行度**）

#### 1) 动机

(1) 在软件构建过程中，某些对象的状态如果改变，其行为也会随之而发生变化，比如文档处于只读状态，其支持的行为和读写状态支持的行为就可能完全不同。

(2) 如何在运行时根据对象的状态来透明地更改对象的行为？而不会为对象操作和状态转化之间引入紧耦合？

#### 2) 模式定义> d)允许一个对象其内部状态改变时改变它的行为。从而使对象看起来似乎修改了其行为。

#### 3) 要点总结

(1) State模式将所有与一个特定状态相关的行为都放入一个State的子类对象中，在对象状态切换时，切换相应的对象；但同时维持State的接口，这样实现了具体操作与状态转换之间的解耦。

(2) 为不同的状态引入不同的对象使得状态转换变得更加明确，而且可以保证不会出现状态不一致的情况，因为转换是原子性的——即要么彻底转换过来，要么不转换。

(3) 如果State对象没有实例变量，那么各个上下文可以共享同一个State对象（Singleton），从而节省对象开销。

#### 4) 优点

(1) 单一职责原则。 将与特定状态相关的代码放在单独的类中。

(2) 开闭原则。 无需修改已有状态类和上下文就能引入新状态。

(3) 通过消除臃肿的状态机条件语句简化上下文代码。

#### 5) 缺点

(1) 如果状态机只有很少的几个状态， 或者很少发生改变， 那么应用该模式可能会显得小题大作。

## 九. 数据结构

> 常常有一些组件在内部具有特定的数据结构，如果让客户程序依赖这些特定的数据结构，将极大地破坏组件的复用。这时候，将这些特定数据结构封装在内部，在外部提供统一的接口，来实现与特定数据结构无关的访问，是一种行之有效的解决方案。

### 1. Composite组合模式（复杂度：**，流行度**）

#### 1) 动机

(1) 软件在某些情况下，客户代码过多地依赖于对象容器复杂的内部实现结构，对象容易内部实现结构（而非抽象接口）的变化将引起客户代码的频繁变化，带来了代码的维护性、扩展性等弊端。

(2) 如何将“客户代码与复杂的对象容器结构”解耦？让对象容器自己来实现自身的复杂结构，从而使得客户代码就像处理简单对象一样来处理复杂的对象容器？

#### 2) 模式定义

将对象组合成树形结构以表示“部分-整体”的层次结构。Composite使得用户对单个对象和组合对象的使用具有一致性（稳定）。

#### 3) 要点总结

(1) Composite模式采用属性结构来实现普遍存在的对象容器，从而将：“一对多”的关系转化为“一对一”的关系，使得客户代码可以一致地（复用）处理对象和对象容器，无需关心处理的是单个的对象，还是组合的对象容器。

(2) 将“客户代码与复杂的对象容器结构”解耦是Composite的核心思想，解耦之后，客户代码将与纯粹的抽象接口——而非对象容器的内部实现结构——发生依赖，从而更能“应对变化”。

(3) Composite模式在具体实现中，可以让父对象中的子对象反向追溯；如果父对象有频繁的遍历需求，可使用缓存技巧来改善效率。

#### 4) 优点

(1) 你可以利用多态和递归机制更方便地使用复杂树结构。

(2) 开闭原则。 无需更改现有代码， 你就可以在应用中添加新元素， 使其成为对象树的一部分。

#### 5) 缺点

(1) 对于功能差异较大的类， 提供公共接口或许会有困难。 在特定情况下， 你需要过度一般化组件接口， 使其变得令人难以理解。

### 2. Iterator迭代子模式（复杂度：**，流行度***，C++有现成的ierator，因此这个在C++的应用上不是很流行）

#### 1) 动机

(1) 在软件构建过程中，集合对象内部结构常常变化各异。但对于这些集合对象，我们希望在不暴露其内部结构的同时，可以让外部客户代码透明地访问其中包含的元素；同时这种“透明遍历”也为“同一种算法在多种集合对象上进行操作”提供了可能。

(2) 使用面向对象技术将这种遍历机制抽象为”迭代器对象“为”应对变化中的集合对象“提供了一种优雅的方式。

#### 2) 模式定义

提供一种方法顺序访问一个聚合对象中的各个元素，而又不暴露（稳定）该对象的内部表示。

#### 3) 要点总结

(1) 迭代抽象：访问一个聚合对象的内容而无需暴露它的内部表示。

(2) 迭代多态：为遍历不同的集合结构提供一个统一的接口，从而支持同样的算法在不同的集合结构上进行操作。

(3) 迭代器的健壮性考虑：遍历的同时更改迭代器所在的集合结构，会导致问题。

#### 4) 优点

(1) 单一职责原则。 通过将体积庞大的遍历算法代码抽取为独立的类， 你可对客户端代码和集合进行整理。

(2) 开闭原则。 你可实现新型的集合和迭代器并将其传递给现有代码， 无需修改现有代码。

(3) 你可以并行遍历同一集合， 因为每个迭代器对象都包含其自身的遍历状态。

(4) 相似的， 你可以暂停遍历并在需要时继续。

#### 5) 缺点

(1) C++ STL库里范型编程的迭代器远比这里的面向对象型迭代器强大高效许多。但Java Python不一样，还是很实用。

(2) 如果你的程序只与简单的集合进行交互， 应用该模式可能会矫枉过正。

(3) 对于某些特殊集合， 使用迭代器可能比直接遍历的效率低。

### 3. Chain of Resposibility责任链模式（复杂度：**，流行度*）

#### 1) 动机

(1) 在软件构建过程中，一个请求可能被多个对象处理，但是每个请求在运行时只能有一个接受者，如果显示指定，将必不可少地带来请求发送者与接受者的紧耦合。

(2) 如何使请求的发送者不需要指定具体的接受者？让请求的接受者自己在运行时决定来处理请求，从而使两者解耦。

#### 2) 模式定义

使多个对象都有机会处理请求，从而避免请求的发送者和接收者之间的耦合关系。将这些对象连成一条链，并沿着这条链传递请求，直到有一个对象处理它为止。

#### 3) 要点总结

(1) 责任链模式的应用场合在于“一个请求可能有多个接受者，但是最后真正的接受者只有一个”，这时候请求发送者与接受者的耦合有可能出现“变化脆弱“的症状，责任链的目的就是将二者解耦，从而更好地应对变化。

(2) 应用了责任链模式后，对象的职责分派将更具灵活性。我们可以在运行时动态添加/修改请求的处理职责。

(3) 如果请求传递到责任链的末尾仍得不到处理，应该有一个合理的缺省机制。这也是每一个接受对象的责任，而不是发出请求的对象的责任。

#### 4) 优点

(1) 你可以控制请求处理的顺序。

(2) 单一职责原则。 你可对发起操作和执行操作的类进行解耦。

(3) 开闭原则。 你可以在不更改现有代码的情况下在程序中新增处理者。

#### 5) 缺点

(1) 部分请求可能未被处理。

## 十. 行为变化

> 在组件的构建过程中，组件行为的变化经常导致组件本身剧烈的变化。“行为变化”模式将组件的行为和组件本身进行解耦，从而支持组件行为的变化，实现两者之间的松耦合。

### 1. Command命令模式（复杂度：*，流行度***）

#### 1) 动机

(1) 在组件构建过程中，“行为请求者”与“行为实现者”通常呈现一种“紧耦合”。但在某些场合——比如需要对行为进行“记录、撤销/重（undo/redo）、事务”等处理，这种无法抵御变化的紧耦合是不合适的。

(2) 在这种情况下，如何将“行为请求者”与“行为实现者”解耦？将一组行为抽象为对象，可以实现二者之间的松耦合。

#### 2) 模式定义

将一个请求（行为）封装为一个对象，从而使你可用不同的请求对客户进行参数化；对请求排队或记录请求日志，以及支持可撤销的操作。

#### 3) 要点总结

(1) Command模式的根本目的在于将“行为请求者”与“行为实现者”解耦，在面向对象语言中，常见的实现手段是“将行为抽象为对象”。

(2) 实现Command接口的具体命令对象ConcreteCommand有时候根据需要可能会保存一些额外的状态信息。通过使用Composite模式，可以将多个“命令“封装为一个”复合命令”MacroCommand。

(3) Command模式与C++中的函数对象有些类似。但两者定义行为接口的规范有所区别：Command以面向对象中的”接口-实现“来定义行为接口规范，更严格，但有性能损失；C++函数对象以函数签名来定义行为接口规范，更灵活，性能更高。

> a) 今天来看，（配合template）函数对象在C++应用更广，因为性能更高。但是Java上Command模式用的比较多。

#### 4) 优点

(1) 单一职责原则。 你可以解耦触发和执行操作的类。

(2) 开闭原则。 你可以在不修改已有客户端代码的情况下在程序中创建新的命令。

(3) 你可以实现撤销和恢复功能。

(4) 你可以实现操作的延迟执行。

(5) 你可以将一组简单命令组合成一个复杂命令。

#### 5) 缺点

(1) 代码可能会变得更加复杂， 因为你在发送者和接收者之间增加了一个全新的层次。

### 2. Visitor访问者模式（复杂度：***，流行度*）

#### 1) 动机

(1) 在软件构建过程中，由于需求的改变，某些类层次结构中常常需要增加新的行为（方法），如果直接在基类中做这样的更改，将会给子类带来很繁重的变更负担，甚至破坏原有设计。

(2) 如何在不更改类层析结构的前提下，在运行时根据需要透明地为类层次结构上的各个类动态添加新的操作，从而避免上述问题？

#### 2) 模式定义

表示一个作用于某对象结构中得各个元素得操作。使得可以在不改变（稳定）各元素的类的前提下定义（扩展）作用于这些元素的新操作（变化）。

#### 3) 要点总结

(1) Visitor模式通过所谓双重分发（double dispatch）来实现在不更改（不添加新的操作-编译时）Element类层次结构的前提下，在运行时透明地为类层次结构上的各个类动态添加新的操作（支持变化）。

(2) 所谓双重分发即Visitor模式中间包括了两个多态分发（注意其中的多态机制）：第一个为accept方法的多态辨析；第二个为visitElmentX方法的多态辨析。

(3) Visitor模式的最大缺点在于扩展类层次结构（增添新的element子类），会导致Visitor类的改变。因此Visitor模式适用于“element类层次结构稳定，而其中的操作却经常面临频繁改动”。

#### 4) 优点

(1) 开闭原则。 你可以引入在不同类对象上执行的新行为， 且无需对这些类做出修改。

(2) 单一职责原则。 可将同一行为的不同版本移到同一个类中。

(3) 访问者对象可以在与各种对象交互时收集一些有用的信息。 当你想要遍历一些复杂的对象结构 （例如对象树）， 并在结构中的每个对象上应用访问者时， 这些信息可能会有所帮助。

#### 5) 缺点

(1) 每次在元素层次结构中添加或移除一个类时， 你都要更新所有的访问者。

(2) 在访问者同某个元素进行交互时， 它们可能没有访问元素私有成员变量和方法的必要权限。

## 十一. 领域问题

### 1. 在特定领域中，某些变化虽然频繁，但可以抽象为某种规则。这时候，结合特定领域，将问题抽象为语法规则，从而给出在该领域下的一般性解决方案。

### 2. Interpreter解释器模式

#### 1) 动机

(1) 在软件构建过程中，如果某一特定领域的问题比较复杂，类似的结构不断重复出现，如果使用普通的编程方式来实现将面临非常频繁的变化。

(2) 在这种情况下，将特定领域的问题表达为某种语法规则下的句子，然后构建一个解释器来解释这样的句子，从而达到解决问题的目的。

#### 2) 模式定义

给定一个语言，定义它的文法的一种表示，并定义一种解释器，这个解释器使用该表示来解释语言种的句子。

#### 3) 要点总结

(1) Interpreter模式的应用场合是Interpreter模式应用中的难点，只有满足“业务规则频繁变化，且类似的结构不断重复出现，并且容易抽象为语法规则的问题”才适合使用Interpreter模式。

(2) 使用Interpreter模式来表示文法规则，从而可以使用面向对象技术来方便地“扩展“文法。

(3) Interpreter模式比较适合简单的文法表示，对于复杂的文法表示，Interpreter模式会产生比较大的类层次结构，需要求助于语法分析生成器这样的标准工具。

#### 4) 优点

#### 5) 缺点

## 十二. 总结

### 1. 核心目标：管理变化，提高复用！

### 2. 两种手段：分解 vs. 抽象

### 3. 八大原则

#### 1) 依赖倒置原则（DIP）

#### 2) 开放封闭原则（OCP）

#### 3) 单一职责原则（SRP）

#### 4) Liskov替换原则（LSP）

#### 5) 接口隔离原则（ISP）

#### 6) 对象组合优于类继承

#### 7) 封装变化点

#### 8) 面向接口编程

### 4. 重构技法

#### 1) 静态 -> 动态

#### 2) 早绑定 -> 晚绑定

#### 3) 继承 -> 组合

#### 4) 编译时依赖 -> 运行时依赖

#### 5) 紧耦合 -> 松耦合

### 5. 什么时候不用模式

#### 1) 代码可读性很差时

#### 2) 需求理解还很浅时

#### 3) 变化没有显现时

#### 4) 不是系统的关键依赖点

#### 5) 项目没有复用价值时

#### 6) 项目将要发布时

### 6. 经验之谈

#### 1) 不要为模式而模式

#### 2) 关注抽象类&接口

#### 3) 理清变化点和稳定点

#### 4) 审视依赖关系

#### 5) 要有Framework和Application的区隔思维

#### 6) 良好的设计是演化的结果
