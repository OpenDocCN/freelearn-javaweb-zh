# 序言

软件一直是企业的 integral 部分，也是其增长的关键贡献者。无论是分析、用户体验、社会营销、决策支持系统，还是其他任何功能领域，软件一直被用来帮助企业实现顺利和高效运作。企业从小开始，随着时间的推移逐渐成长，其软件依赖也是如此。企业应用程序是在一段时间内开发而成的。处理企业软件时，以下方面会带来一定的挑战：

+   它们分布在一批领域内，例如，工资单、库存、报告和社会集成。

+   这些模块中的每一个可能都是独立开发的，并且可能位于不同的平台上，例如，基于 J2EE 栈的员工自我门户、在大型机上的遗留记录管理系统、使用 Salesforce 的 CRM 系统，以及它们专有实现中的一些实时应用程序。

+   这些模块需要相互交互，并与外部系统交互。它们可能需要通过 SOAP 服务或共享文件从外部来源消费数据，或者它们自己必须通过多种数据共享技术之一共享数据。

+   随着软件的衰老，我们需要引入新的平台并替换现有的模块以减轻不断增长的维护成本。一次性替换的策略是不可行的；相反，在过渡过程中应该以同质化方式进行，而不打扰现有模块的稳定性。

这些模块的集成，无论是内部组织还是与外部合作伙伴集成，都是固有复杂的，需要集成异质端点。这是企业应用集成试图解决的情景。**企业集成模式**（**EIP**）是一系列标准企业挑战及其应对方式的集合。Spring Integration 是 EIP 的一种实现，提供了许多 EIP 推荐的现成组件。

# 企业集成挑战如何解决

许多方法已经被尝试以简化集成，同时不牺牲企业至关重要的方面，例如安全性、事务、可用性、可靠性和 so on。随着时间的推移使用的一些著名方法包括**Java Connector Architecture**（**JCA**）、RMI、RPC 和 CORBA 用于平台无关的集成，带有系统适配器的消息代理等等。在幕后，它们试图通过以下一种或多种技术解决集成问题：

+   **共享文件**：这是最简单的方法。系统可以以预定义的格式向文件写入数据，其他端点可以阅读这些文件。可能需要一个适配器来转换两个不同端点之间的格式。让我们考虑一个例子，以前每天都会生成一个 CSV 文件的报告。随着时间的推移，该组织建立了网站，现在需要将报告推送到线上。这该如何实现？最简单的方法是将它倒入由适配器读取并输入到 CMS 系统的文件中。文件系统很简单，但不是最佳解决方案；它不是事务性的。如果某个特定文件损坏了，或者由于网络故障，轮询间隔内文件不可用怎么办？这需要引入一个具有重试机制、过滤能力等许多非功能性方面的复杂系统，如安全访问、归档等等。

+   **共享数据库**：这解决了一些文件系统所解决的问题，如事务性行为、基于角色的访问、性能调优、分布式支持等等。常见的机制是一组连接表——一个应用程序在别人理解的架构中写入数据。另一方面，这引入了紧密耦合；如果架构发生变更，两个系统都需要相应地更新。发展中的应用程序将成为一个挑战，因为它们必须考虑到外部系统限制。集成工作本身可能从一开始就会遇到很多挫折，例如，应用程序数据库供应商提供的 SQL 兼容性问题、数据格式和表中的类型等等。例如，如果一个系统只存储日期，而另一个系统存储带有时间戳的日期，根据需要，至少有一个将必须更改格式。

+   **远程过程调用**：这种机制引入了一个范例，每个系统都可以通过发布合同来提供服务。这些范例可以是一个方法、参数、结果和错误。例如，一个 EJB 服务或一个 SOAP 服务可以暴露出来，为报告模块提供原始数据，并以多种格式呈现。最限制性的方面是同步行为，系统必须等待结果。还有其他挑战，如数据的序列化、网络延迟、模块的性能问题，这些都可能导致整个应用程序崩溃，等等。从安全角度来看，暴露方法和参数会邀请黑客发挥他们的创造力。

+   **消息传递**：它引入了异步模型，其中两个异构模块可以通过数据在预定义的连接上进行交互。最大的优势是解耦——没有任何系统依赖于其他系统的可用性，并且它们可以参与或退出集成，而不会影响其他组件。JMS 是基于消息传递集成的例子。Spring Integration 基于这种范式，其中多个端点连接到一个通道，生产或消费消息，并根据消息中的信息执行进一步的处理。我们将在接下来的章节中介绍通道、端点、消息载荷和其他概念。

即使我们使用了前面提到的某一种技术，企业系统之间也相去甚远，而且它们可能不会一直运行。这使得需要使用中间件来协调这些不同端点之间的可靠通信，这种中间件通常称为**企业服务总线**（**ESB**）。用通俗的话来说，ESB 可以被定义为使异构接口之间能够双向通信的中介。

# 参与者是谁？

如我们之前所讨论的，企业集成的问题复杂多样，许多供应商尝试在他们自己的专有 ESB 框架中解决它——以前，这些领域一直由商业供应商如 Tibco、Vitria、IBM MQSeries、Oracle SOA Suite、Microsoft BizTalk 等主导。随着时间的推移，对于开源框架的需求变得明显，因为小型组织逐渐成长。他们的集成需求有限，而且无法与这些巨头中的任何一个进行前期投资。

除了 Spring Integration 之外，还有一些著名的开源集成框架，如 Camel、Service Mix、Mule ESB、Open ESB 等。对这些框架的全面比较超出了本书的范围，但为了强调 Spring Integration 的简洁性，这里提供了一个另外两个主要开源框架的简要总结：

+   **Mule ESB**：它是一个标准的服务器，解决方案是在其中开发和部署的。Mule 是市场上最突出和最稳定的解决方案之一。需要注意的一点是，它是一个包含应用程序的容器。

+   **Service Mix (SM)**：Apache Service Mix 基于 JAVA 遗留 JBI（Java Business Integration）。Service Mix 试图通过统一 ActiveMQ、Camel、CXF、ODE 和 Karaf 的功能和特性来解决企业集成的几乎所有方面。它提供了一个完整的、企业级就绪的 ESB，专门由 OSGi 提供动力。因为它试图解决很多模块，所以与 Spring Integration 相比，它相当庞大。

# 为什么使用 Spring Integration？

Spring Integration 是一个开源项目，旨在解决集成挑战；它基于 Spring Framework，这是组织中最广泛使用的基于 Java 的框架。它引入了简单的基于 POJO 的编程模型，以支持标准集成模式。

它轻量级；所有它需要的是几个 jar 文件，Maven 目标已经准备好了。快速比较显示 Service Mix 的下载大小约为 55MB，而 Spring Integration 仅为 14MB。

+   Spring Integration 只是一组标准的 Java 库；解决方案部署在应用程序中，而不是将应用程序部署在某些容器中，如 SM 和 Mule 的情况。

对于已经使用 Java 和 Spring 的企业，它简化了集成工作，因为它遵循 Spring 框架相同的习语和模式。

# 本书涵盖内容

第一章, *入门指南*, 解释了如何设置 Eclipse IDE，“Hello World”程序，以及 Spring ROO 如何进一步简化配置方面的介绍。这将帮助克服配置噩梦，并为开发者提供实践经验。

第二章, *消息摄取*, 介绍了消息可以通过哪些通道读取和处理。它描述了点对点和发布-订阅模型，哪种模型最适合给定场景，如何在通道上以解耦的方式处理错误，以及最后如何在内存通道上支持持久化以实现故障转移和恢复解决方案。

第三章, *消息处理*, 解释了如何定义可以对消息应用业务逻辑的组件，介绍了解耦日志记录，可用于审计，并讨论了添加事务行为。

第四章, *消息转换器*, 讲述了处理消息格式，将其转换为同质格式，以及注解如何帮助保持配置的整洁。消息可以以异构格式引入，如 XML、JSON 等，需要转换为系统能理解的格式。

第五章, *消息流*, 将介绍与消息相关的流程方面，例如过滤不符合验证规则的消息，将它们路由到错误分支，分割消息，并将它们重定向到适合其处理的组件—等待不完整载荷，聚合部分消息，最后是业务处理链。

第六章，*与外部系统的集成*，将提供一个实践性的概览，介绍集成点。与外部系统的集成是 Spring Integration 最有趣和强大的方面——与外部系统的交互只需几行配置即可。Spring Integration 引入了适配器、网关和其他组件，使得与文件系统、SQL、NoSQL 持久化存储、HTTP 服务以及其他广泛使用的实体（如不同服务器、社交媒体等）的交互变得轻而易举。

第七章，*与 Spring Batch 的集成*，将介绍如何使用 Spring Integration 和批处理模块来调度、触发和监控批处理作业。

第八章，*测试支持*，将解释如何利用不同组件的可用的模拟，以及要测试什么、测试多少。

第九章，*监控、管理和扩展*，将介绍如何使用 Spring Integration 配置来利用 JMX 获取系统中不同配置组件的性能统计。我们还将探讨扩展 Spring Integration 组件的方法。

第十章，*一个端到端的示例*，提供了一个端到端的实践示例，帮助你回忆不同章节中介绍的概念，并重新确认他们的理解。代码将被推送到社交代码库，如 GitHub，但本章将为用户提供足够的说明来使用它并运行它。

# 本书你需要什么

你需要一个基于 Java 的集成开发环境，推荐使用 Spring STS。需要 JDK 1.6 及以上版本。

# 本书面向谁

本书面向已经熟悉基本 Java 和 Spring 概念的开发者。熟悉企业集成模式的概念会有帮助，但不是强制性的。本书以实践的方式呈现，选择了一个端到端的实例，并在各个章节中实施和解释。本书将为尝试集成方面的初学者提供强有力的伴侣，为已经熟悉这些挑战并在寻找快速样本的开发者提供实践指南。

# 约定

在本书中，你会发现有许多种文本风格，用于区分不同类型的信息。以下是一些这些风格的示例，以及它们的意义解释。

文本中的代码词汇、数据库表名、文件夹名、文件名、文件扩展名、路径名、假网址、用户输入和 Twitter 处理显示如下："通过导航到**文件** | **Spring 项目**创建一个 Spring Integration 项目，如下截图所示："。

代码块如下所示：

```java
<int:channel id="resultPersistenceChannel">
  <int:queue message-store="messageStore"/>
</int:channel>

<int-jdbc:message-store id="messageStore" data-source="someDataSource"/>
```

当我们希望吸引您的注意力到代码块的某个特定部分时，相关的行或项目会被设置为粗体：

```java
public interface ChannelInterceptor {
  Message<?> preSend(Message<?> message, MessageChannel channel);
  void postSend(Message<?> message, MessageChannel channel, boolean sent);
  boolean preReceive(MessageChannel channel);
  Message<?> postReceive(Message<?> message, MessageChannel channel);
```

**新术语**和**重要词汇**以粗体显示。例如，您在屏幕上、菜单或对话框中看到的词汇，在文本中会显示为这样："点击**下一步**按钮会将您带到下一屏"。

### 注意

警告或重要说明会以这样的盒子出现。

### 提示

技巧和窍门会显示成这样。

# 读者反馈

读者反馈对我们来说总是受欢迎的。让我们知道您对这本书的看法——您喜欢或可能不喜欢的地方。读者反馈对我们开发您真正能从中受益的标题非常重要。

要发送一般性反馈，只需发送一封电子邮件到`<feedback@packtpub.com>`，并通过消息主题提及书籍标题。

如果您在某个主题上有专业知识，并且有兴趣撰写或贡献一本书，请查看我们在[www.packtpub.com/authors](http://www.packtpub.com/authors)上的作者指南。

# 客户支持

既然您已经成为 Packt 书籍的骄傲拥有者，我们有很多事情可以帮助您充分利用您的购买。

## 下载示例代码

您可以从您在[`www.packtpub.com`](http://www.packtpub.com)账户中购买的所有 Packt 书籍的示例代码文件。如果您在其他地方购买了这本书，您可以访问[`www.packtpub.com/support`](http://www.packtpub.com/support)并注册以便将文件直接通过电子邮件发送给您。代码也可以从[`github.com/cpandey05/siessentials`](https://github.com/cpandey05/siessentials)拉取。

## 错误报告

虽然我们已经竭尽全力确保内容的准确性，但是错误仍然会发生。如果您在我们的某本书中发现错误——可能是文本或代码中的错误——我们将非常感谢您能向我们报告。这样做，您可以避免其他读者遭受挫折，并帮助我们改进本书的后续版本。如果您发现任何错误，请通过访问[`www.packtpub.com/submit-errata`](http://www.packtpub.com/submit-errata)报告，选择您的书籍，点击**错误提交** **表单**链接，并输入您错误的详细信息。一旦您的错误得到验证，您的提交将被接受，错误将会上传到我们的网站，或者添加到该标题的错误部分中。任何现有的错误可以通过从[`www.packtpub.com/support`](http://www.packtpub.com/support)选择您的标题来查看。

## 盗版

互联网上侵犯版权材料的问题持续存在，遍布所有媒体。在 Packt，我们非常重视对我们版权和许可的保护。如果您在互联网上以任何形式发现我们作品的非法副本，请立即提供给我们位置地址或网站名称，这样我们才能采取补救措施。

请通过`<copyright@packtpub.com>`联系我们，附上疑似侵权材料的链接。

我们感谢您在保护我们的作者和我们的能力带来有价值内容方面所提供的帮助。

## 问题

如果您在阅读本书的任何方面遇到问题，可以通过`<questions@packtpub.com>`联系我们，我们会尽最大努力解决。
