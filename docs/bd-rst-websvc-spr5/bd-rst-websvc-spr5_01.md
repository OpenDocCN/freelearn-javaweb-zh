# 第一章：一些基础知识

随着世界进入大数据时代，收集和处理数据成为大多数 Web 应用程序的主要部分，Web 服务也是如此，因为 Web 服务只处理数据，而不处理用户体验、外观和感觉的其他部分。尽管用户体验对所有 Web 应用程序都非常重要，但 Web 服务通过从客户端消费服务在处理数据方面起着重要作用。

在 Web 服务的早期，**简单对象访问协议**（**SOAP**）是所有后端开发人员的默认选择，他们处理 Web 服务消费。SOAP 主要用于 HTTP 和**简单邮件传输协议**（**SMTP**）在相同或不同平台上进行消息传输。当没有**JavaScript 对象表示**（**JSON**）格式可用于 Web 服务时，XML 曾是 SOAP 可用于 Web 服务消费的唯一格式。

然而，在 JSON 时代，**表述性状态转移**（**REST**）开始主导基于 Web 服务的应用程序，因为它支持多种格式，包括 JSON、XML 和其他格式。REST 比 SOAP 更简单，REST 标准易于实现和消费。此外，与 SOAP 相比，REST 更轻量级。

在本章中，我们将涵盖以下主题：

+   REST——基本理解

+   响应式编程及其基础知识，包括响应式编程的好处

+   使用响应式编程的 Spring 5 基础知识

+   将用作本书其余部分基础的示例 RESTful Web 服务

# REST——基本理解

与流行观念相反，REST 不是一种协议，而是一种管理状态信息的架构原则。它主要用于 Web 应用程序。REST 是由 Roy Fielding 引入的，以克服 SOAP 中的实现困难。Roy 的博士论文为检索数据提供了一种简单的方法，而不管使用的平台是什么。您将在以下部分中看到 RESTful Web 服务的所有组件。

# 统一接口

在 REST 原则中，所有资源都由**统一资源标识符**（**URI**）标识。

HTTP REST 资源以 XML、JSON 和 RDF 等媒体类型表示。此外，RESTful 资源是自描述的，这意味着提供了足够的信息来描述如何处理请求。

在另一个 REST 原则中，客户端通过服务器动态提供的超媒体进行交互。除了端点，客户端不需要知道如何与 RESTful 服务进行交互。这个原则被称为**超媒体作为应用状态的引擎**（**HATEOAS**）。

# 客户端和服务器

通过分离 REST 实体，如客户端和服务器，我们可以减少 REST 原则的复杂性，这将显示服务器和客户端之间的明确边界。这种解耦将有助于开发人员独立地专注于客户端和服务器。此外，它将有助于管理客户端和服务器的不同角色。

# 无状态

在 REST 原则中，服务器不会在服务器端保留有关客户端会话的任何状态；因此，它是无状态的。如果从单个客户端向服务器发出两个调用，服务器将不会识别这两个调用是否来自同一个客户端。就服务器而言，每个请求都是独立的和新的。根据 URL、HTTP 标头和请求体，包括参数，操作可能会在服务器端发生变化。

# 可缓存的

使用 RESTful Web 服务，客户端可以缓存来自服务器的任何响应。服务器可以说明如何以及多长时间可以缓存响应。通过缓存选项，客户端可以使用响应而不是再次联系服务器。此外，缓存将通过避免客户端-服务器交互来提高可伸缩性和性能。

这个原则对可扩展性有显著的优势。缓存技术将在第八章 *性能*中讨论。

由于 REST 通常利用 HTTP，它继承了 HTTP 提供的所有缓存属性。

# 分层系统

通过提供分层系统，服务器可以隐藏其身份。通过这样做，客户端将不知道他们正在处理哪个服务器。这个策略通过提供中间服务器和支持负载平衡功能来提供更多的安全控制。此外，中间服务器可以通过负载平衡和共享缓存来提高可扩展性和性能。

# 按需代码（COD）

**按需代码**（**COD**）被认为是一个可选的原则。服务器可以通过传输可执行代码来扩展客户端的功能。例如，可以向基于 Web 的客户端提供 JavaScript 以自定义功能。由于按需代码减少了客户端的可见性，这个约束是可选的。也不是所有的 API 都需要这个功能。

# 更多关于 REST 的内容

在 Web 应用程序中，REST 通常是通过 HTTP 使用的。REST 不需要绑定到任何特定的协议。在 HTTP REST 中，我们主要使用`GET`、`POST`、`PUT`和`DELETE`方法来改变我们访问的资源的状态。其他 HTTP 方法，如`OPTIONS`、`HEAD`、`CONNECT`和`TRACE`，可以用于更高级的操作，例如用于缓存和调试目的。大多数服务器出于安全和简单性的原因已禁用了高级方法；但是，您可以通过调整服务器配置文件来启用它们。由于 JSON 被用作主要的媒体类型，我们在 Web 服务调用中也只使用 JSON 媒体类型。

# 命令式和响应式编程

让我们来看一下命令式编程和响应式编程之间的小比较：*x = y + z*。

在前面的表达式中，假设*y = 10*和*z = 15*。在这种情况下，*x*的值将是*25*。在表达式*x = y + z*的时候，*x*的值将被分配。在这个表达式之后，*x*的值将永远不会改变。

在传统编程世界中这是完全可以的。然而，我们可能需要一个场景，在这个场景中我们应该能够在改变*y*或*z*的值时跟进*x*。

我们的新场景基于以下值：

+   当*y = 20*和*z = 15*时，*x = 35*

+   当*y = 20*和*z = 25*时，*x = 45*

在日常编程中，我们通常使用的命令式编程中不可能出现上述情景。但在某些情况下，我们可能需要根据*y*或*z*的变化更新*x*的值。Reactive 编程是这种情况的完美解决方案。在 Reactive 编程中，*x*的值将会自动更新，以响应*y*或*z*的变化。

电子表格引用单元格是 Reactive 编程的最佳例子。如果一个单元格的值改变，被引用的单元格的值将自动更新。另一个例子可以在模型-视图-控制器架构中找到，Reactive 编程可以自动更新与模型相关联的视图。

Reactive 编程遵循观察者模式来操作和转换数据流，其中发布者（可观察者）根据订阅者的需求发出项目。当发布者发出项目时，订阅者从发布者那里消耗这些发出的项目。与迭代器拉取项目不同，在这里，发布者将项目推送给订阅者。

由于 Reactive 是非阻塞架构的一部分，当我们扩展应用程序时它将会很有用。此外，在非阻塞架构中，一切都被视为事件流。

我们将在本章后面讨论有关 Java 和 Spring 中的 Reactive 的更多内容。

# Reactive Streams

Reactive Streams 主要是处理异步数据流的数据项，应用程序在接收到数据项时对其做出反应。这种模型更节省内存，因为它不依赖于任何内存中的数据。

响应式流有四个主要组件：

1.  发布者。

1.  订阅者。

1.  订阅。

1.  处理器。

发布者发布数据流，订阅者异步订阅该数据流。处理器在不需要改变发布者或订阅者的情况下转换数据流。处理器（或多个处理器）位于发布者和订阅者之间，将一个数据流转换为另一个数据流。

# 响应式编程的好处

Netflix、Pivotal、Twitter、Oracle 和 TypeSafe 的工程师支持响应式流方法。特别是 TypeSafe 对响应式流做出了更多贡献。甚至 Netflix 工程师用他们自己的话说：

“使用 RxJava 进行响应式编程使 Netflix 开发人员能够利用服务器端并发，而无需担心典型的线程安全和同步问题。”

以下是响应式编程的好处：

+   专注于业务逻辑

+   流处理导致内存效率

+   克服低级线程、同步和并发问题

响应式原则在实时案例中得到应用，例如实时数据库查询、大数据、实时分析、HTTP/2 等。

# Java 和 Spring 5 中的响应式编程

Netflix 工程师引入了 RxJava，以支持 Java 8 中的响应式模型，并与 Reactive Streams 进行了桥接。然而，Java 从 Java 9 开始支持响应式模型，并且在 Java 9 中将 Reactive Streams 合并到了 JDK 中的`java.util.concurrent.Flow`中。

此外，Pivotal 推出了 Reactor 框架，该框架直接构建在 Reactive Streams 上，避免了对 Reactive Streams 的外部桥接。Reactor 被认为是第四代库。

最后，Spring Framework 5.0 添加了内置的响应式功能，包括用于 HTTP 服务器和客户端的工具。Spring 用户在处理 HTTP 请求时，特别是将响应式请求和背压问题分派给框架时，会发现注解和控制器非常方便。

响应式模型似乎在资源利用效率上是高效的，因为它可以使用更少的线程处理更高的负载。然而，响应式模型可能并不是所有问题的正确解决方案。在某些情况下，如果我们在错误的部分使用 Reactor，它可能会使情况变得更糟。

# 我们的 RESTful Web 服务架构

由于我们假设读者熟悉 Spring Framework，我们将直接关注我们将要构建的示例服务。

在本书中，我们将构建一个**工单管理系统**。为了清晰地描述工单管理系统及其使用方式，我们将提出一个场景。

假设我们有一个银行网站应用，由我们的客户 Peter 和 Kevin 使用，我们有 Sammy，我们的管理员，以及 Chloe，**客户服务代表**（CSR），在任何银行应用问题的情况下提供帮助。

如果 Kevin/Peter 在 Web 应用中遇到问题，他们可以在我们的工单管理系统中创建一个工单。这个工单将由管理员处理，并发送给处理工单的 CSR。

CSR 从用户那里获取更多信息，并将信息转发给技术团队。一旦 CSR 解决了问题，他们就可以关闭问题。

在我们的工单管理系统中，我们将使用以下组件：

| **工单** |
| --- |

+   `工单 ID`

+   `创建者 ID`

+   `创建时间`

+   `内容`

+   `严重程度`（轻微，正常，重要，严重）

+   `状态`（打开，进行中，已解决，重新打开）

|

| **用户** |
| --- |

+   `用户 ID`

+   `用户名`

+   `用户类型`（管理员，普通用户，CSR）

|

在这个工单管理系统中，我们将专注于：

1.  用户创建一个工单。

1.  用户更新工单。

1.  管理员更新工单状态。

1.  CSR 更新工单状态。

1.  用户和管理员删除工单。

在初始章节中，当我们涉及诸如 AOP、Spring Security 和 WebFlux 等主题时，我们将讨论用户管理，以保持业务逻辑的简单性。然而，在第十三章中，*票务管理-高级 CRUD*，我们将讨论票务管理系统，并实现我们之前提到的所有业务需求。在第十三章中，*票务管理-高级 CRUD*，您将使用其他章节中使用的所有高级技术来完成我们的业务需求。

# 总结

到目前为止，我们已经了解了 REST 和响应式编程的基础知识，以及响应式流的必要性。我们已经学习了带有 Reactor 支持的 Spring 5。此外，我们已经定义了本书其余部分将使用的业务示例和架构。

在下一章中，我们将讨论使用 Maven 进行简单项目创建以及简单的 REST API。此外，我们将讨论 Maven 文件结构和依赖项，包括示例。