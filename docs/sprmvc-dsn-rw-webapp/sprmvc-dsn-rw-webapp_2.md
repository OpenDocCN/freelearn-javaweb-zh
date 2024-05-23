# 第一章：第 II 部分 模块 2

> **Spring MVC Cookbook**
> 
> *超过 40 个用于使用 Spring MVC 创建云就绪 Java Web 应用程序的食谱*

# 第一章 企业 Spring 应用程序的设置例程

本章涵盖的主题对应于这个四步例程：

+   为 JEE 开发人员和 Java SE 8 安装 Eclipse

+   为 Java SE 8、Maven 3 和 Tomcat 8 配置 Eclipse

+   使用 Maven 定义项目结构

+   安装 Spring、Spring MVC 和 Web 结构

# 介绍

在我们深入介绍这个初始化开发的例程之前，我们将回答一些问题，这些问题应该帮助您更好地理解这个例程。

请记住，本章的结果也将构成所有后续章节的最小起点。

### 注意

让我们愉快地做吧！

在本书中，我们将代表 ZipCloud 公司行事。ZipCloud 旨在在社交和金融行业构建不同的产品。我们将建立公司的第一个产品：`cloudstreetmarket.com`，这将是一个具有社交功能的精彩股票交易平台。这个项目必须是这个小 ZipCloud 初创公司的一个最佳开端！

## 为什么要有这样一个例程？

无论您最初的目标是什么，都有必要确保设计不会因早期阶段的失败而受到影响。这个例程应该保护您免受这种风险。

例程本身的理念是分享一种引导方法，以启动您现在需要的项目基础，并支持您未来的需求。这个例程也是驱动您的产品思想走向可持续架构的关键，这种架构将易于重构和维护。

为企业级架构设置新项目不会扼杀兴奋和创造力！

## 为什么要使用 Eclipse IDE？

在这个领域存在竞争，但 Eclipse 在 Java 社区中很受欢迎，因为它是一种活跃的开源解决方案；因此，任何人都可以在网上无限制地访问它。它还提供了对 Web 实现的很好支持，特别是对 MVC Web 实现的支持。

## 为什么要使用 Maven？

**Maven**是一个*软件项目管理和理解工具*。它是一个由 Apache 社区和 Apache 软件基金会支持的开源项目。在近 10 年里，Maven 带来了巨大的好处。它还为 Java 项目塑造了一个标准结构。通过其**项目对象模型**（**POM**）方法，它为任何人，潜在地也为任何第三方软件，提供了一种统一和彻底的方式来理解和构建 Java 项目层次结构及其所有依赖关系。

在早期的架构中，考虑以下决定是至关重要的：

+   打开项目定义，可能适用于不同的开发环境和持续集成工具。

+   监控依赖关系，可能确保它们的访问

+   在项目层次结构内强制使用统一的目录结构

+   使用自测组件构建自测软件

选择 Maven 可以确保这些点，并满足我们项目使项目可重用、安全和可测试（自动化）的需求。

## Spring 框架带来了什么？

Spring 框架及其社区已经为 Java 平台做出了超过十年的贡献。详细介绍整个框架需要我们写的不止一本书。然而，基于**控制反转**（**IOC**）和**依赖注入**（**DI**）原则的核心功能，通过对 bean 存储库的高效访问，允许相当大的可重用性。保持轻量级，它确保了很好的扩展能力，可能适用于所有现代架构。

# 为 JEE 开发人员和 Java SE 8 安装 Eclipse

以下食谱是关于下载和安装 Eclipse IDE for JEE 开发人员以及下载和安装 JDK 8 Oracle Hotspot 的。

## 准备工作

这个第一个步骤可能看起来多余或不必要，与您的教育或经验相关。然而，在整本书中拥有统一的配置将为您带来许多好处。

例如，您肯定会避免未知的错误（集成或开发）。您还将体验到与所呈现的屏幕截图中相同的界面。此外，由于第三方产品是活的，您不会遇到意外的屏幕或窗口。

## 如何做…

总的来说，整个第一章需要逐步合作。从下一章开始，我们将使用 GIT，您的积极参与将会减轻。

1.  下载一个 Eclipse IDE for Java EE developers 的发行版：

+   在本书中，我们将使用 Eclipse Luna 发行版。我们建议您安装此版本，以便完全匹配我们的指南和屏幕截图。从[`www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/lunasr1`](https://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/lunasr1)下载 Luna 发行版，选择适合您选择的操作系统和环境。

要下载的产品不是已编译的安装程序，而是一个 zip 存档。

+   如果您对使用另一个版本（更近期）的 Eclipse IDE for Java EE Developers 感到足够自信，所有这些版本都可以在[`www.eclipse.org/downloads`](https://www.eclipse.org/downloads)找到。

### 提示

对于即将进行的安装，在 Windows 上，建议将一些目标位置放在根目录（`C:\`）中。为了避免与权限相关的问题，最好将您的 Windows 用户配置为本地管理员。如果您无法成为此组的一部分，请随意选择您有写访问权限的安装目录。

1.  按照以下步骤将下载的存档解压缩到一个`eclipse`目录中：

+   `C:\Users\{system.username}\eclipse`：如果您使用 Windows，请在此处提取

+   `/home/usr/{system.username}/eclipse`：如果您使用 Linux，请在此处提取

+   `/Users/{system.username}/eclipse`：如果您使用 Mac OS X，请在此处提取

1.  选择并下载 JDK 8：

+   我们建议您下载 Oracle Hotspot JDK。Hotspot 是最初由 Sun Microsystems 开发的高性能 JVM 实现。现在由 Oracle 拥有，Hotspot JRE 和 JDK 可免费下载。

+   然后，通过 Oracle 网站的链接[`www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html`](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)选择与您的机器相对应的产品。

### 注意

为了避免后期的兼容性问题，请保持与您之前为 Eclipse 存档选择的架构选择（32 位或 64 位）一致。

1.  使用以下说明在您选择的操作系统上安装 JDK 8：

在 Windows 上，这是一个由可执行文件启动的受监控的安装：

1.  执行下载的文件，并等待直到您达到下一个安装步骤

1.  在安装步骤窗口上，注意目标目录并将其更改为`C:\java\jdk1.8.X_XX`（`X_XX`指的是最新的当前版本。在本书中，我们将使用 jdk1.8.0_25。此外，不需要安装外部 JRE，因此取消选中公共 JRE 功能。）

在 Linux/Mac 上，执行以下步骤：

1.  下载与您的环境相对应的`tar.gz`存档

1.  将当前目录更改为您想要安装 Java 的位置。为了更容易的指导，让我们同意使用`/usr/java`目录

1.  将下载的`tar.gz`存档移动到当前目录

1.  使用以下命令解压缩存档，目标是您的存档名称：`tar zxvf jdk-8u25-linux-i586.tar.gz`（此示例适用于与 Linux x86 机器相对应的二进制存档）

您必须最终得到包含`/bin`、`/db`、`/jre`、`/include`子目录的`/usr/java/jdk1.8.0_25`目录结构。

## 工作原理…

在本节中，我们将提供有关我们使用的 Eclipse 版本以及我们选择特定版本的 JVM 的更多见解。

### Java EE 开发人员的 Eclipse

我们已经成功地在这里安装了 Eclipse IDE for Java EE developers。与 Eclipse IDE for Java Developers 相比，这个版本还附带了一些额外的包，如*Java EE Developer Tools*、*Data Tools Platform*和*JavaScript Development Tools*。这个版本因其能够作为 IDE 本身的一部分管理开发服务器、自定义项目要素以及支持 JPA 的能力而受到赞赏。Luna 版本官方上兼容 Java SE 8；这在撰写时是一个决定性因素。

### 选择 JVM

JVM 实现的选择可以根据性能、内存管理、垃圾回收和优化能力进行讨论。

有许多不同的 JVM 实现，包括一些开源解决方案，如 OpenJDK 和 IcedTea（RedHat）。选择 JVM 实际上取决于应用程序的要求。我们根据经验和在生产中部署的参考实现选择了*Oracle Hotspot*；这个 JVM 实现可以信任用于各种通用目的。*Hotspot*在运行 Java UI 应用程序时也表现得非常好。Eclipse 就是其中之一。

### Java SE 8

如果您还没有尝试过 Scala 或 Clojure，现在是时候用 Java 搭上函数式编程的列车了！使用 Java SE 8，*Lambda 表达式*大大减少了代码量，提供了更好的*可读性和可维护性*。我们不会实现这个 Java 8 功能，但由于它可能是最受欢迎的，因此必须强调它对范式变化的巨大贡献。如今，熟悉这些模式是很重要的。

# 为 Java 8、Maven 3 和 Tomcat 8 配置 Eclipse

这个教程涉及配置技术，以便在 Eclipse 上有效地开发 Java、Maven 和 Tomcat。

## 准备工作

安装了不同的产品后，我们需要遵循一些步骤，主要是使 Eclipse 与 Java SE 8、Maven 3 和 Tomcat 8 正常工作。在这个教程中，我们还将看看如何自定义 Eclipse 配置文件（`Eclipse.ini`），以充分利用运行 Java 的平台，并确保它能应对应用程序的任何显著增长。

## 如何做…

让我们来看看在桌面上配置 Eclipse 的以下步骤：

1.  您可以通过在桌面上创建一个指向 Eclipse 可执行文件的快捷方式来开始：

+   在 Windows 上，可执行文件是`Eclipse.exe`，位于`eclipse`目录根目录下。

+   在 Linux/Mac 上，文件名为`Eclipse`，也位于`eclipse`目录根目录下

1.  然后，我们需要自定义`eclipse.ini`文件：

在您之前解压缩 Eclipse 存档的 Eclipse 目录中，您可以找到`eclipse.ini`文件。*这是一个文本文件，包含一些命令行选项，以控制 Eclipse 的启动*。

+   Eclipse 社区建议在这里指定我们的 JVM 的路径。因此，根据您的系统，在文件顶部添加以下两行：

对于 Windows，添加以下内容：

```java

-vm 
C:\java\jdk1.8.0_25\jre\bin\server\jvm.dll

```

对于 Linux/Mac，添加以下内容：

```java

-vm 
/usr/java/jdk1.8.0_25/jre/lib/{your.architecture}/server/libjvm.so

```

以下是一个可选的设置，您可以考虑：

+   如果您的开发机器至少有 2GB 的 RAM，您可以输入以下选项，使 Eclipse 比默认设置更快运行。*此部分是可选的，因为 Eclipse 的默认设置已经经过优化，适合大多数用户的环境*：

```java

-vmargs
-Xms128m
-Xmx512m
-Xverify:none
-Dosgi.requiredJavaVersion=1.6
-XX:MaxGCPauseMillis=10
-XX:MaxHeapFreeRatio=70
-XX:+UseConcMarkSweepGC
-XX:+CMSIncrementalMode
-XX:+CMSIncrementalPacing

```

如果您的机器 RAM 少于 2GB，您仍然可以输入这组选项，而不会覆盖默认的`-Xms`和`-Xmx`参数。

### 提示

在`-vmargs`下的所有选项都是在启动时传递给 JVM 的参数。重要的是不要混淆 Eclipse 选项（文件的顶部部分）和 VM 参数（文件的底部部分）。

1.  之后，我们将按照以下步骤启动 Eclipse 并设置工作区：

启动步骤*2*中描述的可执行文件。

+   对于我们的项目，指定路径：`<home-directory>/workspace`

这个路径对于每个操作系统都是不同的：

+   `C:\Users\{system.username}\workspace`：这是 Windows 上的路径

+   `/home/usr/{system.username}/workspace`：这是在 Linux 上

+   `/Users/{system.username}/workspace`：这是在 Mac OS 上

+   单击**确定**，让 Eclipse 程序启动

### 注意

工作区是您管理 Java 项目的地方。它可以特定于一个应用程序，但不一定是。

1.  然后，我们需要检查 JRE 定义：

在 Eclipse 中，需要验证一些设置：

1.  在**窗口**下打开**首选项**菜单（在 Mac OS X 上，**首选项**菜单在**Eclipse**菜单下）。

1.  在左侧的导航面板中，打开 Java 层次结构，然后单击**Java**下的**已安装的 JRE**。

1.  在中央屏幕上，删除您可能已经拥有的任何现有 JRE。

1.  单击**添加...**按钮添加标准 JVM。

1.  输入`C:\java\jdk1.8.0_25`（或`/usr/java/...`）作为**JRE 主目录**。

1.  并输入`jdk1.8.0_25`作为**JRE 名称**。

### 注意

我们告诉 Eclipse 使用 JDK 8 的 Java 运行时环境。

完成这些步骤后，您应该得到以下配置：

![如何操作...](img/image00798.jpeg)

1.  现在，我们将检查编译器兼容性级别：

1.  在导航面板中，单击**Java**下的**编译器**。

1.  检查下拉列表中的**编译器兼容性级别**是否设置为**1.8**。

1.  之后，我们需要检查 Maven 配置：

1.  仍然在**首选项**菜单的导航面板中，打开 Maven 层次结构，然后导航到**Maven** | **安装**。

1.  我们将在这里指定我们计划使用的 Maven 安装。对于本书的目的，嵌入式 Maven 将是完美的。

1.  返回到导航面板，转到**Maven** | **用户设置**。

1.  将本地存储库设置为`<home-directory>/.m2/repository`。

### 注意

在本地存储库中，我们将保存所需工件的本地缓存版本。这将防止我们的环境在每次构建时都需要下载它们。

1.  对于**用户设置**字段，在`.m2`目录中创建一个`settings.xml`文件：`<home-directory>/.m2/settings.xml`。

1.  编辑`settings.xml`文件并添加以下块：

（您还可以从`chapter_1/source_code/.m2`目录中复制/粘贴）：

```java
<settings  
  xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.1.0 http://maven.apache.org/xsd/settings-1.1.0.xsd">
  <profiles>
    <profile>
      <id>compiler</id>
        <properties>
          <JAVA_HOME>C:\java\jdk1.8.0_25</JAVA_HOME>
        </properties>
    </profile>
  </profiles>
  <activeProfiles>
  <activeProfile>compiler</activeProfile>
  </activeProfiles>
</settings>
```

### 提示

如果您不是 Windows 机器，请将此文件中的`JAVA_HOME`更改为您的 JDK 安装目录（`/usr/java/jdk1.8.0_25`）。

1.  返回到导航面板，单击**Maven**。按照此截图中给出的配置进行操作：![如何操作...](img/image00799.jpeg)

1.  单击**确定**以保存这些配置更改。

1.  现在我们将在 Eclipse IDE 中安装 Tomcat 8。为此，请按照以下步骤进行：

1.  从 Tomcat 网站下载最新的 Tomcat8 核心版本的 ZIP 存档：[`tomcat.apache.org/download-80.cgi`](http://tomcat.apache.org/download-80.cgi)。

1.  将下载的存档解压缩到以下目录：

+   在 Windows 上，将存档解压缩到`C:\tomcat8`

+   在 Linux 上，将存档解压缩到`/home/usr/{system.username}/tomcat8`

+   在 Mac OS X 上，将存档解压缩到`/Users/{system.username}/tomcat8`

### 注意

根据您的系统，您必须能够从层次结构中访问 bin 目录：`C:\tomcat8\bin, /home/usr/{system.username}/tomcat8/bin 或 /Users/{system.username}/tomcat8/bin`。

1.  在 Eclipse 中，选择**窗口**下的**首选项**菜单，然后在左侧的导航面板中，打开**服务器**层次结构，然后选择**运行时环境**。

1.  在中央窗口中，单击**添加...**按钮。

1.  在下一步（**新服务器**环境窗口）中，导航到**Apache** | **Apache Tomcat v8.0**。

1.  还要检查此选项：**创建新的本地服务器**。

1.  单击**下一步**按钮。

1.  按照以下截图中显示的窗口中的详细信息填写：

![如何做...](img/image00800.jpeg)

### 注意

如果您使用 Linux（或 Mac OS X），请用您的 Tomcat 安装目录替换`C:\tomcat8`。

## 工作原理...

在本节中，我们将回顾这个食谱带我们经历的不同元素和概念。

### eclipse.ini 文件

正如我们已经看到的，`eclipse.ini`文件控制 Eclipse 的启动。它是使 Eclipse 平台非常可配置的额外组件。您可以在他们的文档中找到可以在命令行中使用的命令行参数列表

[`help.eclipse.org/luna/topic/org.eclipse.platform.doc.isv/reference/misc/runtime-options.html`](http://help.eclipse.org/luna/topic/org.eclipse.platform.doc.isv/reference/misc/runtime-options.html)

重要的是要注意文档中提到的以下警告：

+   在`-vmargs`之后的所有行都作为参数传递给 JVM；所有 Eclipse 的参数和选项都必须在`-vmargs`之前指定（就像在命令行上使用参数时一样）

### 注意

这解释了为什么我们在文件顶部插入了`–vm`选项。

+   在命令行上使用`-vmargs`会替换`.ini`文件中所有`-vmargs`的设置，除非在`.ini`文件中或在命令行上指定了`--launcher.appendVmargs`

### 设置`-vm`选项

设置`-vm`选项可以确保 Eclipse 作为程序运行的 JVM 实现。您可能已经注意到，我们已经将 JVM 作为库(`*.dll / *.so`)。它在启动时具有更好的性能，并且还将程序进程标识为 Eclipse 可执行文件，而不仅仅是 Java 可执行文件。

如果您想知道当未设置`–vm`选项时 Eclipse 使用哪个 JVM，请注意 Eclipse *不会*查看`JAVA_HOME`环境变量。（Eclipse wiki）。

相反，Eclipse 执行解析您的路径环境变量的 Java 命令。

### 自定义 JVM 参数

建议的 JVM 参数列表来自 Piotr Gabryanczyk 关于 Java 内存管理模型的工作。最初，对于 JetBRAINS IntelliJ 设置，这个配置对 Eclipse 环境也很有用。它有助于以下任务：

+   防止垃圾收集器暂停应用程序超过 10 毫秒(`-XX:MaxGCPauseMillis=10`)

+   将垃圾收集器开始的级别降低到占用内存的 30%（`-XX:MaxHeapFreeRatio=70`）

+   强制垃圾收集器作为并行线程运行，降低其对应用程序的干扰（`-XX:+UseConcMarkSweepGC`）

+   选择垃圾收集器的增量调整模式，生成 GC 作业中断，以便应用程序可以停止冻结(`–XX:+CMSIncrementalPacing`)

程序生命周期中实例化的对象存储在堆内存中。建议的参数定义了 JVM 启动堆空间为 128 mb（`-Xms`），总体上限为 512 mb（`–Xmx`）。堆分为两个子空间，如下所示：

+   **年轻代**: 新对象存储在这个区域。对于领先的 Hotspot 或 OpenJDK JVM，年轻内存空间分为两部分：

+   `伊甸园`: 新对象存储在这个分区中。寿命短的对象将从这里被释放。

+   `幸存者`: 这是年轻代和老年代之间的缓冲区。幸存者空间比伊甸园小，也分为两部分（`FROM`和`TO`区域）。您可以使用`-XX:SurvivorRatio`调整`伊甸园`和`幸存者`对象之间的比例（这里，`-XX: SurvivorRatio=10`表示`YOUNG = 12`，`EDEN = 10`，`FROM = 1`和`TO =1`）。

### 提示

年轻区的最小大小可以使用`-XX:NewSize`进行调整。最大大小可以使用`-XX:MaxNewSize`进行调整。

+   老一代：当`Eden`或`Survivor`空间中的对象在足够多的垃圾收集后仍然被引用时，它们会被移动到这里。可以使用`-XX:NewRatio`设置`Young`区域大小作为`Old`区域大小的比例。（也就是说，`-XX:NewRatio=2`表示`HEAP = 3，YOUNG = 1`和`OLD =2`）。

### 提示

新一代空间的最大大小`-XX:MaxNewSize`必须始终小于堆空间的一半（`-Xmx/2`），因为垃圾收集器可能会将所有`Young`空间移动到`Old`空间。

使用 Hotspot 或 OpenJDK，永久代空间用于存储与类的定义相关的信息（结构、字段、方法等）。当加载的结构变得太大时，您可能已经遇到过`PermGen space OutOfMemoryError`异常。在这种情况下，解决方案是增加`-XX:MaxPermSize`参数。*在 JDK8 中不再需要*。

为此，**Permanent Generation**（**PermGen**）空间已被一个不属于堆而属于本机内存的元数据空间所取代。这个空间的默认最大大小是无限的。然而，我们仍然可以使用`-XX:MetaspaceSize`或`-XX:MaxMetaspaceSize`来限制它。

### 更改 JDK 兼容级别

降低兼容级别允许我们运行一个比 JDK 本身识别的更低版本的 Java 编译器。它会影响 Eclipse 的构建、错误和警告，以及 JavaDocs。显然，不能设置比编译器的本机版本更高的编译版本。

### 配置 Maven

在 Eclipse 中，大部分的 Maven 配置来自`m2eclipse`插件（也称为 Eclipse 的 Maven 集成）。这个插件默认包含在 Eclipse Luna 中，因此不需要手动下载。在我们经历的 Maven 配置之后，m2eclipse 也非常有助于从 IDE 上下文触发 Maven 操作，并提供帮助来创建 Java Maven 项目。您将在下一节中了解更多关于 m2eclipse 的内容。

然后我们安装了一个基本的`settings.xml`文件。这个文件用于配置 Maven，而不直接绑定到任何项目。`settings.xml`最常见的用途可能是配置文件和凭据存储以访问存储库管理器。

使用 Maven 配置文件，您可以为特定环境运行构建，并匹配特定配置（变量值、依赖项集等）。Maven 配置文件可以相互叠加。它们可以通过命令行、在 Maven 设置中声明，或者通过环境配置（例如文件在文件系统上存在或缺失、使用的 JDK 等）来激活。

### 提示

在我们的`settings.xml`文件中，我们已经定义了一个具有自己`JAVA_HOME`属性的编译器配置文件。编译器配置文件默认激活，以在`<activeProfiles>`部分中声明定义。Maven 在查找系统变量之前将查阅`settings.xml`文件。

### 存储库管理器

存储库管理器是一个第三方应用程序，管理开发应用程序可能需要的所有必需的二进制文件和依赖项。作为开发环境和公共存储库之间的缓冲代理，存储库管理器提供了对关键参数的控制，如构建时间、依赖项的可用性、可见性和访问限制等。

著名的解决方案包括*Apache Archiva*，*Artifactory*，*Sonatype Nexus*。在我们的应用程序环境中，我们不会使用存储库管理器。

### Eclipse 中的 Tomcat 8

Eclipse for JEE 开发人员允许在开发环境中集成 Tomcat 与其他应用服务器。这是通过提供的**Web 工具平台**（**WTP**）插件实现的，可以管理 Web 工件、它们的编译和部署到 Web 服务器。

在`服务器`选项卡（之前可见），双击创建的 Tomcat v8.0 服务器，打开一个配置窗口，并启用设置通常在`tomcat8\conf`目录中的`server.xml` Tomcat 文件中定义的参数的可能性。

默认情况下，WTP 会抽象出这个配置，不会影响真正的`server.xml`文件。这种行为可以通过在**服务器配置**窗口中激活**将模块上下文发布到单独的 XML 文件**选项来更改。

## 还有更多...

+   在[`wiki.eclipse.org/Eclipse/Installation`](http://wiki.eclipse.org/Eclipse/Installation)了解更多关于 Eclipse 安装的信息

+   在`Eclipse.ini`文件中了解更多信息，请访问[`wiki.eclipse.org/Eclipse.ini`](http://wiki.eclipse.org/Eclipse.ini)

+   了解有关 m2eclipse 插件的更多信息，请访问[`maven.apache.org/plugins/maven-eclipse-plugin/`](https://maven.apache.org/plugins/maven-eclipse-plugin/)

+   要了解如何使用存储库管理器，请参阅[`maven.apache.org/repository-management.html`](http://maven.apache.org/repository-management.html)

+   关于 IDE 的垃圾收集优化的 Piotr Gabryanczyk 文章可以在[`piotrga.wordpress.com/2006/12/12/intellij-and-garbage-collection`](http://piotrga.wordpress.com/2006/12/12/intellij-and-garbage-collection)找到

+   您可以在[`pubs.vmware.com/vfabric52/topic/com.vmware.vfabric.em4j.1.2/em4j/conf-heap-management.html`](http://pubs.vmware.com/vfabric52/topic/com.vmware.vfabric.em4j.1.2/em4j/conf-heap-management.html)和[`blog.codecentric.de/en/2012/08/useful-jvm-flags-part-5-young-generation-garbage-collection`](https://blog.codecentric.de/en/2012/08/useful-jvm-flags-part-5-young-generation-garbage-collection)了解更多关于内存优化的信息

# 使用 Maven 定义项目结构

在这个教程中，我们将专注于使用 Maven 定义我们应用程序所需的项目结构。

## 准备工作

我们将首先创建两个 Eclipse 项目：一个用于应用程序，一个用于 ZipCloud 作为公司以后可能与其他项目共享的组件。看一下下面的图片，它展示了我们将要构建的项目组件：

![准备就绪](img/image00801.jpeg)

应用程序项目**cloudstreetmarket-parent**将有三个模块。其中两个将被打包为 Web 存档（**war**）：主 Web 应用程序和 REST API。其中一个将被打包为**jar**依赖项（cloudstreetmarket-core）。

公司特定项目**zipcloud-parent**将只有一个子模块—**zipcloud-core**，它将被打包为**jar**。

## 如何做...

以下步骤将帮助我们创建一个 Maven 父项目：

1.  从 Eclipse 导航到**文件** | **新建** | **其他**。

1.  **新建**向导打开，您可以在其中选择层次结构内的项目类型。然后，打开**Maven**类别，选择**Maven 项目**，然后点击**下一步**。

新的 Maven 项目向导打开，如下截图所示：

![如何做...](img/image00802.jpeg)

1.  确保选中**创建一个简单的项目**选项。点击**下一步**。

1.  按照以下向导填写下一个向导：

+   `edu.zipcloud.cloudstreetmarket`作为**Group Id**

+   `cloudstreetmarket-parent`作为**Artifact Id**

+   `0.0.1-SNAPSHOT`作为**版本**

+   `pom`作为**包装**

+   `CloudStreetMarket Parent`作为**名称**

+   然后，点击**完成**按钮

父项目必须出现在仪表板左侧的包资源管理器中。

![如何做...](img/image00803.jpeg)

现在我们必须告诉 m2eclipse 你计划在这个项目中使用哪个 Java 编译器版本，以便它自动向我们即将创建的子模块添加正确的 JRE 系统库。这是通过`pom.xml`文件完成的。

1.  编辑`pom.xml`文件以指定 Java 编译器版本：

+   双击**pom.xml**文件。**m2eclipse** **概述**选项卡默认显示。您必须点击最后一个选项卡**pom.xml**才能访问完整的 XML 定义。

+   在此定义中，在**<project>**节点的末尾添加以下块。(*您也可以从* `chapter_1` *源代码的* `cloudstreetmarket-parent` *的* `pom.xml` *中复制/粘贴这段代码):*

```java
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.1</version>
      <configuration>
          <source>1.8</source>
          <target>1.8</target>
          <verbose>true</verbose>
          <fork>true</fork>
          <executable>${JAVA_HOME}/bin/javac</executable>
          <compilerVersion>1.8</compilerVersion>
      </configuration>
    </plugin>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-surefire-plugin</artifactId>
      <version>2.4.2</version>
      <configuration>
        <jvm>${JAVA_HOME}/bin/java</jvm>
        <forkMode>once</forkMode>
       </configuration>
    </plugin>
  </plugins>
</build>
```

### 注意

您可能已经注意到了**maven-surefire-plugin**的声明。我们很快将对其进行审查；它允许我们在构建过程中运行单元测试。

1.  现在，我们将创建子模块：

作为父项目的子模块，我们已经看到我们需要一个 Web 模块来处理和渲染网站的屏幕，一个用于 REST API 的 Web 模块，以及另一个模块，用于打包所有与第一个产品`cloudstreetmarket.com`相关的业务逻辑（服务，数据访问等）：

1.  从 Eclipse 的主 Webapp 模块中，导航到**文件** | **新建** | **其他**。一个**新建**向导会打开，您可以在其中选择层次结构中的项目类型。打开**Maven**类别，选择**Maven 模块**，然后点击**下一步**。

1.  在此之后，**新建 Maven 模块**向导打开，填写如下：

勾选创建一个简单的项目。

输入`cloudstreetmarket-webapp`作为**Module Name**。

输入`cloudstreetmarket-parent`作为**Parent project**。

![如何做...](img/image00804.jpeg)

1.  点击**下一步**按钮后，下一步将显示。在新窗口中输入以下条目：

输入`edu.zipcloud.cloudstreetmarket`作为**Group Id**。

输入`0.0.1-SNAPSHOT`作为**Version**。

将**war**作为**Packaging**选择。

输入`CloudStreetMarket Webapp`作为**Name**。

然后点击**完成**按钮。

1.  现在我们将继续创建 REST API 模块：

我们将使用不同的参数重复上述操作。

1.  从 Eclipse 中导航到**文件** | **新建** | **其他**。当您这样做时，选择向导会弹出。在此之后，打开**Maven**类别，选择**Maven 模块**，然后点击**下一步**：

1.  在**新建 Maven 模块**向导中，输入以下条目：

勾选**创建一个简单的项目**选项。

输入`cloudstreetmarket-api`作为**Module Name**。

输入`cloudstreetmarket-parent`作为**Parent project**。

1.  点击**下一步**按钮进入下一步。在该窗口中输入以下条目：

输入`edu.zipcloud.cloudstreetmarket`作为**Group Id**。

输入`0.0.1-SNAPSHOT`作为**Version**。

将**war**作为**Packaging**选择。

输入`CloudStreetMarket API`作为**Name**。

然后点击完成按钮。

1.  现在，我们将创建核心模块：

为此，导航到**文件** | **新建** | **其他**。当您这样做时，选择向导会弹出。打开**Maven**类别，选择**Maven 模块**，然后点击**下一步**。

1.  在**新建 Maven 模块**向导中，输入以下条目：

勾选**创建一个简单的项目**选项。

输入`cloudstreetmarket-core`作为**Module Name**。

输入`cloudstreetmarket-parent`作为**Parent project**。

1.  点击**下一步**按钮进入下一步。填写以下字段：

输入`edu.zipcloud.cloudstreetmarket`作为**Group Id**。

输入`0.0.1-SNAPSHOT`作为**Version**。

这次，将**jar**作为**Packaging**选择。

输入`CloudStreetMarket Core`作为**Name**。

然后点击完成按钮。

如果您已激活了 Java 透视图（在右上角），您应该看到整体创建的结构与此处的屏幕截图匹配：

![如何做...](img/image00805.jpeg)

1.  现在，我们将创建一个特定于公司的项目及其模块：

假设以后公司业务项目将包含许多不同类别的依赖项（核心，消息传递，报告等...）。

1.  我们需要一个父项目，因此从 Eclipse 中导航到**文件** | **新建** | **其他**。选择向导弹出。打开 Maven 类别，选择 Maven 项目，然后点击下一步。

1.  在新 Maven 项目向导的第一步中，对于我们之前创建的父项目，只需选中**创建简单项目**和**使用默认工作区位置**选项。

1.  单击**下一步**按钮，并填写下一个向导如下：

输入`edu.zipcloud`作为**Group Id**。

输入`zipcloud-parent`作为**Artifact Id**。

输入`0.0.1-SNAPSHOT`作为**版本**。

选择**pom**作为**打包**。

输入`ZipCloud Factory Business Parent`作为**名称**。

同样，在创建的`pom.xml`文件中，在`<project>`节点内添加以下块，以正确创建基础模块并启用自动测试执行。 (*您还可以从第一章源代码的 zipcloud-parent 的 pom.xml 文件中复制/粘贴此代码段*):

```java
<build>
  <plugins>
    <plugin>
    <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.1</version>
      <configuration>
        <source>1.8</source>
        <target>1.8</target>
          <verbose>true</verbose>
          <fork>true</fork>
        <executable>${JAVA_HOME}/bin/javac</executable>
      <compilerVersion>1.8</compilerVersion>
      </configuration>
    </plugin>
    <plugin>
    <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-surefire-plugin</artifactId>
        <version>2.4.2</version>
        <configuration>
        <jvm>${JAVA_HOME}/bin/java</jvm>
        <forkMode>once</forkMode>
      </configuration>
    </plugin>
  </plugins>
</build>
```

现在，我们将创建一个公司业务核心模块，它将是我们刚刚创建的父项目的子模块。

为此，请导航至**文件** | **新建** | **其他**。 选择向导弹出。 打开**Maven**类别，选择**Maven 模块**，然后单击**下一步**。

1.  在**新 Maven 模块**向导中，输入以下详细信息：

检查**创建简单项目**选项。

输入`zipcloud-core`作为**模块名称**。

输入`zipcloud-parent`作为**父项目**。

1.  单击**下一步**按钮，进入下一步。 在这里，输入以下详细信息：

输入`edu.zipcloud`作为**Group Id**。

输入`0.0.1-SNAPSHOT`作为**版本**。

选择**jar**作为**打包**。

选择`ZipCloud Factory Core Business`作为**名称**。

1.  现在，构建这两个项目：

如果结构正确，以下 Maven 命令可以成功运行：

```java

mvn clean install

```

### 提示

如果在开发机器上安装了 Maven，则可以在终端中启动此命令。

在我们的研究案例中，我们现在将使用 m2eclipse 修改后的**Run As**菜单进行启动：右键单击 zipcloud-parent 项目，然后单击**Run As** | **Maven Clean**。

### 注意

在 Maven 控制台中，您现在应该在底部看到这一行：

[INFO] BUILD SUCCESS

现在，重复安装构建阶段的操作。 您现在应该在控制台中看到以下输出：

```java

[INFO] ZipCloud Parent .......................SUCCESS [  0.313 s]
[INFO] ZipCloud Core .........................SUCCESS [  1.100 s]
[INFO] ----------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ----------------------------------------------------------

```

好的，现在您应该能够构建`cloudstreetmarket-parent`。

为此，请右键单击**cloudstreetmarket-parent**项目，然后单击**Run As** | **Maven Clean**。 在此步骤之后，Maven 控制台应打印以下内容：

```java

[INFO] BUILD SUCCESS

```

再次右键单击**cloudstreetmarket-parent**项目，然后单击**Run As** | **Maven Install**。 Maven 控制台现在应该打印以下内容：

```java

[INFO] CloudStreetMarket Parent ..............SUCCESS [  0.313 s]
[INFO] CloudStreetMarket Webapp ..............SUCCESS [  6.129 s]
[INFO] CloudStreetMarket Core ................SUCCESS [  0.922 s]
[INFO] CloudStreetMarket API .................SUCCESS [  7.163 s]
[INFO] ----------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ----------------------------------------------------------

```

向上滚动一点应该显示以下跟踪：

```java

-------------------------------------------------------
 T E S T S
-------------------------------------------------------
There are no tests to run.
Results :
Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

```

### 注意

在这里，Maven 借助我们手动添加的 maven-surefire-plugin 解析`src/test/java`目录中遇到的所有类。 再次，此路径可以自定义。

在检测到的测试类中，Maven 还将运行使用 JUnit `@Test`注解标记的方法。 项目中需要 JUnit 依赖项。

## 它是如何工作的...

在本节中，我们将介绍有关 Maven 的许多概念，以便您更好地理解其标准。

### 新的 Maven 项目，新的 Maven 模块

我们刚刚经历的项目创建屏幕也来自 m2eclipse 插件。 这些屏幕用于使用预配置的`pom.xml`文件和标准目录结构初始化 Java 项目。

m2eclipse 插件还提供了一组快捷方式来运行 Maven 构建阶段以及一些方便的选项卡（已经看到）来管理项目依赖关系并可视化`pom.xml`配置。

### 标准项目层次结构

浏览创建的项目，您应该能够注意到以下目录的重复层次结构：`src/main/java`，`src/main/resource`，`src/test/java`和`src/test/resource`。 这种结构是 Maven 引导我们的默认结构。 *这种模型现在已经成为标准*。 但是，我们仍然可以覆盖它（在`pom.xml`文件中）并创建我们自己的层次结构。

如果您还记得在父项目的`pom.xml`文件中添加的**maven-compiler-plugin**定义，我们使用了以下四行代码：

```java
<verbose>true</verbose>
<fork>true</fork>
<executable>${JAVA_HOME}/bin/javac</executable>
<compilerVersion>1.8</compilerVersion>
```

这些行允许 Maven 使用外部 JDK 进行编译。最好能够控制 Maven 使用的编译器，特别是在管理不同环境时。

还有以下两行可能看起来过于配置：

```java
<source>1.8</source>
<target>1.8</target>
```

从严格的 Maven 观点来看，当使用指定的 compilerVersion 定义外部 JDK 时，这些行是可选的。最初，通过这两行，我们可以控制默认代码要在哪个 Java 版本中编译。在维护旧系统时，现有代码可能仍然在以前的 Java 版本中编译。

实际上，m2eclipse 特别希望这两行存在，以便将`JRE System Library [JavaSE-1.8]`添加到`jar`和`war`模块的构建路径中。现在，有了这些行，Eclipse 以与 Maven 相同的方式编译这些项目：在 Java SE 8 中。

### 提示

如果此依赖项仍显示为不同版本的 Java，您可能需要右键单击模块，然后导航到**Maven** | **Update Project**。

### IDE 中的项目结构

关于 Eclipse 项目层次结构中的父项目；您是否注意到创建的子模块似乎重复出现为独立项目和父项目的直接子项目？这是因为 Eclipse 目前在 Luna 中尚未处理项目层次结构。因此，模块显示为分开的项目。这可能会有点令人困惑，因为源代码似乎位于父项目旁边。*实际上并非如此，这只是它们呈现的方式，因此我们可以像通常绑定到项目级别一样拥有所有工具*。

### 注意

此时，JetBRAINS IntelliJ IDEA 已经支持项目的可视化层次结构。

最后，如果您打开父项目的`pom.xml`文件，您应该看到`<modules>`节点中填充了创建的子模块。这也是 m2eclipse 自动完成的。我们建议您密切关注此功能，因为根据您如何更改项目层次结构，m2eclipse 并不总是更新这些`<modules>`节点。

### Maven 的构建生命周期

Maven 中的构建生命周期是一组预定义操作（称为阶段）的特定顺序。Maven 中存在三个生命周期：默认、清理和站点。

让我们看看包括默认和清理生命周期的所有阶段（可能是开发人员最常用的生命周期）。

#### 清理生命周期

Maven 的**clean**阶段起着核心作用。它从 Maven 的角度重置项目构建。通常是删除 Maven 在构建过程中创建的目标目录。以下是**clean**生命周期中包含的一些阶段的详细信息。这些详细信息来自 Maven 文档：

| 阶段 | 描述 |
| --- | --- |
| `pre-clean` | 在实际项目清理之前执行必要的进程 |
| `clean` | 删除上一次构建生成的所有文件 |
| `post-clean` | 这执行需要完成项目清理的进程 |

#### 默认生命周期

在默认生命周期中，您可以找到处理源代码生成、编译、资源处理、测试、集成测试和构件部署的最有趣的构建阶段。以下是默认生命周期中包含的一些阶段的详细信息：

| 阶段 | 描述 |
| --- | --- |
| `validate` | 验证项目是否正确，是否有所有必要的信息可用。 |
| `initialize` | 这初始化构建状态，例如设置属性或创建目录。 |
| `generate-sources` | 生成要包含在编译中的源代码。 |
| `process-sources` | 处理源代码，例如过滤任何值。 |
| `generate-resources` | 这将生成要包含在包中的资源。 |
| `process-resources` | 这将资源复制并处理到目标目录，准备打包。 |
| `compile` | 这将编译项目的源代码。 |
| `process-classes` | 这将处理编译生成的文件，例如对 Java 类进行字节码增强。 |
| `generate-test-sources` | 这将生成任何要包含在编译中的测试源代码。 |
| `process-test-sources` | 这将处理测试源代码，例如过滤任何值。 |
| `generate-test-resources` | 这将创建用于测试的资源。 |
| `process-test-resources` | 这将资源复制并处理到测试目标目录中。 |
| `test-compile` | 这将测试源代码编译到测试目标目录中。 |
| `process-test-classes` | 这个过程处理来自测试编译的生成文件，例如对 Java 类进行字节码增强。适用于 Maven 2.0.5 及以上版本。 |
| `test` | 这将使用适当的单元测试框架运行测试。这些测试不应该需要代码打包或部署。 |
| `prepare-package` | 这将在实际打包之前执行必要的操作以准备包。这通常会导致包的未打包、处理版本。（Maven 2.1 及以上） |
| `package` | 这将编译后的代码打包成可分发的格式，比如 JAR。 |
| `pre-integration-test` | 这将在执行集成测试之前执行所需的操作。这可能涉及设置所需的环境。 |
| `integration-test` | 这将处理并部署包（如果需要）到可以运行集成测试的环境中。 |
| `post-integration-test` | 这在集成测试执行后执行所需的操作。这可能包括清理环境。 |
| `verify` | 这将运行检查以验证包是否有效并符合质量标准。 |
| `install` | 这将包安装到本地存储库中，以便在其他项目中作为依赖项使用。 |
| `deploy` | 这将把最终的包复制到远程存储库，与其他开发人员和项目共享（在集成或发布环境中完成）。 |

#### 插件目标

有了插件的概念，Maven 获得了更广泛的维度。Maven 本身提供了内置插件，但外部插件可以像其他依赖项一样引入（通过 groupIds 和 artefactIds 标识）。

每个构建阶段可以附加到零个、一个或多个插件目标。一个目标代表一个具体的任务，负责以某种方式构建或处理项目。一些阶段通过本机插件默认绑定了目标。

#### 内置生命周期绑定

现在我们已经看到了两个生命周期中每个阶段的目的，我们必须说，默认生命周期取决于我们选择的模块打包类型，只有一些阶段可能会潜在地被激活以执行目标。

让我们看看对于不同的打包类型，我们在默认生命周期中跳过了哪些阶段：

|   | 默认生命周期 |
| --- | --- |
| 打包类型 | jar/war/ejb/ejb3/rar | ear | maven-plugin | pom |
| --- | --- | --- | --- | --- |
| 激活的阶段 |   | generate-resources | generate-resources |   |
| process-resources | process-resources | process-resources |   |
| compile |   | compile |   |
| process-test-resources |   | process-test-resources |   |
| test-compile |   | test-compile |   |
| test |   | test |   |
| package | package | package | package |
| install | install | install | install |
| deploy | deploy | deploy | deploy |

### 提示

在第九章中，*测试和故障排除*，我们将实际将外部插件目标绑定到识别的构建阶段。

总之，在`jar`打包的模块上调用：mvn clean install 将导致执行以下阶段：clean，process-resources，compile，process-test-resources，test-compile，test，package 和 install。

#### 关于 Maven 命令

当告诉 Maven 执行一个或多个针对特定项目的`pom.xml`文件的阶段时，它将为每个模块执行请求的阶段。

然后，对于每个单独请求的阶段，Maven 将执行以下操作：

+   识别阶段所属的生命周期

+   查找当前模块的打包，并识别正确的生命周期绑定

+   执行在已识别的生命周期绑定的层次结构中位于请求阶段之前的所有阶段

### 注意

通过执行所有阶段，我们指的是执行所有检测到的和附加的插件目标（本地插件或非本地插件）。

总之，在`jar`打包的模块上调用`mvn clean install`将执行以下阶段：`clean`，`process-resources`，`compile`，`process-test-resources`，`test-compile`，`test`，`package`和`install`。

## 还有更多...

您可能想知道为什么我们要针对我们的应用程序创建这些项目和模块。

### 我们是如何选择 jar 模块的名称的？

关于 Maven 结构，非部署模块的最佳名称通常强调功能目的、业务创建的特定概念，或者由产品驱动（cloudstreetmarket-chat、cloudstreetmarket-reporting、cloudstreetmarket-user-management 等）。这种策略使得依赖管理更容易，因为我们可以推断一个新模块是否需要另一个模块。在宏观层面考虑控制器、服务和 DAO 层在这个阶段并不是很有意义，这可能会导致设计干扰或循环依赖。这些技术子组件（服务、DAO 等）将作为 Java 包存在或不存在，根据每个功能模块的需要，但不作为 JAR 包依赖。

### 我们是如何选择可部署模块的名称的？

选择可部署模块（`war`）的名称与选择 JAR 打包模块的名称有些不同。可部署的存档必须被视为可扩展和潜在负载平衡。可以合理地假设将针对应用程序检索 HTML 内容的请求可以与将返回 REST 内容的请求区分开来。

基于这一假设，在我们的情况下，我们希望将`war`拆分为两个。这样做可能会引发一个问题，即*web 会话*在两个 web 应用程序之间如何维护。我们将在稍后回答这一点。

### 我们为什么创建核心模块？

首先，我们创建了核心模块，因为可以肯定，在`cloudstreetmarket`应用程序和公司共享项目中，我们将拥有 POJOs、异常、常量、枚举和一些服务，这些服务将被几乎所有模块或应用程序水平使用。如果一个概念是特定于创建的功能模块，它就不应该是核心模块的一部分。

因此，*从大粒度开始*，*稍后再细化*可能更好，而不是考虑可能以不同方式实现甚至根本不实现的模块。在我们的情况下，我们是一家初创公司，可以说我们将要实现的 5 到 10 个功能可能构成这个应用程序的核心业务。

## 另请参阅...

+   我们还建议安装**代码样式格式化程序**。从**保存事件**触发，有了这些格式化程序，我们可以自动地使用统一的预定义重新排列我们的代码。在团队中拥有这样的格式化程序是非常受欢迎的，因为它可以保证在比较两个文件时具有相同的渲染。

# 安装 Spring、Spring MVC 和 Web 结构

在这个配方中，我们将使用继承为我们的`pom.xml`文件添加第三方依赖项。我们将加载`Spring 应用上下文`并创建我们应用的第一个控制器。最后，我们将在 Tomcat 中部署和启动 web 应用。

## 准备工作

现在我们已经准备好 Eclipse 并且正确配置了 Maven，接下来就可以开始了。我们需要在我们的`pom.xml`文件中指定所有必要的 Spring 依赖项，并且需要设置 Spring 以便为每个模块加载和检索其上下文。

我们还需要组织和可选地公开 web 资源，比如 JSP、JavaScript 文件、CSS 文件等。如果你完成了这个配置，我们应该得到一个由 Tomcat 服务器提供的静态欢迎页面，而且没有异常！

## 如何操作...

我们的第一组更改涉及到父项目：

1.  我们将为这些父项目定义依赖项和构建选项。让我们按照以下步骤进行：

1.  打开**chapter_1**源代码目录中的 cloudstreetmarket-parent 的`pom.xml`，然后选择主窗口下的**pom.xml**选项卡。

复制并粘贴`<properties>`、`<dependencyManagement>`和`<build>`块到你的 cloudstreetmarket-parent 的**pom.xml**文件中。

现在，对 zipcloud-parent 重复相同的操作。

1.  打开**chapter_1**源代码中的 zipcloud-parent 的`pom.xml`文件，然后点击**pom.xml**选项卡。

1.  复制并粘贴`<properties>`和`<dependencyManagement>`块到你的 zipcloud-parent 的**pom.xml**中。你应该已经复制了*第三个配方*中的`<build>`部分。

1.  现在，我们将为 web 模块定义依赖项和构建选项：

1.  打开**chapter_1**源代码中的 cloudstreetmarket-api 的`pom.xml`，然后选择**pom.xml**选项卡。

1.  复制并粘贴`<build>`和`<dependencies>`块到你的 cloudstreetmarket-api 的`pom.xml`中。

1.  现在，对 cloustreetmarket-webapp 重复相同的操作。

1.  打开**chapter_1**源代码目录中的 cloudstreetmarket-webapp 的`pom.xml`，然后点击**pom.xml**选项卡。

1.  复制并粘贴`<build>`和`<dependencies>`块到你的 cloudstreetmarket-webapp 的**pom.xml**文件中。

1.  之后，我们为 jar 模块定义依赖项：

1.  打开**chapter_1**源代码中的 cloudstreetmarket-core 的`pom.xml`，然后点击**pom.xml**选项卡。

1.  复制并粘贴整个`<dependencies>`块到你的 cloudstreetmarket-core 的**pom.xml**中。

1.  然后，我们放置 web 资源：

1.  从**chapter_1**源代码中，复制并粘贴整个**src/main/webapp/***目录到你的**cloudstreetmarket-webapp**项目中。你需要最终得到与**chapter_1**源代码相同的**webapp**目录结构：![如何操作...](img/image00806.jpeg)

1.  现在，对**cloudstreetmarket-api**执行相同的操作。从**chapter_1**源代码中复制并粘贴整个**src/main/webapp/***分支到你的**cloudstreetmarket-api**项目中。你需要最终得到与**chapter_1**源代码相同的 webapp 节点和子节点：

![如何操作...](img/image00807.jpeg)

1.  现在，我们为 web 模块定位一个运行时：

1.  在 Eclipse 中，右键单击**cloudmarket-api**项目。

1.  选择**Properties**菜单。

1.  在导航面板上，选择**Targeted Runtimes**。

1.  在中央窗口中，勾选**Server Apache Tomcat v8.0**选项。

1.  点击**OK**，然后在**cloudstreetmarket-webapp**上重复第五个操作。

### 注意

在这之后，**index.jsp**文件中的一些 Eclipse 警告应该已经消失了。

如果你的项目仍然有警告，你的 Eclipse Maven 配置可能与本地仓库不同步。

1.  这一步应该清除现有项目的警告（如果有的话）：

在这种情况下，执行以下步骤：

1.  选择项目层次结构中的所有项目，除了服务器，如下所示：![如何操作...](img/image00808.jpeg)

1.  在选择的某个地方右键单击，然后在**Maven**下单击**更新项目**。此阶段的**警告**窗口应该消失！

1.  让我们部署`wars`并启动 Tomcat：

在 Eclipse 中添加**服务器**视图。为此，请执行以下操作：

1.  导航到**窗口** | **显示视图** | **其他**。

1.  打开**服务器**目录并选择服务器。您应该在仪表板上看到以下选项卡：

![如何做...](img/image00809.jpeg)

1.  要部署 Web 存档，请执行以下操作：

1.  在我们刚刚创建的视图中，右键单击**本地主机上的 Tomcat v8.0 服务器**，然后选择**添加和移除...**。

1.  在下一步，也就是**添加和移除**窗口中，选择两个可用的存档，然后单击**添加**，然后单击**完成**。

1.  要在 Tomcat 中启动应用程序，我们需要完成以下步骤：

1.  在**服务器**视图中，右键单击**本地主机上的 Tomcat v8.0 服务器**，然后单击**启动**。

1.  在**控制台**视图中，最后应该看到以下内容：

```java

INFO: Starting ProtocolHandler ["http-nio-8080"]
Oct 20, 2014 11:43:44 AM org.apache.coyote.AbstractProtocol start
INFO: Starting ProtocolHandler ["ajp-nio-8009"]
Oct 20, 2014 11:43:44 AM org.apache.catalina.startup.Cata.. start
INFO: Server startup in 6898 ms

```

### 注意

如果您浏览这些日志，您不应该有任何异常！

最后，如果您尝试使用浏览器访问`http://localhost:8080/portal/index.html`，您应该收到以下 HTML 内容：

![如何做...](img/image00810.jpeg)

### 注意

对于本章来说，对 HTML 页面的静态访问仍然是一个谦逊的视觉成就。在整本书中，您将发现我们并没有降低 Spring MVC 所处环境和上下文的重要性。

## 它是如何工作的...

通过这个配方，我们一直在处理与 Spring、Spring MVC 和 Web 环境相关的 Web 资源和 Maven 依赖关系。现在，我们将讨论 Maven 依赖关系和插件管理的方式。然后，我们将讨论 Spring Web 应用程序上下文，最后讨论 Web 资源的组织和打包。

### Maven 依赖的继承

关于父项目和子模块之间依赖关系的继承有两种策略。它们都是从父项目实施的。一方面，我们可以选择直接从`<dependencies>`节点中定义这些依赖关系，以这种方式塑造基本继承。另一方面，为了建立受控继承，我们可以将`<dependencies>`节点定义为`<dependencyManagement>`的子节点。让我们看看两者之间的区别。

#### 基本继承

通过基本继承，父`pom.xml`文件中指定的所有依赖关系都会自动继承到具有相同属性（范围、版本、打包类型等）的子模块中，除非您覆盖它们（使用相同的`groupId`/`artifactId`重新定义这些依赖关系）。

一方面，它提供了在我们想要的模块中使用我们想要的依赖关系版本的选项。另一方面，我们可能会得到一个非常复杂的依赖关系架构和子模块中的巨大`pom.xml`文件。此外，管理外部传递依赖关系的版本冲突可能会很痛苦。

### 提示

自 Maven 2.0 以来，传递依赖是一个需要的依赖关系。传递依赖关系已经自动导入。

在这种继承类型中，没有标准的外部依赖关系。

#### 受控继承

使用`<dependencyManagement>`机制，父`pom.xml`中定义的依赖关系不会自动继承到子模块中。但是，依赖属性（范围、版本、打包类型等）是从父依赖关系的定义中提取的，因此，重新定义这些属性是可选的。

这个过程将我们引向一个集中的依赖关系定义，所有子模块使用相同版本的依赖关系，除非特定的依赖关系需要自定义。

### 包括第三方依赖

在复制的依赖项中，你可能已经注意到了一些 Spring 模块，一些测试、Web、日志和实用程序依赖项。

这个想法是从一个基本的 Web 开发工具箱开始，然后使用所有的 Spring 模块进行增强。当我们面对特定情况时，我们将访问实际包含的大多数依赖项。

#### Spring 框架依赖模型

正如从[spring.io](http://spring.io)网站中提取的下图所示，如今，Spring 框架目前由 20 个模块组成，分组在不同的领域中：

![Spring 框架依赖模型](img/image00811.jpeg)

这些模块已经被包含在父 POM 中作为受控依赖项。这将使我们以后能够快速地挑选所需的依赖项，为我们的`wars`缩小选择范围。

#### Spring MVC 依赖

Spring MVC 模块是在`spring-webmvc` jar 中自包含的。在 Web 应用程序中，Spring MVC 是一个基本元素，它处理传入的客户端请求，并从控制器中平稳地监视业务操作。最终，它提供了一些工具和接口，能够以客户端期望的格式准备响应。

所有这些工作流程都伴随着 spring-webmvc jar 输出 HTML 内容或 Web 服务。

Spring MVC 完全集成在 Spring 框架中，其所有组件都符合 Spring 架构选择的标准。

#### 使用 Maven 属性

在每个父`pom.xml`文件中，我们已经在`<project>`部分定义了一个`<properties>`块。这些属性是绑定到项目的用户定义属性，但我们也可以在**Maven Profile**选项中定义这些属性。与变量一样，属性在 POM 中被引用时，其名称被**${…}**包围。

有一个标准，使用句点作为单词分隔符来定义属性名称。这不仅仅是一个标准，它还是一种统一的表示法，可以访问用户定义的变量和构成 Maven 模型的对象的属性。Maven 模型是 Maven 的公共接口，从项目级别开始。

POM **XML 模式定义**（**xsd**）是从这个 Maven 模型生成的。这可能听起来很抽象，但最终，Maven 模型只是一组带有 getter 和 setter 的 POJOs。请查看下面 URL 中 Maven 模型的 JavaDoc，以识别与 pom.xml 文件特定的概念（构建、依赖、插件等）：

[`maven.apache.org/ref/3.0.3/maven-model/apidocs/index.html`](http://maven.apache.org/ref/3.0.3/maven-model/apidocs/index.html)

总之，我们可以检索在 POM 中定义的节点值，并使用基于点的表达语言导航 Maven 模型层次结构，以定位 getter。

例如，`${project.name}`引用了当前的`project.getName()`，`${project.parent.groupId}`引用了当前的`project.getParent().getGroupId()`，依此类推。

定义与 Maven 模型的现有路径匹配的用户属性是覆盖其值的一种方式。这就是我们为`project.build.sourceEncoding`所做的事情。

Maven 还提供了访问`settings.xml`文件中定义的属性的可能性，比如`${settings.localRepository}`；还可以访问环境变量，比如`${env.JAVA_HOME}`；以及 Java 系统属性，比如`${java.class.path}`、`${java.version}`、`${user.home}`或`${user.name}`。

### Web 资源

如果你还记得，我们从`chapter_1`源代码中复制/粘贴了整个`src/main/webapp`目录。`webapp`目录名称是 Maven 的标准。在 Eclipse 中，`webapp`文件夹不需要被标记为构建路径的源文件夹，因为这会为静态文件创建一个复杂且无用的包层次结构。最好是它显示为一个普通的目录树。

`webapp`目录必须被视为应用程序的文档根，并位于 WAR 的根级别。`webapp`下的公共静态 web 资源，如 HTML 文件、Javascript、CSS 和图像文件，可以放在我们选择的子目录和结构中。然而，正如*Servlet 3.0 规范*中所描述的，`WEB-INF`目录是应用程序层次结构中的一个特殊目录。它的所有内容都无法从应用程序外部访问；它的内容只能从调用`ServletContext`的 servlet 代码中访问`getResource`或`getResourceAsStream`。规范还告诉我们，`WEB-INF`目录的内容由以下内容组成：

+   `/WEB-INF/web.xml`部署描述符。

+   `/WEB-INF/classes/`目录用于存放 servlet 和实用类。该目录中的类必须对应用程序类加载器可用。

+   `/WEB-INF/lib/*.jar`区域用于存放 Java ARchive 文件。这些文件包含了打包在 JAR 文件中的 servlet、bean、静态资源和 JSP，以及对 web 应用程序有用的其他实用类。web 应用程序类加载器必须能够从这些存档文件中加载类。

在`WEB-INF`文件夹内创建一个`jsp`目录是一个良好的做法，这样`jsp`文件就不能直接被定位，而必须通过显式定义的控制器传递。

JSP 应用程序确实存在，并且根据定义，它们不会遵循这种做法。这种类型的应用程序可能适合某些需求，但它们也不特别推广 MVC 模式的使用，也不具有很好的关注点分离。

要在 web 应用程序中使用 JSP，必须在`web.xml`中启用该功能，并定义一个类型为`org.apache.jasper.servlet.JspServlet`的 servlet，将其映射到 JSP 文件的位置。

#### 目标运行时环境

我们在`index.jsp`文件中遇到了警告。我们通过向项目添加目标运行时来解决了这些问题。我们还发现 Tomcat 自带了 Eclipse Compilator for Java 作为一个 JAR 库。为了执行 JSP 编译，`tomcat8\lib`目录必须包括以下 JAR 库：`jsp-api`，`servlet-api`和`el-api`等。在 Eclipse 中为项目指定目标运行时模拟并预测应用程序将从外部 Tomcat 容器（使用这些库设置）运行的情况。这也解释了为什么在父 POM 中使用*provided*范围定义了`jsp-api`和`el-api`依赖项。

#### Spring web 应用程序上下文

在`web.xml`文件中，我们定义了一种特殊类型的 Servlet，即 Spring MVC `DispatcherServlet`，并将其命名为`spring`。这个 servlet 覆盖了最广泛的`/*` URL 模式。我们将在下一章重新讨论`DispatcherServlet`。

`DispatcherServlet`有自己的发现算法，构建`WebApplicationContext`。提供了一个可选的`contextConfigLocation`初始化参数，指向一个`dispatcher-context.xml`文件。这个参数覆盖了`DispatcherServlet`发现逻辑中默认的预期文件名和路径（`/WEB-INF/{servletName}-servlet.xml`）。

将`load-on-startup`属性设置为`1`后，一旦 servlet 容器准备就绪，就会加载一个新的`WebApplicationContext`，并且仅对启动 servlet 进行范围限定。现在，*我们不再等待第一个客户端请求来加载 WebApplicationContext*。

Spring `WebApplicationContext`文件通常定义或覆盖了 Spring MVC 为 web 应用程序提供的配置和 bean。

在`web.xml`文件中，设置了`org.sfw.web.context.ContextLoaderListener`监听器。这个监听器的目的是启动和关闭另一个 Spring `ApplicationContext`，它将是根据容器生命周期的根`ApplicationContext`。

要轻松加载多个 spring 上下文文件，这里的诀窍是使用类路径表示法（相对路径）和资源路径中的星号（`*`）字符：

```java
<context-param>
  <param-name>contextConfigLocation</param-name>
  <param-value>classpath*:/META-INF/spring/*-config.xml</param-value>
</context-param>
```

这样做可以*加载在类路径中遇到的所有符合标准表示法和位置的上下文文件*。这种方法受到赞赏，因为它强加了一致性，但也因为它定位底层 jar 中的上下文文件的方式。

所有匹配的上下文文件的聚合创建了一个具有更广泛范围的`ApplicationContext`根，并且`WebApplicationContext`继承它。我们在根上下文中定义的 bean 对`WebApplicationContext`上下文可见。如果需要，我们可以覆盖它们。但是，`DispatcherServlet`上下文的 bean 对根上下文不可见。

#### 插件

Maven 首先是一个插件执行框架。Maven 运行的每个任务都对应一个插件。插件具有一个或多个与生命周期阶段分别关联的目标。与依赖关系一样，插件也由`groupId`、`artifactId`和版本标识。当 Maven 遇到不在本地存储库中的插件时，会下载它。此外，默认情况下，Maven 的特定版本会针对与生命周期阶段匹配的一些插件。这些插件被冻结在固定版本上，因此具有定义行为—您需要覆盖它们的定义以获得更近期的版本或更改它们的默认行为。

##### Maven 编译器插件

maven-compiler-plugin 是 Maven 核心插件。核心插件之所以被命名为核心插件，是因为它们的目标是在 Maven 核心阶段（清理、编译、测试等）上触发的。非核心插件涉及打包、报告、实用工具等。重新定义 maven-compiler-plugin 以控制要使用的编译器版本或触发一些外部工具的操作（实际上是 m2eclipse 项目管理工具）是一个很好的做法。

顾名思义，maven 编译器插件编译 Java 源代码。为此，它使用`javax.tools.JavaCompiler`类，并有两个目标：`compiler:compile`（作为编译阶段的一部分触发，编译`java/main`源类）和`compiler:testCompile`（作为测试编译阶段的一部分触发，编译`java/test`源类）。

##### Maven surefire 插件

maven-surefire-plugin 也是一个 Maven 核心插件，只有一个目标：`surefire:test`。这是作为默认生命周期（测试阶段）的一部分调用，用于运行应用程序中定义的单元测试。默认情况下，它会在`${basedir}/target/surefire-reports`位置生成报告（*.txt 或*.xml）。

##### Maven 强制执行插件

maven-enforcer-plugin 非常有用，可以定义项目的环境条件为*关键*。它有两个目标：`enforcer:enforce`（默认绑定到验证阶段，在该阶段执行每个模块的每个定义规则一次）和`enforcer:display-info`（它在执行规则时显示检测到的信息）。

最有趣的标准规则可能是`DependencyConvergence`：它为我们分析所有使用的依赖关系（直接和传递）。如果版本发生分歧，它会将其突出显示并停止构建。当我们面对这种冲突时，很容易在以下之间做出决定：

+   从类路径中排除最低版本

+   不升级依赖

我们还简要讨论了与 maven-enforcer-plugin 相关联的`<pluginManagement>`部分。在这种情况下，这是因为 m2eclipse 不支持这个插件。因此，为了避免在 Eclipse 中出现警告，有必要添加这个部分，以便 m2eclipse 跳过强制执行目标。

##### Maven war 插件

使用 maven-war-plugin，我们在我们的 web POMs 中重新定义。我们再次覆盖了这个用于打包 web 模块的插件的默认行为。如果您有非 Maven 标准项目结构，这绝对是必要的。

我们可能希望以与 IDE 中组织方式不同的方式打包我们的 Web 资源。出于某种原因，我们可能需要从 war 包中排除一些资源，或者甚至希望为构建的 war 包命名，以便它可以被与应用程序 URL 中的特定上下文路径匹配的 servlet 容器使用（/api，/app 等）。过滤、移动 Web 资源以及管理生成的 war 是这个插件的目的。

### 提示

默认情况下，Web 资源会被复制到 WAR 根目录。要覆盖默认目标目录，请指定目标路径`*`。

## 还有更多...

这是一个相当广泛的概述，涉及到自然需要更深入了解的概念：

+   关于 Maven 管理其依赖项的方式，我们建议您阅读有关此主题的 Maven 文档：

[`maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html`](http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)

+   Sonatype 的电子书很好地介绍了 Maven 属性。您可以在以下网址找到这本电子书：[`books.sonatype.com/mvnref-book/reference/resource-filtering-sect-properties.html#resource-filtering-sect-settings-properties`](https://books.sonatype.com/mvnref-book/reference/resource-filtering-sect-properties.html#resource-filtering-sect-settings-properties)

+   Maven 模型 API 文档也可以在以下网址找到：

[`maven.apache.org/ref/3.0.3/maven-model/apidocs/index.html`](http://maven.apache.org/ref/3.0.3/maven-model/apidocs/index.html)

+   关于我们之前提到的 servlet 3.0 规范，可以在以下网址找到有关`web.xml`文件定义以及 WebArchive 结构的更多信息：[`download.oracle.com/otn-pub/jcp/servlet-3.0-fr-eval-oth-JSpec/servlet-3_0-final-spec.pdf`](http://download.oracle.com/otn-pub/jcp/servlet-3.0-fr-eval-oth-JSpec/servlet-3_0-final-spec.pdf)

+   最后，有关 Maven 插件的更多信息；我们强烈建议您访问 Maven 列表：[`maven.apache.org/plugins`](http://maven.apache.org/plugins)

## 另外

+   Pivotal 的[spring.io](http://spring.io)网站，特别是 Spring Framework 概述页面，也可以更新或介绍一些关键概念。请访问以下网址：[`docs.spring.io/spring-framework/docs/current/spring-framework-reference/html/overview.html`](http://docs.spring.io/spring-framework/docs/current/spring-framework-reference/html/overview.html)

### Maven checkstyle 插件

另一个有趣的插件是 maven-checkstyle-plugin。当团队在壮大时，我们有时需要保证某些开发实践的维护，或者我们可能需要维护特定的与安全相关的编码实践。像 maven-enforcer-plugin 一样，maven-checkstyle-plugin 使我们的构建对这种类型的违规行为进行断言。

在 Maven 文档中再了解有关此插件的更多信息：[`maven.apache.org/plugins/maven-checkstyle-plugin`](http://maven.apache.org/plugins/maven-checkstyle-plugin)。

# 第二章。使用 Spring MVC 设计微服务架构

在这一章中，我们将涵盖以下主题：

+   配置一个具有简单 URL 映射的控制器

+   使用 ViewResolver 配置回退控制器

+   使用 Bootstrap 设置和自定义响应式单页 Web 设计

+   使用 JSTL 在视图中显示模型

+   定义一个常见的 WebContentInterceptor

+   使用 AngularJS 设计客户端 MVC 模式

# 介绍

在开始这一新章节之前，您需要完成第一章。第一章安装了我们正在构建的交易平台的基础。它还创建了一个模块化工具包，每个配方都将使用。

这第二章将产品放在加速坡道上。它将塑造整个责任链，并勾勒出微服务架构的大局。我们将再次为即将到来的章节建立必要的结构，但在另一个层面上。

## 用户体验范式

多年来，我们一直在协助一个非常活跃的前端革命。自从 HTML 5 和 CSS3 的兴起，以及移动开发平台（iOS，Android 等）的普及，再加上连接设备的数量增加，为开发者社区打开了许多门和机会。在开源领域中不断涌现的新 JavaScript 库的频率使其难以跟随。

但这是一场革命！它针对的是客户和用户体验。如今的客户希望能够从台式机、笔记本电脑、电视、平板电脑、手机，甚至是汽车上与品牌或产品进行互动。网络连接速度也各不相同，从每秒超过 150 兆字节到很少的字节。客户还可以期待离线功能，或者至少是一个体验良好的用户体验。显然，由于这种复杂性，出现了新的挑战，以改善用户体验。

随着我们通过不同方式的可及性大大增加，我们对垃圾邮件、直接招揽、广告以及一般营销的暴露程度从未如此之高。有趣的是，我们现在对每一条保持我们在线注意力的消息都更加敏感和自信。因为我们只需要一小部分时间就能决定某件事是否值得，所以我们也因为同样的原因拒绝了糟糕的设计。我们更加苛刻和饱和的目标，每个品牌都必须遵循最新的用户体验标准，以便我们与他们互动。

## 微服务架构

我们已经看到，通过向公众开放其 API（Facebook，Twitter，亚马逊等），互联网组织在沟通、形象和发展方面所产生的巨大好处。这种对 IT 基础设施的根本性变化现在正在成为中小企业和初创公司的常态。

现代架构为其客户提供了有文档的公共 API 和特定设备的安装包：移动应用程序或响应式 HTML 内容以特定的快照交付。REST API 也是**物联网**（**IoT**）更自主模块的可导航维度。

也许主要问题仍然是如何处理服务器端的负载，但更多的计算被转移到客户端设备上，而 REST 架构从定义上是无状态的，因此对可扩展性有很好的支持。

# 配置一个具有简单 URL 映射的控制器

这个配方介绍了 Spring MVC 控制器及其最简单的实现方式。

## 准备工作

我们将在以后发现，特别是在第三章中，*使用 Java 持久性和实体*，Spring MVC 是构建 REST API 的强大工具。在这里，我们将专注于如何创建一个控制器，以在响应中打印一些内容。

从这个配方开始，我们将使用 GIT 来跟踪对`cloudstreetmarket`应用程序所做的每次迭代。在初始设置之后，您将欣赏到您可以顺利升级的流畅性。

## 如何做...

这个配方有两个初始部分，用于安装和配置 GIT。

### 下载和安装 GIT

1.  要下载 GIT，请转到 GIT 下载页面[`git-scm.com/download`](https://git-scm.com/download)。选择与您的环境相对应的正确产品（Mac OS X，Windows，Linux 或 Solaris）。

1.  在 Linux 和 Solaris 上安装 GIT，请使用系统的本机软件包管理器执行建议的安装命令。

对于 Mac OS X，双击下载的`dmg`文件以在硬盘上提取包。转到提取的目录，双击`pkg`文件。选择所有默认选项，一步一步进行，直到**成功安装**屏幕。关闭屏幕。

对于 Windows，执行下载的程序，并按默认选项进行每一步，直到这些屏幕：

+   **调整您的 PATH 环境**：选择**从 Windows 命令提示符使用 Git**选项

+   **选择 SSH 可执行文件**：选择**使用 OpenSSH**选项

+   配置行结束转换：选择**检出 Windows 样式**和**提交 Unix 样式行结束**选项

+   **配置终端仿真器使用 Git Bash**：选择**使用 Windows 默认控制台窗口**

+   **配置实验性能调整**：不要勾选**启用文件系统缓存**复选框

让安装完成，然后单击**完成**按钮。

验证时，打开终端并输入以下命令：

```java

git –version

```

此命令应显示已安装的版本。所呈现的安装指南与`GIT 2.6.3`相关。

### 在 Eclipse 中配置 GIT

1.  我们将首先从终端初始化本地存储库。转到您的工作空间位置：`cd <home-directory>/workspace`。

用您自己的主目录路径替换`<home-directory>`。

1.  输入以下命令在此位置创建本地 Git 存储库：

```java

git init

```

1.  输入以下命令：

```java

git remote add origin https://github.com/alex-bretet/cloudstreetmarket.com

```

1.  然后，输入`git fetch`命令。

1.  选择您的父项目并右键单击其中一个。转到**Team** | **Add to index**：![在 Eclipse 中配置 GIT](img/image00812.jpeg)

1.  从右上角面板，单击**Git** **透视图**：![在 Eclipse 中配置 GIT](img/image00813.jpeg)

如果尚未拥有，请使用![在 Eclipse 中配置 GIT](img/image00814.jpeg)按钮添加此透视图。

1.  从左侧层次结构（**Git**透视图）中，选择**添加现有的本地 Git 存储库**。

1.  一个上下文窗口打开。定位到我们刚创建的本地 Git 存储库的位置（应该是当前工作空间目录）。

1.  **Git**透视图中现在应该出现一个新的存储库。

1.  如下截图所示，右键单击并选择**Checkout**以查看分支**origin/v1.x.x**的最新版本。![在 Eclipse 中配置 GIT](img/image00815.jpeg)

1.  提示时，检出为**新的本地分支**：![在 Eclipse 中配置 GIT](img/image00816.jpeg)

1.  实际工作空间现在应该与分支 v1.x.x 同步。该分支反映了第一章结束时环境的状态，设置*企业 Spring 应用程序的例程*。![在 Eclipse 中配置 GIT](img/image00817.jpeg)

1.  右键单击**zipcloud-parent**执行**Run as | Maven clean**和**Run as | Maven install**。然后在`cloudstreetmarket-parent`上执行相同的操作。每次都会观察到`BUILD SUCCESS`。

1.  最后，右键单击一个项目，转到**Maven** | **Update Project**。选择工作空间的所有项目，然后单击**确定**。

1.  如果您的一个项目仍然显示红色警告（如前一个截图所示），您可能需要重新附加目标运行时环境到**cloudstreetmarket-api**和**cloustreetmarket-webapp**（根据第一章*企业 Spring 应用程序的设置例程*，*第 2 个配方，第 7 步*）。

1.  从终端，转到本地 GIT 存储库：

```java

 cd <home-directory>/workspace 

```

1.  输入以下命令：

```java

 git pull origin v2.2.1

```

1.  重复步骤 13 和 14。（准备在拉取新更改后每次重复这两个步骤。）

1.  在**cloudstreetmarket-webapp**模块中，现在出现了一个新的包：

```java

 edu.zipcloud.cloudstreetmarket.portal.controllers.

```

1.  在这个包中，创建了一个`InfoTagController`类：

```java
@Controller
@RequestMapping("/info")
public class InfoTagController {
  @RequestMapping("/helloHandler")
  @ResponseBody
  public String helloController(){
    return "hello";
  }
}
```

1.  确保两个`war`文件部署在 Tomcat 服务器中。启动 Tomcat 服务器并使用浏览器访问`http://localhost:8080/portal/info/helloHandler` URL。

### 注意

您应该看到一个简单的 hello 显示为 HTML 内容*。*

1.  在`cloudstreetmarket-webapp/src/main/webapp/WEB-INF/dispatcher-context.xml`文件中，添加了以下 bean 定义：

```java
<bean id="webAppVersion" class="java.lang.String">
  <constructor-arg value="1.0.0"/>
</bean>
```

1.  `InfoTagController`类中的以下方法和成员也被添加：

```java
@Autowired
private WebApplicationContext webAppContext;
private final static LocalDateTime startDateTime = LocalDateTime.now();
private final static DateTimeFormatter DT_FORMATTER =  DateTimeFormatter.ofPattern("EEE, d MMM yyyy h:mm a");
@RequestMapping("/server")
@ResponseBody
public String infoTagServer(){
  return new StringJoiner("<br>")
    .add("-------------------------------------")
    .add(" Server: "+ 
    webAppContext.getServletContext().getServerInfo())
    .add(" Start date: "+ 
    startDateTime.format(DT_FORMATTER))
    .add(" Version: " + 
    webAppContext.getBean("webAppVersion"))
    .add("--------------------------------------")
    .toString();
}
```

1.  现在，使用浏览器访问`http://localhost:8080/portal/info/server` URL。

### 注意

您应该看到以下内容呈现为 HTML 文档：

```java

--------------------------------------------------
Server: Apache Tomcat/8.0.14
Start date: Sun, 16 Nov 2014 12:10 AM
Version: 1.0.0
---------------------------------------------------

```

## 它是如何工作的...

我们将草拟 Spring MVC 作为一个框架的概述。然后我们将审查如何从`DispatcherServlet`配置控制器，控制器级别的注解，以及从方法处理程序签名。

### Spring MVC 概述

Spring MVC 实现了两种常见的设计模式：前端控制器设计模式和 MVC 设计模式。

#### 前端控制器

作为前端控制器设计的系统为所有传入的请求公开了一个单一的入口点。在 Java Web 环境中，这个入口点通常是一个 servlet——一个唯一的 servlet，用于分发和委派给其他组件。

### 注意

在 Spring MVC 的情况下，这个唯一的 servlet 就是`DispatcherServlet`。

Servlet 在 Java Web 中是标准。它们与预定义的 URL 路径相关联，并在部署描述符（`web.xml`文件）中注册。解析部署描述符时，servlet 容器（如 Apache Tomcat）识别声明的 servlet 及其 URL 映射。在运行时，servlet 容器拦截每个 HTTP 客户端请求，并为每个请求创建一个新的线程。这些线程将使用 Java 转换的请求和响应对象调用匹配的相关 servlet。

#### MVC 设计模式

MVC 设计模式更多地是一种架构风格。它描述了整个应用程序。它鼓励在请求线程必须通过的三个不同层之间清晰地分离关注：**模型**，**视图**和**控制器**——控制器，模型，然后是视图。

![MVC 设计模式](img/image00818.jpeg)

当一个客户端请求被 servlet 容器拦截时，它被路由到`DispatcherServlet`。`DispatcherServlet`将请求发送到一个控制器（一个控制器方法处理程序），该控制器具有与请求状态匹配的配置（如果找到匹配）。

控制器协调业务逻辑，模型生成，并最终选择一个视图用于模型和响应。从这个角度来看，模型代表了由控制器处理并提供给视图进行可视化的填充数据结构。

但是这三个组件（模型、视图和控制器）也可以在宏观尺度上被视为独立的静态层。每个组件都是一个层，也是每个独立组成部分的占位符，属于该类别的一部分。**控制器层**包含所有注册的控制器以及 Web 拦截器和转换器；模型生成层（和业务逻辑层）包含业务服务和数据访问组件。视图层包含模板（例如 JSP）和其他 Web 客户端组件。

#### Spring MVC 流程

Spring MVC 流程可以用以下图表表示：

![Spring MVC 流程](img/image00819.jpeg)

我们之前提到 Spring MVC 实现了前端控制器模式。入口点是`DispatcherServlet`。这个`DispatcherServlet`依赖于`HandlerMapping`的实现。使用不同的策略和特定性，`HandlerMapping`解析请求的控制器方法处理程序。

一旦`DispatcherServlet`有了一个控制器方法处理程序，它就会将请求分派给它。方法处理程序返回一个视图名称（或直接返回视图本身），还返回填充的模型对象给`DispatcherServlet`。

使用视图名称，`DispatcherServlet`要求`ViewResolver`实现查找并选择视图。

有了请求，视图和模型，`DispatcherServlet`就有了构建客户端响应的一切。视图使用所有这些元素进行处理，最终将响应返回给 servlet 容器。

### DispatcherServlet- Spring MVC 入口点

正如所解释的，`DispatcherServlet`在 Spring MVC 中是一个非常核心的部分。它拦截针对应用程序的预定义 URL 路径的客户端请求。它将它们映射到属于业务逻辑运算符（控制器，拦截器，过滤器等）的处理程序。它还提供一组工具，可用作 bean 来解决重复的 Web 开发问题和技术，例如提供集中和模块化的视图层，处理国际化，主题，处理异常等。

在一切之前，`DispatcherServlet`是一个 servlet，并且在`web.xml`文件中以 servlet 配置和 servlet 映射的形式进行定义。 代码如下：

```java
<servlet>
  <servlet-name>spring</servlet-name>
   <servlet-class>
      org.springframework.web.servlet.DispatcherServlet
  </servlet-class>
  <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
   <servlet-name>spring</servlet-name>
   	<url-pattern>/*</url-pattern>
</servlet-mapping>
```

在我们的应用程序中，在**cloudstreetmarket-webapp**中，`DispatcherServlet`被命名为 spring，并覆盖了应用程序的完整上下文路径：`/*`。

我们已经看到每个`DispatcherServlet`都有一个受限范围的`WebApplicationContext`，它从根`ApplicationContext`继承 bean。

默认情况下，对于`WebApplicationContext`，Spring MVC 在`/WEB-INF`目录中查找名为`{servletName}-servlet.xml`的配置文件。但是，我们通过初始化参数`contextConfigLocation`覆盖了此默认名称和位置：

```java
<servlet>
 <servlet-name>spring</servlet-name>
   <servlet-class>
    org.springframework.web.servlet.DispatcherServlet
  </servlet-class>
   <init-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/dispatcher-context.xml</param-value>
   </init-param>
   <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
    <servlet-name>spring</servlet-name>
    <url-pattern>/*</url-pattern>
</servlet-mapping>
```

在`web.xml`中，您可以看到根应用程序上下文（`classpath*:/META-INF/spring/*-config.xml`）以`ContextLoaderListener`开头：

```java
<listener>
  <listener-class>
    org.springframework.web.context.ContextLoaderListener
  </listener-class>
</listener>
```

### 由注解定义的控制器

Spring MVC 控制器是客户端请求真正开始由特定于业务的代码处理的地方。自*Spring 2.5*以来，我们已经能够在控制器上使用注解，因此我们不必在配置中显式声明它们为 bean。这使得它们的实现更容易扩展和理解。

#### @Controller

`@Controller`注解标记一个类为 Web 控制器。它仍然是用于表示层的 Spring Stereotype。定义 Spring Stereotype 的主要目的是使目标类型或方法在 Spring 类路径扫描期间可发现，该扫描由以下命令激活：

```java
<context:component-scan base-package="edu.zipcloud.cloudstreetmarket.portal"/>
```

与此注解相关的自定义逻辑并不多。如果我们不介意使应用程序变得更清洁，我们可以使用其他 Stereotype 注解（`@Component`或`@Service`）运行控制器。

#### @RequestMapping

`@RequestMapping`注解将处理程序定义到控制器类和/或控制器方法上。这些注解在`DispatcherServlet`中在构造类中进行查找。 `@RequestMapping`注解背后的主要思想是在类级别上定义主要路径映射，并在方法上缩小 HTTP 请求方法，标头，参数和媒体类型。

为了实现这种缩小，`@RequestMapping`注解在括号内接受逗号分隔的参数。

考虑以下示例：

```java
@RequestMapping(value="/server", method=RequestMethod.GET)
```

`@RequestMapping`可用参数总结在以下表中：

| 参数和类型 | 使用/描述（来自 JavaDoc） |
| --- | --- |
| --- | --- |
| `name（String）` | 为映射分配一个名称。 |
| `value（String[]）` | 路径映射 URI（例如，`/myPath.do`）。还支持 Ant 样式路径模式（例如，`/myPath/*.do`）。 |
| 路径映射 URI 可能包含占位符（例如，`/${connect}`）针对本地属性和/或系统属性和环境变量。 |
| 路径实现 URI 模板，通过模式，变量，占位符和矩阵变量（请参阅 URI 模板部分）访问 URL 的选定部分。 |
| 在方法级别，主映射中支持相对路径（例如，`edit.do`）。 |
| `method``(RequestMethod[])` | GET、POST、HEAD、OPTIONS、PUT、PATCH、DELETE、TRACE。 |
| `params (String[])` | 一系列`myParam=myValue`风格的表达式。 |
| 表达式可以使用`!=`运算符否定，如`myParam!=myValue`。 |
| `headers (String[])` | 一系列`My-Header=myValue`风格的表达式。 |
| 仅指定标题名称（例如，`My-Header`）是受支持的（允许具有任何值）。 |
| 也支持否定标题名称（例如，`!My-Header`）（指定的标题不应出现在请求中）。 |
| 还支持媒体类型通配符（`*`），用于`Accept`和`Content-Type`等标题。 |
| `consumes (String[])` | 映射请求的可消耗媒体类型。 |
| 仅在`{@code Content-Type}`匹配这些媒体类型之一时映射。 |
| 否定表达式（例如，`!text/xml`）也受支持。 |
| `produces (String[])` | 映射请求的可生产媒体类型。 |
| 仅在`{@code Accept}`匹配这些媒体类型之一时映射。 |
| 否定表达式（例如，`!text/plain`）也受支持。它匹配所有具有`{@code Accept}`不是"text/plain"的请求。 |

所有这些参数都可以在类型级别和方法级别使用。在类型级别使用时，所有方法级参数都继承父级缩小。

### 控制器方法处理程序签名

多个组成部分构成控制器方法处理程序。以下是 Spring MVC 中这样一个处理程序的另一个示例：

```java
@RequestMapping(value="/index")
public ModelAndView getRequestExample(ServletRequest request){
    ModelAndView mav = new ModelAndView();
    mav.setViewName("index");
    mav.addObject("variable1", new ArrayList<String>());
    return mav;
}
```

我们刚刚讨论了如何使用`@RequestMapping`注解。关于方法签名，此注解只能放置在返回类型之前。

#### 支持的方法参数类型

声明处理程序方法的特定类型的参数可以让 Spring 自动在其中注入对外部对象的引用。这些对象与请求生命周期、会话或应用程序配置相关。由于这些参数类型受方法范围的限制，因此它们在以下表中呈现：

| 支持的参数 | 使用/描述 | 包 |
| --- | --- | --- |
| `ServletRequest /``HttpServletRequest` | 注入 servlet 请求/响应。 | `javax.servlet.http.*` |
| `ServletResponse /``HttpServletResponse` |
| `HttpSession` | 注入绑定到 servlet 请求的 HTTP 会话。如果为 null，Spring 将创建一个新的。如果应该在`AbstractController`或`RequestMappingHandlerAdapter`中共享会话，则必须设置`synchronizeOnSession`。 |
| `WebRequest / NativeWebRequest` | 注入一个包装器，用于仅访问请求参数和请求/会话属性。 | `org.springframework.web.context.request.*` |
| `Locale` | 使用配置的`LocaleResolver`注入请求的本地 e。 | `java.util.*` |
| `InputStream / Reader` | 直接访问请求/响应有效负载。 | `java.io.*` |
| `OutputStream / Writer` |
| `HttpMethod` | 注入请求的当前方法。 | `org.springframework.http.*` |
| `Principal` | 使用 Spring 安全上下文，它注入了经过身份验证的账户。 | `java.security.*` |
| `HttpEntity<?>` | Spring 将入站请求转换并注入到自定义类型中，同时提供对请求头的访问。 | `org.springframework.http.*` |
| `Map` | 为我们实例化一个`BindingAwareModelMap`，以在视图中使用。 | `java.util.*` |
| `Model` | `org.springframework.ui.*` |
| `ModelMap` |
| `RedirectAttributes` | 注入并重新填充在请求重定向期间维护的属性和闪存属性的映射。 | `org.springframework.web.servlet.mvc.support.*` |
| `Errors` | 注入参数列表中紧挨着的参数的验证结果。 | `org.springframework.validation.*` |
| `BindingResult` |
| `SessionStatus` | 允许使用`setComplete`(Boolean)标记会话的完成。此方法清除使用@SessionAttributes 在类型级别定义的会话属性。 | `org.springframework.web.bind.support.*` |
| `UriComponentsBuilder` | 注入 Spring URL 构建器 UriComponentsBuilder。 | `org.springframework.web.util.*` |

#### 方法参数的支持注解

一组用于方法处理程序参数的本机注解已经被设计出来。它们必须被视为配置控制器方法的 Web 行为的句柄，以便处理传入的请求或尚未构建的响应。

它们标识了方便的 Spring MVC 函数的抽象，例如请求参数绑定，URI 路径变量绑定，请求有效负载注入到参数，HTML 表单参数绑定等。

| 支持的注解参数 | 用途/描述 | 包 |
| --- | --- | --- |
| `@PathVariable` | 将 URI 模板变量注入到参数中。 | `org.springframework.web.bind.annotation.*` |
| `@MatrixVariable` | 将位于 URI 路径段中的名称-值对注入到参数中。 |
| `@RequestParam` | 将特定请求参数注入到参数中。 |
| `@RequestHeader` | 将特定请求的 HTTP 标头注入到参数中。 |
| `@RequestBody` | 允许直接访问请求有效负载，并将其注入到参数中。 |
| `@RequestPart` | 将多部分/表单编码请求的特定部分（元数据、文件数据等）的内容注入到匹配类型的参数中（MetaData、MultipartFile 等）。 |
| `@ModelAttribute` | 使用 URI 模板自动填充模型的属性。此绑定在方法处理程序处理之前操作。 |

这些注解必须放在要填充的方法参数之前：

```java
@RequestMapping(value="/index")
public ModelAndView getRequestExample(@RequestParam("exP1") String exP1){
   ModelAndView mav = new ModelAndView();
   mav.setViewName("index");
   mav.addObject("exP1", exP1);
   return mav;
}
```

#### 支持的返回类型

Spring MVC，具有不同可能的控制器方法返回类型，允许我们指定要发送回客户端的响应，或者用于定位或填充中间视图层变量的必要配置。根据我们想要做什么或实际应用状态，我们可以在以下选项中进行选择：

| 支持的返回类型 | 用途/描述 | 包 |
| --- | --- | --- |
| `Model` | Spring MVC 为处理程序方法创建模型接口的实现。模型的对象在处理程序方法内部手动填充，或者使用`@ModelAttribute`的帮助。需要使用 RequestToViewNameTranslator 将要呈现的视图映射到请求。 | `org.springframework.ui.*` |
| `ModelAndView` | 一个包装器对象，包含模型、视图和视图名称。如果提供了视图名称，Spring MVC 将尝试解析关联的视图。否则，将呈现嵌入式视图。模型对象在方法内部手动填充，或者使用`@ModelAttribute`。 |
| `Map` | 允许自定义模型实现。需要使用`RequestToViewNameTranslator`将要呈现的视图映射到请求。 | `java.util.*` |
| `View` | 允许呈现自定义视图对象。Spring MVC 为处理程序方法创建模型接口的实现。模型的对象在方法内部手动填充，或者使用`@ModelAttribute`的帮助。 | `org.springframework.web.servlet.*` |
| `String` | 如果处理程序方法上没有指定`@ResponseBody`注解，则返回的字符串将被处理为视图名称（视图标识符）。 | `java.lang.*` |
| `HttpEntity<?> / ResponseEntity<?>` | 两个包装对象，用于轻松管理响应头和 Spring 转换的主体（使用`HttpMessageConverters`）。 | `org.springframework.http.*` |
| `HttpHeaders` | 为 HEAD 响应提供一个包装器对象。 | `org.springframework.http .*` |
| `Callable<?>` | 当 Spring MVC 控制线程时，可以异步生成一个类型化对象。 | `java.util.concurrent.*` |
| `DeferredResult<?>` | 当线程不受 Spring MVC 控制时，可以异步产生一个类型化对象。 | `org.springframework.web.context.request.async.*` |
| `ListenableFuture<?>` | `org.springframework.util.concurrent.*` |
| `void` | 当视图由`RequestToViewNameTranslator`外部解析时，或者当方法直接在响应中打印时。 |   |

## 还有更多...

在`InfoTagController.infoTagServer()`方法处理程序中，我们在返回类型之前使用了`@ResponseBody`注解。这个注解是从特定于 REST 的工具中借来的。当您不需要处理视图时，`@ResponseBody`指令将使用注册的 Spring 转换器将返回的对象编组成期望的格式（XML、JSON 等）。然后将编组的内容写入响应主体（作为响应有效载荷）。

在没有更多配置的 String 对象的情况下，它会在响应主体中打印出来。我们可以使用`ResponseEntity<String>`返回类型来实现相同的目标。

# 使用 ViewResolver 配置回退控制器

这个配方介绍了一些与控制器相关的更高级的概念和工具，比如`ViewResolvers`、URI 模板模式和 Spring MVC 的注入作为参数。这个配方很简单，但还有更多要谈论。

## 准备工作

我们将继续从之前的配方中保持相同的代码库状态，其中我们从远程存储库中拉取了 v2.2.1 标签。这只涉及创建一个带有其处理程序方法的控制器。

## 如何做...

1.  在**cloudstreetmarket-webapp**模块和包`edu.zipcloud.cloudstreetmarket.portal.controllers`中，创建了以下`DefaultController`：

```java
@Controller
public class DefaultController {
  @RequestMapping(value="/*", method={RequestMethod.GET,RequestMethod.HEAD})
  public String fallback() {
    return "index";
  }
}
```

### 注意

我们将详细解释这种方法处理程序如何作为回退拦截器。

1.  使用浏览器访问`http://localhost:8080/portal/whatever`或`http://localhost:8080/portal/index` URL。

您还应该收到我们之前看到的 HTML 内容：

![如何做...](img/image00820.jpeg)

## 它是如何工作的...

这个第二个配方重新访问了`@RequestMapping`注解的使用。不再是固定的 URI 作为路径值，而是一个开放的模式（回退）。该配方还利用了我们之前没有使用的配置的视图解析器。

### URI 模板模式

模板词在 Spring 术语中是重复出现的。它通常指的是通用支持 Spring API，可以实例化以填充特定的实现或自定义（REST 模板用于进行 REST HTTP 请求，JMS 模板用于发送 JMS 消息，WS 模板用于进行 SOAP Web 服务请求，JDBC 模板等）。它们是开发人员需要 Spring 核心功能的桥梁。

在这种光线下，URI 模板允许配置具有模式和变量的通用 URI，用于控制器端点。可以实例化 URI 构建器来实现 URI 模板，但开发人员可能主要使用 URI 模板来支持`@RequestMapping`注解。

#### Ant 风格的路径模式

我们已经利用这些类型的模式来定义我们的回退处理程序方法的路径值：

```java

@RequestMapping(value="/*", ...)

```

这种特殊情况下，使用`*`通配符，允许以应用程序显示名称之后的`/`开头的任何请求 URI 都有资格由此方法处理。

通配符可以匹配一个字符、一个单词或一系列单词。考虑以下例子：

```java
/portal/1, /portal/foo, /portal/foo-bar
```

一个限制是在最后一个序列中使用另一个斜杠：

```java
/portal/foo/bar
```

请记住这里的表格的区别：

| `/*` | 所有资源和目录在该级别 |
| --- | --- |
| `/**` | 所有资源和目录在该级别和子级别 |

我们故意在`cloudstreetmarket-webapp`应用程序中使用了单个通配符。对于其他类型的应用程序，将每个不匹配的 URI 重定向到默认 URI 可能更合适。在我们的单页面应用程序中，它将是面向 REST 的，当找不到资源时，最好通知客户端出现`404`错误。

在路径模式的末尾使用通配符并不是唯一的选择。如果需要，我们可以实现以下类型的模式：

```java
/portal/**/foo/*/bar  	
```

（尽管不是为了回退目的）。

我们将看到 Spring MVC 如何选择一个处理程序，它会比较所有匹配的路径模式，并选择最具体的路径模式。

### 提示

在 Controller 类型级别，我们没有指定`@RequestMapping`。如果我们这样做了，方法级别的指定路径将被连接到类型级别的路径上（实现缩小范围）。

例如，以下定义将为我们的回退控制器定义路径模式`/portal/default/*`：

```java
@RequestMapping(value="/default"...)
@Controller
public class DefaultController…{
      @RequestMapping(value="/*"...)
      public String fallback(Model model) {...}
}
```

#### `/portal/*`

当给定的 URL 匹配多个已注册的路径模式时，Spring MVC 会进行路径模式比较，以选择将请求映射到哪个处理程序。

### 注意

被认为最具体的模式将被选择。

第一个标准是在比较的路径模式中计算变量和通配符的数量：具有最低数量变量和通配符的模式被认为是最具体的。

要区分具有相同累积变量和通配符数量的两个路径模式，请记住具有最低通配符数量的模式将是最具体的，然后最长的路径将是最具体的。

最后，具有双通配符的模式始终比没有任何通配符的模式不具体。

为了说明这一选择，让我们考虑以下从最具体到最不具体的层次结构：

`/portal/foo`

`/portal/{foo}`

路径模式比较

`/portal/{foo}/{bar}`

`/portal/default/*/{foo}`

`/portal/{foo}/*`

`/portal/**/*`

`/portal/**`

#### 视图解析器

在**cloudstreetmarket-webapp**的`dispatcher-context.xml`中，我们已经定义了`viewResolver` bean：

```java
<bean id="viewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver">
  <property name="viewClass" value="org.springframework.web.servlet.view.JstlView" />
  <property name="prefix" value="/WEB-INF/jsp/" />
  <property name="suffix" value=".jsp" />
</bean>
```

`viewResolver` bean 是预定义类的特定实例，用于提供有组织和统一的视图层集合。在我们配置的情况下，`viewResolver` bean 是`InternalResourceViewResolver`的一个实例，它可以提供 JSP 页面，处理 JSTL 和 tiles。这个类还继承了`UrlBasedViewResolver`，可以导航应用程序资源，并可以将逻辑视图名称绑定到视图资源文件。这种能力可以防止创建额外的映射。

在我们的配置中，我们已经定义了视图存储库`(/WEB-INF/jsp/*.jsp)`，我们可以直接使用字符串`index`引用`index.jsp`。

最好将 JSP 存储库设置在`/WEB-INF`下，这样这些 JSP 就不能被公开访问。我们可以使用`VelocityViewResolver`或`FreeMarkerViewResolver`来代替 JSP 模板，而不是 JSP 模板。

此外，当我们构建 REST API 时，我们将在后面讨论`ContentNegotiatingViewResolver`。

## 还有更多...

本节特别强调了`@PathVariable`注解。这个注解是控制器方法处理程序参数的注解（我们在前面的示例中介绍了所有这些）。

### @PathVariable 用于读取 URI 模板模式中的变量

稍后您将在几个示例中找到方法级别的`@RequestMapping`注解。这些注解有时会与方法处理程序参数上的`@PathVariable`注解相关联。现在，让我们考虑以下示例：

```java
@RequestMapping(value="/example/{param}")
public HttpEntity<String> example(@PathVariable("param") String parameter) {
  return new HttpEntity<>(parameter);
}
```

如前所述，`@PathVariable`告诉 Spring MVC 在何处以及如何从请求 URI 中实现其注入作为参数。框架将解析当前 URI 模板模式以提取名为`param`的变量，并将匹配值注入当前 URI 中的目标方法参数。

我们还声明要返回的`HTTPEntity`。这个`HTTPEntity`将是一个 String 泛型类型的包装器。在方法处理程序内部，我们使用必要的 String 元素实例化这个包装器。

如果我们调用`/portal/example/foo` URI，它将作为返回的`HTTPEntity`的正文显示：String`foo`。

通过另一个有趣的特性，我们可以使用以下`@PathVariable`声明构建最后一个场景：

```java
@RequestMapping(value="/example/{param}")
public HttpEntity<String> example(@PathVariable String param) {
  return new HttpEntity<>(param);
}
```

### 提示

如果不向注释提供值，Spring MVC 默认会在 URI 模板模式中查找与目标参数同名的变量。

我们将探讨关于`@RequestMapping`和`@PathVariable`的其他功能。

# 使用 Bootstrap 设置和定制响应式单页网页设计

Bootstrap 最初是由 Twitter 的 Mark Otto 和 Jacob Thornton 创建的 UI 框架。它是一个了不起的样式、图标和行为来源，用于定义和丰富组件。Bootstrap 提供了一套易于理解、统一的样式定义模式。以前没有类似的。如果您从未使用过它，您将会对从 DOM 的快速定义中获得如此多的视觉反馈感到兴奋。

2014 年 6 月，它是 GitHub 上的第一个项目，拥有超过 73,000 颗星星和超过 27,000 个分支。他们的文档非常流畅，易于阅读。

## 准备工作

在这个配方中，我们将使用 Bootstrap 从现有的 Bootstrap 主题为 CloudStreet Market 项目设置 Web 设计基础。我们将重新制作`index.jsp`页面，以呈现一个外观更好的欢迎页面，可以通过以下屏幕截图预览。

![准备工作](img/image00821.jpeg)

## 如何做...

这个配方有三个主要步骤：

+   安装 Bootstrap 主题

+   定制 Bootstrap 主题

+   创建响应式内容

从 Eclipse 的 Git 视角，检出`v2.x.x`分支的最新版本：

![如何做...](img/image00822.jpeg)

### 安装 Bootstrap 主题

1.  在`chapter_2`目录中，您可以找到一个`freeme.zip`存档。这是一个可免费下载的响应式 Bootstrap 模板。这个 zip 来自[bootstrapmaster.com](http://bootstrapmaster.com)网站。

1.  在这个存档中，您会看到一个`css`目录，一个`js`目录，一个`img`目录，最后是一个`index.html`文件。使用 Web 浏览器打开`index.html`文件应该呈现以下主页：![安装 Bootstrap 主题](img/image00823.jpeg)

我们正在使用此模板作为 webapp 模块的基础。

1.  所有位于`freeme/js`目录中的 JavaScript 文件已复制到`/cloudstreetmarket-webapp/src/main/webapp/js`目录中。

1.  所有位于`freeme/css`目录中的 CSS 文件已复制到`/cloudstreetmarket-webapp/src/main/webapp/css`目录中。

1.  所有位于`freeme/img`中的图片已复制到`/cloudstreetmarket-webapp/src/main/webapp/img`目录中。

1.  `freeme/index.html`文件的内容已被复制并粘贴到`/cloudstreetmarket-webapp/src/main/webapp/WEB-INF/jsp/index.jsp`文件中，使用 UTF-8。

1.  此外，`freeme/licence.txt`已被复制并粘贴到`/cloudstreetmarket-webapp/src/main/webapp/WEB-INF/jsp`目录中。

1.  此时，使用 Web 浏览器调用`http://localhost:8080/portal/index`将显示与之前看到的完全相同的视觉效果，但由我们的应用程序提供。

### 定制 Bootstrap 主题

在本节中，我们将详细介绍为了使下载的模板适应我们的用例而做了什么。

1.  以前位于`cloudstreetmarket-webapp\src\main\webapp\img\logos`中的所有图片已被删除，并用代表我们在整个应用程序和本书中一直在使用的技术产品品牌的六张新图片替换。

1.  在`cloudstreetmarket-webapp`模块中的`index.jsp`文件中已实现以下更改：

1.  以下两行已添加到顶部：

```java
<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<%@ page isELIgnored="false" %>
```

1.  `<!-- start: Meta -->`部分已替换为以下内容：

```java
<!-- start: Meta -->
<meta charset="utf-8">
<title>Spring MVC: CloudST Market</title> 
<meta name="description" content="Spring MVC CookBook: Cloud Street Market"/>
<meta name="keywords" content="spring mvc, cookbook, packt publishing, microservices, angular.js" />
<meta name="author" content="Your name"/>
<!-- end: Meta -->
```

1.  `<!--start: Logo -->`部分已替换为以下内容：

```java
<!--start: Logo -->
<div class="logo span4">
  CLOUD<span class="sub">ST</span><span>Market</span>
</div>
<!--end: Logo -->
```

1.  导航菜单定义已更改：

```java
<ul class="nav">
  <li class="active"><a href="index">Home</a></li>
  <li><a href="markets">Prices and markets</a></li>
  <li><a href="community">Community</a></li>
  <li><a href="sources">Sources</a></li>
  <li><a href="about">About</a></li>
  <li><a href="contact">Contact</a></li>
</ul>
```

1.  已删除`<!-- start: Hero Unit -->`和`<!-- start: Flexslider -->`部分，并清空了导航菜单(`<!--end: Navigation-->`)后面的`<div class="row">`：

```java
<!-- start: Row -->
<div class="row"></div>
<!-- end: Row -->
```

1.  `<!-- start: Row -->`部分到`<!-- end: Row -->`部分，在`<!-- end Clients List -->`之后，已删除，并且紧随其后的`<hr>`也已删除。

1.  页脚部分`<!-- start: Footer Menu -->`到`<!-- end: Footer Menu -->`已替换为以下内容：

```java
<!-- start: Footer Menu -->
<div id="footer-menu" class="hidden-tablet hidden-phone">
  <!-- start: Container -->
  <div class="container">
    <!-- start: Row -->
    <div class="row">
      <!-- start: Footer Menu Logo -->
      <div class="span1">
      <div class="logoSmall">CLOUD<span class="sub">ST</span><span>M!</span>
        </div>
        </div>
      <!-- end: Footer Menu Logo -->
      <!-- start: Footer Menu Links-->
      <div class="span10" >
      <div id="footer-menu-links">
      <ul id="footer-nav" style="margin-left:35pt;">
        <li><a href="index">Home</a></li>
        <li><a href="markets">Prices and markets</a></li>
      <li><a href="community">Community</a></li>
        <li><a href="sources">Sources</a></li>
        <li><a href="about">About</a></li>
        <li><a href="contact">Contact</a></li>
        </ul>
        </div>
        </div>
        <!-- end: Footer Menu Links-->
        <!-- start: Footer Menu Back To Top -->
        <div class="span1">
        <div id="footer-menu-back-to-top">
          <a href="#"></a>
          </div>
        </div>
        <!-- end: Footer Menu Back To Top -->
    </div>
    <!-- end: Row -->
    </div>
  <!-- end: Container  -->	
</div>	
<!-- end: Footer Menu -->
```

1.  `<!-- start: Photo Stream -->`到`<!-- end: Photo Stream -->`部分已替换为：

```java
<!-- start: Leaderboard -->
<div class="span3">
  <h3>Leaderboard</h3>
  <div class="flickr-widget">
    <script type="text/javascript" src=""></script>
    <div class="clear"></div>
  </div>
</div>
<!-- end: Leaderboard -->
```

1.  在`index.jsp`文件中的最后一个更改是，版权部分已经调整。

1.  在先前复制的`cloudstreetmarket-webapp/src/main/webapp/css/style.css`文件中，已添加了以下类：

```java
.logo{
  font-family: 'Droid Sans';	font-size: 24pt; color: 	#666; width:157pt; font-weight:bold; margin-top:18pt; 	margin-left:10pt; height:30pt;
}
.logo span{
  position:relative;float:right; margin-top: 3pt;	font-weight:normal; font-family: 'Boogaloo'; font-	style:italic;	color: #89C236; padding-right: 3pt;
}
.logo .sub {
  vertical-align: super;	font-style:normal;font-size: 16pt; font-family: 'Droid Sans';	font-weight:bold; position: absolute;	color: #888; 	margin:-4pt 0 -4pt 0;
}
.logoSmall{
  font-family: 'Droid Sans';	font-size: 16pt; color: #888;width:80pt;	font-weight:bold; margin-top:10pt;height:20pt; margin-right:30pt;
}
.logoSmall span{
  position:relative;	float:right; margin-top: 3pt;
  font-weight:normal;font-family: 'Boogaloo';	font-style:italic;color: #89C236;
}
.logoSmall .sub {
  vertical-align: super;
  font-style:normal;	font-size: 10pt;font-family: 'Droid Sans';font-weight:bold;position: absolute; color: #666;margin:-2pt 0 -4pt 0;
}
```

1.  在所有这些更改之后，重新启动 Tomcat 并调用相同的 URL`http://localhost:8080/portal/index`导致了以下状态：![自定义 Bootstrap 主题](img/image00824.jpeg)

### 创建响应式内容

我们将在本节中重点关注填充欢迎页面的响应式内容所做的更改。通过响应式，理解为内容将根据设备大小和方向呈现适当的样式。

1.  在`index.jsp`文件中：

1.  `<div class="row">`已添加了以下内容：

```java
<div class='span12'>
  <div class="hero-unit hidden-phone"><p>Welcome to CloudStreet Market, the educational platform.</p></div>
</div>
<div class='span5'>
    <div id='landingGraphContainer'></div>
    <div id='tableMarketPrices'>
      <table class="table table-hover table-condensed table-bordered table-striped">
        <thead>
          <tr>
            <th>Index</th>
            <th>Value</th>
            <th>Change</th>
          </tr>
         </thead>
         <tbody>
       <tr>
           <td>Dow Jones-IA</td><td>17,634.74</td>
           <td class='text-success'><b>-18.05</b></td>
            </tr>
            ...
            <tr>
              <td>FTSE MIB</td><td>18,965.41</td>
              <td class='text-error'><b>-182.86</b></td>
            </tr>
            ...
        </tbody>
        </table>
      </div>
</div>
<div id="containerCommunity" class='span7'>
    <div id="divRss3"></div>
</div>
```

### 注意

在先前添加的*landingGraphContainer*中，我们已插入了一个生成的图表，显示了最近开放日内特定市场的发展情况。该图表使用了`morris.js`库([`morrisjs.github.io/morris.js`](http://morrisjs.github.io/morris.js))，它还依赖于`raphael.js`库([`cdnjs.com/libraries/raphael`](https://cdnjs.com/libraries/raphael))。

1.  在文件底部，已添加了`<!-- start: Java Script -->`部分到`<!-- end: Java Script -->`部分的以下内容：

```java
<script src="img/jquery-1.8.2.js"></script>
<script src="img/bootstrap.js"></script>
<script src="img/flexslider.js"></script>
<script src="img/carousel.js"></script>
<script def src="img/custom.js"></script>
<script src="img/FeedEk.js"></script>
<script src="img/raphael.js"></script>
<script src="img/morris.min.js"></script>
<script>
$(function () {
    var financial_data = [
     {"period": "08:00", "index": 66},{"period": "09:00", "index": 62},
	 {"period": "10:00", "index": 61},{"period": "11:00", "index": 66},
     {"period": "12:00", "index": 67},{"period": "13:00", "index": 68},
     {"period": "14:00", "index": 62},{"period": "15:00", "index": 61},
     {"period": "16:00", "index": 61},{"period": "17:00", "index": 54}
    ];
    Morris.Line({
      element: 'landingGraphContainer',
      hideHover: 'auto', data: financial_data,
      ymax: 70, ymin: 50,
      pointSize: 3, hideHover:'always',
      xkey: 'period', xLabels: 'month',
      ykeys: ['index'], postUnits: '',
      parseTime: false, labels: ['Index'],
      resize: true, smooth: false,
      lineColors: ['#A52A2A']
    });
});
</script>
```

1.  在`cloudstreetmarket-webapp\src\main\webapp\js`目录中，`morris.min.js`和`raphael.js`库已从它们各自的网站复制并粘贴。

1.  回到`index.jsp`文件：

1.  先前创建的`<div id='containerCommunity'>`已填充了以下内容：

```java
<div id="divRss3">
  <ul class="feedEkList">
    <li>
    <div class="itemTitle">
      <div class="listUserIco">
        <img src='img/young-	lad.jpg'>
      </div>
      <span class="ico-white ico-up-arrow   listActionIco 	actionBuy"></span>
        <a href="#">happyFace8</a> buys 6 <a href="#">NXT.L</a> at $3.00
        <p class="itemDate">15/11/2014 11:12 AM</p>
    </div>
    </li>
    <li>
    <div class="itemTitle">
      <div class="ico-user listUserIco"></div>
      <span class="ico-white ico-down-arrow listActionIco actionSell"></span>
      <a href="#">actionMan9</a> sells 6 <a href="#">CCH.L</a> at $12.00
      <p class="itemDate">15/11/2014 10:46 	AM</p>
    </div>
    </li>
      ...
  </ul>
</div>
```

1.  此部分使用了 feedEk jQuery 插件。它带有自己的 CSS 和 JavaScript 文件。

1.  `cloudstreetmarket-webapp\src\main\webapp\js`目录包括与 feedEk jQuery 插件相关的`FeedEk.js`文件。此插件可以在线找到([`jquery-plugins.net/FeedEk/FeedEk.html`](http://jquery-plugins.net/FeedEk/FeedEk.html))。

1.  `cloudstreetmarket-webapp\src\main\webapp\css`目录还有相关的`FeedEk.css`文件。

1.  仍然在`index.jsp`中，在`<!-- start: CSS -->`注释下面，已添加了`FeedEk css`文档：

```java
<link href="css/FeedEk.css" rel="stylesheet">
```

1.  在`style.css`文件中，在第一个媒体查询定义`(@media only screen and (min-width: 960px)`之前，已经添加了以下样式定义：

```java
.listUserIco {
    background-color:#bbb;
    float:left;
    margin:0 7px 0 0;
}
.listActionIco {
    float:right; 
    margin-top:-3px;
}
.actionSell {
    background-color:#FC9090;
}
.actionBuy {
    background-color:#8CDBA0;
}
#landingGraphContainer{
    height:160px;
    padding: 0px 13px 0 10px;
}
.tableMarketPrices{
    padding: 13px 13px 0 15px;
}
```

1.  最后，两张新图片（个人资料图片）已添加到`cloudstreetmarket-webapp\src\main\webapp\img`。

1.  尝试动态调整渲染的浏览器窗口大小：`http://localhost:8080/portal/index`。您应该观察到响应式和自适应的样式，就像下面的图片一样：![创建响应式内容](img/image00825.jpeg)

## 它是如何工作的...

为了理解我们的 Bootstrap 部署，我们现在将回顾它是如何作为一个预设计的主题安装的。然后我们将发现 Bootstrap 框架的一些关键特性——不仅仅是已实现的特性，因为合乎逻辑的是，框架的一些特性只能在一个单独的页面示例上进行视觉使用。

### 主题安装

我们获得的主题不过是一个经典的静态主题，就像您可以在互联网上找到成千上万个一样。它们是由网页设计师制作并免费或商业分发的。这个主题是由 HTML 文件的基本结构、一个 JS 目录、一个 CSS 目录和一个 IMG 目录制作的。

主题安装非常容易理解，因为我们只是将 JavaScript 文件、CSS 文件和图像放在了应用程序的预期位置。

### 提示

Bootstrap 的核心特性包含在`bootstrap.js`、`bootstrap.css`和`bootstrap-responsive.css`中。您实际上不需要直接调整这些文件。

### Bootstrap 亮点

实现的主题（FreeME）使用了 Bootstrap 2。我们将回顾一些已在模板中实现并适用于我们项目需求的功能。

#### Bootstrap 脚手架

Bootstrap 脚手架有助于设计通常由网格模型构建的 HTML 结构。关于这个主题的 Bootstrap 策略在以下部分中有描述。

##### 网格系统和响应式设计

Bootstrap 提供了一个样式框架来处理特定页面的网格系统。关键点在于默认的网格系统由 12 列组成，设计用于 940 像素宽的非响应式容器。

通过使用`<meta name="viewport"…>`标签和导入`boostrap-responsive.css`文件，可以激活 Bootstrap 的响应特性。在这种情况下，容器宽度可以从 724 像素扩展到 1170 像素。

### 提示

此外，在 767 像素以下，列会变成流动并垂直堆叠。

这些 Bootstrap 规范定义了一组相当严格的约束条件，但 Bootstrap 在某种程度上为其实现创建了易于理解的设计统一性。

在我们的模板中，视口元标签如下：

```java
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
```

### 注意

如果您对这个标签不熟悉，它的主要目的是在文档中定义特定设备的尺寸。从这些尺寸中，为特定方向和特定设备的渲染定义规则。绑定到样式定义的这些规则称为媒体查询。您可以在 style.css 文件中找到媒体查询的示例：

```java
/* Higher than 960 (desktop devices)
================================================================ */
@media only screen and (min-width: 960px) {
...
  #footer-menu {
    padding-left: 30px;
    padding-right: 30px;
    margin-left: -30px;
    margin-right: -30px;
  }
...
}
```

这个媒体查询覆盖了仅在设备宽度大于 960 像素时呈现的 id footer menu 的特定样式。

##### 定义列

为了在网格系统中定义列，Bootstrap 引导我们使用标记为`row`类元素的`row` div。然后，想法是定义用自定义`span*`类元素标记的子 div，其中`*`字符表示我们必须处理的 12 列网格的子分区。

例如，考虑以下两种可能的设计：

![定义列](img/image00826.jpeg)

左侧示例中的两列可以从 DOM 定义中呈现出来：

```java
<div class="row">
  <div class="span4">...</div>
  <div class="span8">...</div>
</div>
```

右侧示例中的两列可以从 DOM 定义中呈现出来：

```java
<div class="row">
  <div class="span6">...</div>
  <div class="span6">...</div>
</div>
```

考虑到这一点，我们欢迎页面的网格实际上是这样的：

![定义列](img/image00827.jpeg)

##### 偏移和嵌套

偏移列允许您创建一个与一个或多个不可见列相对应的固定大小的衰减。例如，考虑以下代码片段：

```java
<div class="row">
    <div class="span6">...</div>
    <div class="span4 offset2">...</div>
</div>
```

这个 DOM 定义将对应以下列：

![偏移和嵌套](img/image00828.jpeg)

一个列也可以嵌套在另一个列中，重新定义一个新的行。新创建的列的总和必须与父元素的大小相对应：

```java
<div class="row">
   <div class="span6">
      <div class="row">
        <div class="span2">...</div>
        <div class="span4">...</div>
      </div>
   </div>
</div>
```

##### 流动网格

我们之前说过，使用 Boostrap2，当屏幕宽度小于 767 像素时，*列会变成流动并垂直堆叠*。模板网格可以从静态变为流动，将`.row`类更改为`.row-fluid`。这个系统将使用百分比，而不是固定像素大小的列。

#### Bootstrap CSS 实用程序

Bootstrap 还提供了一些预设计的元素，如按钮、图标、表格、表单，以及支持排版或图像的实用程序。

##### 统一按钮

可以从`<a>`和`<button>`标签中创建默认样式的按钮，只需添加`.btn`类元素。然后可以以不同的颜色变化来拒绝创建的默认灰色按钮。例如，默认情况下，以下类组合：

+   `.btn .btn-primary`: 这会产生一个强烈的群青蓝色按钮，以标识主要操作

+   `.btn .btn-info`: 这会产生一个中等的绿松石蓝色按钮

+   `.btn .btn-success`: 这会产生一个积极的绿色按钮

+   `.btn .btn-warning`: 这会产生一个警告橙色按钮

+   `.btn .btn-danger`: 这会产生一个危险的红色按钮

+   `.btn .btn-inverse`: 这会产生一个黑色按钮，带有白色文本

+   `.btn .btn-link`: 这会产生一个链接，同时保持按钮行为

这些按钮也可以通过添加`.btn-large`类、添加`.btn-small`类或添加`.btn-mini`类来进行可调整大小的声明：

![统一按钮](img/image00829.jpeg)

通过将其添加为**disabled**属性，可以禁用按钮。同样，可以通过添加`.disabled`类来禁用`<a>`标记的按钮。我们还没有使用按钮，但这是一个很好的功能，可以在这一点上进行介绍。

##### 图标

Bootstrap 2 带有一个令人印象深刻的 140 个深灰色图标集，可用作精灵并由 Glyphicons 提供：

![图标](img/image00830.jpeg)

### 提示

这些图标通常是商业可用的，但作为 Bootstrap 产品的一部分，它们也可以免费使用。但是 Bootstrap 要求我们提供一个可选的回链到[`glyphicons.com`](http://glyphicons.com)。

所有这些图标都可以通过简单的类从 DOM 中提取，例如`<i class="icon-search"></i>`。

令人惊讶的是，您实际上可以将这些图标嵌入到每个适合的 Bootstrap 组件中。例如，按钮定义：`<a class="btn btn-mini" href="#"><i class="icon-star"></i> Star</a>`，会产生以下结果：

![图标](img/image00831.jpeg)

##### 表格

我们已经为市场活动概览实现了一个 Bootstrap 表格。我们基本上设计了以下表格：

```java
<table class="table table-hover table-condensed table-bordered table-striped">
  <thead>
    <tr><th>Index</th>
       <th>Value</th>
       <th>Change</th></tr>
  </thead>
  <tbody>
      <tr><td>...</td>
       <td>...</td>
       <td>...</td>
    </tr>
  </tbody>
</table>
```

与我们可以定义一个使用自定义类覆盖的按钮类一样，我们已经定义了一个通用的 Bootstrap 表格，使用了`.table`类，然后我们使用了以下自定义类：

+   `.table .table-hover`: 这可以在`<tbody>`中的表格行上启用悬停状态

+   `.table .table-condensed`: 这使表格更紧凑

+   `.table .table-bordered`: 这为表格添加了边框和圆角

+   `.table .table-striped`: 这为`<tbody>`中的任何表格行添加斑马条纹

#### Bootstrap 组件

该框架还具有其他预设计的元素，称为组件。其中，下拉菜单、按钮组、面包屑、分页、导航栏、标签和徽章、缩略图、警报、进度条等。这里我们只介绍其中一些：

##### 导航栏

Bootstrap 导航栏提供了基本导航菜单的支持。它们默认不固定在页面顶部；它们必须包含在`.container`中。代码如下：

```java
<div class="navbar navbar-inverse">
  <div class="navbar-inner">
  ...
  <ul class="nav">
    <li class="active"><a href="index">Home</a></li>
    <li><a href="markets">Prices and markets</a></li>
    <li><a href="community">Community</a></li>
    <li><a href="sources">Sources</a></li>
    <li><a href="about">About</a></li>
    <li><a href="contact">Contact</a></li>
  </ul>
...
```

导航栏中最基本的功能是可激活的链接：

![导航栏](img/image00832.jpeg)

上面的示例可以根据以下 DOM 定义进行设计：

```java
<ul class="nav">
     <li class="active"><a href="#">Home</a></li>
     <li><a href="#">Link</a></li>
</ul>
```

我们强烈建议阅读 Bootstrap 文档。关于如何实现其他功能的更多细节可以在文档中找到。例如，Bootstrap 提供了以下工具：

+   例如输入文本、搜索字段和提交按钮的表单元素。

+   不同的定位变化，例如固定在顶部（使用`.navbar-fixed-top`）、固定在底部（使用`.navbar-fixed-bottom`），与随页面滚动而消失的全宽度导航栏相对（使用`.navbar-static-top`）。

+   可折叠的响应式导航栏（`.nav-collapse.collapse`）可以节省大量空间。通过使用 data-toggle HTML5 属性，可以在没有额外 JavaScript 配置的情况下进行动态处理。

##### 主要单元

提供的模板中定义了一个英雄单元。我们只是稍微移动了一下，以适应我们的响应需求。

这是一个轻量级、灵活的组件，用于在您的网站上展示关键内容。

![英雄单元](img/image00833.jpeg)

上面的示例可以从以下 DOM 定义中设计：

```java
<div class="hero-unit"><p>Welcome to CloudStreet Market, the educational platform.</p></div>
```

##### 警报

Bootstrap 警报非常适合快速生成预定义样式的警告消息或其他上下文消息。Bootstrap 警报带有一个**可选的**关闭按钮（它将隐藏警报，无需额外的 JavaScript 配置）。代码如下：

```java
<div class="alert">
    <button type="button" class="close" data-dismiss="alert">&times;</button>
    <strong>Warning!</strong> Best check yo self, you're not looking too good.
</div>
```

此定义产生了这里呈现的输出：

![警报](img/image00834.jpeg)

警报是在`<div>`标签上用`.alert`类定义的，可以设置上下文颜色变化，提供额外的覆盖类，如`.alert-success`、`.alert-info`或`.alert-error`。

##### 徽章和标签

Bootstrap 标签非常适合丰富内容。它们在列表或表格中表现得特别好。在这里找到可能的上下文变化的概述：

![徽章和标签](img/image00835.jpeg)

这里的标签将被定义为：

```java
<span class="label">Default</span>
<span class="label label-success">Success</span>
<span class="label label-important">Important</span>
…
```

徽章将被定义为：

```java
<span class="badge">1</span>
<span class="badge badge-warning">4</span>
<span class="badge badge-important">6</span>
…
```

## 还有更多...

Bootstrap 还有比这个*小*概述更丰富的官方文档。再次强调，官方文档非常完善和易懂。

访问[`getbootstrap.com`](http://getbootstrap.com)获取与框架的最新支持版本相关的文档。转到[`getbootstrap.com/2.3.2`](http://getbootstrap.com/2.3.2)获取与我们项目中使用的版本相关的文档。

我们将在接下来的章节中实现更多功能，并且将尽可能地突出它们。

## 另请参阅

如果你喜欢 Bootstrap，并且希望在你的项目中使用它，你必须考虑版本 3。

### 提示

Bootstrap 3 与 Bootstrap 2 不是直接兼容的，但它实现了一个非常相似的网格系统和略有不同的标记。

+   Bootstrap 3 的新功能：这里是从 Bootstrap 2 到 Bootstrap 3 的重要变化的预览。

+   新的扁平化设计：新设计很容易注意到，按钮、导航栏和其他菜单的 3D 和纹理已经消失。他们现在采用了新的扁平风格，没有渐变。这确实符合当前的全球设计趋势。

+   列命名跨度重命名为 col-：除了不再作为 row-fluid 类（现在所有行都自动是流体的）的混淆，列命名模式已经重新思考，以获得更一致性。

+   移动优先：框架的响应特性现在原生地包含在`bootstrap.js`和`bootstrap.css`文件中（不再有`bootstrap-responsive.js`或`bootstrap-responsive.css`）。现在可以直接从 DOM 使用一组新的设备特定类来驱动媒体查询任务。

# 在视图中显示模型，使用 JSTL

此示例显示了如何使用数据填充 Spring MVC 视图以及如何在视图中呈现这些数据。

## 准备工作

在这一点上，我们没有任何真实的数据要在我们的视图中显示。为此，我们创建了三个 DTO 和两个服务层，它们从它们的接口注入到控制器中。

有两个虚拟的服务实现，旨在生成一组虚假数据。我们将使用**Java Server Tags Library**（**JSTL**）和**JSP Expression Language**（**JSP EL**）在我们的 JSP 中的正确位置呈现服务器数据。

## 如何做到...

1.  在检出`v2.x.x`分支（在上一个示例中），**cloudstreetmarket-core**模块中现在显示了一些新组件：两个接口，两个实现，一个枚举和三个 DTO。代码如下：

```java
public interface IMarketService {
  DailyMarketActivityDTO getLastDayMarketActivity(String string);
  List<MarketOverviewDTO> getLastDayMarketsOverview();
}
    public interface ICommunityService {
    List<UserActivityDTO> getLastUserPublicActivity(int number);
}
```

如你所见，它们指的是三个创建的 DTO：

```java
public class DailyMarketActivityDTO {
  String marketShortName;
  String marketId;
  Map<String, BigDecimal> values;
  Date dateSnapshot;
  ... //and constructors, getters and setters
}
public class MarketOverviewDTO {
  private String marketShortName;
  private String marketId;
  private BigDecimal latestValue;
  private BigDecimal latestChange;
  ... //and constructors, getters and setters
}
public class UserActivityDTO {
  private String userName;
  private String urlProfilePicture;
  private Action userAction;
  private String valueShortId;
  private int amount;
  private BigDecimal price;
  private Date date;
  ... //and constructors, getters and setters
}
```

这最后一个 DTO 是指`Action`枚举：

```java
public enum Action {
  BUY("buys"), SELL("sells");
  private String presentTense;
    Action(String present){
  presentTense = present;
  }
    public String getPresentTense(){
    return presentTense;
  }
}
```

此外，之前创建的`cloudstreetmarket-webapp`中的`DefaultController`已经被修改为：

```java
@Controller
public class DefaultController {
  @Autowired
  private IMarketService marketService;
  @Autowired
  private ICommunityService communityService;
  @RequestMapping(value="/*", method={RequestMethod.GET,RequestMethod.HEAD})
  public String fallback(Model model) {
    model.addAttribute("dailyMarketActivity", marketService.getLastDayMarketActivity("GDAXI"));
    model.addAttribute("dailyMarketsActivity", marketService.getLastDayMarketsOverview());
    model.addAttribute("recentUserActivity", communityService.getLastUserPublicActivity(10));
    return "index";
  }
}
```

这里有两个虚拟实现：

```java
@Service
public class DummyMarketServiceImpl implements IMarketService {
    private DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm");
    public DailyMarketActivityDTO 
    getLastDayMarketActivity(String string){
    Map<String, BigDecimal> map = new HashMap<>();
    map.put("08:00", new BigDecimal(9523));
    map.put("08:30", new BigDecimal(9556));
    ...
    map.put("18:30", new BigDecimal(9758));
    LocalDateTime ldt = LocalDateTime.parse("2015-04-10 17:00", formatter);
    return new DailyMarketActivityDTO("DAX 30","GDAXI", map, Date.from(ldt.toInstant(ZoneOffset.UTC)));
  }
    @Override
  public List<MarketOverviewDTO> getLastDayMarketsOverview() {
      List<MarketOverviewDTO> result = Arrays.asList(
      new MarketOverviewDTO("Dow Jones-IA", "DJI", new BigDecimal(17810.06), new BigDecimal(0.0051)),
      ...
      new MarketOverviewDTO("CAC 40", "FCHI", new BigDecimal(4347.23), new BigDecimal(0.0267))
    );
    return result;
  }
}
  @Service
public class DummyCommunityServiceImpl implements ICommunityService {
  private DateTimeFormatter formatter = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm");
    public List<UserActivityDTO> getLastUserPublicActivity(int number){
      List<UserActivityDTO> result = Arrays.asList(
      new UserActivityDTO("happyFace8", "img/young-lad.jpg", Action.BUY, "NXT.L", 6, new BigDecimal(3), LocalDateTime.parse("2015-04-10 11:12", formatter)),
      ...
       new UserActivityDTO("userB", null, Action.BUY, "AAL.L", 7, new BigDecimal(7), LocalDateTime.parse("2015-04-10 13:29", formatter))
      );
    return result;
  }
}
```

`index.jsp`已经被修改，增加了以下部分在图表容器下面：

```java
<div class='morrisTitle'>
  <fmt:formatDate value="${dailyMarketActivity.dateSnapshot}" pattern="yyyy-MM-dd"/>
</div>
<select class="form-control centeredElementBox">
  <option value="${dailyMarketActivity.marketId}"> ${dailyMarketActivity.marketShortName}
  </option>
</select> 
```

市场概览表，特别是主体部分，已经添加：

```java
<c:forEach var="market" items="${dailyMarketsActivity}">
  <tr>
    <td>${market.marketShortName}</td>
    <td style='text-align: right'>
      <fmt:formatNumber type="number" maxFractionDigits="3" value="${market.latestValue}"/>
  </td>
   <c:choose>
      <c:when test="${market.latestChange >= 0}">
      <c:set var="textStyle" scope="page" value="text-success"/>
      </c:when>
      <c:otherwise>
        <c:set var="textStyle" scope="page" value="text-error"/>
      </c:otherwise>
    </c:choose>        
      <td class='${textStyle}' style='text-align: right'>
        <b><fmt:formatNumber type="percent" maxFractionDigits="2" value="${market.latestChange}"/>
    </b>
  </td>
  </tr>
</c:forEach>
```

社区活动容器已添加：

```java
<c:forEach var="activity" items="${recentUserActivity}">
   <c:choose>
     <c:when test="${activity.userAction == 'BUY'}">
       <c:set var="icoUpDown" scope="page" value="ico-up-arrow actionBuy"/>
     </c:when>
     <c:otherwise>
       <c:set var="icoUpDown" scope="page" value="ico-down-	arrow actionSell"/>
     </c:otherwise>
    </c:choose>
    <c:set var="defaultProfileImage" scope="page" value=""/>
    <c:if test="${activity.urlProfilePicture == null}">
    <c:set var="defaultProfileImage" scope="page" value="ico-user"/>
    </c:if>
  <li>
  <div class="itemTitle">
    <div class="listUserIco ${defaultProfileImage}">
      <c:if test="${activity.urlProfilePicture != 	null}">
    <img src='${activity.urlProfilePicture}'>
</c:if>
</div>
  <span class="ico-white ${icoUpDown} listActionIco"></span>
<a href="#">${activity.userName}</a> 
${activity.userAction.presentTense} ${activity.amount} 
  <a href="#">${activity.valueShortId}</a> 
  at $${activity.price}
    <p class="itemDate">
      <fmt:formatDate value="${activity.date}" pattern="dd/MM/yyyy hh:mm aaa"/>
    </p>
    </div>
  </li>
</c:forEach>
```

在文件底部，现在从服务器填充了一组硬编码的 JavaScript 数据：

```java
<script>
  var financial_data = [];
  <c:forEach var="dailySnapshot" items="${dailyMarketActivity.values}">
  financial_data.push({"period": '<c:out value="${dailySnapshot.key}"/>', "index": <c:out value='${dailySnapshot.value}'/>});
  </c:forEach>
</script>
<script>
  $(function () {
    Morris.Line({
      element: 'landingGraphContainer',
      hideHover: 'auto', data: financial_data,
      ymax: <c:out value="${dailyMarketActivity.maxValue}"/>,
      ymin: <c:out value="${dailyMarketActivity.minValue}"/>,
      pointSize: 3, hideHover:'always',
      xkey: 'period', xLabels: 'month',
      ykeys: ['index'], postUnits: '',
      parseTime: false, labels: ['Index'],
      resize: true, smooth: false,
      lineColors: ['#A52A2A']
    });
});
</script>
```

## 它是如何工作的...

这些改变并没有产生基本的 UI 改进，但它们塑造了我们视图层的数据供应。

### 处理我们的数据的方法

我们将在这里审查数据供应实现的服务器端。

#### 通过接口注入服务

预测应用需要为首页提供动态数据，选择将两个服务层`marketService`和`communityService`注入到控制器中。问题是我们还没有一个合适的数据访问层。（这将在第四章中讨论，*构建无状态架构的 REST API*！）。尽管如此，我们需要控制器连接以呈现首页。

控制器的连接需要与其服务层松散耦合。在本章中创建虚拟服务实现的想法下，使用接口设计了连接。然后依赖 Spring 来注入预期的实现到服务依赖中，使用相关接口进行类型化。

```java
@Autowired
private IMarketService marketService;
@Autowired
private ICommunityService communityService;
```

请注意类型`IMarketService`和`ICommunityService`，它们不是`DummyCommunityServiceImpl`或`DummyMarketServiceImpl`。否则，当切换到真实实现时，我们将受到这些类型的限制。

#### Spring 如何选择虚拟实现？

它在**cloudstreetmarket-core** Spring 上下文文件中选择这些实现：`csmcore-config.xml`。我们之前定义了这些 bean：

```java
<context:annotation-config/>
<context:component-scan base-package="edu.zipcloud.cloudstreetmarket.core" />  
```

Spring 扫描与根包`edu.zipcloud.cloudstreetmarket.core`匹配的所有类型，以查找构造型和配置注解。

与`DefaultController`标记为`@Controller`注解的方式相同，我们的两个虚拟实现类标记为`@Service`，这是一个 Spring 构造型。在检测到的构造型和 bean 中，虚拟实现是唯一可用于注入配置的实现：

```java
@Autowired
private IMarketService marketService;

@Autowired
private ICommunityService communityService;
```

Spring 只需每个字段匹配一个相应的类型，就可以自动识别，无需额外配置。

#### DTOs 用于视图层

我们在 JSP 中获取的变量中使用了 DTOs。在同时维护多个版本时，暴露的 DTOs 在 Web 服务中特别有用。更一般地，当目标和目的对象有显著差异时，实现了 DTOs。

我们将稍后实现**实体**。最好不要在呈现或特定版本的逻辑中使用这些**实体**，而是将它们推迟到专门用于此目的的层。

尽管必须指出，创建 DTO 层会产生大量与类型转换相关的样板代码（影响其他层、测试等）。

#### 虚拟服务实现

`DummyMarketServiceImpl`实现了`getLastDayMarketActivity`方法，构建了一个活动地图（由静态每日时间关联到市场、指数的值）。它返回一个新的`DailyMarketActivityDTO`实例（从这个地图构建），它最终是一个包含单个市场或指数的每日活动的包装，比如 DAX 30。

`getLastDayMarketsOverview`方法返回一个`MarketOverviewDTOs`列表，也是从硬编码数据构建的。它模拟了一些市场（指数）的每日活动概况。

`DummyCommunityServiceImpl`实现了`getLastUserPublicActivity`方法，返回一个实例化的`UserActivityDTO`列表，模拟了最近六次用户活动。

### 在控制器中填充模型

在本章的第一个示例中介绍了可能的方法处理程序参数，我们已经看到可以注入一个 Model。这个 Model 可以在方法内部填充数据，并且会透明地传递到预期的视图中。

这就是我们在`fallback`方法处理程序中所做的。我们已经将服务层的三个结果传递给了三个变量`dailyMarketActivity`，`dailyMarketsActivity`和`recentUserActivity`，以便它们可以在视图中使用。

### 使用 JSP EL 渲染变量

JSP 表达式语言允许我们访问存储在**JavaBeans 组件**中的应用程序数据。`${...}`表示访问变量，例如`${recentUserActivity}`或`${dailyMarketActivity.marketShortName}`通常是 JSP EL 表示法。

当我们想要访问对象的属性（比如`dailyMarketActivity`的`marketShortName`）时，一个重要的要点是对象类必须为目标属性提供 JavaBeans 标准的 getter。

换句话说，`dailyMarketActivity.marketShortName`在`MarketOverviewDTO`类中指的是一个期望的：

```java
public String getMarketShortName() {
  return marketShortName;
}
```

#### 隐式对象

JSP EL 还提供了隐式对象，可以作为 JSP 中的快捷方式使用，无需在模型中声明或预填充。在这些隐式对象中，不同的范围 pageScope、requestScope、sessionScope 和 applicationScope 反映了相关范围中属性的映射。

例如，考虑以下属性：

```java
request.setAttribute("currentMarket", "DAX 30");
request.getSession().setAttribute("userName", "UserA");
request.getServletContext().setAttribute("applicationState", "FINE");
```

这些可以在 JSP 中分别访问：

```java
${requestScope["currentMarket"]}
${sessionScope["username"]}
${applicationScope["applicationState"]}
```

其他有用的隐式对象是请求头的映射：`header`（即`${header["Accept-Encoding"]}`），请求 cookie 的映射：`cookies`（即`${cookie["SESSIONID"].value}`），请求参数的映射：`param`（即`${param["paramName"]}`）或者上下文初始化参数的映射（来自`web.xml`）`initParam`（即`${initParam["ApplicationID"]}`）。

最后，JSP EL 提供了一些基本运算符：

+   **算术**：`+`，`-`（二进制），`*`，`/`和`div`，`%`和`mod`，`-`（一元）。

+   **逻辑**：`and`，`&&`，`or`，`||`，`not`，`!`。

+   **关系**：`==`，`eq`，`!=`，`ne`，`<`，`lt`，`>`，`gt`，`<=`，`ge`，`>=`，`le`。

可以与其他值或布尔值、字符串、整数或浮点数文字进行比较。

+   **Empty**：空操作符是一个前缀操作，用于确定值是否为 null 或空。

+   条件：`A ? B : C`。

根据对`A`的评估结果，评估`B`或`C`。

这些操作符的描述来自于 JavaEE 5 教程。

### 使用 JSTL 渲染变量

**JSP 标准标签库**（**JSTL**）是用于 JSP 页面的一组工具。它并不是 Java web 的全新功能，但仍然在使用中。

当我们需要显示逻辑或者需要在视图层格式化数据或构建层次结构时，最常用的标签可能是 Core 和 I18N。

| 区域 | 功能 | 标签 | 描述 |
| --- | --- | --- | --- |
| `Core` | `变量支持` | `c:set``c:remove` | 从范围中设置/取消设置变量。 |
| `流程控制` | `c:choose``c:when``c:otherwise` | 实现条件块 IF/THEN/ELSE。 |
| `c:if` | 实现条件 IF 块。 |
| `c:forEach` | 遍历集合类型。 |
| `c:forTokens` | 遍历由提供的分隔符分隔的令牌。 |
| `URL 管理` | `c:import``c:param` | 解析 URL，将其内容导入页面、变量（var）或变量读取器（varReader）。可以使用 param 将参数传递给底层资源。 |
| `c:redirect``c:param` | 重定向到 URL。可以传递参数。 |
| `c:url``c:param` | 创建 URL。可以分配参数。 |
| `杂项` | `c:catch` | 捕获其块中发生的任何可抛出的异常。 |
| `c:out` | 获取表达式或变量。 |
| `I18N` | `设置 Locale` | `fmt:setLocale``fmt:requestEncoding` | 在特定范围内存储 Locale。设置页面的 HTTP 请求的编码类型。 |
| `消息传递` | `fmt:bundle``fmt:message``fmt:param``fmt:setBundle` | 为特定标签或范围设置 bundle。检索消息，输出其内容，传递可选参数。 |
| `数字和日期格式化` | `fmt:formatNumber``fmt:formatDate``fmt:parseDate``fmt:parseNumber``fmt:setTimeZone``fmt:timeZone` | 以不同格式输出不同内容。解析日期和数字。为特定标签或范围设置时区。 |

这些介绍的标签并不是 JSTL 的唯一功能，访问 Java EE 教程以获取更多详细信息：

[`docs.oracle.com/javaee/5/tutorial/doc/bnakc.html`](http://docs.oracle.com/javaee/5/tutorial/doc/bnakc.html)

#### JSP 中的 Taglib 指令

如果我们计划使用上述任何一个标签，我们首先需要在 JSP 页面中包含适当的指令：

```java
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/fmt" prefix="fmt" %>
```

## 还有更多...

### 关于 JSP EL 的更多信息

JSP EL 还涵盖了更多功能。请随时阅读 Oracle 教程，比如[`docs.oracle.com/javaee/5/tutorial/doc/bnahq.html`](http://docs.oracle.com/javaee/5/tutorial/doc/bnahq.html)。

### 关于 JavaBeans 标准的更多信息

当使用 JSP EL 时，我们已经谈到了预期的 JavaBean 标准。关于 JavaBeans 的更多信息可以再次在 Oracle 教程中找到：

[`docs.oracle.com/javaee/5/tutorial/doc/bnair.html`](http://docs.oracle.com/javaee/5/tutorial/doc/bnair.html)

### 关于 JSTL 的更多信息

正如宣布的那样，您可以在 Java EE 教程中发现 JSTL 的更多模块：

[`docs.oracle.com/javaee/5/tutorial/doc/bnakc.html`](http://docs.oracle.com/javaee/5/tutorial/doc/bnakc.html)

# 定义一个通用的 WebContentInterceptor

在这个示例中，我们将重点介绍我们如何为控制器实现了一个`WebContentInterceptor`超类。

## 准备工作

我们将要介绍一个控制器超类，具有作为`WebContentInterceptor`注册的特性。这个超类允许我们全局控制会话并管理缓存选项。

它将帮助我们理解整个框架和其他潜在拦截器的请求生命周期。

## 如何做...

1.  使用特定配置注册默认的`WebContentInterceptor`可以完全通过配置方法完成：

```java
<mvc:interceptors>
  <bean id="webContentInterceptor" class="org.sfw.web.servlet.mvc.WebContentInterc	eptor">
    <property name="cacheSeconds" value="0"/>  
    <property name="requireSession" value="false"/>  
    ...
  </bean>
<mvc:interceptors>
```

### 提示

在我们的应用程序中，我们已经注册了自定义的`WebContentInterceptors`来覆盖默认的行为。

1.  在代码库中，仍然从先前检出的`v2.x.x`分支中，可以在`cloudstreetmarket-api`中找到一个新的`cloudstreetApiWCI`类：

```java
public class CloudstreetApiWCI extends WebContentInterceptor {
  public CloudstreetApiWCI(){
    setRequireSession(false);
    setCacheSeconds(0);
  }
  @Override
  public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws ServletException {
      super.preHandle(request, response, handler);
      return true;
  }
  @Override
  public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, 	ModelAndView modelAndView) throws Exception {
  }
  @Override
  public void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex) throws Exception {
  }
}
```

1.  在**cloudstreetmarket-webapp**中也有一个类似的`CloudstreetWebAppWCI`：

```java
public class CloudstreetWebAppWCI extends WebContentInterceptor {
  public CloudstreetWebAppWCI(){
    setRequireSession(false);
    setCacheSeconds(120);
    setSupportedMethods("GET","POST", "OPTIONS", "HEAD");
  }
  @Override
  public boolean preHandle(HttpServletRequest request, HttpServletResponse  response, Object handler) throws ServletException {
      super.preHandle(request, response, handler);
      return true;
  }
  @Override
  public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView 	modelAndView) throws Exception {
  }
  @Override
  public void afterCompletion(HttpServletRequest request, HttpServletResponse response, Object handler, Exception ex) throws Exception {
  }
}
```

1.  在**cloudstreetmarket-webapp**中，`DefaultController`和`InfoTagController`现在都继承自`CloudstreetWebAppWCI`：

```java
public class InfoTagController extends CloudstreetWebAppWCI {
...
}
public class DefaultController extends CloudstreetWebAppWCI {
...
}
```

1.  在**cloudstreetmarket-webapp**中，`dispatcher-context.xml`上下文文件注册了拦截器：

```java
<mvc:interceptors>
  <bean 	class="edu.zc...controllers.CloudstreetWebAppWCI">
    <property name="cacheMappings">
      <props>
        <prop key="/**/*.js">86400</prop>
        <prop key="/**/*.css">86400</prop>
        <prop key="/**/*.png">86400</prop>
        <prop key="/**/*.jpg">86400</prop>
      </props>
    </property>
  </bean> 
</mvc:interceptors>
```

1.  在**cloudstreetmarket-api**的`dispatcher-context.xml`中，另一个拦截器也已经注册：

```java
  <mvc:interceptors>
    <bean class="edu.zc...controllers.CloudstreetApiWCI"/>
  </mvc:interceptors>
```

1.  最后，在`dispatcher-context.xml`中，`RequestMappingHandlerAdapter` bean 已经设置了`synchronizeOnSession`属性：

```java
<bean class="org.sfw...annotation.RequestMappingHandlerAdapter">
    <property name="synchronizeOnSession" value="true"/>
    </bean>
```

## 它是如何工作的...

在每个 web 模块中，我们都为控制器创建了一个超类。例如，在**cloudstreetmarket-webapp**模块中，`InfoTagController`和`DefaultController`现在都继承自`CloudstreetWebAppWCI`超类。

### 控制器的常见行为

除了`WebContentInterceptor`的功能，如果它们与配置（应用程序或业务）相关，共享公共逻辑和属性是一个很好的做法；这样可以避免创建另一个服务层。我们将在进一步的实现中看到，这是一个定义用户上下文的好地方。

通过其`WebContentGenerator`超类，`WebContentInterceptor`提供了有用的请求和会话管理工具，我们现在将介绍。作为拦截器，它必须以声明方式注册。这就是为什么我们在上下文文件中添加了两个`<mvc:interceptors>`条目的原因。

### 全局会话控制

一个`WebContentInterceptor`，处理请求提供了控制应用程序如何与 HTTP 会话交互的能力。

#### 需要会话

`WebContentInterceptor`通过`WebContentGenerator`提供了`setRequireSession(boolean)`方法。这允许定义处理请求时是否需要会话。

如果请求没有绑定到会话（例如，会话已过期），控制器将抛出`SessionRequiredException`方法。在这种情况下，最好定义一个全局的`ExceptionHandler`。我们将在构建 REST API 时设置全局异常映射器。默认情况下，不需要会话。

#### 同步会话

另一个有趣的特性是我们在`RequestMappingHandlerAdapter`定义中将`synchronizeOnSession`属性设置为 true。当设置为 true 时，会话对象被序列化，并且在同步块中进行访问。这允许对相同会话进行并发访问，并避免在使用多个浏览器窗口或选项卡时有时会发生的问题。

### 缓存头管理

我们在`CloudstreetWebAppWCI`和`CloudstreetApiWCI`的构造函数中使用了`setCacheSeconds(int)`方法；`WebContentInterceptor`与`WebContentGenerator`可以管理与缓存相关的一些 HTTP 响应头。

设置为零，会在响应中添加额外的头，如 Pragma、Expires、Cache-control 等。

我们还在配置级别为静态文件定义了自定义缓存：

```java
<props>
  <prop key="/**/*.js">86400</prop>
  <prop key="/**/*.css">86400</prop>
  <prop key="/**/*.png">86400</prop>
  <prop key="/**/*.jpg">86400</prop>
</props>
```

我们所有的静态资源都是以这种方式缓存的，有效期为 24 小时，这要归功于原生的`WebContentInterceptor.preHandle`方法。

### HTTP 方法支持

我们还为 HTTP 方法定义了高级限制。可以通过控制器级别的`@RequestMapping`方法属性进行缩小。访问不允许的方法将导致`405 HTTP 错误：方法不受支持`。

### 高级拦截器

在`dispatcher-context.xml`中的拦截器注册中，我们没有为拦截器定义操作的路径映射。这是因为默认情况下，Spring 在这种独立的拦截器定义上应用双通配符操作符`/**`。

并不是因为我们让`DefaultController`扩展了一个拦截器，拦截器就会在控制器的`@RequestMapping`路径上起作用。拦截器的注册只是通过配置进行的。如果需要修改覆盖的路径映射，我们可以以以下方式覆盖我们的注册：

```java
  <mvc:interceptors>
    <mvc:interceptor>
    <mvc:mapping path="/**"/>
    <bean class="edu.zc.csm.portal...CloudstreetWebAppWCI">
    <property name="cacheMappings">
      <props>
      <prop key="/**/*.js">86400</prop>
      <prop key="/**/*.css">86400</prop>
      <prop key="/**/*.png">86400</prop>
      <prop key="/**/*.jpg">86400</prop>
      </props>
    </property>
    </bean>
    </mvc:interceptor>
  </mvc:interceptors>
```

我们还重写了`WebContentInterceptor`方法的`preHandle`、`postHandle`和`afterCompletion`。这将允许我们在控制器请求处理之前和之后定义常见的业务相关操作。

### 请求生命周期

在拦截器的整个过程中，每个请求都按照以下生命周期进行处理：

+   准备请求的上下文

+   定位控制器的处理程序

+   执行拦截器的`preHandle`方法

+   调用控制器的处理程序

+   执行拦截器的`postHandle`方法

+   处理异常

+   处理视图

+   执行拦截器的`afterCompletion`方法

为了更好地理解顺序，特别是在发生异常时，以下工作流程非常有用：

![请求生命周期](img/image00836.jpeg)

*参考：Santosh Kumar K.的 Spring 和 Hibernate*

从这个图表中，你可以看到：

+   调用控制器的处理程序，除非其中一个拦截器的`preHandle`方法抛出异常。

+   当控制器的处理程序完成而没有抛出异常，并且没有前面的`postHandler`方法抛出异常时，将调用拦截器的`postHandle`方法。

+   除非前面的`afterCompletion`抛出异常，否则总是调用拦截器的`afterCompletion`。

显然，如果没有注册拦截器，同样的顺序适用，跳过拦截器的步骤。

## 还有更多...

关于`WebContentGenerator`类还有更多要说。

### WebContentGenerator 提供的更多功能

再次强调，`WebContentGenerator`是`WebContentInterceptor`的超类。从其 JavaDoc 页面：[`docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/support/WebContentGenerator.html`](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/support/WebContentGenerator.html) 您可以找到例如以下内容：

+   三个常量（String）`METHOD_GET`，`METHOD_POST`和`METHOD_HEAD`分别指代`GET`，`POST`和`HEAD`的值

+   一些特定于缓存的方法，如`setUseExpiresHeader`，`setUseCacheControlHeader`，`setUseCacheControlNoStore`，`setAlwaysMustRevalidate`和`preventCaching`

此外，通过`WebApplicationObjectSupport`，`WebContentGenerator`提供：

+   通过`getServletContext()`从请求或响应对象中访问`ServletContext`。

+   通过`getTempDir()`从当前 Web 应用程序的临时目录访问，由 Servlet 容器提供。

+   通过`getWebApplicationContext()`访问`WebApplicationContext`。

+   此外，还有一些工具可以设置和初始化`ServletContext`和`WebApplicationContext`，即使这些工具最初是用于 Framework 内部使用的。

## 另请参阅...

我们很快就通过了 Web 缓存。在这个领域有很多定制和标准。此外，Spring MVC 3.1 中还创建了一个新的`RequestMappingHandlerAdapter`。这将有助于理解这一变化。

### Web 缓存

通过这个非常完整的缓存教程了解更多关于 Web 缓存的信息：

[`www.mnot.net/cache_docs`](https://www.mnot.net/cache_docs)

### Spring MVC 3.1 以来的新的@RequestMapping 支持类

我们已经在`dispatcher-context.xml`中使用了`RequestMappingHandlerAdapter`及其 bean 定义。这个 bean 是 Spring MVC 3.1 的一个新特性，取代了以前的`AnnotationMethodHandlerAdapter`。此外，支持类`DefaultAnnotationHandlerMapping`现在已被`RequestMappingHandlerMapping`取代。

我们将在第四章中更深入地了解`RequestMappingHandlerAdapter`，*为无状态架构构建 REST API*。

与此同时，您可以阅读官方的变更说明：

[`docs.spring.io/spring-framework/docs/3.1.x/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-31-vs-30`](http://docs.spring.io/spring-framework/docs/3.1.x/spring-framework-reference/html/mvc.html#mvc-ann-requestmapping-31-vs-30)

# 使用 AngularJS 设计客户端 MVC 模式

本教程解释了安装和配置 AngularJS 来管理单页 Web 应用程序。

## 准备工作

在这个教程中，我们将解释如何摆脱先前在 JSP 中引入的渲染逻辑来构建 DOM。我们现在将依赖 AngularJS 来完成这项工作。

即使我们还没有一个 REST API，我们的前端可以查询，我们暂时会让 JSP 构建所需的 JavaScript 对象，就好像它们是由 API 提供的一样。

AngularJS 是一个开源的 Web 应用程序框架。它支持构建可以直接满足微服务架构要求的单页应用程序。AngularJS 的第一个版本于 2009 年发布。现在由 Google 和开源社区维护。

AngularJS 本身就是一个完整的话题。作为一个框架，它既深又广。试图将其作为一个整体呈现将超出本书的范围，也不太适合我们的方法。

因此，我们将重点介绍 Framework 的细节、特性和特点，以便我们可以利用它们来开发应用程序。

## 如何做...

### 设置 DOM 和创建模块

1.  仍然是之前检出的`v2.x.x`分支，`index.jsp`文件已经添加了一个 Angular 指令到 HTML 标签中：

```java
<HTML ng-app="cloudStreetMarketApp">
```

1.  AngularJS JavaScript 库（来自[`angularjs.org`](https://angularjs.org)的 angular.min.js）已放置在`cloudstreetmarket-webapp/src/main/webapp/js`目录中。

`index.jsp`文件在`landingGraphContainer`周围添加了一个包装器`landingGraphContainerAndTools` div，一个选择框和一个`ng-controller="homeFinancialGraphController"`：

```java
<div id='landingGraphContainer' ng-controller="homeFinancialGraphController">
    <select class="form-control centeredElementBox">
      <option value="${dailyMarketActivity.marketId}"> 
      ${dailyMarketActivity.marketShortName}</option>
    </select> 
  </div>
```

整个 tableMarketPrices div 已经以以下方式重新塑造：

```java
<div id='tableMarketPrices'>
    <script>
      var dailyMarketsActivity = [];
      var market;
    </script>
    <c:forEach var="market" items="${dailyMarketsActivity}">
    <script>
      market = {};
      market.marketShortName = '${market.marketShortName}';
      market.latestValue = (${market.latestValue}).toFixed(2);
      market.latestChange = 	(${market.latestChange}*100).toFixed(2);
      dailyMarketsActivity.push(market);
    </script>
    </c:forEach>
<div>
<table class="table table-hover table-condensed table-bordered table-striped" data-ng-controller='homeFinancialTableController'>
    <thead>
      <tr>
        <th>Index</th>
        <th>Value</th>
        <th>Change</th>
      </tr>
    </thead>
    <tbody>
        <tr data-ng-repeat="value in financialMarkets">
        <td>{{value.marketShortName}}</td>
        <td style="text-	align:right">{{value.latestValue}}</td>
        <td class='{{value.style}}' style="text-align:right">
        <strong>{{value.latestChange}}%</strong>
        </td>
      </tr>
    </tbody>
    </table>
    </div>
</div>	
```

然后，`<div id="divRss3">` div 已经进行了重大的重构：

```java
<div id="divRss3">
  <ul class="feedEkList" data-ng-controller='homeCommunityActivityController'>
    <script>
      var userActivities = [];
      var userActivity;
     </script>
      <c:forEach var="activity" items="${recentUserActivity}">
      <script>
        userActivity = {};
        userActivity.userAction = '${activity.userAction}';
         userActivity.urlProfilePicture = '${activity.urlProfilePicture}';
           userActivity.userName = '${activity.userName}';
           userActivity.urlProfilePicture = 	'${activity.urlProfilePicture}';
        userActivity.date = '<fmt:formatDate ="${activity.date}" pattern="dd/MM/yyyy hh:mm aaa"/>';
        userActivity.userActionPresentTense = '${activity.userAction.presentTense}';
        userActivity.amount = ${activity.amount};
        userActivity.valueShortId = '${activity.valueShortId}';
        userActivity.price = (${activity.price}).toFixed(2);
        userActivities.push(userActivity);
      </script>
       </c:forEach>
    <li data-ng-repeat="value in communityActivities">
    <div class="itemTitle">
    <div class="listUserIco {{value.defaultProfileImage}}">
      <img ng-if="value.urlProfilePicture" src='{{value.urlProfilePicture}}'>
    </div>
    <span class="ico-white {{value.iconDirection}} listActionIco"></span>
      <a href="#">{{value.userName}}</a> 
      {{value.userActionPresentTense}} {{value.amount}} 
      <a href="#">{{value.valueShortId}}</a> at {{value.price}}
      <p class="itemDate">{{value.date}}</p>
      </div>
    </li>
  </ul>
</div>
```

图表生成部分已经消失，现在被替换为：

```java
<script>
  var cloudStreetMarketApp = 
    angular.module('cloudStreetMarketApp', []);
  var tmpYmax = <c:out 
    value="${dailyMarketActivity.maxValue}"/>;
  var tmpYmin = <c:out 	
    value="${dailyMarketActivity.minValue}"/>;
</script>
```

这个图表生成已经外部化在其中一个三个自定义的 JavaScript 文件中，包括声明：

```java
<script src="img/angular.min.js"></script>

<script src="img/home_financial_graph.js"></script>
<script src="img/home_financial_table.js"></script>
<script src="img/home_community_activity.js"></script>
```

接下来我们将看到这三个自定义的 JavaScript 文件。

### 定义模块的组件

1.  如前所述，三个自定义的 JavaScript 文件位于`cloudstreetmarket-webapp/src/main/webapp/js`目录中。

1.  第一个文件`home_financial_graph.js`与图表相关。它创建了一个工厂，其最终作用是拉取和提供数据：

```java
cloudStreetMarketApp.factory("financialDataFactory", function () {
    return {
        getData: function (market) {
          return financial_data;
        },
        getMax: function (market) {
          return tmpYmax;
        },
        getMin: function (market) {
          return tmpYmin;
        }
    }
});
```

同样的文件还创建了一个控制器：

```java
cloudStreetMarketApp.controller('homeFinancialGraphController', function ($scope, financialDataFactory){
  readSelectValue();
  drawGraph();
  $('.form-control').on('change', function (elem) {
    $('#landingGraphContainer').html('');
    readSelectValue()
    drawGraph();
  });
  function readSelectValue(){
  $scope.currentMarket = $('.form-control').val();
  }
  function drawGraph(){
    Morris.Line({
      element: 'landingGraphContainer',
        hideHover: 'auto',
        data:financialDataFactory.getData($scope.currentMarket),
        ymax: financialDataFactory.getMax($scope.currentMarket),
        ymin: financialDataFactory.getMin($scope.currentMarket),
        pointSize: 3,
        hideHover:'always',
        xkey: 'period', xLabels: 'time',
        ykeys: ['index'], postUnits: '',
        parseTime: false, labels: ['Index'],
        resize: true, smooth: false,
        lineColors: ['#A52A2A']
      });
  }
});
```

第二个文件：`home_financial_table.js`与市场概览表相关。就像`home_financial_graph.js`一样，它创建了一个工厂：

```java
cloudStreetMarketApp.factory("financialMarketsFactory", function () {
  var data=[];
    return {
        fetchData: function () {
          return data;
        },
        pull: function () {
        $.each( dailyMarketsActivity, function(index, el ) {
          if(el.latestChange >=0){
            dailyMarketsActivity[index].style='text-success';
          }
          else{
            dailyMarketsActivity[index].style='text-error';
          }
        });
        data = dailyMarketsActivity;
        }
    }
});
```

`home_financial_table.js`文件也有自己的控制器：

```java
cloudStreetMarketApp.controller('homeFinancialTableController', function ($scope, financialMarketsFactory){
   financialMarketsFactory.pull();
   $scope.financialMarkets = financialMarketsFactory.fetchData();
});
```

1.  第三个也是最后一个文件`home_community_activity.js`与社区活动表相关。它定义了一个工厂：

```java
cloudStreetMarketApp.factory("communityFactory", function () {
  var data=[];
    return {
        fetchData: function () {
          return data;
        },
        pull: function () {

        $.each( userActivities, function(index, el ) {
        if(el.userAction =='BUY'){
          userActivities[index].iconDirection='ico-up-arrow actionBuy';
          }
          else{
          userActivities[index].iconDirection='ico-down-arrow actionSell';
        }
        userActivities[index].defaultProfileImage='';
        if(!el.urlProfilePicture){
          userActivities[index].defaultProfileImage='ico-	user';
        }
        userActivities[index].price='$'+el.price;
        });
        data = userActivities;
        }
    }
});
```

以及它的控制器：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', function ($scope, communityFactory){
   communityFactory.pull();
   $scope.communityActivities = communityFactory.fetchData();
});
```

## 它是如何工作的...

为了更好地理解我们的 AngularJS 部署是如何工作的，我们将看到 AngularJS 是如何启动的，以及我们的 Angular 模块（应用程序）是如何启动的。然后，我们将了解 AngularJS 控制器和工厂，最后是实现的 Angular 指令。

### 每个 HTML 文档只能有一个应用程序

当 DOM 加载时，AngularJS 会自动初始化。

### 注意

**文档对象模型**（**DOM**）是与 HTML、XHTML 对象交互的跨平台约定。当浏览器加载网页时，它会创建该页面的文档对象模型。

AngularJS 会查找 DOM 中的`ng-app`声明，以便将模块绑定到 DOM 元素并启动（自动引导）该模块。每个 HTML 文档只能自动引导一个应用程序（或模块）。

我们仍然可以为每个文档定义多个应用程序，并在需要时手动引导它们。但是，AngularJS 社区推动我们将应用程序绑定到 HTML 或 BODY 标记。

#### 模块自动引导

我们的应用程序是自动引导的，因为它在 HTML 标记中被引用：

```java
<HTML ng-app="cloudStreetMarketApp">
```

还有，因为模块已经创建（直接在 HTML 文档的`<script>`元素中）：

```java
var cloudStreetMarketApp= angular.module('cloudStreetMarketApp', []);
```

### 提示

注意模块创建中的空数组；它允许将依赖项注入到模块中。我们将很快详细介绍 AngularJS 依赖注入。

#### 手动模块引导

如前所述，我们可以手动引导应用程序，特别是如果我们想要控制初始化流程，或者如果我们在一个文档中有多个应用程序。代码如下：

```java
angular.element(document).ready(function() {
      angular.bootstrap(document, ['myApp']);
});
```

### AngularJS 控制器

AngularJS 控制器是框架的核心部分。它们监视前端发生的所有数据变化。控制器绑定到 DOM 元素，对应于屏幕的功能和视觉区域。

目前，我们已经为市场图表、市场列表和社区活动订阅定义了三个控制器。我们还需要为菜单和页脚元素定义控制器。

![AngularJS 控制器](img/image00837.jpeg)

DOM 绑定是通过指令的 ng-controller 操作的：

```java
<div ng-controller="homeFinancialGraphController">
  <table data-ng-controller='homeFinancialTableController'>
  <ul data-ng-controller='homeCommunityActivityController'>
```

每个控制器都有一个作用域，这个作用域作为函数参数传递给控制器的声明。我们可以将其作为对象读取和更改：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', function ($scope, communityFactory){
  ...
  $scope.communityActivities = communityFactory.fetchData();
  $scope.example = 123;
}
```

#### 双向 DOM-scope 绑定

作用域与控制器绑定的 DOM 区域同步。AngularJS 管理 DOM 和控制器作用域之间的双向数据绑定。这可能是理解 AngularJS 最重要的特性。

### 提示

AngularJS 模型是控制器的作用域对象。与 Backbone.js 不同，例如，Angular 中没有真正的视图层，因为模型直接反映在 DOM 中。

可以使用`{{...}}`符号在 DOM 中呈现作用域变量的内容。例如，`$scope.example`变量可以在 DOM 中使用`{{example}}`获取。

### AngularJS 指令

指令也是 AngularJS 的一个著名特性。它们提供了直接附加到 DOM 的能力。我们可以创建自己的指令或使用内置的指令。

我们将尽量在本书中讨论尽可能多的指令。目前，我们已经使用了以下指令。

#### ng-repeat

为了迭代`communityActivities`和`financialMarkets`集合，我们在循环中定义一个本地变量名称，并使用`{{...}}`符号单独访问每个项目。 代码如下：

```java
<li data-ng-repeat="value in communityActivities">
  <div class="itemTitle">
    <div class="listUserIco {{value.defaultProfileImage}}">
     <img ng-if="value.urlProfilePicture" src='{{value.urlProfilePicture}}'>
    </div>
    ...
  </div>
</li>
```

#### ng-if

该指令允许根据条件删除、创建或重新创建整个 DOM 元素或 DOM 层次结构。

在下一个示例中，当用户没有自定义配置文件图片时，`{{value.defaultProfileImage}}`变量只会呈现 CSS 类`".ico-user"`（以显示默认的通用配置文件图片）。

当用户有配置文件图片时，`value.urlProfilePicture`变量因此被填充，`ng-if`条件得到满足，并且在 DOM 中创建`<img>`元素。 代码如下：

```java
<div class="listUserIco {{value.defaultProfileImage}}">
  <img ng-if="value.urlProfilePicture" src='{{value.urlProfilePicture}}'>
</div>
```

### AngularJS 工厂

工厂被用来获取新的对象实例。我们已经将工厂用作数据生成器。我们还将把它们用作服务协调员和服务与控制器之间的中间层。服务将从服务器 API 中拉取数据。 代码如下：

```java
cloudStreetMarketApp.factory("communityFactory", function () {
  var data=[];
    return {
        fetchData: function () {
        return data;
        },
        pull: function () {
        $.each( userActivities, function(index, el ) {
          if(el.userAction =='BUY'){
            userActivities[index].iconDirection='ico-up-arrow     actionBuy';
          }
          else{
          userActivities[index].iconDirection='ico-down-arrow actionSell';
          }
          userActivities[index].defaultProfileImage='';
          if(!el.urlProfilePicture){
          userActivities[index].defaultProfileImage='ico-user';
          }
          userActivities[index].price='$'+el.price;
        });
        data = userActivities;
        }
    }
});
```

在这个工厂中，我们定义了两个函数：`pull()`和`fetchData()`来填充和检索数据：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', function ($scope, communityFactory){
   communityFactory.pull();
   $scope.communityActivities = communityFactory.fetchData();
});
```

一旦控制器加载，它将`pull()`和`fetchData()`到`$scope.communityActivities`。这些操作在这种情况下只执行一次。

### 提示

我们的工厂被注入为依赖项到我们的控制器声明中：

cloudStreetMarketApp.controller(`'homeCommunityActivityController'`，function `($scope`，`communityFactory`)

#### 依赖注入

在我们的工厂、控制器和模块定义中，我们使用 AngularJS 依赖注入来处理组件的生命周期和它们的依赖关系。

AngularJS 使用注入器执行配置的注入。有三种注释依赖的方式使它们符合注入的条件：

+   使用内联数组注释：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', ['$scope', 'communityFactory', function ($scope, 
communityFactory){
   communityFactory.pull();
   $scope.communityActivities = communityFactory.fetchData();
}]);
```

+   使用`$inject`属性注释：

```java
var homeCommunityActivityController = function ($scope, 
communityFactory){
   communityFactory.pull();
   $scope.communityActivities = communityFactory.fetchData();
}
homeCommunityActivityController.$inject = ['$scope', 'communityFactory'];
cloudStreetMarketApp.controller('homeCommunityActivityController', homeCommunityActivityController);
```

+   使用函数参数名称的隐式注释模式：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', function ($scope, communityFactory){
    communityFactory.pull();
    $scope.communityActivities = communityFactory.fetchData();
});
```

虽然我们主要使用了隐式注释样式和内联数组注释样式，但我们必须强调隐式注释依赖注入在使用 JavaScript 缩小时将无法工作。

## 还有更多...

正如你可能想象的那样，这是对 AngularJS 的一个快速介绍。当我们的应用程序有一个 REST API 和更多功能时，我们将在现场发现更多关于它的内容。

AngularJS 变得非常流行，一个活跃的社区正在支持它。它的核心思想和实现，基于显式的 DOM，提供了一种与应用程序联系的激进和简化的方式。

文档非常详细：[`docs.angularjs.org`](https://docs.angularjs.org)。

网络上有大量的教程和视频：

+   [`www.w3schools.com/angular`](http://www.w3schools.com/angular)

+   [`tutorials.jenkov.com/angularjs`](http://tutorials.jenkov.com/angularjs)

+   [`egghead.io`](https://egghead.io)

# 第三章。使用 Java 持久性和实体

在本章中，我们将开发以下配方：

+   在 Spring 中配置**Java 持久性 API**（**JPA**）

+   定义有用的 EJB3 实体和关系

+   利用 JPA 和 Spring Data JPA

# 介绍

**Java 持久化 API**（**JPA**）是一个规范，从 2006 年（JPA 1.0）到 2013 年（JPA 2.1）由一组各种专家发布了不同版本。从历史上看，它是 EJB 3.0 规范的三个部分之一，它随 JEE5 一起出现。

JPA 不仅仅是**企业 JavaBean**（**EJB**）的升级，它在很大程度上是一次完全的重新设计。当时，领先的对象关系映射解决方案提供商（如 Hibernate）和 J2EE 应用服务器提供商（如 WebSphere，JBoss）都参与其中，全局结果无疑更简单。所有类型的 EJB（有状态的，无状态的和实体）现在都是简单的**普通的旧 Java 对象**（**POJOs**），它们被特定的元数据丰富，这些元数据以注解的形式呈现。

## 实体的好处

实体在 EJB3 模型中扮演着关键角色。作为简单的 POJO，它们可以在应用程序的每一层中使用。

理想情况下，一个实体代表着业务领域内可识别的功能单元。通常是使一个实体代表数据库表行。作为简单的 POJO，实体可以依赖继承（IS-A 关系）并且可以有属性（HAS-A 关系），就像数据库模式通常描述的那样。通过这些关系，实体与其他实体建立连接。这些连接用`@Annotations`描述，这些注解构成了实体的元数据。

实体必须被视为数据库表行的应用程序等价元素。JPA 允许操作这个元素及其整个生态系统作为 Java 对象层次结构，并将其持久化为这样的对象。

实体已经带来了对持久化层的惊人革新（通过减少需要维护的硬编码 SQL 查询的数量），以及对服务和转换层的简化。能够通过所有层级（甚至在视图中使用），它们极大地驱动了应用程序中使用的领域特定名称和概念（方法，类和属性）。它们间接地专注于基本要素，并在应用程序概念和数据库概念之间强加一致性。

从一开始就拥有一个坚实而深思熟虑的模式显然是一个加分项。

### 注意

JPA 在 UI 应用程序上带来了惊人的性能和可维护性结果。然而，如果用于执行批处理或大量数据库操作，它可能并不总是符合性能期望。有时候，考虑直接使用 JDBC 访问可能更明智。

## 实体管理器及其持久化上下文

我们已经看到实体可以与其他实体有关系。为了我们能够对实体进行操作（从数据库中读取，更新，删除和持久化），有一个后台 API 生成 SQL 查询的准备工作。这个 API 在持久化提供者（Hibernate，Toplink 等）中被称为 EntityManager。一旦它为应用程序加载了对象，我们就可以信任它来管理其生命周期。

在继续之前，我们需要回顾一下与 EntityManager 相关的一些概念。一旦 EntityManager 从数据库读取（显式或隐式）获取了实体的实例，该实体就被管理。JPA 持久化上下文由整个受管理实体集的概念聚合形成。持久化上下文始终只携带一个实体的实例，通过其标识符（`@Id`或唯一 ID 类）进行区分。

如果由于某种原因，一个实体没有被管理，那么它被称为脱管（即脱离持久化上下文）。

# 在 Spring 中配置 Java 持久化 API

现在我们已经介绍了 JPA，它的作用以及使用实体的好处，我们现在可以专注于如何配置我们的 Spring 应用程序来处理它们。

## 准备工作

正如我们之前所说，JPA 是一个规范。选择持久性提供程序（Hibernate、OpenJPA、TopLink 等）或应用程序的数据库提供程序不会成为承诺，只要它们符合标准。

我们将看到，在 Spring 中，我们的 JPA 配置是通过定义两个 bean 来完成的：**dataSource**和**entityManagerFactory**。然后，可选的`Spring Data JPA`库提供了一个`JPA`存储库抽象，能够令一些数据库操作出人意料地简化。

## 如何做...

1.  从 Eclipse 的**Git Perspective**中，检出`v3.x.x`分支的最新版本。

1.  如前所介绍的，我们已经在 Spring 配置文件（核心模块中的`csmcore-config.xml`）中添加了一些 bean：

```java
<jpa:repositories base-package="edu.zc.csm.core.daos" />
<bean id="dataSource" class="org.sfw.jdbc.datasource.DriverManagerDataSource>
  <property name="driverClassName">
  <value>org.hsqldb.jdbcDriver</value>
  </property>
  <property name="url">
  <value>jdbc:hsqldb:mem:csm</value>
  </property>
  <property name="username">
  <value>sa</value>
  </property>
</bean>

<bean id="entityManagerFactory" class="org.sfw.orm.jpa.LocalContainerEntityManagerFactoryBean">
      <property name="persistenceUnitName" value="jpaData"/>
      <property name="dataSource" ref="dataSource" />
      <property name="jpaVendorAdapter">
      <beanclass="org.sfw.orm.jpa.vendor.HibernateJpaVendorAdapter"/>
      </property>
      <property name="jpaProperties">
      <props>
          <prop key="hibernate.dialect">
            org.hibernate.dialect.HSQLDialect
          </prop>
          <prop key="hibernate.show_sql">true</prop>
          <prop key="hibernate.format_sql">false</prop>
          <prop key="hibernate.hbm2ddl.auto">create-drop</prop>
          <prop key="hibernate.default_schema">public</prop>
      </props>
    </property>
</bean>
```

1.  最后，以下依赖项已添加到父项目和核心项目中：

+   `org.springframework.data:spring-data-jpa` (1.0.2.RELEASE)

+   `org.hibernate.javax.persistence:hibernate-jpa-2.0-api` (1.0.1.Final)

+   `org.hibernate:hibernate-core` (4.1.5.SP1)

添加此依赖项会导致 Maven 强制执行插件与`jboss-logging`引发版本冲突。这就是为什么 jboss-logging 已从这个第三方库中排除，并作为自己的依赖项引用的原因：

+   `org.hibernate:hibernate-entitymanager` (4.1.5.SP1)

`jboss-logging`也已从这个第三方库中排除，因为它现在被引用为自己的依赖项：

+   `org.jboss.logging:jboss-logging` (3.1.0.CR1)

+   `org.hsqldb:hsqldb` (2.3.2)

+   `org.javassist:javassist` (3.18.2-GA)

+   `org.apache.commons:commons-dbcp2` (2.0.1)

## 它是如何工作的...

我们将审查这三个配置点：**dataSource** bean、**entityManagerFactory** bean 和 Spring Data JPA。

### 由 Spring 管理的 DataSource bean

因为创建数据库连接是耗时的，特别是通过网络层，而且共享和重用已打开的连接或连接池是明智的，**数据源**有责任优化这些连接的使用。它是一个可扩展性指标，也是数据库和应用程序之间高度可配置的接口。

在我们的示例中，Spring 管理数据源就像管理任何其他 bean 一样。数据源可以通过应用程序创建，也可以通过 JNDI 查找远程访问（如果选择放弃连接管理给容器）。在这两种情况下，Spring 将管理配置的 bean，提供我们的应用程序所需的代理。

在我们的示例中，我们正在使用于 2014 年发布的 Apache Common DBCP 2 数据源。

### 提示

在生产环境中，切换到基于 JNDI 的数据源，例如本机 Tomcat JDBC 池，可能是一个好主意。

Tomcat 网站明确建议，在高并发系统上，使用 Tomcat JDBC 池而不是 DBCP1.x 可以显著提高性能。

### EntityManagerFactory bean 及其持久单元

正如其名称所示，`EntityManagerFactory` bean 生成实体管理器。`EntityManagerFactory`的配置条件了实体管理器的行为。

`EntityManagerFactory` bean 的配置反映了一个持久单元的配置。在 Java EE 环境中，可以在`persistence.xml`文件中定义和配置一个或多个持久单元，该文件在应用程序存档中是唯一的。

在 Java SE 环境中（我们的情况），使用 Spring 可以使`persistence.xml`文件的存在变得可选。`EntityManagerFactory` bean 的配置几乎完全覆盖了持久单元的配置。

持久单元的配置，因此`EntityManagerFactory` bean 的配置，可以声明覆盖的实体，也可以扫描包以找到它们。

### 注意

持久性单元可以被视为水平扩展生态系统中的一个子区域。产品可以被分解为每个功能区域的 war（web 存档）。功能区域可以用持久性单元限定的一组实体来表示。

主要的重点是避免创建与不同持久性单元重叠的实体。

### Spring Data JPA 配置

我们将使用 Spring Data JPA 项目中的一些非常有用的工具。这些工具旨在简化持久性层的开发（和维护）。最有趣的工具可能是存储库抽象。您将看到，为一些数据库查询提供实现可能是可选的。如果它们的声明符合标准，存储库接口的实现将在运行时从方法签名中生成。

例如，Spring 将推断以下方法`signature`的实现（如果`User`实体具有`String userName`字段）：

```java
List<User> findByUserName(String username);

```

Spring Data JPA 上我们的 bean 配置的更详细的例子可能是以下内容：

```java
<jpa:repositories base-package="edu.zipcloud.cloudstreetmarket.core.daos" 
    entity-manager-factory-ref="entityManagerFactory"
    transaction-manager-ref="transactionManager"/>
```

正如您所看到的，Spring Data JPA 包含一个自定义命名空间，允许我们定义以下存储库 bean。可以按照以下方式配置此命名空间：

+   在这个命名空间中提供`base-package`属性是强制性的，以限制 Spring Data repositories 的查找。

+   提供`entity-manager-factory-ref`属性是可选的，如果在`ApplicationContext`中只配置了一个`EntityManagerFactory` bean。它明确地连接`EntityManagerFactory`，用于检测到的 repositories。

+   如果在`ApplicationContext`中只配置了一个`PlatformTransactionManager` bean，提供`transaction-manager-ref`属性也是可选的。它明确地连接`PlatformTransactionManager`，用于检测到的 repositories。

有关此配置的更多详细信息，请访问项目网站：

[`docs.spring.io/spring-data/jpa/docs/1.4.3.RELEASE/reference/html/jpa.repositories.html`](http://docs.spring.io/spring-data/jpa/docs/1.4.3.RELEASE/reference/html/jpa.repositories.html)。

## 另请参阅

+   **HikariCP DataSource**：HikariCP（从其 BoneCP 祖先）是一个开源的 Apache v2 许可项目。它似乎在速度和可靠性方面表现比任何其他数据源都要好。在选择数据源时，现在可能应该考虑这个产品。有关更多信息，请参阅[`brettwooldridge.github.io/HikariCP`](https://brettwooldridge.github.io/HikariCP)。

# 定义有用的 EJB3 实体和关系

这个主题很重要，因为良好设计的映射可以防止错误，节省大量时间，并对性能产生重大影响。

## 准备工作

在本节中，我们将介绍大部分我们应用程序所需的实体。这里选择了一些实现技术（从继承类型到关系案例），并且为了示例目的进行了突出显示。

*它是如何工作的…*部分将解释为什么以及如何定义它们的方式，以及是什么思想驱使我们朝着我们所做的实体定义的方向前进。

## 如何做…

以下步骤将帮助您在应用程序中创建实体：

1.  这个配方的所有更改都位于新包`edu.zipcloud.cloudstreetmarket.core.entities`中。首先，按照这里所示创建了三个简单的实体：

+   `User`实体：

```java
  @Entity
  @Table(name="user")
  public class User implements Serializable{
    private static final long serialVersionUID = 1990856213905768044L;
    @Id
    @Column(nullable = false)
    private String loginName;
    private String password;
    private String profileImg;

  @OneToMany(mappedBy="user", cascade = {CascadeType.ALL}, fetch = FetchType.LAZY)
  @OrderBy("id desc")
  private Set<Transaction> transactions = new LinkedHashSet< >();
  ...
  }
```

+   `Transaction`实体：

```java
  @Entity
  @Table(name="transaction")
  public class Transaction implements Serializable{
    private static final long serialVersionUID = -6433721069248439324L;
    @Id
    @GeneratedValue
    private int id;

    @ManyToOne(fetch = FetchType.EAGER)
    @JoinColumn(name = "user_name")
    private User user;

    @Enumerated(EnumType.STRING)
    private Action type;

    @OneToOne(fetch = FetchType.EAGER)
    @JoinColumn(name = "stock_quote_id")
    private StockQuote quote;
    private int quantity;
  ...
  }
```

+   还有`Market`实体：

```java
  @Entity
  @Table(name="market")
  public class Market implements Serializable {
    private static final long serialVersionUID = -6433721069248439324L;
    @Id
  private String id;
  private String name;

  @OneToMany(mappedBy = "market", cascade = { CascadeType.ALL }, fetch = FetchType.EAGER)
  private Set<Index> indices = new LinkedHashSet<>();
  ...
  }
```

1.  然后，我们创建了一些更复杂的实体类型，比如抽象的`Historic`实体：

```java
@Entity
@Inheritance(strategy = InheritanceType.SINGLE_TABLE)
@DiscriminatorColumn(name = "historic_type")
@Table(name="historic")
public abstract class Historic {

  private static final long serialVersionUID = -802306391915956578L;

  @Id
  @GeneratedValue
  private int id;

  private double open;

  private double high;

  private double low;

  private double close;

  private double volume;

  @Column(name="adj_close")
  private double adjClose;

  @Column(name="change_percent")
  private double changePercent;

  @Temporal(TemporalType.TIMESTAMP)
  @Column(name="from_date")
  private Date fromDate;

  @Temporal(TemporalType.TIMESTAMP)
  @Column(name="to_date")
  private Date toDate;

  @Enumerated(EnumType.STRING)
  @Column(name="interval")
private QuotesInterval interval;
...
  }
```

我们还创建了两个 Historic 子类型，`HistoricalIndex`和`HistoricalStock`：

```java
  @Entity
  @DiscriminatorValue("idx")
  public class HistoricalIndex extends Historic implements Serializable {

  private static final long serialVersionUID = -802306391915956578L;

  @ManyToOne(fetch = FetchType.EAGER)
  @JoinColumn(name = "index_code")
  private Index index;
...
}
@Entity
@DiscriminatorValue("stk")
public class HistoricalStock extends Historic implements Serializable {

  private static final long serialVersionUID = -802306391915956578L;

  @ManyToOne(fetch = FetchType.LAZY)
  @JoinColumn(name = "stock_code")
  private StockProduct stock;

  private double bid;
  private double ask;
  ...
    }
```

1.  然后，我们还创建了带有其 StockProduct 子类型的`Product`实体：

```java
    @Entity
    @Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
    public abstract class Product {
      private static final long serialVersionUID = -    802306391915956578L;
      @Id
      private String code;
      private String name;
      ...
    }

    @Entity
    @Table(name="stock")
    public class StockProduct extends Product implements Serializable{
      private static final long serialVersionUID = 1620238240796817290L;
      private String currency;
      @ManyToOne(fetch = FetchType.EAGER)
      @JoinColumn(name = "market_id")
      private Market market;
      ...
    }
```

1.  实际上，在金融世界中，指数（标普 500 或纳斯达克）不能直接购买；因此，指数没有被视为产品：

```java
@Entity
@Table(name="index_value")
public class Index implements Serializable{
  private static final long serialVersionUID = -2919348303931939346L;
  @Id
  private String code;
  private String name;

  @ManyToOne(fetch = FetchType.EAGER)
  @JoinColumn(name = "market_id", nullable=true)
  private Market market;

  @ManyToMany(fetch = FetchType.LAZY)
  @JoinTable(name = "stock_indices", joinColumns={@JoinColumn(name = "index_code")}, inverseJoinColumns={@JoinColumn(name ="stock_code")})
  private Set<StockProduct> stocks = new LinkedHashSet<>();
  ...
}
```

1.  最后，具有两个子类型`StockQuote`和`IndexQuote`的`Quote`抽象实体已经创建（指数不是产品，但我们仍然可以从中获得即时快照，并且稍后将调用 Yahoo!财务数据提供商来获取这些即时报价）：

```java
@Entity
@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
public abstract class Quote {
  @Id
  @GeneratedValue(strategy = GenerationType.TABLE)
  protected Integer id;
  private Date date;
  private double open;

  @Column(name = "previous_close")
  private double previousClose;
  private double last;
  ...
}

@Entity
@Table(name="stock_quote")
public class StockQuote extends Quote implements Serializable{
  private static final long serialVersionUID = -8175317254623555447L;
  @ManyToOne(fetch = FetchType.EAGER)
  @JoinColumn(name = "stock_code")
  private StockProduct stock;
  private double bid;
  private double ask;
  ...
}

@Entity
@Table(name="index_quote")
public class IndexQuote extends Quote implements Serializable{
  private static final long serialVersionUID = -8175317254623555447L;

  @ManyToOne(fetch = FetchType.EAGER)
  @JoinColumn(name = "index_code")
  private Index index;
  ...
}
```

## 工作原理...

我们将介绍一些基本和更高级的概念，这些概念我们用来构建我们的关系映射。

### 实体要求

要被 API 视为实体，实体需要满足以下条件：

+   它必须在类型级别上用`@Entity`注解进行注释。

+   它需要具有已定义的**标识符**，可以是基本类型或复杂类型。在大多数情况下，基本标识符就足够了（在特定实体字段上的`@Id`注解）。

+   它必须被定义为 public 并且不能声明为 final。

+   它需要有一个默认构造函数（隐式或非隐式）。

### 映射模式

数据库和 Java 对象都有特定的概念。实体的元数据注解以及默认配置描述了关系映射。

#### 映射表

实体类映射一个表。在类型级别上不指定`@Table(name="xxx")`注解将实体类映射到以实体名称命名的表（这是默认命名）。

### 注意

Java 的类命名标准是驼峰式命名，首字母大写。这种命名方案实际上并不符合数据库表命名标准。因此，经常使用`@Table`注解。

`@Table`注解还具有一个可选的`schema`属性，允许我们在 SQL 查询中将表绑定到模式（例如`public.user.ID`）。这个`schema`属性将覆盖默认的模式 JPA 属性，可以在持久性单元上定义。

#### 映射列

与表名一样，将字段映射到列名是使用`@Column(name="xxx")`注解指定的。同样，这个注解是可选的，不指定将使映射回退到默认命名方案，即字段的大小写名称（在单词的情况下，这通常是一个不错的选择）。

实体类的字段不能定义为 public。还要记住，几乎可以持久化所有标准的 Java 类型（原始类型、包装器、字符串、字节或字符数组和枚举）以及大型数值类型，如`BigDecimals`或`BigIntegers`，还有 JDBC 时间类型（`java.sql.Date`、`java.sql.TimeStamp`）甚至可序列化对象。

#### 注释字段或 getter

实体的字段（如果未标记为`@Transient`）对应于数据库行每列将具有的值。还可以从 getter 中定义列映射（而不一定要有相应的字段）。

`@Id`注解定义了实体标识符。同时，在字段或 getter 上定义这个`@Id`注解会定义表列是应该由字段还是 getter 映射的。

当使用 getter 访问模式时，如果未指定`@Column`注解，则列名的默认命名方案使用 JavaBeans 属性命名标准（例如，`getUser()` getter 对应于`user`列）。

#### 映射主键

正如我们已经看到的，`@Id`注解定义了实体的标识符。持久性上下文将始终管理具有单个标识符的实体的不超过一个实例。

`@Id`注解在实体类上必须映射表的持久标识符，即主键。

#### 标识符生成

`@GeneratedValue`注解允许从 JPA 级别生成 ID。在对象持久化之前，这个值可能不会被填充。

`@GeneratedValue`注解具有`strategy`属性，用于配置生成方法（例如，依赖于现有的数据库序列）。

### 定义继承

我们已经为“产品”、“历史”和“报价”的子类型定义了实体继承。当两个实体足够接近以被分组为单一概念，并且如果它们实际上可以与应用程序中的父实体关联，那么值得使用 JPA 继承。

根据特定数据的持久化策略，可以考虑不同的存储选项来进行继承映射。

JPA 允许我们从不同的策略中配置继承模型。

#### 单表策略

这种策略期望或创建一个带有模式上的鉴别器字段的大表。这个表包含父实体字段；这些字段对所有子实体都是通用的。它还包含所有子实体类的字段。因此，如果一个实体对应于一个子类型或另一个子类型，它将填充特定字段并留下其他字段为空。

以下表格代表了具有其`HISTORIC_TYPE`鉴别器的`Historic`表：

![单表策略](img/image00838.jpeg)

#### 表格每类策略

这种策略针对具体实体使用特定的表。这里没有涉及鉴别器，只是针对子类型的特定表。这些表包含通用和特定字段。

例如，我们已经为“报价”实体及其具体的“股票报价”和“指数报价”实体实施了这种策略：

![表格每类策略](img/image00839.jpeg)

### 定义关系

实体具有反映其类属性中的数据库外键和表与表之间关系的能力。

在应用程序端，由于这些关系是由实体管理器透明地构建的，因此可以绕过大量的开发工作。

#### 实体之间的关系是如何选择的

在讨论实体之间的关系之前，有必要了解我们计划在*cloudstreet-market*应用程序中做什么。

正如在第一章中介绍的，企业 Spring 应用程序的设置例程，我们将从开放其 API 的提供者（实际上是 Yahoo!）那里获取财务数据。为此，始终需要牢记每个 IP 或经过身份验证的用户的调用频率方面的限制。我们的应用程序还将在其内部拥有社区，其中将共享财务数据。对于财务数据提供者来说，当谈论给定股票时，股票的历史视图和股票的即时报价是两个不同的概念。我们必须处理这两个概念来构建我们自己的数据集。

在我们的应用程序中，用户将能够通过执行“交易”来购买和出售“产品”（股票、基金、期权等）：

+   首先，让我们考虑用户/交易关系的以下截图：![实体之间的关系是如何选择的](img/image00840.jpeg)

+   一个“用户”实体可以有多个“交易”实体。

### 注意

在用户类中，`@OneToMany`关系注解的第二部分（`Many`元素）驱动我们正在创建的属性类型。将`Many`指定为第二部分声明了起源实体（`User`）可以有多个目标实体（`Transactions`）。这些目标将必须包含在一个集合类型中。如果起源实体不能有多个目标，则关系的第二部分必须是`One`。

+   一个“交易”只能有一个“用户”实体。

### 注意

在用户类中，`@OneToMany`关系的第一部分（`@One`元素）是目标实体中定义的关系注解的第二部分（如果已定义）。必须知道目标实体是否可以有多个起源，以便完成起源中的注解。

+   然后我们可以推断出两个注解：`User`中的`@OneToMany`和`Transactions`中的`@ManyToOne`。

+   如果我们不是`@ManyToMany`关系的情况，我们谈论的是单向关系。从数据库的角度来看，这意味着两个表中的一个具有指向另一个表的连接列。在 JPA 中，具有这个连接列的表是关系的**所有者**。

### 提示

关系的所有者实体必须在关系上指定一个`@JoinColumn`注解。不是所有者的实体必须为其关系注解提供一个`mappedBy`属性，该属性指向相对实体中的相应 Java 字段名称。

+   这可以解释`Transaction`中的关系：

```java
@ManyToOne(fetch = FetchType.EAGER)
@JoinColumn(name = "user_name")
private User user;
```

`user_name`列预期（或自动添加）在交易表中。我们将在*还有更多……部分*中讨论 fetch 类型。

+   `User`实体中的关系定义如下：

```java
  @OneToMany(mappedBy="user", cascade ={CascadeType.ALL}, fetch = FetchType.LAZY)
  @OrderBy("id desc")
  private Set<Transaction> transactions = new LinkedHashSet<>();
```

### 提示

`@OrderBy`注解告诉 JPA 实现在其 SQL 查询中添加一个`ORDER BY`子句。

一个`Index`实体有一个`Market`实体。我们决定市场是地理区域（欧洲、美国、亚洲等）。一个市场有几个具体的指数。

这看起来又像是`@OneToMany`/`@ManyToOne`关系。关系的所有者是`Index`实体，因为我们期望在`Index`表中有一个`Market`列（而不是`Market`表中的`Index`列）。

在具体的`Product`（如`StockProduct`）和`Market`实体之间，情况与之前类似，只是因为在应用程序中直接从`Market`检索股票看起来不是必需的，关系没有在`Market`实体方面声明。我们只保留了所有者方面。

关于具体的`Quotes`实体（如`StockQuote`）和具体的`Products`实体（如`StockProduct`），一个报价将有一个产品。如果我们有兴趣从`Product`实体中检索`Quote`，一个产品将有多个报价。关系的所有者是具体的`Quote`实体。

对于`IndexQuote`和`Index`，情况与之前的点相同。

在`Index`和`StockProduct`之间，实际上，指数（标普 500、纳斯达克等）有组成部分，组成部分的值之和构成指数值。因此，一个`Index`实体有几个潜在的`StockProduct`实体。同样，一个`StockProduct`可以属于几个`Indices`。这看起来像是一个双向关系。我们在这里展示了`Index`方面：

```java
@ManyToMany(fetch = FetchType.LAZY)
@JoinTable(name = "stock_indices", joinColumns={@JoinColumn(name = "index_code")}, inverseJoinColumns={@JoinColumn(name ="stock_code")})
private Set<StockProduct> stocks = new LinkedHashSet<>();
```

这个关系指定了一个额外的连接表（JPA 预期或生成的）。基本上是一个具有两个连接列指向各自实体的`@Ids`字段的表。

## 还有更多...

我们将讨论两个尚未解释的元数据属性：`FetchType`属性和`Cascade`属性。

### FetchType 属性

我们已经看到关系注解`@OneToOne`、`@OneToMany`和`@ManyToMany`可以在 fetch 属性中指定，可以是`FetchType.EAGER`或`FetchType.LAZY`。

当选择`FetchType.EAGER`属性时，当实体被管理时，关系会被`entityManager`自动加载。JPA 执行的 SQL 查询总量显著增加，特别是因为一些可能每次都不需要的相关实体仍然被加载。如果我们有两个、三个或更多级别的实体绑定到根实体，我们可能应该考虑将一些字段本地切换到`FetchType.LAZY`。

`FetchType.LAZY`属性指定 JPA 实现在实体加载的 SQL 查询中不填充字段值。当程序明确要求时（例如，在`HistoricalStock`实体的情况下调用`getStock()`时），JPA 实现会生成额外的异步 SQL 查询来填充`LAZY`字段。在使用 Hibernate 作为实现时，`FetchType.LAZY`被视为关系的默认获取类型。

重要的是要考虑减轻关系加载的负担，特别是在集合上。

### 级联属性

在关系注解中要提到的另一个属性是 Cascade 属性。这个属性可以取值`CascadeType.DETACH`、`CascadeType.MERGE`、`CascadeType.PERSIST`、`CascadeType.REFRESH`、`CascadeType.REMOVE`和`CascadeType.ALL`。

这个属性指定了 JPA 实现在被要求对主实体执行操作（如持久化、更新、删除、查找等）时应该如何处理相关实体。这是一个可选属性，通常默认为**不进行级联操作**。

## 另请参阅

有第三种定义实体继承的策略：

+   **联接表继承策略**：我们还没有实现它，但这个策略与表对应的类策略有些相似。它与之不同之处在于，JPA 不会在具体的表中重复父实体字段（列），而是创建或期望一个只包含父实体列的额外表，并通过这个表透明地管理连接。

# 利用 JPA 和 Spring Data JPA

在本节中，我们将为我们的应用程序连接所需的业务逻辑。

因为我们已经为 JPA 和 Spring Data JPA 设置了配置，并且已经定义了我们的实体及其关系，现在我们可以使用这个模型来节省时间和精力。

## 如何做...

以下步骤将指导您完成这些更改：

1.  在`edu.zipcloud.cloudstreetmarket.core.daos`包中，我们可以找到以下两个接口：

```java
public interface HistoricalIndexRepository {
  Iterable<HistoricalIndex> findIntraDay(String code, Date of);
  Iterable<HistoricalIndex> findLastIntraDay(String code);
  HistoricalIndex findLastHistoric(String code);
}
public interface TransactionRepository {
  Iterable<Transaction> findAll();
  Iterable<Transaction> findByUser(User user);
  Iterable<Transaction> findRecentTransactions(Date from);
  Iterable<Transaction> findRecentTransactions(int nb);
}
```

1.  这两个接口都带有各自的实现。其中两个中的`HistoricalIndexRepositoryImpl`实现定义如下：

```java
@Repository
public class HistoricalIndexRepositoryImpl implements HistoricalIndexRepository{

  @PersistenceContext 
  private EntityManager em;

  @Override
  public Iterable<HistoricalIndex> findIntraDay(String code,Date of){
    TypedQuery<HistoricalIndex> sqlQuery = em.createQuery("from HistoricalIndex h where h.index.code = ? and h.fromDate >= ? and h.toDate <= ? ORDER BY h.toDate asc", HistoricalIndex.class);

    sqlQuery.setParameter(1, code);
    sqlQuery.setParameter(2, DateUtil.getStartOfDay(of));
    sqlQuery.setParameter(3, DateUtil.getEndOfDay(of));

    return sqlQuery.getResultList();
  }

  @Override
  public Iterable<HistoricalIndex> findLastIntraDay(String code) {
    return findIntraDay(code,findLastHistoric(code).getToDate());
  }

  @Override
  public HistoricalIndex findLastHistoric(String code){
     TypedQuery<HistoricalIndex> sqlQuery =  em.createQuery("from HistoricalIndex h where h.index.code = ? ORDER BY h.toDate desc", HistoricalIndex.class);

  sqlQuery.setParameter(1, code);

    return sqlQuery.setMaxResults(1).getSingleResult();
  }
}
```

`TransactionRepositoryImpl`的实现如下：

```java
@Repository
public class TransactionRepositoryImpl implements TransactionRepository{
  @PersistenceContext 
  private EntityManager em;
  @Autowired
  private TransactionRepositoryJpa repo;
  @Override
  public Iterable<Transaction> findByUser(User user) {
    TypedQuery<Transaction> sqlQuery = em.createQuery("from Transaction where user = ?", Transaction.class);
    return sqlQuery.setParameter(1, user).getResultList();
  }
  @Override
  public Iterable<Transaction> findRecentTransactions(Date from) {
    TypedQuery<Transaction> sqlQuery = em.createQuery("from Transaction t where t.quote.date >= ?", Transaction.class);
    return sqlQuery.setParameter(1, from).getResultList();
  }
  @Override
  public Iterable<Transaction> findRecentTransactions(int nb) {
  TypedQuery<Transaction> sqlQuery = em.createQuery("from Transaction t ORDER BY t.quote.date desc", Transaction.class);
    return sqlQuery.setMaxResults(nb).getResultList();
  }
  @Override
  public Iterable<Transaction> findAll() {
    return repo.findAll();
  }
}
```

1.  `dao`包中的所有其他接口都没有明确定义的实现。

1.  以下 bean 已经添加到 Spring 配置文件中：

```java
  <jdbc:initialize-database data-source="dataSource">
      <jdbc:script location="classpath:/META-INF/db/init.sql"/>
  </jdbc:initialize-database>
```

1.  这个最后的配置允许应用在启动时执行创建的`init.sql`文件。

1.  您会注意到`cloudstreetmarket-core`模块已经在其`pom.xml`文件中添加了一个依赖项，即我们创建的`zipcloud-core`的`DateUtil`类。

1.  为了替换我们在第二章中创建的两个虚拟实现，*使用 Spring MVC 设计微服务架构*，已经创建了`CommunityServiceImpl`和`MarketServiceImpl`的实现。

### 注意

我们使用`@Autowired`注解在这些实现中注入了存储库依赖。

另外，我们使用声明的`value`标识符为这两个实现添加了 Spring `@Service`注解：

```java
@Service(value="marketServiceImpl")
@Service(value="communityServiceImpl")
```

1.  在`cloudstreetmarket-webapp`模块中，`DefaultController`已经在其`@Autowired`字段中修改为针对这些新实现，而不再是虚拟的。这是通过在`@Autowired`字段上指定`@Qualifier`注解来实现的。

1.  启动服务器并调用主页 URL，`http://localhost:8080/portal/index`，应该在控制台中记录一些 SQL 查询：![如何做...](img/image00841.jpeg)

另外，**欢迎**页面应该保持不变。

## 它是如何工作的...

让我们通过以下几个部分来分解这个配方。

### 注入 EntityManager 实例

我们在本章的第一个配方中看到，`entityManagerFactory` bean 的配置反映了持久化单元的配置。

由容器历史创建的 EntityManagers 需要处理事务（用户或容器管理器事务）。

`@PersistenceContext`注解是一个 JPA 注解。它允许我们注入一个由容器管理生命周期的 EntityManager 实例。在我们的情况下，Spring 处理了这个角色。有了 EntityManager，我们可以与持久化上下文交互，获取受管理或分离的实体，并间接地查询数据库。

### 使用 JPQL

使用**Java 持久化查询语言**（**JPQL**）是一种标准化的查询持久化上下文和间接地查询数据库的方式。JPQL 在语法上类似于 SQL，但是操作的是 JPA 管理的实体。

你一定注意到了存储库中的以下查询：

```java

from Transaction where user = ?

```

查询的选择部分是可选的。参数可以注入到查询中，这一步由持久性提供者的实现来管理。这些实现提供了防止 SQL 注入的保护（使用预编译语句）。通过这个例子，看看过滤子实体属性有多实用：

```java

from Transaction t where t.quote.date >= ?

```

在适当的情况下，它避免了声明连接。尽管如此，我们仍然可以声明`JOIN`：

```java

from HistoricalIndex h where h.index.code = ? ORDER BY h.toDate desc

```

一些关键字（如`ORDER`）可以作为 JPQL 的一部分来操作通常在 SQL 中可用的函数。在 JavaEE 6 教程的 JPQL 语法中找到关键字的完整列表：[`docs.oracle.com/javaee/6/tutorial/doc/bnbuf.html`](http://docs.oracle.com/javaee/6/tutorial/doc/bnbuf.html)。

JPQL 受到早期创建的**Hibernate 查询语言**（**HQL**）的启发。

### 使用 Spring Data JPA 减少样板代码

我们在*如何做…*部分讨论了一些我们的存储库接口没有明确定义实现的情况。这是 Spring Data JPA 非常强大的功能。

#### 查询创建

我们的`UserRepository`接口定义如下：

```java
@Repository
public interface UserRepository extends JpaRepository<User, String>{
  User findByUserName(String username);
  User findByUserNameAndPassword(String username, String password);
}
```

我们让它扩展了`JpaRepository`接口，通过通用类型`User`（这个存储库将关联的实体类型）和`String`（用户标识字段的类型）。

通过扩展`JpaRepository`，`UserRepository`从 Spring Data JPA 获得了定义查询方法的能力，只需声明它们的方法签名。我们已经在方法`findByUserName`和`findByUserNameAndPassword`中这样做了。

Spring Data JPA 会在运行时透明地创建我们的`UserRepository`接口的实现。它会根据我们在接口中命名方法的方式推断 JPA 查询。关键字和字段名用于这种推断。

从 Spring Data JPA 文档中找到以下关键字表：

![查询创建](img/image00842.jpeg)

在不指定任何配置的情况下，我们已经默认回到了 JPA 存储库的配置，它会注入我们单一的`EntityManagerFactory` bean 的实例和我们单一的`TransactionManager` bean 的实例。

我们的自定义`TransactionRepositoryImpl`是一个示例，它同时使用自定义的 JPQL 查询和`JpaRepository`实现。正如你可能猜到的那样，在`TransactionRepositoryImpl`中自动装配的`TransactionRepositoryJpa`实现继承了用于保存、删除和查找`Transaction`实体的多个方法。

我们还将使用这些方法提供的有趣的分页功能。我们提取的`findAll()`方法就是其中之一。

#### 持久化实体

Spring Data JPA 还指定了以下内容：

可以通过`CrudRepository.save(…)`方法来保存实体。它将使用底层的 JPA EntityManager 来持久化或合并给定的实体。如果实体尚未持久化，Spring Data JPA 将通过调用`entityManager.persist(…)`方法来保存实体；否则，将调用`entityManager.merge(…)`方法。

这是一个有趣的行为，我们将再次使用它来减少大量样板代码。

## 还有更多...

还有更多可以探索的方面。

### 使用本地 SQL 查询

我们还没有使用原生 SQL 查询，但我们将会使用。了解如何实现它们很重要，因为有时绕过 JPA 层在性能上可能是更好的选择。

以下链接指向 Oracle 网站的一篇文章，与原生 SQL 查询相关，非常有趣。

[`www.oracle.com/technetwork/articles/vasiliev-jpql-087123.html`](http://www.oracle.com/technetwork/articles/vasiliev-jpql-087123.html)

### 交易

我们还没有对我们的存储库实现应用任何特定的事务配置。有关事务的更多详细信息，请参阅第七章，“开发 CRUD 操作和验证”。

## 另请参阅

+   Spring Data 存储库的自定义实现：通过重新定义我们从 TransactionRepositoryJpa 中需要的方法的示例 TransactionRepositoryImpl，我们提出了创建数据存储库的自定义实现的模式。这在某种程度上迫使我们维护一个中间代理。相关的 Spring 文档提出了解决这个问题的不同技术。这种技术在[`docs.spring.io/spring-data/jpa/docs/current/reference/html/#repositories.custom-implementations`](http://docs.spring.io/spring-data/jpa/docs/current/reference/html/#repositories.custom-implementations)上有详细介绍。

# 第四章。为无状态架构构建 REST API

本章将介绍以下配方：

+   绑定请求和编组响应

+   配置内容协商（`json`、`xml`等）

+   添加分页、过滤和排序功能

+   全局处理异常

+   使用 Swagger 文档化和公开 API

# 介绍

在本章中，将实施相当多的变化。实际上，这一章真正加速了我们的应用程序开发。

在深入了解代码之前，我们需要复习一下关于 REST 的一些概念。

## REST 的定义

REST 是一种架构风格。它的名称是表述状态转移的缩写。这个术语是由 HTTP 规范的主要作者之一 Roy Fielding 发明的。REST 架构围绕着一些标记设计：

+   可识别资源：资源定义了领域。资源必须通过 URI 进行标识。这个 URI 必须尽可能清晰地使用资源类别和层次结构。我们的资源将是指数快照、股票快照、历史指数数据、历史股票数据、用户等等。

+   HTTP 作为通信协议：我们使用有限数量的 HTTP 方法（`GET`、`POST`、`PUT`、`DELETE`、`HEAD`和`OPTIONS`）与资源进行交互。

+   资源表示：资源以特定的表示形式呈现。表示通常对应于媒体类型（`application/json`、`application/xml`、`text/html`）和/或文件扩展名（`*.json`、`*.xml`、`*.html`）。

+   无状态对话：服务器不得保留对话的痕迹。禁止使用 HTTP 会话，而是通过资源提供的链接（超媒体）进行导航。客户端身份验证在每个请求中都会重复。

+   可扩展性：无状态设计意味着易于扩展。一个请求可以分派到一个或另一个服务器。这是负载均衡器的作用。

+   超媒体：正如我们刚才提到的，资源带来了链接，这些链接驱动了对话的转换。

## RESTful CloudStreetMarket

从本章开始，所有实现的数据检索现在都使用 AngularJS 通过 REST 处理。我们使用 Angular 路由来完成单页应用程序设计（从服务器加载一次）。还有一些新的服务，支持关于股票和指数的三个新屏幕。

尽管 REST 实现仍然是部分的。我们只实现了数据检索（`GET`）；我们还没有有效的身份验证，超媒体也将在以后介绍。

# 绑定请求和编组响应

这个配方解释了如何配置 Spring MVC 以使 REST 处理程序尽可能与其业务领域集成。我们专注于设计自解释的方法处理程序，外部化类型转换以及抽象响应编组（序列化为特定格式，如`json`，`xml`，`csv`等）。

## 准备工作

我们将审查应用于`cloudstreetmarket-api` webapp 的配置更改，以便从请求参数或 URI 模板变量设置类型转换。

我们将看到如何配置自动编组（用于响应）为`json`。我们将专注于为本章创建的两个非常简单的方法处理程序。

## 如何做...

以下步骤描述了与请求绑定和响应编组配置相关的代码库更改：

1.  在 Eclipse 的**Git Perspective**中，检出分支`v4.x.x`的最新版本。然后在`cloudstreetmarket-parent`模块上运行`maven clean install`命令。要这样做，右键单击模块，选择**Run as...** | **Maven Clean**，然后再次选择**Run as...** | **Maven Install**。之后，选择**Maven Update Project**以将 Eclipse 与 Maven 配置同步。要这样做，右键单击模块，然后选择**Maven** | **Update Project...**。

1.  主要的配置更改在`dispatcher-context.xml`文件中（在**cloudstreetmarket-api**模块中）。已定义`RequestMappingHandlerAdapter` bean 的三个`webBindingInitializer`，`messageConverters`和`customArgumentResolvers`属性：

```java
<bean class="org.sfw.web...
  method.annotation.RequestMappingHandlerAdapter">
  <property name="webBindingInitializer">
    <bean class="org.sfw...
     support.ConfigurableWebBindingInitializer">
      <property name="conversionService" ref="conversionService"/>
    </bean>
    </property>
  <property name="messageConverters">
    <list>
        <ref bean="jsonConverter"/>
      </list>
  </property>
  <property name="customArgumentResolvers">
    <list>
      <bean class="net.kaczmarzyk.spring.data.jpa.web.
      SpecificationArgumentResolver"/>
      <bean	class="org.sfw.data.web.PageableHandlerMethodArgumentResolver">
          <property name="pageParameterName" value="pn"/>
          <property name="sizeParameterName" value="ps"/>
          </bean>
    </list>
  </property>
  <property name="requireSession" value="false"/>
</bean>

<bean id="jsonConverter" class="org.sfw...
    converter.json.MappingJackson2HttpMessageConverter">
    <property name="supportedMediaTypes" value="application/json"/>
  <property name="objectMapper">
    <bean class="com.fasterxml.jackson. databind.ObjectMapper">
      <property name="dateFormat">
     <bean class="java.text.SimpleDateFormat">
       <constructor-arg type="java.lang.String" value="yyyy-MM-dd HH:mm"/>
       </bean>
      </property>
    </bean>
    </property>
</bean>
<bean id="conversionService" class="org.sfw.format.support.FormattingConversionServiceFactoryBean">
  <property name="converters">
    <list>
      <bean class="edu.zc.csm.core. converters.StringToStockProduct"/>
    </list>
  </property>
</bean>
```

1.  以下 Maven 依赖项已添加到父项目（间接添加到核心和 API 项目）中：

```java
      <dependency>
         <groupId>com.fasterxml.jackson.core</groupId>
             <artifactId>jackson-annotations</artifactId>
             <version>2.5.1</version>
       </dependency>
         <dependency>
             <groupId>com.fasterxml.jackson.core</groupId>
             <artifactId>jackson-databind</artifactId>
             <version>2.5.1</version>
         </dependency>
         <dependency>
             <groupId>commons-collections</groupId>
             <artifactId>commons-collections</artifactId>
             <version>3.2</version>
         </dependency>
         <dependency>
             <groupId>net.kaczmarzyk</groupId>
             <artifactId>specification-arg-resolver</artifactId>
             <version>0.4.1</version>
         </dependency>
```

1.  在我们控制器的超类`CloudstreetApiWCI`中，使用`@InitBinder`注解创建了`allowDateBinding`方法：

```java
  private DateFormat df = new SimpleDateFormat("yyyy-MM-dd");

  @InitBinder
  public void allowDateBinding ( WebDataBinder binder ){
    binder.registerCustomEditor( Date.class, new CustomDateEditor( df, true ));
  }
```

1.  所有这些配置使我们能够定义自解释和无逻辑的方法处理程序，例如`IndexController`中的`getHistoIndex()`方法：

```java
  @RequestMapping(value="/{market}/{index}/histo", method=GET)
  public HistoProductDTO getHistoIndex(
    @PathVariable("market") MarketCode market, 
    @PathVariable("index") String indexCode,
    @RequestParam(value="fd",defaultValue="") Date fromDate,
    @RequestParam(value="td",defaultValue="") Date toDate,
    @RequestParam(value="i",defaultValue="MINUTE_30") QuotesInterval interval){
    return marketService.getHistoIndex(indexCode, market, fromDate, toDate, interval);
  }
```

1.  现在部署`cloudstreetmarket-api`模块并重新启动服务器。要这样做，首先在**服务器**选项卡中右键单击 Tomcat 服务器：![操作步骤...](img/image00843.jpeg)

1.  然后从右键菜单中选择**添加和删除...**。在添加和删除...窗口中，确保已设置以下配置，并启动服务器。![操作步骤...](img/image00844.jpeg)

1.  尝试调用 URL `http://localhost:8080/api/indices/EUROPE/^GDAXI/histo.json`。

1.  此 URL 针对所呈现的`getHistoIndex`方法处理程序，并生成以下`json`输出：![操作步骤...](img/image00845.jpeg)

1.  现在让我们看看`StockProductController`。它托管以下方法处理程序：

```java
@RequestMapping(value="/{code}", method=GET)
@ResponseStatus(HttpStatus.OK)
public StockProductOverviewDTO getByCode(
@PathVariable(value="code") StockProduct stock){
  return StockProductOverviewDTO.build(stock);
}
```

### 提示

这里没有对任何服务层进行显式调用。方法处理程序的返回类型是`StockProductOverviewDTO`，这是一个简单的 POJO。响应主体的编组是透明进行的。

1.  在**cloudstreetmarket-core**模块中，必须呈现`StringToStockProduct`转换器，因为它是实现前一步所需的：

```java
@Component
public class StringToStockProduct implements Converter<String, StockProduct> {

@Autowired
private ProductRepository<StockProduct> productRepository;

@Override
public StockProduct convert(String code) {
  StockProduct stock = productRepository.findOne(code);
  if(stock == null){
    throw new NoResultException("No result has been found for the value "+ code +" !");
  }
  return stock;
}
}
```

### 提示

此转换器已在*步骤 2*中注册到`conversionService`。

1.  尝试调用 URL `http://localhost:8080/api/products/stocks/NXT.L.json`。这应该针对所呈现的`getByCode`处理程序，并生成以下`json`响应：![操作步骤...](img/image00846.jpeg)

## 它是如何工作的...

要了解前面的元素如何一起工作，我们必须介绍`RequestMappingHandlerAdapter`的关键作用。

### 一个超级 RequestMappingHandlerAdapter bean

我们在第二章中简要介绍了`RequestMappingHandlerAdapter`，*使用 Spring MVC 设计微服务架构*。这个 bean 实现了高级的`HandlerAdapter`接口，允许自定义 MVC 核心工作流实现。`RequestMappingHandlerAdapter`是框架自带的原生实现。

我们提到`RequestMappingHandlerAdapter`和`RequestMappingHandlerMapping`分别是现在已经弃用的`AnnotationMethodHandlerAdapter`和`DefaultAnnotationHandlerMapping`的两个替代类。

实际上，`RequestMappingHandlerAdapter`为所有方法处理程序提供了更好的集中化。此外，一些新的功能已经为`HandlerInterceptors`和`HandlerExceptionResolver`打开。

### 提示

实际上，在`preHandle`、`postHandle`和`afterCompletion`方法的签名中可以找到的处理程序参数（`WebContentInterceptors`）可以被转换为`HandlerMethod`对象。`HandlerMethod`类型提供了一些有趣的检查方法，比如`getReturnType`、`getMethodAnnotation`、`getMethodParameters`。

此外，关于`RequestMappingHandlerAdapter`和`RequestMappingHandlerMapping`，Spring 文档指定：

|   | *"MVC 命名空间和 MVC Java 配置默认情况下启用了新的支持类，但如果不使用这两者，则必须显式配置。"* |   |
| --- | --- | --- |
|   | --*JavaDoc* |

在我们的 web 应用程序中，我们都使用了`<mvc:annotation-driven/>`元素来特别使用 MVC 命名空间。

这个元素很受欢迎，因为它在一些 web 功能上激活了默认配置功能。然而，在许多情况下，可能仍然期望不同的行为。

在大多数情况下，自定义定义要么在命名空间本身上，要么在`RequestMappingHandlerAdapter`上。

#### @RequestMapping 注解得到了广泛的支持

`RequestMappingHandlerAdapter`的主要作用是为`HandlerMethod`类型的处理程序提供支持和定制。这些处理程序与`@RequestMapping`注解绑定。

|   | *"HandlerMethod 对象封装了有关处理程序方法的信息，包括方法和 bean。提供了对方法参数、方法返回值、方法注解的便捷访问。"* |   |
| --- | --- | --- |
|   | --*JavaDoc* |

`RequestMappingHandlerAdapter`大部分的支持方法都来自于历史悠久的`DefaultAnnotationHandlerMapping`。让我们更仔细地看看特别让我们感兴趣的方法。

##### setMessageConverters

`messageConverters`模板可以通过`setMessageConverters` setter 注册为`List<HttpMessageConverter>`。Spring 将为我们执行将 HTTP 请求体解组成 Java 对象和将 Java 资源组成 HTTP 响应体的编组。

重要的是要记住，框架为主要的媒体类型提供了转换器实现。这些默认情况下与`RequestMappingHandlerAdapter`和`RestTemplate`（在客户端上）注册。

以下表格总结了我们可以利用的原生转换器：

| 提供的实现 | 默认支持的媒体类型 | (默认)行为 |
| --- | --- | --- |
| `StringHttpMessageConverter` | `text/*` | 使用`text/plain`内容类型进行写入。 |
| `FormHttpMessageConverter` | `application/x-www-form-urlencoded` | 表单数据从`MultiValueMap<String, String>`中读取和写入。 |
| `ByteArrayHttpMessageConverter` | `*/*` | 使用`application/octet-stream`内容类型进行写入（可以被覆盖）。 |
| `MarshallingHttpMessageConverter` | `text/xml 和 application/xml` | 需要`org.springframework.oxm`和`Marshaller`/`Unmarshaller`。 |
| `MappingJackson2HttpMessageConverter` | `application/json` | 可以使用 Jackson 注解自定义 JSON 映射。如果需要映射特定类型，必须注入自定义的`ObjectMapper`属性。 |
| `MappingJackson2XmlHttpMessageConverter` | `application/xml` | XML 映射可以使用 JAXB 或 Jackson 注解进行自定义。如果需要映射特定类型，必须将自定义的`XmlMapper`属性注入到`ObjectMapper`属性中。 |
| `SourceHttpMessageConverter` | `text/xml 和 application/xml` | 可以从 HTTP 请求和响应中读取和写入`javax.xml.transform`.`Source`。只支持`DOMSource`、`SAXSource`和`StreamSource`。 |
| `BufferedImageHttpMessageConverter` |   | 可以从 HTTP 请求和响应中读取和写入`java.awt.image.BufferedImage`。 |

请查看以下地址，获取有关使用 Spring 进行远程和 Web 服务的信息：[`docs.spring.io/spring/docs/current/spring-framework-reference/html/remoting.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/remoting.html)。

在我们的应用程序中，我们已经重写了两个本地`MappingJackson2HttpMessageConverter`和`MarshallingHttpMessageConverter`类的定义。

##### setCustomArgumentResolvers

`setCustomArgumentResolvers` setter 为`RequestMappingHandlerAdapter`提供了对自定义参数的支持。如果你还记得第二章中的内容，*使用 Spring MVC 支持响应式设计*，第一个配方谈到了支持参数的注解。当时，我们看到了`@PathVariable`、`@MatrixVariable`、`@RequestBody`、`@RequestParam`等。

所有这些注解都是内置的`ArgumentResolver`。它们被映射到注册的实现，以从不同的来源外部预填充参数。

我们有可能定义自己的注解，并根据所需的业务逻辑预填充我们的方法参数。这些解析器必须实现`HandlerMethodArgumentResolver`接口。

我们的应用程序开发并没有特别需要开发`customArgumentResolver`。但是，我们已经注册了其中两个：

+   `net.kaczmarzyk.spring.data.jpa.web.SpecificationArgumentResolver`：这个解析器是一个第三方库，我们将在本章的第 3 个配方中进行解释

+   `org.springframework.data.web.PageableHandlerMethodArgumentResolver`：这将允许自动解析分页参数，以使用原生 Spring Data 分页支持

##### setWebBindingInitializer

`WebBindingInitializer`接口是一个回调接口，用于全局初始化`WebDataBinder`并在 web 请求的上下文中执行数据绑定。

在继续之前，我们必须停下来重新访问配方的第 4 步，定义了以下方法：

```java
  @InitBinder
  public void allowDateBinding(WebDataBinder binder){
    binder.registerCustomEditor(Date.class, new CustomDateEditor( df, true ));
  }
```

我们在控制器中定义了这个方法，以注册使用`PropertyEditor`进行抽象日期转换绑定。

现在让我们专注于`WebDataBinder`参数。在这一部分，我们谈论的是初始化部分。`WebDataBinder`接口提供了一些有趣的方法。这些方法大多与验证相关（`validate`、`setRequiredFields`、`isAllowed`、`getErrors`等）和转换相关（`getTypeConverter`、`registerCustomEditor`、`setBindingErrorProcessor`、`getBindingResult`等）。

`WebDataBinder`参数也可以设置为`ConversionService`对象。我们将使用全局和声明性初始化，而不是在我们的`allowDateBinding`方法中本地执行（使用`WebDataBinder.setConversion` setter）。

我们选择的`WebBindingInitializer`实现是 Spring 的`ConfigurableWebBindingInitializer` bean。这确实是一个在 Spring 应用程序上下文中进行声明性配置的方便类。它使得预配置的初始化器可以在多个控制器/处理程序上重复使用。

在我们的情况下，`WebBindingInitializer`将有助于全局初始化注册的类型转换器，比如`StringToStockProduct`，同时也可以实现我们的全局异常处理目标。

#### ConversionService API

第 11 步定义了一个`StringToStockProduct`转换器，允许定义一个简洁清晰的`getByCode`方法处理程序：

```java
@RequestMapping(value="/{code}", method=GET)
@ResponseStatus(HttpStatus.OK)
public StockProductOverviewDTO getByCode(
@PathVariable(value="code") StockProduct stock){
  return StockProductOverviewDTO.build(stock);
}
```

这些转换器可以在 Spring 应用程序中广泛使用，而不限于请求范围。它们的泛型使用可能非常有益。它们绑定到`conversionService` bean，没有特定的方法可以避免它们的单独声明。

#### 在`PropertyEditors`和转换器之间进行选择

`PropertyEditors`和`ConversionService`中的转换器在它们的字符串到类型使用中可能看起来是彼此的替代品。

Spring 在设置 bean 属性时大量使用`PropertyEditors`的概念。在 Spring MVC 中，它们用于解析 HTTP 请求。它们在 Spring MVC 中的声明与请求范围相关。

即使它们可以在全局初始化，你必须将`PropertyEditors`视为最初受限范围的元素。以这种方式看待它们合法地将它们附加到`@InitBinder`方法和`WebBinderData`上。它们比转换器更不通用。

在使用`PropertyEditors`处理枚举时，Spring 提供了一种命名约定，可以避免单独声明枚举。我们稍后将利用这个方便的约定。

## 还有更多...

我们将在下一个示例中查看其他`RequestMappingHandlerAdapter`属性。目前，还有更多关于`PropertyEditors`特别是内置编辑器的讨论。

### 内置的 PropertyEditor 实现

以下`PropertyEditors`实现是 Spring 原生支持的。它们可以在所有控制器中手动应用以进行绑定。你可能会认出`CustomDateEditor`，它已在`CloudstreetApiWCI`中注册。

| 提供的实现 | 默认行为 |
| --- | --- |
| `ByteArrayPropertyEditor` | 这是字节数组的编辑器。字符串将简单地转换为它们对应的字节表示。默认情况下由`BeanWrapperImpl`注册。 |
| `ClassEditor` | 将字符串表示的类解析为实际类，反之亦然。当找不到类时，会抛出`IllegalArgumentException`异常。默认情况下由`BeanWrapperImpl`注册。 |
| `CustomBooleanEditor` | 这是一个可定制的布尔属性编辑器。默认情况下由`BeanWrapperImpl`注册，但可以通过注册自定义实例来覆盖它。 |
| `CustomCollectionEditor` | 这是集合的属性编辑器，将任何源集合转换为给定的目标集合类型。 |
| `CustomDateEditor` | 这是一个可定制的`java.util.Date`属性编辑器，并支持自定义的`DateFormat`。默认情况下未注册。用户必须根据需要以适当的格式注册它。 |
| `CustomNumberEditor` | 这是任何数字子类（如`Integer`、`Long`、`Float`或`Double`）的可定制属性编辑器。默认情况下由`BeanWrapperImpl`注册，但可以通过注册自定义实例来覆盖它。 |
| `FileEditor` | 这个编辑器能够将字符串解析为`java.io.File`对象。默认情况下由`BeanWrapperImpl`注册。 |
| `InputStreamEditor` | 这是一个单向属性编辑器，能够接受文本字符串并生成`InputStream`（通过中间的`ResourceEditor`和`Resource`）。`InputStream`属性可以直接设置为字符串。默认情况下不会关闭`InputStream`属性。它默认由`BeanWrapperImpl`注册。 |

### Spring IO 参考文档

在 Spring IO 参考文档中查找有关类型转换和`PropertyEditors`的更多详细信息，请访问：[`docs.spring.io/spring/docs/3.0.x/spring-framework-reference/html/validation.html`](http://docs.spring.io/spring/docs/3.0.x/spring-framework-reference/html/validation.html)。

# 配置内容协商（JSON、XML 等）

在这个示例中，我们将看到如何配置系统根据客户端的期望来决定渲染格式的方式。

## 准备工作

我们主要将在这里审查 XML 配置。然后，我们将使用不同的请求测试 API，以确保对 XML 格式提供支持。

## 如何做...

1.  `RequestMappingHandlerAdapter`配置已在`dispatcher-context.xml`中更改。已添加了`contentNegotiationManager`属性，以及一个`xmlConverter` bean：

```java
<bean class="org.sfw.web...
  method.annotation.RequestMappingHandlerAdapter">
  <property name="messageConverters">
    <list>
      <ref bean="xmlConverter"/>
      <ref bean="jsonConverter"/>
      </list>
  </property>
  <property name="customArgumentResolvers">
    <list>
      <bean class="net.kaczmarzyk.spring.data.jpa. web.SpecificationArgumentResolver"/>
    <bean class="org.sfw.data.web. PageableHandlerMethodArgumentResolver">
      <property name="pageParameterName" value="pn"/>
      <property name="sizeParameterName" value="ps"/>
      </bean>
    </list>
  </property>
  <property name="requireSession" value="false"/>
  <property name="contentNegotiationManager" ref="contentNegotiationManager"/>
</bean>

<bean id="contentNegotiationManager" class="org.sfw.web.accept. ContentNegotiationManagerFactoryBean">
  <property name="favorPathExtension" value="true" />
  <property name="favorParameter" value="false" />
  <property name="ignoreAcceptHeader" value="false"/>
  <property name="parameterName" value="format" />
  <property name="useJaf" value="false"/>
  <property name="defaultContentType" value="application/json" />
  <property name="mediaTypes">
    <map>
      <entry key="json" value="application/json" />
      <entry key="xml" value="application/xml" />
   </map>
  </property>
</bean>
<bean id="xmlConverter" class="org.sfw.http...xml.MarshallingHttpMessageConverter">
  <property name="marshaller">
    <ref bean="xStreamMarshaller"/>
  </property>
  <property name="unmarshaller">
    <ref bean="xStreamMarshaller"/>
  </property>
</bean>
<bean id="xStreamMarshaller" class="org.springframework.oxm.xstream.XStreamMarshaller">
  <property name="autodetectAnnotations" value="true"/>
</bean>
```

1.  已添加了`XStream`的 Maven 依赖项如下：

```java
    <dependency>
      <groupId>com.thoughtworks.xstream</groupId>
       <artifactId>xstream</artifactId>
      <version>1.4.3</version>
    </dependency>
```

1.  调用 URL：`http://localhost:8080/api/indices/EUROPE/^GDAXI/histo.json`应该像以前一样定位`getHistoIndex()`处理程序，您应该收到相同的`json`响应：![如何做...](img/image00845.jpeg)

1.  此外，现在调用 URL `http://localhost:8080/api/indices/EUROPE/^GDAXI/histo.xml`应该生成以下 XML 格式的响应：![如何做...](img/image00847.jpeg)

## 它是如何工作的...

我们已经添加了对 XML 的支持，使用了`MarshallingHttpMessageConverter` bean，定义了默认媒体类型(`application/json`)，并定义了全局内容协商策略。

### 支持 XML 编组

正如我们在上一个示例中所说的，`MarshallingHttpMessageConverter`随框架提供，但它需要`spring-oxm`依赖项，以及编组器和解组器的定义。`spring-oxm`是要引用的 Maven 构件：

```java
<dependency>
  <groupId>org.springframework</groupId>
  <artifactId>spring-oxm</artifactId>
  <version>${spring.version}</version>
</dependency>
```

#### XStream 编组器

我们选择`XStreamMarshaller`作为 XML 编组操作的提供者：

```java
<bean class="org.springframework.oxm.xstream.XStreamMarshaller">
  <property name="autodetectAnnotations" value="true"/>
</bean>
```

`XStream`编组器是`spring-oxm`项目的一部分。即使它*不建议*用于外部源解析（这*不*是我们的意图），它非常好，并且默认情况下需要非常少的配置（不需要特定的类注册或初始映射策略）。

类型和字段可以被注释以自定义默认行为。您可以在这里找到一些来自他们文档的例子：

+   `@XStreamAlias`：用于类型、字段或属性

+   `@XStreamImplicit`：用于集合或数组

+   `@XStreamAsAttribute`：用于将字段标记为属性

+   `@XStreamConverter`：为字段指定特定的转换器

在我们的情况下，我们在 DTO 中应用了最小的编组自定义。

您可以在官方网站[`xstream.codehaus.org`](http://xstream.codehaus.org)上找到有关`XStream`的更多信息。

### ContentNegotiationManager 中的协商策略

在这里，我们谈论的是我们配置系统选择响应的媒体类型的方式。客户端在其请求中显示期望，服务器会尽力满足这些期望，以最大程度地满足可用的分辨率。

客户端有三种方式来指定其媒体类型的期望。我们将在以下部分讨论它们。

#### 接受标头

客户端请求指定 mime 类型或 mime 类型列表（`application/json`、`application/xml`等）作为`Accept`标头的值。这是 Spring MVC 的默认选择。

Web 浏览器可以发送各种`Accept`标头，因此完全依赖这些标头是有风险的。因此，至少支持一种替代方案是很好的。

这些标头甚至可以完全忽略`ContentNegotiationManager`中的`ignoreAcceptHeader`布尔属性。

#### URL 路径中的文件扩展名后缀

在 URL 路径中允许指定文件扩展名后缀是一种替代方案。这是我们配置中的判别器选项。

为此，`ContentNegotiationManager`中的`favorPathExtension`布尔属性已设置为 true，我们的 AngularJS 工厂实际上请求`.json`路径。

#### 请求参数

如果您不喜欢路径扩展选项，可以定义特定的查询参数。此参数的默认名称是`format`。它可以通过`parameterName`属性进行自定义，并且可能的预期值是已注册的格式后缀（`xml`、`html`、`json`、`csv`等）。

这个选项可以作为`favorParameter`布尔属性的判别器选项设置。

#### Java 激活框架

将`useJaf`布尔属性设置为 true，配置为依赖于 Java 激活框架，而不是 Spring MVC 本身，用于后缀到媒体类型的映射（`json`对应`application/json`，`xml`对应`application/xml`等）。

### @RequestMapping 注解作为最终过滤器

最后，带有`@RequestMapping`注解的控制器，特别是`produces`属性，应该对将呈现的格式有最终决定权。

## 还有更多...

现在我们将看一下 JAXB2 作为 XML 解析器的实现和`ContentNegotiationManagerFactoryBean`的配置。

### 使用 JAXB2 实现作为 XML 解析器

JAXB2 是当前的 Java XML 绑定规范。我们使用`XStream`的示例只是一个示例，当然可以使用另一个 XML 编组器。Spring 支持 JAXB2。它甚至在`spring-oxm`包中提供了默认的 JAXB2 实现：`org.springframework.oxm.jaxb.Jaxb2Marshaller`。

在 DTO 中使用 JAXB2 注解可能是可移植性更好的选择。访问`Jaxb2Marshaller`的 JavaDoc 以获取有关其配置的更多详细信息：[`docs.spring.io/autorepo/docs/spring/4.0.4.RELEASE/javadoc-api/org/springframework/oxm/jaxb/Jaxb2Marshaller.html`](http://docs.spring.io/autorepo/docs/spring/4.0.4.RELEASE/javadoc-api/org/springframework/oxm/jaxb/Jaxb2Marshaller.html)。

### ContentNegotiationManagerFactoryBean JavaDoc

`ContentNegotiationManagerFactoryBean`的完整配置在其 JavaDoc 中再次可访问：

[`docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/accept/ContentNegotiationManagerFactoryBean.html`](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/accept/ContentNegotiationManagerFactoryBean.html)

# 添加分页、过滤和排序功能

现在我们已经介绍了 Spring MVC 的 REST 配置的基础，我们将通过添加分页、过滤和排序功能来改进我们的 REST 服务。

## 做好准备

分页是 Spring Data 项目中开发的一个概念。为了添加分页，我们将引入`Pageable`接口，用于从请求中填充的包装器实现。这些接口随后被 Spring Data 识别和处理。

`Page`接口，特别是`PageImpl`实例，可以由 Spring Data 生成以格式化其结果。我们将使用它们，因为它们非常适合于 REST 呈现。

最后，我们将详细介绍这里使用的两个数据绑定工具，以将过滤和分页从我们的控制器逻辑中抽象出来。

## 如何做到这一点...

1.  对于方法处理程序，我们已经添加了我们希望它们支持的参数。`IndexController`中的以下处理程序现在提供分页和排序：

```java
import org.springframework.data.domain.PageRequest;

    @RequestMapping(value="/{market}", method=GET)
    public Page<IndexOverviewDTO> getIndicesPerMarket(
      @PathVariable MarketCode market,
      @PageableDefault(size=10, page=0, sort={"dailyLatestValue"}, direction=Direction.DESC) Pageable pageable){
        return marketService. getLastDayIndicesOverview(market, pageable);
}
```

1.  在相应的服务层实现中，将`pageable`实例传递给 Spring Data JPA 的抽象实现：

```java
@Override
public Page<IndexOverviewDTO> getLastDayIndicesOverview(Pageable pageable) {
    Page<Index> indices = indexProductRepository.findAll(pageable);
    List<IndexOverviewDTO> result = new LinkedList<>();
    for (Index index : indices) {
      result.add(IndexOverviewDTO.build(index));
    }
    return new PageImpl<>(result, pageable,   indices.getTotalElements());
}
```

这基本上就是关于分页和排序模式的全部内容！所有样板代码都是透明的。它使我们能够神奇地检索一个包装在页面元素中的资源，该元素携带了前端可能需要的分页工具。对于我们特定的方法处理程序，调用 URL：

`http://localhost:8080/api/indices/US.json?size=2&page=0&sort=dailyLatestValue`,`asc`的结果是以下 JSON 响应：

![如何做到这一点...](img/image00848.jpeg)

1.  我们还将此模式应用于动态检索带有分页的索引，即使它几乎是相同的方法处理程序定义。

1.  我们还将相同的模式应用于检索用户活动（在`CommunityController`中）：

```java
@RequestMapping(value="/activity", method=GET)
@ResponseStatus(HttpStatus.OK)
public Page<UserActivityDTO> getPublicActivities(
  @PageableDefault(size=10, page=0, sort={"quote.date"},direction=Direction.DESC) Pageable pageable){
  return communityService.getPublicActivity(pageable);
}
```

1.  现在我们已经调整了 AngularJS 层（在本配方的*另请参阅...*部分有详细介绍），我们已经能够完全重构我们的欢迎页面，使用 REST 服务，并为用户活动提供无限滚动：![如何做...](img/image00849.jpeg)

1.  为了充分利用 REST 服务的功能，现在有一个名为*INDICES BY MARKET*的新屏幕，可以从**价格和市场**菜单访问：![如何做...](img/image00850.jpeg)

这里呈现的表格是完全自主的，因为它具有完全的 angular 化（AngularJS）和异步分页/排序功能。

1.  `StockProductController`对象在其`search()`方法处理程序中实现了分页和排序模式，还提供了一个过滤功能，允许用户操作`LIKE` SQL 操作符与`AND`限制相结合：

```java
@RequestMapping(method=GET)
@ResponseStatus(HttpStatus.OK)
public Page<ProductOverviewDTO> search(
@And(value = { @Spec(params = "mkt", path="market.code",spec = EqualEnum.class)},
   and = { @Or({
@Spec(params="cn", path="code", spec=LikeIgnoreCase.class),
@Spec(params="cn", path="name", spec=LikeIgnoreCase.class)})}
  ) Specification<StockProduct> spec,
@RequestParam(value="mkt", required=false) MarketCodeParam market, 
@RequestParam(value="sw", defaultValue="") String startWith, 
@RequestParam(value="cn", defaultValue="") String contain, 
@PageableDefault(size=10, page=0, sort={"dailyLatestValue"}, direction=Direction.DESC) Pageable pageable){
  return productService.getProductsOverview(startWith, spec, pageable);
}
```

1.  `productService`实现，在其`getProductsOverview`方法中（如所示），引用了一个创建的`nameStartsWith`方法：

```java
@Override
public Page<ProductOverviewDTO> getProductsOverview(String startWith, Specification<T> spec, Pageable pageable) {
  if(StringUtils.isNotBlank(startWith)){
    spec = Specifications.where(spec).and(new ProductSpecifications<T>().nameStartsWith(startWith);
  }
  Page<T> products = productRepository.findAll(spec, pageable);
  List<ProductOverviewDTO> result = new LinkedList<>();
  for (T product : products) {
    result.add(ProductOverviewDTO.build(product));
  }
  return new PageImpl<>(result, pageable, products.getTotalElements());
}
```

1.  `nameStartsWith`方法是位于核心模块内的`ProductSpecifications`类中的规范工厂：

```java
public class ProductSpecifications<T extends Product> {
public Specification<T> nameStartsWith(final String searchTerm) {
  return new Specification<T>() {
  private String startWithPattern(final String searchTerm) {
    StringBuilder pattern = new StringBuilder();
	pattern.append(searchTerm.toLowerCase());
    pattern.append("%");
    return pattern.toString();
  }
    @Override
      public Predicate toPredicate(Root<T> root,CriteriaQuery<?> query, CriteriaBuilder cb) {    
      return cb.like(cb.lower(root.<String>get("name")), startWithPattern(searchTerm));
}
    };
  }
}
```

1.  总的来说，`search()` REST 服务广泛地用于与股票检索相关的三个新屏幕。这些屏幕可以通过**价格和市场**菜单访问。这是新的**ALL PRICES SEARCH**表单：![如何做...](img/image00851.jpeg)

1.  以下截图对应于**SEARCH BY MARKET**表单：![如何做...](img/image00852.jpeg)

1.  最后，找到以下新的**Risers and Fallers**屏幕：![如何做...](img/image00853.jpeg)

## 它是如何工作的...

再次强调，这个配方主要是关于 Spring Data 以及如何让 Spring MVC 为我们支持 Spring Data。

### Spring Data 分页支持（你会喜欢它！）

我们已经在上一章中看到了 Spring Data 存储库抽象的一些好处。

在本节中，我们将看到 Spring Data 如何在其抽象的存储库中支持分页概念。Spring MVC 还提供了一个非常有益的扩展，通过特定的参数解析器来防止任何自定义适配逻辑。

#### 存储库中的分页和排序

你可以注意到我们的存储库接口的方法中使用了 Pageable 参数。例如下面是`IndexRepositoryJpa`存储库：

```java
public interface IndexRepositoryJpa extends JpaRepository<Index, 
  String>{
  List<Index> findByMarket(Market market);
  Page<Index> findByMarket(Market market, Pageable pageable);
  List<Index> findAll();
  Page<Index> findAll(Pageable pageable);
  Index findByCode(MarketCode code);
}
```

Spring Data 将`org.springframework.data.domain.Pageable`类型识别为方法参数。当不需要完整的`Pageable`实例时，它还识别`org.springframework.data.domain.Sort`类型。它动态地应用分页和排序到我们的查询中。

你可以在这里看到更多例子（摘自 Spring 参考文档）：

```java
Page<User> findByLastname(String lastname, Pageable pageable);
Slice<User> findByLastname(String lastname, Pageable pageable);
List<User> findByLastname(String lastname, Sort sort);
List<User> findByLastname(String lastname, Pageable pageable);
```

### 提示

请记住，排序选项也是通过`Pageable`处理的。顺便说一句，这就是我们在应用程序中进行排序的方式。

从这些额外的例子中，你可以看到 Spring Data 可以返回一个`Page`（`org.springframework.data.domain.Page`）、一个`Slice`（`org.springframework.data.domain.Slice`）或者简单的`List`。

但是这里有一个惊人的部分：`Page`对象包含了构建强大分页工具所需的一切！之前，我们看到了提供了一个`Page`元素的`json`响应。

通过以下请求：`http://localhost:8080/api/indices/US.json?size=2&page=0&sort=dailyLatestValue,asc`，我们要求第一页，并收到一个`Page`对象告诉我们这一页是不是第一页或最后一页（`firstPage: true/false`，`lastPage: true/false`），页面内的元素数量（`numberOfElements: 2`），总页数和总元素数量（`totalPages: 2`，`totalElements: 3`）。

### 提示

这意味着 Spring Data 首先执行了我们想要执行的查询，然后透明地执行了一个不带分页过滤的计数查询。

`Slice`对象是`Page`的超级接口，不包含`numberOfElements`和`totalElements`的计数。

#### PagingAndSortingRepository<T,ID>

如果一个仓库还没有扩展`JpaRepository<T,ID>`，我们可以让它扩展`PagingAndSortingRepository<T,ID>`，这是`CrudRepository<T,ID>`的扩展。它将提供额外的方法来使用分页和排序抽象检索实体。这些方法包括：

```java

Iterable<T> findAll(Sort sort);
  Page<T> findAll(Pageable pageable);
```

#### Web 部分 - PageableHandlerMethodArgumentResolver

正如我们之前介绍的，我们已经将`org.springframework.data.web.PageableHandlerMethodArgumentResolver` bean 添加到我们的`RequestMappingHandlerAdapter`中作为`customArgumentResolver`。这样做使我们能够依赖 Spring 数据绑定来透明地预填充一个作为方法处理程序参数可用的`Pageable`实例（在本教程的第一步中以粗体显示）。

以下是关于我们可以用于绑定的请求参数的更多信息：

| 参数名称 | 目的/用法 | 默认值 |
| --- | --- | --- |
| `page` | 我们想要检索的页面。 | 0 |
| `size` | 我们想要检索的页面大小。 | 10 |
| `sort` | 应该按照`property,property(,ASC | DESC)`格式进行排序的属性。如果我们想要切换方向，例如：`?sort=firstname&sort=lastname,asc`，我们应该使用多个`sort`参数。 | 默认排序方向是升序。 |

正如我们在第一步中实现的那样，在特定参数缺失的情况下，可以自定义默认值。这是通过`@PageableDefault`注解实现的：

```java
@PageableDefault(
size=10, page=0, sort={"dailyLatestValue"}, direction=Direction.DESC
)
```

### 提示

页面、大小和排序参数名称可以通过在 Spring 配置中设置适当的`PageableHandlerMethodArgumentResolver`属性来进行覆盖。

如果由于某种原因我们不使用`PageableHandlerMethodArgumentResolver`，我们仍然可以捕获我们自己的请求参数（用于分页），并从中构建一个`PageRequest`实例（例如，`org.springframework.data.domain.PageRequest`是一个`Pageable`实现）。

### 一个有用的规范参数解析器

在引入这个有用的规范参数解析器之前，我们必须介绍规范的概念。

#### JPA2 criteria API 和 Spring Data JPA 规范

Spring Data 参考文档告诉我们，JPA 2 引入了一个可以用于以编程方式构建查询的 criteria API。在编写`criteria`时，我们实际上为域类定义了查询的 where 子句。

Spring Data JPA 从 Eric Evans 的书*Domain Driven Design*中引入了规范的概念，遵循相同的语义，并提供了使用 JPA criteria API 定义这些规范的 API。

为了支持规范，我们可以在我们的仓库接口中扩展`JpaSpecificationExecutor`接口，就像我们在我们的`ProductRepository`接口中所做的那样：

```java
@Repository
public interface ProductRepository<T extends Product> extends JpaRepository<T, String>, JpaSpecificationExecutor<T> {
  Page<T> findByMarket(Market marketEntity, Pageable pageable);
  Page<T> findByNameStartingWith(String param, Pageable pageable);
  Page<T> findByNameStartingWith(String param, Specification<T> spec, Pageable pageable);
}
```

在我们的示例中，`findByNameStartingWith`方法检索特定类型（`StockProduct`）的所有产品，这些产品的名称以`param`参数开头，并且与`spec`规范匹配。

#### 规范参数解析器

正如我们之前所说，这个`CustomArgumentResolver`还没有绑定到官方的 Spring 项目中。它的使用可以适用于一些用例，比如本地搜索引擎，以补充 Spring Data 动态查询、分页和排序功能。

与我们从特定参数构建`Pageable`实例的方式相同，这个参数解析器也允许我们从特定参数透明地构建一个`Specification`实例。

它使用`@Spec`注解来定义`like`、`equal`、`likeIgnoreCase`、`in`等`where`子句。这些`@Spec`注解可以通过`@And`和`@Or`注解的帮助组合在一起，形成`AND`和`OR`子句的组。一个完美的用例是开发我们的搜索功能，作为分页和排序功能的补充。

您应该阅读以下文章，这是该项目的介绍。这篇文章的标题是“使用 Spring MVC 和 Spring Data JPA 过滤数据的另一种 API”：

[`blog.kaczmarzyk.net/2014/03/23/alternative-api-for-filtering-data-with-spring-mvc-and-spring-data`](http://blog.kaczmarzyk.net/2014/03/23/alternative-api-for-filtering-data-with-spring-mvc-and-spring-data)

此外，使用以下地址找到项目的存储库和文档：

[`github.com/tkaczmarzyk/specification-arg-resolver`](https://github.com/tkaczmarzyk/specification-arg-resolver)

### 提示

尽管这个库的用户数量远远低于 Spring 社区，但它仍然非常有用。

## 还有更多...

到目前为止，我们一直在关注 Spring MVC。然而，随着呈现的新屏幕，前端（AngularJS）也发生了变化。

### Spring Data

要了解更多关于 Spring Data 功能的信息，请查看官方参考文档：

[`docs.spring.io/spring-data/jpa/docs/1.8.0.M1/reference/html`](http://docs.spring.io/spring-data/jpa/docs/1.8.0.M1/reference/html)

### Angular 路由

如果在**主页**和**价格和市场**菜单之间导航，您会发现整个页面从未完全刷新。所有内容都是异步加载的。

为了实现这一点，我们使用了 AngularJS 路由。`global_routes.js`文件是为此目的而创建的：

```java
cloudStreetMarketApp.config(function($locationProvider, $routeProvider) {
  $locationProvider.html5Mode(true);
  $routeProvider
    .when('/portal/index', {
      templateUrl: '/portal/html/home.html', 
      controller: 'homeMainController'
    })
  .when('/portal/indices-:name', {
    templateUrl: '/portal/html/indices-by-market.html', 
    controller: 'indicesByMarketTableController' 
  })
    .when('/portal/stock-search', {
      templateUrl: '/portal/html/stock-search.html', 
      controller:  'stockSearchMainController'
    })
    .when('/portal/stock-search-by-market', {
      templateUrl: '/portal/html/stock-search-by-market.html', 
      controller:  'stockSearchByMarketMainController'
    })
    .when('/portal/stocks-risers-fallers', {
      templateUrl: '/portal/html/stocks-risers-fallers.html', 
      controller:  'stocksRisersFallersMainController'
    })
    .otherwise({ redirectTo: '/' });
});
```

在这里，我们定义了路由（应用程序通过`href`标签的 URL 路径查询的一部分）和 HTML 模板（作为公共静态资源在服务器上可用）之间的映射表。我们为这些模板创建了一个`html`目录。

然后，AngularJS 在每次请求特定 URL 路径时异步加载一个模板。通常情况下，AngularJS 通过 transclusions 来操作这一点（它基本上删除并替换整个 DOM 部分）。由于模板只是模板，它们需要绑定到控制器，这些控制器通过我们的工厂操作其他 AJAX 请求，从我们的 REST API 中提取数据，并呈现预期的内容。

在前面的例子中：

+   `/portal/index`是一个路由，也就是一个请求的路径

+   `/portal/html/home.html`是映射的模板

+   `homeMainController`是目标控制器

## 另请参阅

您可以在以下网址了解更多关于 AngularJS 路由的信息：

[`docs.angularjs.org/tutorial/step_07`](https://docs.angularjs.org/tutorial/step_07)

### 使用 Angular UI 实现 Bootstrap 分页

我们使用了来自 AngularUI 团队（[`angular-ui.github.io`](http://angular-ui.github.io)）的 UI Bootstrap 项目（[`angular-ui.github.io/bootstrap`](http://angular-ui.github.io/bootstrap)）的分页组件。该项目提供了一个与 AngularJS 一起操作的`Boostrap`组件。

在分页的情况下，我们获得了一个`Bootstrap`组件（与 Bootstrap 样式表完美集成），由特定的 AngularJS 指令驱动。

我们的分页组件之一可以在`stock-search.html`模板中找到：

```java
<pagination page="paginationCurrentPage" 
  ng-model="paginationCurrentPage" 
  items-per-page="pageSize" 
  total-items="paginationTotalItems"
  ng-change="setPage(paginationCurrentPage)">   
</pagination>
```

`page`，`ng-model`，`items-per-page`，`total-items`和`ng-change`指令使用变量（`paginationCurrentPage`，`pageSize`和`paginationTotalItems`），这些变量附加到`stockSearchController`范围。

### 提示

要了解有关该项目的更多信息，请访问其文档：

[`angular-ui.github.io/bootstrap`](http://angular-ui.github.io/bootstrap)

# 全局处理异常

本教程介绍了在 Web 应用程序中全局处理异常的技术。

## 准备工作

在 Spring MVC 中处理异常有不同的方法。我们可以选择定义特定于控制器的`@ExceptionHandler`，或者我们可以选择在`@ControllerAdvice`类中全局注册`@ExceptionHandler`。

我们在 REST API 中开发了第二个选项，即使我们的`CloudstreetApiWCI`超类可以在其控制器之间共享`@ExceptionHandler`。

现在我们将看到如何自动将自定义和通用异常类型映射到 HTTP 状态代码，以及如何将正确的错误消息包装在通用响应对象中，该对象可被任何客户端使用。

## 如何做...

1.  当发生错误时，我们需要一个包装对象发送回客户端：

```java
public class ErrorInfo {
    public final String error;
    public int status;
    public final String date;

    private static final DateFormat dateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.SSS");
    public ErrorInfo(Throwable throwable, HttpStatus status){
      this.error = ExceptionUtil.getRootMessage(throwable);
      this.date = dateFormat.format(new Date());
      this.status = status.value();
   }
   public ErrorInfo(String message, HttpStatus status) {
      this.error = message;
      this.date = dateFormat.format(new Date());
      this.status = status.value();
   }
  @Override
  public String toString() {
    return "ErrorInfo [status="+status+", error="+error+ ", date=" + date + "]";
  }
}
```

1.  我们创建了一个带有`@ControllerAdvice`注释的`RestExceptionHandler`类。这个`RestExceptionHandler`类还继承了`ResponseEntityExceptionHandler`支持类，这使我们可以访问一个默认的映射异常/响应状态，可以被覆盖：

```java
@ControllerAdvice
public class RestExceptionHandler extends ResponseEntityExceptionHandler {

   @Override
protected ResponseEntity<Object> handleExceptionInternal(Exception ex, Object body, HttpHeaders headers, HttpStatus status, WebRequest request) {
if(body instanceof String){
return new ResponseEntity<Object>(new ErrorInfo((String) body, status), headers, status);
   }
  return new ResponseEntity<Object>(new ErrorInfo(ex, status), headers, status);
}

    // 400
    @Override
protected ResponseEntity<Object> handleHttpMessageNotReadable(final HttpMessageNotReadableException ex, final HttpHeaders headers, final HttpStatus status, final WebRequest request) {
return handleExceptionInternal(ex, "The provided request body is not readable!", headers, HttpStatus.BAD_REQUEST, request);
}

@Override
protected ResponseEntity<Object> handleTypeMismatch(TypeMismatchException ex, HttpHeaders headers, HttpStatus status, WebRequest request) {
  return handleExceptionInternal(ex, "The request parameters were not valid!", headers, HttpStatus.BAD_REQUEST, request);
  }
(...)

@ExceptionHandler({ InvalidDataAccessApiUsageException.class, DataAccessException.class , IllegalArgumentException.class })
protected ResponseEntity<Object> handleConflict(final RuntimeException ex, final WebRequest request) {
    return handleExceptionInternal(ex, "The request parameters were not valid!", new HttpHeaders(), HttpStatus.BAD_REQUEST, request);
}
(...)

// 500
@ExceptionHandler({ NullPointerException.class, IllegalStateException.class })
public ResponseEntity<Object> handleInternal(final RuntimeException ex, final WebRequest request) {
return handleExceptionInternal(ex,  "An internal 	error happened during the request! Please try 	again or contact an administrator.", new HttpHeaders(), HttpStatus.INTERNAL_SERVER_ERROR, request);
}
}
```

### 提示

`ErrorInfo`包装器和`RestExceptionHandler`都将支持国际化。这将在第七章中进行演示，*开发 CRUD 操作和验证*。

1.  我们为 MarketCode 和 QuotesInterval Enums 创建了以下两个属性编辑器：

```java
public class MarketCodeEditor extends PropertyEditorSupport{
public void setAsText(String text) {
    try{
      setValue(MarketCode.valueOf(text));
    } catch (IllegalArgumentException e) {
      throw new IllegalArgumentException("The provided value for the market code variable is invalid!");
    }
    }
}
public class QuotesIntervalEditor extends PropertyEditorSupport {
    public void setAsText(String text) {
    try{
       setValue(QuotesInterval.valueOf(text));
    } catch (IllegalArgumentException e) {
      throw new IllegalArgumentException("The provided value for the quote-interval variable is invalid!");
    }
  }
}
```

### 提示

这两个属性编辑器会自动注册，因为它们满足命名和位置约定。由于`MarketCode`和`QuotesInterval`是枚举值，Spring 会在枚举包中查找`MarketCodeEditor`（Editor 后缀）和`QuotesIntervalEditor`。

1.  就是这样！您可以通过在 AngularJS 工厂的`getHistoIndex`方法中提供一个不正确的市场代码来测试它（在`home_financial_graph.js`文件中）。将调用从`$http.get("/api/indices/"+market+"wrong/"+index+"/histo.json")`更改为`$http.get("/api/indices/"+market+"/"+index+"/histo.json")`。

1.  重新启动整个应用程序（**cloudstreetmarket-webapp**和**cloudstreetmarket-api**）后，对`http://localhost:8080/portal/index`的调用将导致**Ajax GET**请求加载索引的结果为**400**状态码：![操作步骤...](img/image00854.jpeg)

1.  有关此失败请求的更多详细信息将显示在`json`响应中：![操作步骤...](img/image00855.jpeg)

接收到的错误消息——**提供的市场变量值无效！**现在是可以接受的。

1.  在获得这个结果后，您可以重置`home_financial_graph.js`文件。

## 工作原理...

在这里，我们关注的是在 REST 环境中处理异常的方式。期望与纯 Web 应用程序略有不同，因为直接用户可能不一定是人类。因此，REST API 必须保持标准、一致和自解释的通信，即使过程生成了错误或失败。

这种一致性是通过始终向客户端返回适当的 HTTP 状态码反馈来实现的，服务器关于请求处理，并始终以客户端期望的格式返回响应主体（与 HTTP 请求的**Accept**头中列出的 MIME 类型之一匹配的格式）。

### 使用@ControllerAdvice 进行全局异常处理

Spring 3.2 带来了一种比以前的异常处理机制更适合 REST 环境的解决方案。使用这种解决方案，使用`@ControllerAdvice`注释的类可以在 API 的不同位置注册。这些注释通过类路径扫描查找，并自动注册到一个公共存储库中，以支持所有控制器（默认情况下）或控制器的子集（使用注释选项）。

在我们的情况下，我们定义了一个单一的`@ControllerAdvice`来监视整个 API。这个想法是在`@ControllerAdvice`注释的`class(es)`中定义相关的方法，这些方法可以将特定的异常类型匹配到特定的 ResponseEntity。一个 ResponseEntity 携带一个主体和一个响应状态码。

这些方法的定义都带有`@ExceptionHandler`注释。此注释的选项允许您针对特定的异常类型。在定义`@ControllerAdvice`时的一个常见模式是使其扩展支持类`ResponseEntityExceptionHandler`。

#### 支持 ResponseEntityExceptionHandler 类

支持`ResponseEntityExceptionHandler`类提供了本机异常（如`NoSuchRequestHandlingMethodException`、`ConversionNotSupportedException`、`TypeMismatchException`等）和 HTTP 状态码之间的预定义映射。

`ResponseEntityExceptionHandler`实现了响应呈现的常见模式。它调用了声明为受保护的特定情况呈现方法，比如下面的`handleNoSuchRequestHandlingMethod`。

```java
protected ResponseEntity<Object> handleNoSuchRequestHandlingMethod(NoSuchRequestHandlingMethod Exception ex, HttpHeaders headers, HttpStatus status, WebRequest request) {
    pageNotFoundLogger.warn(ex.getMessage());
  return handleExceptionInternal(ex, null, headers, status, request);
}
```

这些方法显然可以在`@ControllerAdvice`注解的类中完全重写。重要的是返回`handleExceptionInternal`方法。

这个`handleExceptionInternal`方法也被定义为受保护的，然后可以被重写。这就是我们所做的——返回一个统一的`ErrorInfo`实例：

```java
@Override
protected ResponseEntity<Object> handleExceptionInternal(Exception ex, Object body, HttpHeaders headers, HttpStatus status, WebRequest request) {
  return new ResponseEntity<Object>(new ErrorInfo(ex, (body!=null)? body.toString() : null, status), headers, status);
}
```

#### 统一的错误响应对象

关于统一错误响应对象应该公开的字段，没有具体的标准实践。我们决定为`ErrorInfo`对象提供以下结构：

```java
{
  error: "Global categorization error message",
  message: "Specific and explicit error message",
  status: 400,
  date: "yyyy-MM-dd HH:mm:ss.SSS"
}
```

使用两个不同级别的消息（来自异常类型的全局错误消息和特定情况的消息）允许客户端选择更合适的消息（甚至两者都选择！）在每种情况下呈现在应用程序中。

正如我们已经说过的，这个`ErrorInfo`对象目前还不支持国际化。我们将在第七章 *开发 CRUD 操作和验证*中进行改进。

## 还有更多...

我们在这里提供了一系列与 Web 环境中异常处理相关的资源：

### HTTP 状态码

**万维网联盟**为 HTTP/1.1 指定了明确的响应状态码。比错误消息本身更重要的是，对于 REST API 来说，实现它们至关重要。您可以在这里阅读更多相关信息：

[`www.w3.org/Protocols/rfc2616/rfc2616-sec010.html`](http://www.w3.org/Protocols/rfc2616/rfc2616-sec010.html)

### Spring MVC 异常处理的官方文章

spring.io 博客中的一篇文章是一个非常有趣的资源。它不仅限于 REST 用例。可以从这个地址访问：[`spring.io/blog/2013/11/01/exception-handling-in-spring-mvc`](http://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc)。

### JavaDocs

在这里，我们提供了两个 JavaDoc 资源的 URL，用于配置或简单使用：

ExceptionHandlerExceptionResolver：

[`docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/mvc/method/annotation/ExceptionHandlerExceptionResolver.html`](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/mvc/method/annotation/ExceptionHandlerExceptionResolver.html)

ResponseEntityExceptionHandler：

[`docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/mvc/method/annotation/ResponseEntityExceptionHandler.html`](http://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/web/servlet/mvc/method/annotation/ResponseEntityExceptionHandler.html)

## 另请参阅

+   查看官方演示网站，展示了 Spring MVC 不同类型异常的呈现方式：[`mvc-exceptions-v2.cfapps.io`](http://mvc-exceptions-v2.cfapps.io)

# 使用 Swagger 文档化和公开 API

本节详细介绍了如何使用 Swagger 提供和公开关于 REST API 的元数据。

## 准备工作

我们经常需要为用户和客户文档化 API。在文档化 API 时，根据我们使用的工具，我们经常会得到一些额外的功能，比如能够从 API 元数据生成客户端代码，甚至生成 API 的集成测试工具。

目前还没有公认的和通用的 API 元数据格式标准。这种标准的缺乏导致了市场上有很多不同的 REST 文档解决方案。

我们选择了 Swagger，因为它拥有最大和最活跃的社区。它自 2011 年以来一直存在，并且默认提供了非常好的 UI/测试工具和出色的配置。

## 如何做...

本节详细介绍了在已检出的 v4.x.x 分支的代码库中可以做什么，以及我们已经做了什么。

1.  我们已经为**cloudstreetmarket-core**和**cloudstreetmarket-parent**添加了`swagger-springmvc`项目（版本 0.9.5）的 Maven 依赖：

```java
<dependency>
  <groupId>com.mangofactory</groupId>
  <artifactId>swagger-springmvc</artifactId>
  <version>${swagger-springmvc.version}</version>
</dependency> 
```

1.  已创建以下 swagger `configuration`类：

```java
@Configuration
@EnableSwagger //Loads the beans required by the framework
public class SwaggerConfig {

  private SpringSwaggerConfig springSwaggerConfig;
  @Autowired
    public void setSpringSwaggerConfig(SpringSwaggerConfig springSwaggerConfig) {
    this.springSwaggerConfig = springSwaggerConfig;
    }
  @Bean
  public SwaggerSpringMvcPlugin customImplementation(){
      return new SwaggerSpringMvcPlugin( this.springSwaggerConfig)
          .includePatterns(".*")
          .apiInfo(new ApiInfo(
          "Cloudstreet Market / Swagger UI",
          "The Rest API developed with Spring MVC Cookbook [PACKT]",
          "",
          "alex.bretet@gmail.com",
          "LGPL",
          "http://www.gnu.org/licenses/gpl-3.0.en.html"
      ));
  }
}
```

1.  以下配置已添加到`dispatch-context.xml`中：

```java
<bean class="com.mangofactory.swagger.configuration.SpringSwaggerConfig"/>

<bean class="edu.zc.csm.api.swagger.SwaggerConfig"/>
<context:property-placeholder location="classpath*:/META-INF/properties/swagger.properties" />
```

1.  根据先前的配置，在路径`src/main/resources/META-INF/properties`添加了一个 swagger.properties 文件，内容如下：

```java
  documentation.services.version=1.0
  documentation.services.basePath=http://localhost:8080/api
```

1.  我们的三个控制器已经添加了基本文档。请参阅添加到`IndexController`的以下文档注释：

```java
@Api(value = "indices", description = "Financial indices") 
@RestController
@RequestMapping(value="/indices", produces={"application/xml", "application/json"})
public class IndexController extends CloudstreetApiWCI {

@RequestMapping(method=GET)
@ApiOperation(value = "Get overviews of indices", notes = "Return a page of index-overviews")
public Page<IndexOverviewDTO> getIndices(
@ApiIgnore @PageableDefault(size=10, page=0, sort={"dailyLatestValue"}, direction=Direction.DESC) Pageable pageable){
    return 
    marketService.getLastDayIndicesOverview(pageable);
}

@RequestMapping(value="/{market}", method=GET)
@ApiOperation(value = "Get overviews of indices filtered by market", notes = "Return a page of index-overviews")
public Page<IndexOverviewDTO> getIndicesPerMarket(
  @PathVariable MarketCode market,
  @ApiIgnore 
@PageableDefault(size=10, page=0, sort={"dailyLatestValue"}, direction=Direction.DESC) Pageable pageable){
    return 
    marketService.getLastDayIndicesOverview(market, pageable);
}

@RequestMapping(value="/{market}/{index}/histo", method=GET)
@ApiOperation(value = "Get historical-data for one index", notes = "Return a set of historical-data from one index")
public HistoProductDTO getHistoIndex(
  @PathVariable("market") MarketCode market, 
  @ApiParam(value="Index code: ^OEX") 
  @PathVariable("index") String 
  indexCode,@ApiParam(value="Start date: 2014-01-01") @RequestParam(value="fd",defaultValue="") Date fromDate,
  @ApiParam(value="End date: 2020-12-12") 
  @RequestParam(value="td",defaultValue="") Date toDate,
  @ApiParam(value="Period between snapshots") @RequestParam(value="i",defaultValue="MINUTE_30") QuotesInterval interval){
    return marketService.getHistoIndex(indexCode, market, fromDate, toDate, interval);
  }
}
```

1.  我们从[`github.com/swagger-api/swagger-ui`](https://github.com/swagger-api/swagger-ui)下载了 swagger UI 项目。这是一个静态文件集合（JS、CSS、HTML 和图片）。它已经被粘贴到我们的**cloudstreetmarket-api**项目的 webapp 目录中。

1.  最后，以下 mvc 命名空间配置再次添加到`dispatch-context.xml`中，以便 Spring MVC 打开项目中的静态文件的访问权限：

```java
<!-- Serve static content-->
<mvc:default-servlet-handler/>
```

1.  当我们有了这个配置，访问服务器上的以下 URL `http://localhost:8080/api/index.html` 就会打开 Swagger UI 文档门户：![如何做...](img/image00856.jpeg)

不仅仅是一个 REST 文档存储库，它也是一个方便的测试工具：

![如何做...](img/image00857.jpeg)

## 它是如何工作的...

Swagger 有自己的控制器，发布我们的 API 的元数据。Swagger UI 针对此元数据，解析它，并将其表示为可用的接口。

### 一个公开的元数据

在服务器端，通过将`com.mangofactory/swagger-springmvc`依赖添加到`swagger-springmvc`项目，并使用提供的`SwaggerConfig`类，该库在根路径上创建一个控制器：`/api-docs`，并在那里发布整个元数据供 REST API 使用。

如果您访问`http://localhost:8080/api/api-docs`，您将到达我们的 REST API 文档的根目录：

![一个公开的元数据](img/image00858.jpeg)

这个内容是实现 Swagger 规范的公开元数据。元数据是一个可导航的结构。在 XML 内容的`<path>`节点中可以找到到元数据其他部分的链接。

### Swagger UI

Swagger UI 只由静态文件（CSS、HTML、JavaScript 等）组成。JavaScript 逻辑实现了 Swagger 规范，并递归解析了整个公开的元数据。然后动态构建 API 文档网站和测试工具，挖掘出每个端点及其元数据。

## 还有更多...

在这一部分，我们建议您进一步了解 Swagger 及其 Spring MVC 项目的实现。

### Swagger.io

访问框架的网站和规范：[`swagger.io`](http://swagger.io)。

### swagger-springmvc 文档

swagger-springmvc 项目正在发生变化，因为它正在成为一个名为 SpringFox 的更大的项目的一部分。SpringFox 现在还支持 Swagger 规范的第二个版本。我们建议您访问他们当前的参考文档：

[`springfox.github.io/springfox/docs/current`](http://springfox.github.io/springfox/docs/current)

他们还提供了一个迁移指南，从我们实现的 swagger 规范 1.2 迁移到 swagger 规范 2.0：

[`github.com/springfox/springfox/blob/master/docs/transitioning-to-v2.md`](https://github.com/springfox/springfox/blob/master/docs/transitioning-to-v2.md)

## 另请参阅

本节指导您使用 Swagger 的替代工具和规范：

### 不同的工具，不同的标准

我们已经提到还没有一个明确合法化一个工具胜过另一个的共同标准。因此，可能很好地承认除了 Swagger 之外的工具，因为在这个领域事情发展得非常快。在这里，您可以找到两篇很好的比较文章：

+   [`www.mikestowe.com/2014/07/raml-vs-swagger-vs-api-blueprint.php`](http://www.mikestowe.com/2014/07/raml-vs-swagger-vs-api-blueprint.php)

+   [`apiux.com/2013/04/09/rest-metadata-formats`](http://apiux.com/2013/04/09/rest-metadata-formats)

# 第五章。使用 Spring MVC 进行身份验证

本章涵盖以下内容：

+   配置 Apache HTTP 以代理您的 Tomcat

+   调整用户和角色以适应 Spring 安全

+   通过 BASIC 方案进行身份验证

+   在 REST 环境中存储凭据

+   使用第三方 OAuth2 方案进行身份验证

+   在服务和控制器上进行授权

# 介绍

在本章中，我们将介绍在 Spring 环境中进行身份验证的两种方式。

我们认为只提供安全注释来限制控制器和服务不足以给出 Spring 身份验证的整体图景。如果没有一些关键概念，如`Authentication`对象的作用，Spring 安全过滤器链，`SecurityInterceptor`工作流程等，就不可能对可以与 Spring MVC 一起使用的安全工具感到自信。由于需要配置 OAuth，我们还将向您展示如何在您的机器上设置 Apache HTTP 代理和主机别名，以在本地模拟`cloudstreetmarket.com`域。

# 配置 Apache HTTP 以代理您的 Tomcat

我们将使用本地别名`cloudstreetmarket.com`（端口`80`）访问应用程序，而不是以前的`localhost:8080`。在开发第三方集成时，实施该配置有时是一个强制性步骤。在我们的情况下，第三方将是 Yahoo！及其 OAuth2 身份验证服务器。

## 准备工作

这主要是关于配置。我们将安装 Apache HTTP 服务器，并遵循 Apache Tomcat 操作指南。这将使我们更新 Tomcat 连接器并在 Apache 配置文件中创建虚拟主机。

您将发现这种配置如何允许灵活性，并简单地为客户提供高级和可扩展的架构来提供网页内容。

## 如何做...

1.  在 MS Windows 上，下载并安装 Apache HTTP 服务器。

+   最简单的方法可能是直接从官方分发商下载二进制文件。从以下 URL 之一选择并下载适当的最新 Zip 存档：

+   创建一个目录`C:\apache24`，并将下载的存档解压缩到此位置。

[`www.apachelounge.com/download`](http://www.apachelounge.com/download)

[`www.apachehaus.com/cgi-bin/download.plx`](http://www.apachehaus.com/cgi-bin/download.plx)

### 注意

您应该能够通过此表格访问 bin 目录：`C:\apache24\bin`。

1.  在 Linux / Mac OS 上，下载并安装 Apache HTTP 服务器。

1.  从 Apache 网站下载最新的源代码（压缩在`tar.gz`存档中）：

[`httpd.apache.org/download.cgi#apache24`](http://httpd.apache.org/download.cgi#apache24)

1.  从下载的存档中提取源代码：

```java

$ tar –xvzf httpd-NN.tar.gz
$ cd httpd-NN

```

### 注意

`NN`命令是当前版本的 Apache HTTP。

1.  自动配置目录结构：

```java

$ ./configure

```

1.  编译软件包：

```java

$ make

```

1.  安装目录结构：

```java

$ make install

```

1.  在 MS Windows 上，在 hosts 文件中添加一个新的别名。

1.  使用记事本编辑可以在以下路径找到的文件：

```java
%SystemRoot%\system32\drivers\etc\hosts
```

### 注意

这个文件没有扩展名，记事本在保存文件时不会抱怨。

1.  在文件末尾添加以下条目：

```java
127.0.0.1 cloudstreetmarket.com
```

1.  保存修改。

1.  在 Linux / Mac OS 上，在 hosts 文件中添加一个新的别名。

1.  编辑可以在以下路径找到的文件：`/etc/hosts`

1.  在文件末尾添加以下条目：

```java
127.0.0.1 cloudstreetmarket.com
```

1.  保存修改。

1.  对于所有操作系统，编辑`httpd.conf` Apache 配置文件。

1.  此文件可以在`C:\apache24\conf`（Windows 上）或`/usr/local/apache2/conf`（Linux 或 Mac 上）找到。

1.  取消以下两行的注释：

```java

LoadModule proxy_module modules/mod_proxy.so
LoadModule proxy_http_module modules/mod_proxy_http.so

```

1.  在文件的最底部添加以下块：

```java
<VirtualHost cloudstreetmarket.com:80>
  ProxyPass        /portal http://localhost:8080/portal
  ProxyPassReverse /portal http://localhost:8080/portal
  ProxyPass        /api  http://localhost:8080/api
  ProxyPassReverse /api  http://localhost:8080/api
  RedirectMatch ^/$ /portal/index
</VirtualHost>
```

### 注意

可以在`chapter_5/source_code/app/apache`目录中找到修改后的`httpd.conf`文件示例（适用于 Apache HTTP 2.4.18）。

1.  编辑`server.xml` Tomcat 配置文件。

1.  此文件可以在`C:\tomcat8\conf`（在 Windows 上）或`/home/usr/{system.username}/tomcat8/conf`（在 Linux 或 Mac 上）找到。

1.  找到`<Connector port"="8080"" protocol"="HTTP/1.1""... >`定义并编辑如下：

```java
    <Connector port"="8080"" protocol"="HTTP/1.1""
    connectionTimeout"="20000" redirectPort"="8443"" 
    proxyName"="cloudstreetmarket.com"" proxyPort"="80""/>
```

### 注意

可以在`chapter_5/source_code/app/tomcat`目录中找到修改后的`server.xml`文件示例（适用于 Apache Tomcat 8.0.30）。

1.  在 MS Windows 上，启动 Apache HTTP 服务器。

1.  打开命令提示符窗口。

+   输入以下命令：

```java
$ cd C:/apache24/bin
```

1.  安装 Apache 服务：

```java

$ httpd.exe –k install

```

+   启动服务器：

```java
$ httpd.exe –k start
```

1.  在 Linux/Mac OS 上，启动 Apache HTTP 服务器：

+   启动服务器：

```java
$ sudo apachectl start
```

现在启动 Tomcat 服务器并打开您喜欢的网络浏览器。转到`http://cloudstreetmarket.com`，您应该获得以下着陆页：

![如何做...](img/image00859.jpeg)

## 工作原理...

我们在这里进行的 Apache HTTP 配置现在在某种程度上是标准的。它提供了无限级别的网络定制。它还允许我们启动可扩展性。

### DNS 配置或主机别名

让我们重新审视一下网络浏览器的工作原理。当我们在网络浏览器中输入 URL 时，最终服务器是通过其 IP 访问的，以在特定端口上建立 TCP 连接。浏览器需要解析指定名称的 IP。

为此，它查询一系列域名服务器（在互联网上，该链通常从用户的**互联网服务提供商**（**ISP**）开始）。每个 DNS 基本上都是这样工作的：

+   它尝试自行解析 IP，查找其数据库或缓存中的 IP

+   如果不成功，它会询问另一个 DNS 并等待响应以缓存结果并将其发送回调用者

管理特定域名的 DNS 称为**权威起始**（**SOA**）。这样的 DNS 通常由注册商提供，我们通常使用他们的服务来为域区配置记录（和我们的服务器 IP）。

在网络上，每个 DNS 都尝试解析最终的 SOA。DNS 服务器的顶层层次结构称为**根名称服务器**。有数百个根名称服务器绑定到一个特定的**顶级域**（**TLD**，如.com、.net、.org...）。

当浏览器获得 IP 时，它会尝试在指定端口上建立 TCP 连接（默认为 80）。远程服务器接受连接并通过网络发送 HTTP 请求。

### 在生产中-编辑 DNS 记录

一旦我们接近生产阶段，我们需要真正的域名在域名提供商的网站上在线配置 DNS 记录。有不同类型的记录需要编辑。每个记录都有特定的目的或资源类型：主机、规范名称、邮件交换器、名称服务器等。通常可以在域名提供商的网站上找到具体的指导。

### 主机的别名

在联系任何类型的 DNS 之前，操作系统可能能够自行解析 IP。为此，主机文件是一个纯文本的`注册表`。向此注册表添加别名定义了对任何最终服务器的代理。这是开发环境的常见技术，但不限于它们。

每一行代表一个 IP 地址，后面跟着一个或多个主机名。每个字段由空格或制表符分隔。可以在一行的开头用`#`字符指定注释。空行将被忽略，IP 可以用*IPv4*或*IPv6*定义。

此文件仅用于主机别名，我们在此阶段不处理端口！

#### OAuth 开发的别名定义

在这一章中，我们将使用 OAuth2 协议进行身份验证。在 OAuth 中，有一个**认证服务器（AS）**和一个**服务提供商（SP）**。在我们的情况下，认证服务器将是一个第三方系统（Yahoo！），服务提供商将是我们的应用程序（`cloudstreetmarket.com`）。

OAuth2 认证和授权发生在第三方端。一旦完成这些步骤，认证服务器将 HTTP 请求重定向到服务提供商，使用作为参数传递或存储为变量的回调 URL。

第三方有时会阻止指向`localhost:8080`的回调 URL。在本地测试和开发 OAuth2 对话仍然是必要的。

为主机名配置代理（在 hosts 文件中）和在 HTTP 服务器中管理端口、URL 重写和重定向的虚拟主机是本地环境以及生产基础设施的一个好解决方案。

### Apache HTTP 配置

Apache HTTP 服务器使用 TCP/IP 协议并提供了 HTTP 的实现。TCP/IP 允许计算机在整个网络中相互通信。

在网络上使用 TCP/IP 的每台计算机（局域网或广域网）都有一个 IP 地址。当请求到达接口（例如以太网连接）时，会尝试将其映射到机器上的服务（DNS、SMTP、HTTP 等）使用目标端口号。Apache 通常使用端口 80 进行监听。这是 Apache HTTP 处理一个站点的情况。

#### 虚拟主机

这个功能允许我们从单个 Apache 实例运行和维护多个网站。我们通常在`<VirtualHost...>`部分中对一组专用站点的 Apache 指令进行分组。每个组由一个**站点 ID**标识。

不同的站点可以定义如下：

1.  按名称：

```java
NameVirtualHost 192.168.0.1
<VirtualHost portal.cloudstreetmarket.com>…</VirtualHost>
<VirtualHost api.cloudstreetmarket.com>…</VirtualHost>
```

1.  按 IP（你仍然需要在块内定义一个`ServerName`）：

```java
<VirtualHost 192.168.0.1>…</VirtualHost>
<VirtualHost 192.168.0.2>…</VirtualHost>
```

1.  按端口：

```java
Listen 80
Listen 8080
<VirtualHost 192.168.0.1:80>…</VirtualHost>
<VirtualHost 192.168.0.2:8080>…</VirtualHost>
```

我们当前的配置只有一台机器和一个 Tomcat 服务器，并不是展示虚拟主机所有好处的理想场景。然而，我们已经限定了一个站点及其配置。这是朝着可扩展性和负载平衡迈出的第一步。

#### mod_proxy 模块

这个 Apache 模块为 Apache HTTP 服务器提供了代理/网关功能。这是一个核心功能，因为它可以将 Apache 实例转变为一个能够管理网络上多台机器上的复杂应用程序集的独特接口。

它将 Apache 推向了其初始目的之外：通过 HTTP 在文件系统上公开目录。它依赖于五个特定的子模块：`mod_proxy_http`、`mod_proxy_ftp`、`mod_proxy_ajp`、`mod_proxy_balancer`和`mod_proxy_connect`。每当需要时，它们都需要主要的`mod_proxy`依赖项。代理可以被定义为正向（`ProxyPass`）和/或反向（`ProxyPassReverse`）。它们经常用于为位于防火墙后面的服务器提供互联网访问。

`ProxyPass`可以被替换为`ProxyPassMatch`以提供正则匹配功能。

#### ProxyPassReverse

反向代理处理响应和重定向，就好像它们是自己的 Web 服务器一样。要激活它们，它们通常绑定到`ProxyPass`定义，就像我们在这里的用例中一样：

```java
ProxyPass         /api  http://localhost:8080/api
ProxyPassReverse  /api  http://localhost:8080/api
```

##### 工作者

代理管理底层服务器的配置，还管理它们之间的通信参数，使用称为**workers**的对象（将它们视为一组参数）。当用于反向代理时，这些 workers 使用`ProxyPass`或`ProxyPassMatch`进行配置：

```java
ProxyPass /api http://localhost:8080/api connectiontimeout=5 timeout=30
```

一些 worker-parameters 的例子是：`connectiontimeout`（以秒为单位），`keepalive`（开/关），`loadfactor`（从 1 到 100），`route`（在负载均衡器内使用时绑定到`sessionid`），`ping`（它向 ajp13 连接发送 CPING 请求以确保 Tomcat 没有忙），`min/max`（到底层服务器的连接池条目数），`ttl`（到底层服务器的连接的到期时间）。

#### mod_alias 模块

这个模块提供了 URL 别名和客户端请求重定向。我们已经使用这个模块将请求（默认情况下）重定向到`cloudstreetmarket.com`到门户网站应用程序的索引页面（`cloudstreetmarket.com/portal/index`）。

请注意，与`ProxyPass`改进`ProxyPassMatch`的方式相同，`RedirectMatch`通过正则匹配功能改进了`Redirect`。

### Tomcat 连接器

**连接器**代表一个处理单元，它：监听特定端口以接收请求，将这些请求转发到特定的引擎，接收引擎生成的动态内容，最后将生成的内容发送回端口。在`Service`组件中可以定义多个连接器，共享一个*engine*。一个 Tomcat 实例（`Server`）可以定义一个或多个*service*。Tomcat 有两种类型的连接器。

#### HTTP 连接器

这个连接器在 Tomcat 的 8080 端口上默认设置。它支持 HTTP1/1 协议，并允许 Catalina 作为独立的 Web 服务器运行。HTTP 连接器可以在代理后面使用。Tomcat 支持`mod_proxy`作为负载均衡器。这是我们的预期配置。当在代理后面实现时，可以设置`proxyName`和`proxyPort`属性，以便 Servlet 将指定的值绑定到请求属性`request.getServerPort()`和`request.getServerName()`。

“这个连接器具有最低的延迟和最佳的整体性能。”

Tomcat 文档还指出了以下关于 HTTP 代理的内容：

“应该注意到，HTTP 代理的性能通常低于 AJP 的性能。”

然而，配置 AJP 集群会在架构上增加一个额外的层。对于无状态架构来说，这个额外层的必要性是值得商榷的。

#### AJP 连接器

AJP 连接器的行为与 HTTP 连接器相似，只是它们支持 AJP 协议而不是 HTTP。**Apache JServ Protocol**（**AJP**）是 HTTP 连接器的优化二进制版本。

它允许 Apache HTTP 有效地在不同的 Tomcat 之间平衡请求。它还允许 Apache HTTP 提供 Web 应用的静态内容，而 Tomcat 专注于动态内容。

在 Apache HTTP 方面，这个连接器需要`mod_proxy_ajp`。我们的配置可能是：

```java
ProxyPass / ajp://localhost:8009/api
ProxyPassReverse / http://cloudstreetmarket.com/api/
```

## 还有更多...

在本节中，我们将提供一些更深入了解这些主题的链接：

+   DNS 和分布式系统：

[`computer.howstuffworks.com/dns.htm`](http://computer.howstuffworks.com/dns.htm)

[`en.wikipedia.org/wiki/Root_name_server`](https://en.wikipedia.org/wiki/Root_name_server)

+   域名系统的工作原理：

[`wiki.bravenet.com/How_the_domain_name_system_works`](http://wiki.bravenet.com/How_the_domain_name_system_works)

+   Apache HTTP：

[`httpd.apache.org/docs/trunk/getting-started.html`](http://httpd.apache.org/docs/trunk/getting-started.html)

+   我们使用的模块：

[`httpd.apache.org/docs/2.2/mod/mod_alias.html`](http://httpd.apache.org/docs/2.2/mod/mod_alias.html)

[`httpd.apache.org/docs/2.2/en/mod/mod_proxy.html`](http://httpd.apache.org/docs/2.2/en/mod/mod_proxy.html)

+   Tomcat 连接器：

[`tomcat.apache.org/tomcat-8.0-doc/connectors.html`](http://tomcat.apache.org/tomcat-8.0-doc/connectors.html)

[`wiki.apache.org/tomcat/FAQ/Connectors`](http://wiki.apache.org/tomcat/FAQ/Connectors)

[`www.mulesoft.com/tcat/tomcat-connectors`](https://www.mulesoft.com/tcat/tomcat-connectors)

+   在代理模式下：

[`tomcat.apache.org/tomcat-8.0-doc/proxy-howto.html#Apache_2.0_Proxy_Support`](http://tomcat.apache.org/tomcat-8.0-doc/proxy-howto.html#Apache_2.0_Proxy_Support)

## 另请参阅

+   使用 AJP 连接器时，ProxyPassReverse 的定义与 HTTP 连接器略有不同：

[`www.apachetutor.org/admin/reverseproxies`](http://www.apachetutor.org/admin/reverseproxies)

[`www.humboldt.co.uk/the-mystery-of-proxypassreverse`](http://www.humboldt.co.uk/the-mystery-of-proxypassreverse)

+   如果您希望实现 AJP 集群，请查看以下网址：

[`www.richardnichols.net/2010/08/5-minute-guide-clustering-apache-tomcat/`](http://www.richardnichols.net/2010/08/5-minute-guide-clustering-apache-tomcat/)

### 替代方案 Apache HTTP

可以争论使用 Apache HTTP 在非常高的流量上，特别是因为默认配置可能导致程序为每个连接创建一个新进程。

如果我们只是寻找代理和负载均衡器，我们也应该考虑 HAProxy。HAProxy 是一个高可用的负载均衡器和代理服务器。它是一个免费的开源产品，被 GitHub、StackOverflow、Reddit、Twitter 等引用（[`haproxy.org`](http://haproxy.org)）。

Nginx 可能（目前）是对 Apache HTTP 最受欢迎的替代品。它专注于高并发和低内存使用，其许可证是 2 条款的 BSD 许可证（[`nginx.org`](http://nginx.org)）。

# 将用户和角色调整到 Spring Security

我们认为将这一部分拆分开是有趣的，因为用户和角色通常处于应用程序和 Spring Security 之间的边界。

## 准备工作

在这个配方中，我们将安装 Spring Security 依赖项并更新`User`实体。我们还将创建一个基于我们创建的自定义`Role`枚举的`Authority`实体。最后，我们更新`init.sql`脚本以添加一组现有用户。

## 如何做...

1.  从 Eclipse 的**Git Perspective**中，检出分支`v5.x.x`的最新版本。然后，在`cloudstreetmarket-parent`模块上运行`maven clean install`命令（右键单击模块，转到**Run as…** | **Maven Clean**，然后转到**Run as…** | **Maven Install**）。执行`Maven Update Project`以将 Eclipse 与 maven 配置同步（右键单击模块，然后转到**Maven** | **Update Project…)**。

### 注意

您将注意到前端和后端代码都有一些变化。

1.  Spring Security 附带以下依赖项，添加到`cloudstreetmarket-parent`、`cloudstreetmarket-core`和`cloudstreetmarket-api`中：

```java
<!-- Spring Security -->
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-web</artifactId>
  <version>4.0.0.RELEASE</version>
</dependency>
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-config</artifactId>
  <version>4.0.0.RELEASE</version>
</dependency>
```

1.  `User`实体已更新。它现在反映了`users`表（而不是以前的`user`表）。它还实现了`UserDetails`接口：

```java
@Entity
@Table(name="users")
public class User implements UserDetails{
private static final long serialVersionUID = 1990856213905768044L;

@Id
@Column(name = "user_name", nullable = false)
private String username;

@Column(name = "full_name")
private String fullName;

private String email;
private String password;
private boolean enabled = true;
private String profileImg;

@Column(name="not_expired")
private boolean accountNonExpired;

@Column(name="not_locked")
private boolean accountNonLocked;

@Enumerated(EnumType.STRING)
private SupportedCurrency currency;

@OneToMany(mappedBy= "user", cascade = CascadeType.ALL, fetch = FetchType.LAZY)
@OrderBy("id desc")
private Set<Action> actions = new LinkedHashSet<Action>();

@OneToMany(mappedBy="user", cascade = CascadeType.ALL, fetch = FetchType.EAGER)
private Set<Authority> authorities = new LinkedHashSet<Authority>();

@OneToMany(cascade=CascadeType.ALL, fetch = FetchType.LAZY)
private Set<SocialUser> socialUsers = new LinkedHashSet<SocialUser>();

//getters and setters as per the UserDetails interface
...
}
```

这个`User`实体与`SocialUser`有关联。`SocialUser`在 OAuth2 认证中发挥作用，我们将在稍后开发这部分。

1.  已创建一个 Authority 实体并映射了`authorities`表。该实体还实现了`GrantedAuthority`接口。该类如下：

```java
@Entity
@Table(name"="authorities"", uniqueConstraints={@UniqueConstraint(columnNames = "{"username""","authority""})})
public class Authority implements GrantedAuthority{
  private static final long serialVersionUID = 1990856213905768044L;
  public Authority() {}
  public Authority(User user, Role authority) {
    this.user = user;
    this.authority = authority;
  }
  @Id
  @GeneratedValue
  private Long  id;
  @OneToOne(fetch = FetchType.LAZY)
  @JoinColumn(name = ""username"", nullable=false)
  private User user;
  @Column(nullable = false)
  @Enumerated(EnumType.STRING)
  private Role authority;
  //getters and setters as per the GrantedAuthority 
  //interface
  ...
}
```

1.  为了使代码更易读，我们在`cloudstreetmarket-core`模块中创建了一个`Role`枚举，用于不同的角色：

```java
public enum Role {
  ROLE_ANONYMOUS,
  ROLE_BASIC,
  ROLE_OAUTH2,
  ROLE_ADMIN,
  ROLE_SYSTEM,
  IS_AUTHENTICATED_REMEMBERED; //Transitory role
}
```

1.  此外，我们在`init.sql`文件中进行了一些更改。现有的与用户相关的预初始化脚本已经适应了新的模式：

```java
insert into users(username, fullname, email, password, profileImg, enabled, not_expired, not_locked) values ('userC', '', 'fake12@fake.com', '123456', '', true, true, true);
insert into authorities(username, authority) values ('userC', 'ROLE_'BASIC');
```

1.  启动应用程序。（不应观察到任何异常）。

1.  单击主菜单右侧的**登录**按钮。您将看到以下弹出窗口，允许输入用户名和密码进行登录：![如何做...](img/image00860.jpeg)

1.  您还可以选择创建一个新用户。在上一个弹出窗口中，单击右下角的**创建新帐户**链接。这将加载以下弹出内容：![如何做...](img/image00861.jpeg)

1.  让我们用以下值创建一个新用户：

```java
username: <marcus>
email: <marcus@chapter5.com>
password: <123456>
preferred currency: <USD>
```

### 注意

对于个人资料图片，您必须在文件系统上创建与`cloudstreetmarket-api/src/main/resources/application.properties`中的属性`pictures.user.path`相对应的目录结构。

然后，点击用户图标以上传个人资料图片。

![如何做...](img/image00862.jpeg)

最后，点击**注册**按钮，弹出窗口应该消失。

1.  现在，调用以下 URI：`http://cloudstreetmarket.com/api/users/marcus`。应用程序应该获取 Marcus 用户的以下持久数据：![如何做...](img/image00863.jpeg)

## 工作原理...

在这个阶段，我们预先配置了我们的实体，使它们符合 Spring Security。关于 Spring Security 的一些概念在这部分提到，并在接下来的部分中进行了开发。

### Spring Security 简介

Spring Security 围绕三个核心组件构建：`SecurityContextHolder`对象、`SecurityContext`和`Authentication`对象。

`SecurityContextHolder`对象允许我们为一个 JVM 定义并携带一个`SecurityContextHolderStrategy`实现（专注于存储和检索`SecurityContext`）。

### 注意

`SecurityContextHolder`有以下`static`字段：

```java
private static SecurityContextHolderStrategy strategy;
```

默认情况下，在大多数设计中，所选的策略使用`Threadlocals`（`ThreadLocalSecurityContextHolderStrategy`）。

### ThreadLocal 上下文持有者

一个 Tomcat 实例管理一个 Spring MVC servlet（像任何其他 servlet 一样）并使用多个线程来处理多个 HTTP 请求。代码如下：

```java
final class ThreadLocalSecurityContextHolderStrategy implements
    SecurityContextHolderStrategy {
  private static final ThreadLocal<SecurityContext> contextHolder = new ThreadLocal<SecurityContext>();
  ...
}
```

在 Spring MVC 上为请求分配的每个线程都可以访问携带一个用户（或其他可识别的事物）的`Authentication`对象的`SecurityContext`的副本。

一旦`SecurityContext`的副本不再被引用，它就会被垃圾回收。

### 显著的 Spring Security 接口

Spring Security 中有一堆显著的接口。我们将特别访问`Authentication`、`UserDetails`、`UserDetailsManager`和`GrantedAuthority`。

### Authentication 接口

Spring `Authentication`对象可以从`SecurityContext`中检索。这个对象通常由 Spring Security 管理，但应用程序仍经常需要访问它来进行业务处理。

这是`Authentication`对象的接口：

```java
public interface Authentication extends Principal, Serializable {
  Collection<? extends GrantedAuthority> getAuthorities();
  Object getCredentials();
  Object getDetails();
  Object getPrincipal();
  boolean isAuthenticated();
  void setAuthenticated(boolean isAuthenticated) throws IllegalArgumentException;
}
```

它提供对`Principal`（代表已识别的用户、实体、公司或客户）、其凭据、其权限以及可能需要的一些额外详细信息的访问。现在让我们看看如何从`SecurityContextHolder`中检索用户：

```java
Object principal = SecurityContextHolder.getContext()
  .getAuthentication()
  .getPrincipal();
if (principal instanceof UserDetails) {
    String username = ((UserDetails) principal).getUsername();
} else {
  String username = principal.toString();
}
```

`Principal`类可以转换为 Spring `UserDetails`类型，该类型由核心框架公开。该接口用作几个扩展模块（*Spring Social*、*Connect*、*Spring Security SAML*、*Spring Security LDAP*等）中的标准桥梁。

### UserDetails 接口

`UserDetails`实现以可扩展和特定于应用程序的方式表示主体。

您必须了解提供核心框架中账户检索的关键方法`loadUserByUsername`的单方法`UserDetailsService`接口：

```java
public interface UserDetailsService {
  UserDetails loadUserByUsername(String username) throws UsernameNotFoundException;
}
```

Spring Security 为这个接口提供了两种实现：`CachingUserDetailsService`和`JdbcDaoImpl`，无论我们是想要从内存中的`UserDetailsService`还是从基于 JDBC 的`UserDetailsService`实现中受益。更普遍地，通常重要的是用户和角色在哪里以及如何持久化，以便 Spring Security 可以自行访问这些数据并处理认证。

#### 认证提供者

Spring Security 访问用户和角色数据的方式是通过在 Spring Security 配置文件中使用安全命名空间中的身份验证提供程序的选择或引用进行配置的。

以下是使用原生`UserDetailsService`实现时的两个配置示例：

```java
<security:authentication-manager alias="authenticationManager">
  <security:authentication-provider>
    <security:jdbc-user-service data-source-ref="dataSource" />
  </security:authentication-provider>
</security:authentication-manager>
```

这个第一个例子指定了基于 JDBC 的`UserDetailsService`。下一个例子指定了一个内存中的`UserDetailsService`。

```java
<security:authentication-manager alias="authenticationManager">
  <security:authentication-provider>
    <security:user-service id="inMemoryUserDetailService"/>
  </security:authentication-provider>
</security:authentication-manager>
```

在我们的情况下，我们已经注册了我们自己的`UserDetailsService`实现（`communityServiceImpl`）如下：

```java
<security:authentication-manager alias="authenticationManager">
  <security:authentication-provider user-service-ref='communityServiceImpl'>
    <security:password-encoder ref="passwordEncoder"/>
  </security:authentication-provider>
</security:authentication-manager>
```

我们认为通过 JPA 抽象继续访问数据库层更合适。

##### UserDetailsManager 接口

Spring Security 提供了一个`UserDetails`实现`org.sfw.security.core.userdetails.User`，可以直接使用或扩展。User 类定义如下：

```java
public class User implements UserDetails, CredentialsContainer {
  private String password;
  private final String username;
  private final Set<GrantedAuthority> authorities;
  private final boolean accountNonExpired;
  private final boolean accountNonLocked;
  private final boolean credentialsNonExpired;
  private final boolean enabled;
  ...
}
```

### 注意

管理用户（创建、更新等）可以是 Spring Security 的共同责任。尽管通常主要由应用程序执行。

引导我们朝着`UserDetails`的结构，Spring Security 还提供了一个用于管理用户的`UserDetailsManager`接口：

```java
public interface UserDetailsManager extends UserDetailsService {
  void createUser(UserDetails user);
  void updateUser(UserDetails user);
  void deleteUser(String username);
  void changePassword(String oldPassword, String newPassword);
  boolean userExists(String username);
}
```

Spring Security 有两个原生实现，用于非持久化（`InMemoryUserDetailsManager`）和基于 JDBC 的（`JdbcUserDetailsManager`）用户管理。

当决定不使用内置的身份验证提供程序时，实现所提供的接口是一个很好的做法，特别是为了保证在 Spring Security 的未来版本中向后兼容。

#### GrantedAuthority 接口

在 Spring Security 中，`GrantedAuthorities`反映了授予`Principal`的应用程序范围的权限。Spring Security 引导我们朝着基于角色的身份验证。这种身份验证要求创建能够执行操作的用户组。

### 注意

除非某个功能有强烈的业务意义，最好使用例如`ROLE_ADMIN`或`ROLE_GUEST`而不是`ROLE_DASHBOARD`或`ROLE_PAYMENT`…

角色可以从`Authentication`对象的`getAuthorities()`中提取，作为`GrantedAuthority`实现的数组。

`GrantedAuthority`接口非常简单：

```java
public interface GrantedAuthority extends Serializable {
  String getAuthority();
}
```

`GrantedAuthority`实现是包装器，携带角色的文本表示。这些文本表示可能与安全对象的配置属性匹配（我们将在*服务和控制器授权*中详细介绍这个概念）。

`Role`嵌入在`GrantedAuthority`中，可以通过`getAuthority()` getter 访问，对于 Spring Security 来说，这比包装器本身更重要。

我们创建了自己的实现：`Authority`实体与`User`有关联。框架还提供了`SimpleGrantedAuthority`的实现。

在最后一个配方中，我们将讨论 Spring Security 的授权过程。我们将看到 Spring Security 提供了`AccessDecisionManager`接口和几个`AccessDecisionManager`实现。这些实现是基于投票的，并使用`AccessDecisionVoter`实现。其中最常用的是`RoleVoter`类。

### 注意

`RoleVoter`实现在配置属性（Authority 的文本表示）以预定义前缀开头时，对用户授权进行积极投票。默认情况下，此前缀设置为`ROLE_`。

## 还有更多…

Spring Security 的身份验证和授权过程将在服务和控制器授权的深度覆盖中进行。本节介绍了 Spring Security 参考文档中更多的细节。

### Spring Security 参考

Spring Security 安全参考是理论和实践信息的绝佳来源。

#### 技术概述

技术概述是 Spring Security 框架的一个很好的介绍：

[`docs.spring.io/spring-security/site/docs/3.0.x/reference/technical-overview.html`](http://docs.spring.io/spring-security/site/docs/3.0.x/reference/technical-overview.html)

#### 示例应用程序

Spring Security 参考提供了许多不同身份验证类型（*LDAP*、*OPENID*、*JAAS*等）的 Spring Security 示例。其他基于角色的示例也可以在以下找到：

[`docs.spring.io/spring-security/site/docs/3.1.5.RELEASE/reference/sample-apps.html`](http://docs.spring.io/spring-security/site/docs/3.1.5.RELEASE/reference/sample-apps.html)

#### 核心服务

了解更多关于内置的`UserDetailsService`实现（内存或 JDBC）的信息：

[`docs.spring.io/spring-security/site/docs/3.1.5.RELEASE/reference/core-services.html`](http://docs.spring.io/spring-security/site/docs/3.1.5.RELEASE/reference/core-services.html)

# 通过 BASIC 方案进行身份验证

通过 BASIC 方案进行身份验证是我们这种无状态应用程序的一种流行解决方案。凭据随着 HTTP 请求发送。

## 准备工作

在这个配方中，我们完成了 Spring Security 配置。我们使其支持应用程序所需的 BASIC 身份验证方案。

我们稍微定制了生成的响应头，这样它们就不会触发浏览器显示原生的 BASIC 认证表单（这对我们的用户来说不是最佳体验）。

## 如何做...

1.  为了使用 Spring 安全命名空间，我们将以下过滤器添加到`cloudstreetmarket-api web.xml`中：

```java
<filter>
  <filter-name>springSecurityFilterChain</filter-name>
  <filter-class> org.sfw.web.filter.DelegatingFilterProxy
  </filter-	class>
</filter>
<filter-mapping>
  <filter-name>springSecurityFilterChain</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

1.  一个 Spring 配置文件已经专门为`cloudstreetmarket-api`模块的 Spring Security 创建。这个文件包含以下 bean 定义：

```java
<bean id="authenticationEntryPoint" class="edu.zc.csm.api.authentication.CustomBasicAuthenticationEntryPoint">
  <property name="realmName" value="cloudstreetmarket.com" />
</bean> 
<security:http create-session="stateless" authentication-manager-ref="authenticationManager" entry-point-ref="authenticationEntryPoint">
    <security:custom-filter ref="basicAuthenticationFilter" after="BASIC_AUTH_FILTER" />
   <security:csrf disabled="true"/>
</security:http>

<bean id="basicAuthenticationFilter" class="org.sfw.security.web.authentication.www.BasicAuthenticationFilter">
  <constructor-arg name="authenticationManager" ref="authenticationManager" />
  <constructor-arg name="authenticationEntryPoint" ref="authenticationEntryPoint" />
</bean>
<security:authentication-manager alias="authenticationManager">
    <security:authentication-provider user-service-ref='communityServiceImpl'>
      <security:password-encoder ref="passwordEncoder"/>
  </security:authentication-provider>
</security:authentication-manager>

<security:global-method-security secured-annotations="enabled" pre-post-annotations="enabled" authentication-manager-ref="authenticationManager"/>
```

1.  这个新的配置是指`CustomBasicAuthenticationEntryPoint`类。这个类有以下内容：

```java
public class CustomBasicAuthenticationEntryPoint extends BasicAuthenticationEntryPoint {
  @Override
  public void commence(HttpServletRequest request, HttpServletResponse response, AuthenticationException authException) throws IOException, ServletException {
    response.setHeader("WWW-Authenticate", "CSM_Basic realm=\ + getRealmName() + \");
    response.sendError(HttpServletResponse.SC_UNAUTHORIZED, authException.getMessage()
    );
  }
}
```

1.  已添加新的`@ExceptionHandler`来捕获认证异常：

```java
@ExceptionHandler({BadCredentialsException.class, AuthenticationException.class, AccessDeniedException.class})
protected ResponseEntity<Object> handleBadCredentials(final RuntimeException ex, final WebRequest request) {
  return handleExceptionInternal(ex, "The attempted  operation has been denied!", new HttpHeaders(),   FORBIDDEN, request);
}
...
```

### 注意

就是这样了！我们已经让我们的后端支持了 BASIC 认证。但是，我们还没有限制我们的服务（作为安全对象）。我们现在将这样做。

1.  出于示例目的，请更新`cloudstreetmarket-core`中的`IMarketService`接口。将`@Secured("ROLE_BASIC")`注解添加到`Type`中，如下所示：

```java
@Secured ("ROLE_BASIC")
public interface IMarketService {
  Page<IndexOverviewDTO> getLastDayIndicesOverview( MarketCode market, Pageable pageable);
  Page<IndexOverviewDTO> getLastDayIndicesOverview( Pageable pageable);
  HistoProductDTO getHistoIndex(String code, MarketCode market, Date fromDate, Date toDate, QuotesInterval interval);
}
```

1.  现在重新启动 Tomcat 服务器（这样做将删除您之前创建的用户）。

1.  在您喜欢的 Web 浏览器中，打开开发者选项卡，并在刷新主页时观察 AJAX 查询。您应该注意到有两个 AJAX 查询返回了`403`状态码（`禁止`）。![如何做...](img/image00864.jpeg)

这些查询也返回了 JSON 响应：

```java
{"error":"Access is denied","message":"The attempted operation has been denied!","status":403","date":"2015-05-05 18:01:14.917"}
```

1.  现在，使用登录功能/弹出窗口，请使用之前创建的具有`BASIC`角色的用户之一登录：

```java
Username: <userC> 
Password: <123456>
```

1.  刷新页面并观察相同的两个 AJAX 查询。在请求头中，您可以看到我们的前端发送了一个特殊的**Authorization**头：![如何做...](img/image00865.jpeg)

1.  这个授权头携带的值是：`Basic dXNlckM6MTIzNDU2`。编码后的`dXNlckM6MTIzNDU2`是`userC:123456`的 base64 编码值。

1.  让我们来看看对这些查询的响应：![如何做...](img/image00866.jpeg)

状态现在是`200 (OK)`，您还应该收到正确的 JSON 结果：

![如何做...](img/image00867.jpeg)

1.  服务器在响应中发送了一个`WWW-Authenticate`头，其值为：**CSM_Basic realm"="cloudstreetmarket.com"**

1.  最后，撤销您在`IMarketService`（第 5 步）中所做的更改。

## 它是如何工作的...

我们将探讨使用 Spring Security 进行 BASIC 认证背后的概念：

### Spring Security 命名空间

与往常一样，Spring 配置命名空间带来了一个特定的语法，适合模块的需求和用法。它通过更好的可读性减轻了整体的 Spring 配置。命名空间通常带有默认配置或自动配置工具。

Spring Security 命名空间带有 spring-security-config 依赖项，并可以在 Spring 配置文件中定义如下：

```java
<beans   xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xsi:schemaLocation"="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.xsd http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security-4.0.0.xsd">
    ...
</beans>
```

命名空间分为三个顶级组件：`<http>`（关于 Web 和 HTTP 安全），`<authentication-manager>`和`<global-method-security>`（服务或控制器限制）。

然后，其他概念被这些顶级组件引用为属性或子元素：`<authentication-provider>`，`<access-decision-manager>`（为 Web 和安全方法提供访问决策），和`<user-service>`（作为`UserDetailsService`实现）。

#### `<http>`组件

命名空间的`<http>`组件提供了一个我们没有在这里使用的`auto-config`属性。`<http auto-config"="true">`的定义将是以下定义的快捷方式：

```java
  <http>
    <form-login />
    <http-basic />
    <logout />
  </http>
```

对于我们的 REST API 来说不值得，因为我们没有计划为表单登录实现服务器端生成的视图。此外，`<logout>`组件对我们来说是无用的，因为我们的 API 不管理会话。

最后，`<http-basic>`元素创建了基础的`BasicAuthenticationFilter`和`BasicAuthenticationEntryPoint`到配置中。

我们使用我们自己的`BasicAuthenticationFilter`来自定义`WWW-Authenticate`响应头的值，从`Basic base64token`到`CSM_Basic base64token`。这是因为包含以**Basic**关键字开头的值的 AJAX HTTP 响应（来自我们的 API）会自动触发 Web 浏览器打开本机的基本表单弹出窗口。这不是我们想要建立的用户体验类型。

#### Spring Security 过滤器链

在食谱的第一步中，我们在`web.xml`中声明了一个名为`springSecurityFilterChain`的过滤器：

```java
  <filter>
    <filter-name>springSecurityFilterChain</filter-name>
  <filter-class>org.sfw.web.filter.DelegatingFilterProxy</filter-class>
</filter>
<filter-mapping>
  <filter-name>springSecurityFilterChain</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

在这里，`springSecurityFilterChain`也是一个 Spring bean，它是由 Spring Security 命名空间（特别是`http`组件）在内部创建的。`DelegatingFilterProxy`是 Spring 的基础设施，它在应用程序上下文中寻找特定的 bean 并调用它。目标 bean 必须实现`Filter`接口。

整个 Spring Security 机制是通过一个单一的 bean 连接起来的。

`<http>`元素的配置在定义过滤器链的制定中起着核心作用。它直接定义的元素创建了相关的过滤器。

|   | *"一些核心过滤器总是在过滤器链中创建，其他的将根据存在的属性和子元素添加到堆栈中。"* |   |
| --- | --- | --- |
|   | --*Spring Security* |

重要的是要区分配置相关的过滤器和不能被移除的核心过滤器。作为核心过滤器，我们可以计算`SecurityContextPersistenceFilter`、`ExceptionTranslationFilter`和`FilterSecurityInterceptor`。这三个过滤器是与`<http>`元素本地绑定的，并且可以在下一个表中找到。

这个表来自 Spring Security 参考文档，它包含了所有核心过滤器（随框架提供）的内容，可以使用特定的元素或属性激活。它们按照它们在链中的位置顺序列在这里。

| 别名 | 过滤器类 | 命名空间元素或属性 |
| --- | --- | --- |
| --- | --- | --- |
| `CHANNEL_FILTER` | ChannelProcessingFilter | http/intercept-url@requires-channel |
| `SECURITY_CONTEXT_FILTER` | SecurityContextPersistenceFilter | http |
| `CONCURRENT_SESSION_FILTER` | ConcurrentSessionFilter | session-management/concurrency-control |
| `HEADERS_FILTER` | HeaderWriterFilter | http/headers |
| `CSRF_FILTER` | CsrfFilter | http/csrf |
| `LOGOUT_FILTER` | LogoutFilter | http/logout |
| `X509_FILTER` | X509AuthenticationFilter | http/x509 |
| `PRE_AUTH_FILTER` | AbstractPreAuthenticatedProcessingFilter Subclasses | N/A |
| `CAS_FILTER` | CasAuthenticationFilter | N/A |
| `FORM_LOGIN_FILTER` | UsernamePasswordAuthenticationFilter | http/form-login |
| `BASIC_AUTH_FILTER` | BasicAuthenticationFilter | http/http-basic |
| `SERVLET_API_SUPPORT_FILTER` | SecurityContextHolderAwareRequestFilter | http/@servlet-api-provision |
| `JAAS_API_SUPPORT_FILTER` | JaasApiIntegrationFilter | http/@jaas-api-provision |
| `REMEMBER_ME_FILTER` | RememberMeAuthenticationFilter | http/remember-me |
| `ANONYMOUS_FILTER` | AnonymousAuthenticationFilter | http/anonymous |
| `SESSION_MANAGEMENT_FILTER` | SessionManagementFilter | session-management |
| `EXCEPTION_TRANSLATION_FILTER` | ExceptionTranslationFilter | http |
| `FILTER_SECURITY_INTERCEPTOR` | FilterSecurityInterceptor | http |
| `SWITCH_USER_FILTER` | SwitchUserFilter | N/A |

请记住，自定义过滤器可以相对地定位，或者可以使用`custom-filter`元素替换这些过滤器中的任何一个：

```java
<security:custom-filter ref="myFilter" after="BASIC_AUTH_FILTER"/>
```

##### 我们的<http>配置

我们为`<http>`的'命名空间'组件定义了以下配置：

```java
<security:http create-session="stateless" entry-point-ref="authenticationEntryPoint" authentication-manager- ref="authenticationManager">
  <security:custom-filter ref="basicAuthenticationFilter" after="BASIC_AUTH_FILTER" />
  <security:csrf disabled="true"/>
</security:http>
<bean id="basicAuthenticationFilter" class="org.sfw.security.web.authentication.www.BasicAuthenticationFilter">
  <constructor-arg name="authenticationManager" ref="authenticationManager" />
  <constructor-arg name="authenticationEntryPoint" ref="authenticationEntryPoint" />
</bean>
<bean id="authenticationEntryPoint" class="edu.zc.csm.api. authentication.CustomBasicAuthenticationEntryPoint">
  <property name="realmName" value="${realm.name}" />
</bean>
```

在这里，我们告诉 Spring 不要创建会话，并使用`create-session=="stateless"`忽略传入的会话。我们这样做是为了追求无状态和可扩展的微服务设计。

出于同样的原因，我们目前已经禁用了**跨站请求伪造**（**csrf**）支持。这个功能自 3.2 版本以来默认已经被框架启用。

由于我们没有实现命名空间预配置的任何身份验证策略（`http-basic`或`login-form`），因此需要定义一个`entry-point-ref`。

我们定义了一个自定义过滤器`BasicAuthenticationFilter`，在核心`BASIC_AUTH_FILTER`的理论位置之后执行。

现在，我们将看看三个引用的角色：`authenticationEntryPoint`、`authenticationManager`和`basicAuthenticationFilter`。

### AuthenticationManager 接口

首先，`AuthenticationManager`是一个单方法接口：

```java
public interface AuthenticationManager {
  Authentication authenticate(Authentication authentication) throws AuthenticationException;
}
```

Spring Security 提供了一个实现：`ProviderManager`。这个实现允许我们插入多个`AuthenticationProviders`。`ProviderManager`按顺序尝试所有`AuthenticationProviders`，调用它们的`authenticate`方法。代码如下：

```java
public interface AuthenticationProvider {
  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
  boolean supports(Class<?> authentication);
}
```

`ProviderManager`在找到非空的`Authentication`对象时停止迭代。或者，在抛出`AuthenticationException`时，它会失败`Authentication`。

使用命名空间，可以使用`ref`元素来针对特定的`AuthenticationProviders`，如下所示：

```java
<security:authentication-manager >
  <security:authentication-provider ref='myAuthenticationProvider'/>
</security:authentication-manager>
```

现在，这是我们的配置：

```java
<security:authentication-manager alias"="authenticationManager"">
  <security:authentication-provider user-service-ref='communityServiceImpl'>
    <security:password-encoder ref="passwordEncoder"/>
  </security:authentication-provider>
</security:authentication-manager>
```

在我们的配置中没有`ref`元素。命名空间将默认实例化一个`DaoAuthenticationProvider`。它还将注入我们的`UserDetailsService`实现：`communityServiceImpl`，因为我们已经用`user-service-ref`指定了它。

当`DaoAuthenticationProvider`中`UserDetailsService`加载的密码与`UsernamePasswordAuthenticationToken`中提交的密码不匹配时，会抛出`AuthenticationException`。

在我们的项目中还有一些其他`AuthenticationProviders`可以使用，例如`RememberMeAuthenticationProvider`、`LdapAuthenticationProvider`、`CasAuthenticationProvider`或`JaasAuthenticationProvider`。

### 基本认证

正如我们所说，使用 BASIC 方案是 REST 应用程序的一个很好的技术。但是，在使用它时，使用加密通信协议（HTTPS）是至关重要的，因为密码是以明文形式发送的。

在*如何做*部分演示的，原则非常简单。HTTP 请求与通常相同，只是多了一个`Authentication`头。这个头的值由关键词`Basic`后跟一个空格，再跟一个 base 64 编码的字符串组成。

我们可以在线找到一堆免费的服务，快速对一个字符串进行 base 64 编码/解码。要进行 base 64 编码的字符串必须是以下形式：`<username>:<password>`。

#### BasicAuthenticationFilter

为了实现我们的基本认证，我们已经将`BasicAuthenticationFilter`添加到了我们的过滤器链中。这个`BasicAuthenticationFilter`（`org.sfw.security.web.authentication.www.BasicAuthenticationFilter`）需要一个`authenticationManager`，并且可以选择一个`authenticationEntryPoint`。

可选的`authenticationEntryPoint`配置驱动过滤器朝着下面介绍的两种不同行为。

两者都是从相同的方式开始：过滤器从链中的位置触发。它在请求中查找认证头，并委托给`authenticationManager`，后者依赖于`UserDetailsService`实现来与数据库中的用户凭据进行比较。

##### 使用 authenticationEntryPoint

这是我们的配置，它的行为如下：

+   当认证成功时，过滤器链停止，并返回一个`Authentication`对象。

+   当认证失败时，`authenticationEntryPoint`方法会在过滤器链中断时被调用。我们的认证入口点设置了一个自定义的`WWW-Authenticate`响应头和一个`401`状态码（`FORBIDDEN`）。

这种类型的配置提供了一个预身份验证，其中检查 HTTP 请求中的`Authentication Header`，以查看业务服务是否需要授权（安全对象）。

这种配置允许通过 Web 浏览器快速反馈，可能会提示一个本地 BASIC 表单。我们目前选择了这种配置在我们的应用程序中。

##### 没有 authenticationEntryPoint

没有 authenticationEntryPoint，过滤器的行为如下：

+   当身份验证成功时，过滤器链停止，并返回一个`Authentication`对象。

+   当身份验证失败时，过滤器链继续。之后，如果链中的另一个身份验证成功，用户将相应地进行身份验证。但是，如果链中没有其他身份验证成功，那么用户将以匿名角色进行身份验证，这可能适合或不适合服务访问级别。

## 还有更多...

### 在 Spring Security 参考中

这一部分在很大程度上受到了 Spring rsecurity 参考的启发，这又是一个很好的资源：

[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle)

附录提供了 Spring Security 命名空间的非常完整的指南：

[`docs.spring.io/spring-security/site/docs/current/reference/html/appendix-namespace.html`](http://docs.spring.io/spring-security/site/docs/current/reference/html/appendix-namespace.html)

### 记住我 cookie/功能

我们跳过了`RememberMeAuthenticationFilter`，它提供了服务器在会话之间记住 Principal 身份的不同方式。Spring Security 参考提供了关于这个主题的广泛信息。

# 使用第三方 OAuth2 方案进行身份验证

这个配方使用 Spring social 项目，以便从客户端的角度使用 OAuth2 协议。

## 准备工作

我们不会在这里创建一个 OAuth2 **身份验证服务器** (**AS**)。我们将建立到第三方身份验证服务器（Yahoo!）的连接，以在我们的应用程序上进行身份验证。我们的应用程序将充当**服务提供商** (**SP**)。

我们将使用 Spring social，其第一个作用是透明地管理社交连接，并提供一个调用提供者 API（Yahoo! Finance）的外观，使用 Java 对象。

## 如何做...

1.  为 Spring social 添加了两个 Maven 依赖项：

```java
    <!– Spring Social Core –>
    <dependency>
      <groupId>org.springframework.social</groupId>
      <artifactId>spring-social-core</artifactId>
      <version>1.1.0.RELEASE</version>
    </dependency>
    <!– Spring Social Web (login/signup controllers) –>
    <dependency>
      <groupId>org.springframework.social</groupId>
      <artifactId>spring-social-web</artifactId>
      <version>1.1.0.RELEASE</version>
    </dependency>
```

1.  如果我们想要处理到 Twitter 或 Facebook 的 OAuth2 连接，我们还需要添加以下依赖项：

```java
  <!– Spring Social Twitter –>
    <dependency>
      <groupId>org.springframework.social</groupId>
      <artifactId>spring-social-twitter</artifactId>
      <version>1.1.0.RELEASE</version>
    </dependency>
    <!– Spring Social Facebook –>
      <dependency>
      <groupId>org.springframework.social</groupId>
      <artifactId>spring-social-facebook</artifactId>
      <version>1.1.0.RELEASE</version>
    </dependency>
```

1.  在 BASIC 身份验证部分之后，Spring Security 配置文件并没有太多改变。在`http` bean 中可以注意到一些拦截器：

```java
<security:http create-session="stateless" entry-point-ref="authenticationEntryPoint" authentication-manager-ref="authenticationManager">
  <security:custom-filter ref="basicAuthenticationFilter" after="BASIC_AUTH_FILTER" />
  <security:csrf disabled="true"/>
  <security:intercept-url pattern="/signup" access="permitAll"/>
  ...
  <security:intercept-url pattern="/**" access="permitAll"/>
</security:http>
```

使用以下`SocialUserConnectionRepositoryImpl`，我们已经创建了自己的`org.sfw.social.connect.ConnectionRepository`的实现，这是一个`Spring Social`的`core`接口，具有管理社交用户连接的方法。代码如下：

```java
@Transactional(propagation = Propagation.REQUIRED)
@SuppressWarnings("unchecked")
public class SocialUserConnectionRepositoryImpl implements ConnectionRepository {
@Autowired
private SocialUserRepository socialUserRepository;
private final String userId;
private final ConnectionFactoryLocator connectionFactoryLocator;
private final TextEncryptor textEncryptor;
public SocialUserConnectionRepositoryImpl(String userId, SocialUserRepository socialUserRepository, ConnectionFactoryLocator connectionFactoryLocator, TextEncryptor textEncryptor){
    this.socialUserRepository = socialUserRepository;
    this.userId = userId;
    this.connectionFactoryLocator = connectionFactoryLocator;
    this.textEncryptor = textEncryptor;
}
 ...
public void addConnection(Connection<?> connection) {
try {
   ConnectionData data = connection.createData();
  int rank = socialUserRepository.getRank(userId, data.getProviderId()) ;
  socialUserRepository.create(userId, data.getProviderId(), data.getProviderUserId(), rank, data.getDisplayName(), data.getProfileUrl(), data.getImageUrl(), encrypt(data.getAccessToken()), encrypt(data.getSecret()), encrypt(data.getRefreshToken()), data.getExpireTime()    );
    } catch (DuplicateKeyException e) {
  throw new   DuplicateConnectionException(connection.getKey());
}
}
...
public void removeConnections(String providerId) {
  socialUserRepository.delete(userId,providerId);
}
  ...
}
```

### 注意

实际上，这个自定义实现扩展并调整了[`github.com/mschipperheyn/spring-social-jpa`](https://github.com/mschipperheyn/spring-social-jpa)的工作，该工作是在 GNU GPL 许可下发布的。

1.  正如你所看到的，`SocialUserConnectionRepositoryImpl` 使用了一个自定义的 Spring Data JPA `SocialUserRepository` 接口，其定义如下：

```java
public interface SocialUserRepository {
  List<SocialUser> findUsersConnectedTo(String providerId);
  ...
  List<String> findUserIdsByProviderIdAndProviderUserIds( String providerId, Set<String> providerUserIds);
...
  List<SocialUser> getPrimary(String userId, String providerId);
  ...
  SocialUser findFirstByUserIdAndProviderId(String userId, String providerId);
}
```

1.  这个 Spring Data JPA 存储库支持我们创建的`SocialUser`实体（社交连接）。这个实体是`JdbcUsersConnectionRepository`期望找到的`UserConnection` SQL 表的直接模型，如果我们使用这个实现而不是我们自己的实现。`SocialUser`的定义如下代码：

```java
@Entity
@Table(name="userconnection", uniqueConstraints = {@UniqueConstraint(columnNames = { ""userId", "providerId", "providerUserId" }), 
@UniqueConstraint(columnNames = { "userId", "providerId", "rank" })})
public class SocialUser {
  @Id
  @GeneratedValue
  private Integer id;

  @Column(name = "userId")
  private String userId;

  @Column(nullable = false)
  private String providerId;
  private String providerUserId;

  @Column(nullable = false)
  private int rank;
  private String displayName;
  private String profileUrl;
  private String imageUrl;

  @Lob
  @Column(nullable = false)
  private String accessToken;
  private String secret;
  private String refreshToken;
  private Long expireTime;
  private Date createDate = new Date();
  //+ getters / setters
  ...
} 
```

1.  `SocialUserConnectionRepositoryImpl` 在更高级别的服务层中实例化：`SocialUserServiceImpl`，这是 Spring `UsersConnectionRepository`接口的实现。该实现如下创建：

```java
@Transactional(readOnly = true)
public class SocialUserServiceImpl implements SocialUserService {
   @Autowired
   private SocialUserRepository socialUserRepository;
  @Autowired
   private ConnectionFactoryLocator connectionFactoryLocator;
  @Autowired
  private UserRepository userRepository;
  private TextEncryptor textEncryptor = Encryptors.noOpText();
public List<String> findUserIdsWithConnection(Connection<?> connection) {
   ConnectionKey key = connection.getKey();
  return socialUserRepository. findUserIdsByProviderIdAndProviderUserId(key.getProviderId(), key.getProviderUserId());
}
public Set<String> findUserIdsConnectedTo(String providerId, Set<String> providerUserIds) {
    return Sets.newHashSet(socialUserRepository.findUserIdsByProviderIdAndProviderUserIds(providerId, providerUserIds));
}
public ConnectionRepository createConnectionRepository(String userId) {
  if (userId == null) {
    throw new IllegalArgumentException"("userId cannot be null"");
  }
  return new SocialUserConnectionRepositoryImpl(
      userId,
      socialUserRepository,
      connectionFactoryLocator,
      textEncryptor);
}
 	...
}
```

1.  这个更高级别的`SocialUserServiceImpl`在`cloudstreetmarket-api` Spring 配置文件（`dispatcher-context.xml`）中注册为一个工厂 bean，具有在请求范围内（对于特定的社交用户配置文件）生成`SocialUserConnectionRepositoryImpl`的能力。代码如下：

```java
<bean id="usersConnectionRepository" class="edu.zc.csm.core.services.SocialUserServiceImpl"/>
<bean id="connectionRepository" factory-method="createConnectionRepository" factory-bean="usersConnectionRepository" scope"="request">
  <constructor-arg value="#{request.userPrincipal.name}"/>
  <aop:scoped-proxy proxy-target-class"="false"" />
</bean>
```

1.  在`dispatcher-context.xml`文件中定义了另外三个 bean：

```java
<bean id="signInAdapter" class="edu.zc.csm.api.signin.SignInAdapterImpl"/>
<bean id="connectionFactoryLocator" 
  class="org.sfw.social.connect.support. ConnectionFactoryRegistry">
  <property name="connectionFactories">
    <list>
    <bean class"="org.sfw.social.yahoo.connect.YahooOAuth2ConnectionFactory"">
      <constructor-arg value="${yahoo.client.token}"/>
      <constructor-arg value="${yahoo.client.secret}" />
      <constructor-arg value="${yahoo.signin.url}" />
    </bean>
    </list>
  </property>
</bean>
<bean class="org.sfw.social.connect.web.ProviderSignInController">
  <constructor-arg ref="connectionFactoryLocator"/>
  <constructor-arg ref="usersConnectionRepository"/>
  <constructor-arg ref="signInAdapter"/>
  <property name="signUpUrl" value="/signup"/>
  <property name="postSignInUrl" value="${frontend.home.page.url}"/>
</bean>
```

1.  `SignInAdapterImpl`在我们的应用程序中对 OAuth2 认证后登录用户。从应用程序业务角度来看，它执行我们希望在这一步执行的操作。代码如下：

```java
@Transactional(propagation = Propagation.REQUIRED)
@PropertySource("classpath:application.properties")
public class SignInAdapterImpl implements SignInAdapter{
  @Autowired
  private UserRepository userRepository;
  @Autowired
  private CommunityService communityService;
  @Autowired
  private SocialUserRepository socialUserRepository;
  @Value("${oauth.success.view}")
  private String successView;
  public String signIn(String userId, Connection<?> connection, NativeWebRequest request) {
      User user = userRepository.findOne(userId);
      String view = null;
      if(user == null){
        //temporary user for Spring Security
        //won't be persisted
        user = new User(userId, communityService.generatePassword(), null, true, true, true, true, communityService.createAuthorities(newRole[]{Role.ROLE_BASIC, Role.ROLE_OAUTH2}));
    }
    else{
        //We have a successful previous oAuth 	//authentication
        //The user is already registered
        //Only the guid is sent back
        List<SocialUser> socialUsers = 
        socialUserRepository. findByProviderUserIdOrUserId(userId, userId);
        if(CollectionUtils.isNotEmpty(socialUsers)){
          //For now we only deal with Yahoo!
          view = successView.concat(
            "?spi=" + socialUsers.get(0) .getProviderUserId());
    }
    }
    communityService.signInUser(user);
    return view;
  }
}
```

1.  `connectionFactoryLocator`也可以引用多个连接工厂。在我们的情况下，我们只有一个：`YahooOAuth2ConnectionFactory`。这些类是社交提供商 API 的入口点（为 Java 编写）。我们通常可以在网络上找到它们（来自官方来源或其他来源），以满足我们的 OAuth 协议目标（OAuth1、OAuth1.0a 和 OAuth2）。

### 注意

目前对于 Yahoo!来说，现有的 OAuth2 适配器很少。我们不得不自己做。这就是为什么这些类作为源代码而不是作为 jar 依赖项（在 Zipcloud 项目中）可用的原因。

1.  在控制器声明方面，`dispatcher-context.xml`配置了一个`ProviderSignInController`，它在`Spring Social Core`中完全抽象。然而，为了在我们的应用程序中注册 OAuth2 用户（用户第一次访问网站时），我们创建了一个自定义的`SignUpController`：

```java
@Controller
@RequestMapping"("/signup"")
@PropertySource"("classpath:application.properties"")
public class SignUpController extends CloudstreetApiWCI{
  @Autowired
  private CommunityService communityService;
  @Autowired
  private SignInAdapter signInAdapter;
  @Autowired
  private ConnectionRepository connectionRepository;
  @Value("${oauth.signup.success.view}")
  private String successView;
  @RequestMapping(method = RequestMethod.GET)
  public String getForm(NativeWebRequest request, @ModelAttribute User user) {
    String view = successView;
    // check if this is a new user signing in via //Spring Social
    Connection<?> connection = ProviderSignInUtils.getConnection(request);
      if (connection != null) {
        // populate new User from social connection //user profile
        UserProfile userProfile = connection.fetchUserProfile();
        user.setUsername(userProfile.getUsername());
        // finish social signup/login
        ProviderSignInUtils. handlePostSignUp(user.getUsername(), request);
        // sign the user in and send them to the user //home page
        signInAdapter.signIn(user.getUsername(), connection, request);
      view += ?spi=+ user.getUsername();
    }
    return view;
  }
}
```

1.  现在是时候试一试了。为了继续，我们建议您创建一个 Yahoo!账户。我们实际上并不是雅虎的赞助商。这只是为了我们伟大的 Zipcloud 公司的战略，该公司以金融服务为导向。这不仅仅是为了玛丽莎·梅耶尔的蓝眼睛！（[`login.yahoo.com`](https://login.yahoo.com)）。

1.  启动 Tomcat 服务器，然后单击主菜单最右侧的登录按钮。然后点击**使用 Yahoo!登录**按钮

1.  您应该被重定向到 Yahoo!服务器，以便您在他们的一侧进行身份验证（如果您尚未登录）：![如何做...](img/image00868.jpeg)

1.  登录后，同意 Cloudstreet Market 将能够访问您的个人资料和联系人。我们不会使用联系人；但是，我们有 Java 适配器来访问它们。如果这太可怕了，只需创建一个空的新 Yahoo!账户：![如何做...](img/image00869.jpeg)

1.  单击**同意**按钮。

1.  Yahoo!现在应该重定向到本地的`cloudstreetmarket.com`服务器，特别是到`/api/signin/yahoo`处理程序，并带有授权码作为 URL 参数。

1.  应用程序检测到`Cloudstreet Market`数据库中没有为`SocialUser`注册的`User`。这将触发以下弹出窗口，并应该一直返回给用户，直到账户实际上被创建：![如何做...](img/image00870.jpeg)

1.  用以下数据填写表格：

```java
username: <marcus>
email: <marcus@chapter5.com>
password: <123456>
preferred currency: <USD>
```

此外，单击用户图标以上传个人资料图片（如果需要）。在这样做时，请确保`cloudstreetmarket-api/src/main/resources/application.properties`中的`pictures.user.path`属性指向文件系统上创建的路径。

1.  完成此步骤后，欢迎页面上应该出现新的公共活动**Marcus 注册了一个新账户**。

1.  此外，与 API 的每个 REST 响应绑定，额外的头部**Authenticated**和**WWW-Authenticate**必须存在。这证明我们在应用程序中具有 OAuth2 功能的身份验证。![如何做...](img/image00871.jpeg)

## 它是如何工作的...

在这个配方中，我们在我们的应用程序中进行了社交集成。OAuth2 认证涉及服务提供商（cloudstreetmarket.com）和身份提供商（Yahoo!）。

只有当用户拥有（或准备拥有）双方账户时才能发生这种情况。这是一种非常流行的身份验证协议。由于大多数互联网用户至少在主要的社交 SaaS 提供商（Facebook、Twitter、LinkedIn、Yahoo!等）中拥有一个账户，这种技术大大减少了在网络服务提供商上花费的注册时间和登录时间。

### 从应用程序的角度来看

当用户点击“使用 Yahoo!登录”按钮时，将向我们的 API 处理程序`/api/signin/yahoo`发出 HTTP POST 请求。这个处理程序对应于`ProviderSignInController`，由`Spring Social`抽象。

+   这个处理程序将用户重定向到 Yahoo!服务器，用户可以在那里进行身份验证，并授权应用程序使用他的社交身份和访问他的一些 Yahoo!数据。

+   Yahoo!将授权码作为重定向到回调 URL 的参数发送给应用程序。

+   应用程序使用授权码作为参数处理回调。此回调针对抽象的`ProviderSignInController`中的不同方法处理程序。这个处理程序完成连接，回调 Yahoo!以交换授权码和**刷新令牌**和**访问令牌**。这个操作在`Spring Social`后台透明地完成。

+   相同的处理程序在数据库中查找该用户的现有持久化社交连接：

+   如果找到一个连接，用户将在`Spring Security`中进行身份验证，并被重定向到门户的首页，Yahoo!用户 ID 作为请求参数（参数名为`spi`）。

+   如果找不到连接，用户将被重定向到`SignupController`，在那里创建和持久化他的连接。然后在 Spring Security 中进行身份验证，并被重定向到门户的首页，Yahoo!用户 ID 作为请求参数（名为`spi`）。

+   当加载门户首页时，检测到 Yahoo!用户 ID 请求参数，并将该标识符存储在 HTML5 的`sessionStorage`中（我们已经完成了所有这些）。

+   从现在开始，在用户向 API 发出的每个单独的 AJAX 请求中，`spi`标识符将作为请求头传递，直到用户实际注销或关闭浏览器。

### 从 Yahoo!的角度来看

Yahoo! API 提供了两种 OAuth2 认证方式。这导致了两种不同的流程：适用于服务器端（Web）应用程序的显式 OAuth2 流程，以及特别适用于前端 Web 客户端的隐式 OAuth2 流程。我们将重点介绍实现的显式流程。

#### OAuth2 显式授权流程

这是我们的应用程序和 Yahoo!之间通信协议的摘要图片。这更或多或少是一个标准的 OAuth2 对话：

![OAuth2 显式授权流程](img/image00872.jpeg)

在通信中带有`*`符号标记的参数是可选的。这个流程也在 OAuth2 Yahoo!指南中有详细说明：

[`developer.yahoo.com/oauth2/guide/flows_authcode`](https://developer.yahoo.com/oauth2/guide/flows_authcode)

#### 刷新令牌和访问令牌

必须理解这两个令牌之间的区别。访问令牌用于在 Yahoo! API 上执行操作时识别用户（Yahoo!用户）。例如，下面是一个可以执行的 GET 请求的示例，用于检索由 Yahoo! ID abcdef123 标识的用户的 Yahoo!个人资料：

```java
GET https://social.yahooapis.com/v1/user/abcdef123/profile
Authorization: Bearer aXJUKynsTUXLVY 
```

为了对这个调用提供标识，**访问令牌**必须作为`Authorization`请求头的值传递，带有`Bearer`关键字。一般来说，访问令牌的生命周期非常有限（对于 Yahoo!来说，它是一个小时）。

刷新令牌用于请求新的访问令牌。刷新令牌的生命周期更长（对于 Yahoo!来说，它们实际上永远不会过期，但可以被撤销）。

### Spring social - 角色和关键特性

Spring social 的作用是与 Facebook、Twitter 或 Yahoo!等“软件即服务”（SaaS）提供商建立连接。Spring social 还负责代表用户在应用程序（Cloudstreet Market）服务器端调用 API。

这两个职责都在 spring-social-core 依赖中使用“连接框架”和 OAuth 客户端支持来实现。

简而言之，Spring social 是：

+   一个处理与服务提供商的核心授权和连接流程的“连接框架”

+   一个“连接控制器”，处理 Web 应用环境中服务提供商、消费者和用户之间的 OAuth 交换

+   一个“登录控制器”，允许用户在我们的应用程序中进行身份验证，使用他们的 Saas 提供商账户登录

### 社交连接持久性

Spring social core 提供了能够使用 JDBC 在数据库中持久化社交连接的类（特别是使用`JdbcUsersConnectionRepository`）。该模块甚至嵌入了用于模式定义的 SQL 脚本：

```java
create table UserConnection (userId varchar(255) not null,
    providerId varchar(255) not null,
    providerUserId varchar(255),
    rank int not null,
    displayName varchar(255),
    profileUrl varchar(512),
    imageUrl varchar(512),
    accessToken varchar(255) not null,
    secret varchar(255),
    refreshToken varchar(255),
    expireTime bigint,
    primary key (userId, providerId, providerUserId));
create unique index UserConnectionRank on UserConnection(userId, providerId, rank);
```

当应用程序（比如我们的应用）使用 JPA 时，可以创建一个实体来表示持久化上下文中的表。我们在配方的第六步中为此目的创建了`SocialUser`实体。

在这个表实体中，你可以看到以下字段：

+   `userId`：这个字段匹配用户注册时的`@Id`（用户名）。`userId`是 GUID（Yahoo！用户 ID，在 Web 端也称为`spi`），如果用户尚未注册。

+   `providerId`：这个字段是提供商的小写名称：Yahoo，Facebook 或 Twitter。

+   `providerUserId`：这个字段是提供商系统中的 GUID，即唯一标识符（Yahoo！用户 ID 或“spi”）。

+   “accessToken，secret，refreshToken 和 expireTime”：这些是连接的 OAuth2 令牌（凭证）及其相关信息。

框架附带了两个接口：

+   `ConnectionRepository`：这个管理一个用户连接的持久化。实现是为了识别用户的请求范围。

+   `UsersConnectionRepository`：这提供了对所有用户的全局连接存储的访问。

如果你记得的话，我们创建了我们自己的`UsersConnectionRepository`实现（`SocialUserServiceImpl`）。在`dispatcher-servlet.xml`文件中注册，这个实现充当一个工厂，用于生成请求范围的`connectionRepository`实现（`SocialUserConnectionRepositoryImpl`）：

```java
<bean id="connectionRepository" factory-method="createConnectionRepository" factory-bean="usersConnectionRepository" scop="request">
  <constructor-arg value="#{request.userPrincipal.name}" />
  <aop:scoped-proxy proxy-target-class="false" />
</bean>
<bean id="usersConnectionRepository" class="edu.zc.csm.core.services.SocialUserServiceImpl"/>
```

这两个自定义实现都使用了我们为查找、更新、持久化和移除连接创建的 Spring Data JPA`SocialUserRepository`。

在`SocialUserServiceImpl`实现`UsersConnectionRepository`接口时，一个`ConnectionFactoryLocator`属性被`autowired`，并且一个`TextEncryptor`属性被初始化为默认的`NoOpTextEncryptor`实例。

### 注意

默认的`TextEncryptor`实例可以被适当的加密替换，用于在数据库中维护的 SocialUser 数据。查看 spring-security-crypto 模块：

[`docs.spring.io/spring-security/site/docs/3.1.x/reference/crypto.html`](http://docs.spring.io/spring-security/site/docs/3.1.x/reference/crypto.html)

### 特定于提供商的配置

特定于提供商的配置（Facebook，Twitter，Yahoo！）从`connectionFactoryLocator` bean 的定义开始。

#### 一个入口点 - connectionFactoryLocator

我们在`dispatcher-servlet.xml`中定义的`connectionFactoryLocator` bean 在 Spring Social 中扮演着一个核心角色。它的注册如下：

```java
<bean id="connectionFactoryLocator" class="org.sfw.social.connect.support.ConnectionFactoryRegistry">
  <property name="connectionFactories">
    <list>
    <bean class"="org.sfw.social.yahoo.connect. YahooOAuth2ConnectionFactory"">
        <constructor-arg value="${yahoo.client.token}" />
        <constructor-arg value="${yahoo.client.secret}" />
        <constructor-arg value="${yahoo.signin.url}" />
      </bean>
    </list>
  </property>
</bean>
```

有了这个 bean，Spring social 实现了一个`ServiceLocator`模式，允许我们轻松地插入/拔出新的社交连接器。最重要的是，它允许系统在运行时解析特定于提供商的连接器（一个`connectionFactory`）。

我们的`connectionFactoryLocator`的指定类型是`ConnectionFactoryRegistry`，这是`ConnectionFactoryLocator`接口的提供的实现：

```java
public interface ConnectionFactoryLocator {
    ConnectionFactory<?> getConnectionFactory(String providerId);
    <A> ConnectionFactory<A> getConnectionFactory(Class<A> apiType);
    Set<String> registeredProviderIds();
}
```

我们在`ProviderSignInController.signin`方法中有一个`connectionFactory`查找的示例：

```java
ConnectionFactory<?> connectionFactory = connectionFactoryLocator.getConnectionFactory(providerId);
```

在这里，`providerId`参数是一个简单的字符串（在我们的例子中是 yahoo）。

#### 特定于提供者的 ConnectionFactories

`ConnectionFactory`，如`YahooOAuth2ConnectionFactory`，在`ConnectionFactoryRegistry`中注册了 OAuth2 消费者密钥和消费者密钥，这些密钥（通过授权）在提供者端标识了我们的应用程序。

我们已经开发了`YahooOAuth2ConnectionFactory`类，但您应该能够从官方的`Spring Social`子项目（`spring-social-facebook`，`spring-social-twitter`等）或开源项目中找到您的`ProviderSpecificConnectionFactory`。

#### 使用提供者帐户登录

为了执行 OAuth2 认证步骤，Spring social 提供了一个抽象的 Spring MVC 控制器：`ProviderSignInController`。

这个控制器执行 OAuth 流程并与提供者建立连接。它尝试找到先前建立的连接，并使用连接的帐户来验证应用程序中的用户。

如果没有匹配的先前连接，流程将发送到创建的`SignUpController`，匹配特定的请求映射`/signup`。此时，用户不会自动注册为 CloudStreetMarket 的`User`。当 API 调用出现 OAuth2 认证但没有绑定本地用户时，我们会强制用户通过`Must-Register`响应头手动创建他的帐户。这个`Must-Register`响应头会在客户端触发**立即创建帐户**弹出窗口（请参见`home_community_activity.js`中的`loadMore`函数）。

就是在这个注册过程中，连接（`SocialUser`实体）与创建的`User`实体同步（请参见`CommunityController.createUser`方法）。

`ProviderSignInController`与`SignInAdapter`实现密切配合（我们也必须构建），实际上使用 Spring Security 将用户验证到 CloudStreetMarket。通过调用`communityService.signInUser(user)`触发验证。

以下是创建`Authentication`对象并将其存储到`SecurityContext`的方法的详细信息：

```java
@Override
public Authentication signInUser(User user) {
  Authentication authentication = new UsernamePasswordAuthenticationToken(user, user.getPassword(), user.getAuthorities());
  SecurityContextHolder.getContext().setAuthentication(authentication);
  return authentication;
}
```

我们使用以下配置为`ProviderSigninController`注册和初始化 Spring bean：

```java
<bean class"="org.sfw.social.connect.web.ProviderSignInController"">
  <constructor-arg ref="connectionFactoryLocator"/>
  <constructor-arg ref="usersConnectionRepository"/>
  <constructor-arg ref="signInAdapter"/>
  <property name="signUpUrl"" value"="/signup"/>
  <property name="postSignInUrl" value="${frontend.home.page.url}"/>
</bean>
```

正如您所看到的，我们已将`signUpUrl`请求映射指定为在数据库中找不到先前连接时重定向到我们自定义的`SignupController`。

或者，指定的`postSignInUrl`允许用户在`ProviderSignInController`解析现有连接以重用时重定向到门户的主页。

## 还有更多...

让我们来看看 Spring social 的其他特性。

### 执行经过身份验证的 API 调用

在本教程中，我们专注于介绍 OAuth2 客户端认证过程。在下一章中，我们将看到如何使用 Spring social 代表用户对 Yahoo! API 执行请求。我们将看到如何在此目的中使用现有库以及它们的工作原理。在我们的案例中，我们不得不开发 API 连接器到 Yahoo!金融 API。

### Spring social ConnectController

Spring social web 提供了另一个抽象的控制器，允许社交用户直接与他们的社交连接进行交互，连接、断开连接并获取他们的连接状态。`ConnectController`也可以用于构建一个交互式监控屏幕，用于管理站点可能处理的所有提供者的连接。查看 Spring social 参考了解更多详情：

[`docs.spring.io/spring-social/docs/current/reference/htmlsingle/#connecting`](http://docs.spring.io/spring-social/docs/current/reference/htmlsingle/#connecting)

## 另请参阅

### SocialAuthenticationFilter

这是一个要添加到 Spring Security 中的过滤器，以便可以从 Spring Security 过滤器链（而不是像我们之前那样外部地）执行社交认证。

[`docs.spring.io/spring-social/docs/current/reference/htmlsingle/#enabling-provider-sign-in-with-code-socialauthenticationfilter-code`](http://docs.spring.io/spring-social/docs/current/reference/htmlsingle/#enabling-provider-sign-in-with-code-socialauthenticationfilter-code)

### Spring 社交连接器列表

您将在项目的主页上找到一系列已实现的 Saas 提供商连接器：[`projects.spring.io/spring-social`](http://projects.spring.io/spring-social)

### 实现 OAuth2 认证服务器

您可以使用 Spring Security OAuth 项目：

[`projects.spring.io/spring-security-oauth`](http://projects.spring.io/spring-security-oauth)

### 和谐发展博客

关于 Spring 社交的文章启发了这个配方。欢迎访问这个博客：

[`harmonicdevelopment.tumblr.com/post/13613051804/adding-spring-social-to-a-spring-mvc-and-spring`](http://harmonicdevelopment.tumblr.com/post/13613051804/adding-spring-social-to-a-spring-mvc-and-spring)

# 在 REST 环境中存储凭据

这个配方提供了在 RESTful 应用程序中存储凭据的解决方案。

## 准备工作

这个解决方案是临时客户端存储和永久服务器端存储之间的折衷。

在客户端，我们使用 HTML5 会话存储来临时存储以 base 64 编码的用户名和密码。在服务器端，只有密码的哈希值被存储。这些哈希值是使用`passwordEncoder`创建的。这个`passwordEncoder`被注册在 Spring Security 中，自动装配，并在`UserDetailsService`实现中使用。

## 如何做...

### 客户端（AngularJS）

1.  我们已经使用了 HTML5 的`sessionStorage`属性。主要的变化是创建了一个`httpAuth`工厂。这个工厂在`http_authorized.js`文件中呈现，它是一个围绕`$http`的包装器，用于透明地处理客户端存储和身份验证头。这个工厂的代码如下：

```java
cloudStreetMarketApp.factory("httpAuth", function ($http) {
  return {
    clearSession: function () {
      var authBasicItem = sessionStorage.getItem('basicHeaderCSM');
      var oAuthSpiItem = sessionStorage.getItem('oAuthSpiCSM');
    if(authBasicItem || oAuthSpiItem){
      sessionStorage.removeItem('basicHeaderCSM');
      sessionStorage.removeItem('oAuthSpiCSM');
      sessionStorage.removeItem('authenticatedCSM');
      $http.defaults.headers.common.Authorization = undefined;
      $http.defaults.headers.common.Spi = undefined;
      $http.defaults.headers.common.OAuthProvider = undefined;
  }
  },
  refresh: function(){
    var authBasicItem = sessionStorage.getItem('basicHeaderCSM');
    var oAuthSpiItem = sessionStorage.getItem('oAuthSpiCSM');
    if(authBasicItem){
      $http.defaults.headers.common.Authorization = 
      $.parseJSON(authBasicItem).Authorization;
      }
      if(oAuthSpiItem){
        $http.defaults.headers.common.Spi = oAuthSpiItem;
        $http.defaults.headers.common.OAuthProvider = "yahoo";
    }
    },
    setCredentials: function (login, password) {
    //Encodes in base 64
    var encodedData = window.btoa(login+":"+password);
    var basicAuthToken = 'Basic '+encodedData;
    var header = {Authorization: basicAuthToken};
    sessionStorage.setItem('basicHeaderCSM', JSON.stringify(header));
    $http.defaults.headers.common.Authorization = basicAuthToken;
  },
  setSession: function(attributeName, attributeValue) {
    sessionStorage.setItem(attributeName, attributeValue);
  },
  getSession: function (attributeName) {
    return sessionStorage.getItem(attributeName);
  },
  post: function (url, body) {
    this.refresh();
  return $http.post(url, body);
  },
  post: function (url, body, headers, data) {
    this.refresh();
    return $http.post(url, body, headers, data);
  },
  get: function (url) {
    this.refresh();
    return $http.get(url);
  },
  isUserAuthenticated: function () {
    var authBasicItem = sessionStorage.getItem('authenticatedCSM');
  if(authBasicItem){
    return true;
    }
  return false;
  }
}});
```

1.  这个工厂在以前的地方（或几乎在所有地方）被调用，用于传递和处理 AJAX 请求所需的凭据或身份验证头。

1.  我们已经避免直接处理不同控制器中的`sessionStorage`属性，以防止与这个存储解决方案紧密耦合。

1.  `account_management.js`文件汇集了不同的控制器（`LoginByUsernameAndPasswordController`、`createNewAccountController`和`OAuth2Controller`），通过`httpAuth`将凭据和提供商 ID 存储在`sessionStorage`中。

1.  一些工厂也已经被修改，通过`httpAuth`工厂来拉取和推送数据。例如，`indiceTableFactory`（来自`home_financial_table.js`）透明地处理凭据来请求市场的指数：

```java
cloudStreetMarketApp.factory("indicesTableFactory", function (httpAuth) {
    return {
        get: function (market) {
        return httpAuth.get("/api/indices/" + market + ".json?ps=6");
        }
    }
});
```

### 服务器端

1.  我们在`security-config.xml`（在`cloudstreetmarket-core`模块中）中声明了一个`passwordEncoder` bean：

```java
<bean id="passwordEncoder" 
  class="org.sfw.security.crypto.bcrypt.BCryptPasswordEnco  der"/>
```

1.  在`security-config.xml`中，我们在`authenticationProvider`中做了对`password-encoder`的引用。

```java
<security:authentication-manager alias"="authenticationManager">
  <security:authentication-provider user-service-ref='communityServiceImpl'>
    <security:password-encoder ref="passwordEncoder"/>
  </security:authentication-provider>
</security:authentication-manager>
```

1.  `passwordEncoder` bean 在`CommunityServiceImpl`（我们的`UserDetailsService`实现）中被自动装配。在这里，当账户被注册时，密码会被哈希化。存储的哈希值然后与用户提交的密码进行比较，当用户尝试登录时。`CommunityServiceImpl`的代码如下：

```java
@Service(value="communityServiceImpl")
@Transactional(propagation = Propagation.REQUIRED)
public class CommunityServiceImpl implements CommunityService {
  @Autowired
  private ActionRepository actionRepository;	
  ...
  @Autowired
  private PasswordEncoder passwordEncoder;
  ...
  @Override
  public User createUser(User user, Role role) {
    if(findByUserName(user.getUsername()) != null){
      throw new ConstraintViolationException("The provided user name already exists!", null, null);
     }
    user.addAuthority(new Authority(user, role));
    user.addAction(new AccountActivity(user, UserActivityType.REGISTER, new Date()));
    user.setPassword(passwordEncoder. encode(user.getPassword()));
    return userRepository.save(user);
  }
  @Override
  public User identifyUser(User user) {
    Preconditions.checkArgument(user.getPassword() != null, "The provided password cannot be null!");
   Preconditions.checkArgument( StringUtils.isNotBlank(user.getPassword()), "The provided password cannot be empty!");
    User retreivedUser = userRepository.findByUsername(user.getUsername());
    if(!passwordEncoder.matches(user.getPassword(), retreivedUser.getPassword())){
      throw new BadCredentialsException"("No match has been found with the provided credentials!");
    }
  return retreivedUser;
  }
  ...
}
```

1.  我们的`ConnectionFactory`实现`SocialUserConnectionRepositoryImpl`在`SocialUserServiceImpl`中被实例化，使用 Spring 的`TextEncryptor`实例。这使得可以加密 OAuth2 的存储连接数据（最重要的是访问令牌和刷新令牌）。目前，这些数据在我们的代码中没有加密。

## 它是如何工作的...

在这一章中，我们试图保持我们的 RESTful API 的无状态性，以获得它所提供的好处（可扩展性、易部署、容错性等）。

### 微服务认证

保持无状态符合微服务的一个关键概念：我们的模块的自给自足。我们不会使用粘性会话来实现可扩展性。当状态被维护时，仅由客户端保留，有限时间内保留用户的标识和/或凭据。

微服务的另一个关键概念是有限和确定的责任（水平可扩展性）的概念。即使应用程序的大小不需要领域分割，我们的设计也支持这一原则。我们完全可以想象按领域（社区、指数和股票、监控等）拆分我们的 API。Spring Security 位于核心模块中，可以在每个 API war 中嵌入而不会出现任何问题。

让我们专注于客户端如何维护状态。我们为用户提供了两种登录方式：使用基本方案或使用 OAuth2。

+   用户可以为基本认证注册帐户，然后决定以 OAuth2 登录（为此，他必须将他的社交帐户绑定到他现有的帐户）。

+   或者，用户可以使用 OAuth2 注册他的帐户，然后以基本表单登录。他的 OAuth2 凭据自然会绑定到他的身份验证。

### 使用基本认证

当用户注册帐户时，他定义了用户名和密码。这些凭据使用`httpAuth`工厂和`setCredentials`方法存储。

在`account_management.js`文件中，特别是在`createNewAccountController`（通过`create_account_modal.html`模态调用），`setCredentials`调用可以在`createAccount`方法的成功处理程序中找到：

```java
httpAuth.setCredentials($scope.form.username, $scope.form.password);
```

目前，该方法使用 HTML5 的`sessionStorage`作为存储设备：

```java
setCredentials: function (login, password) {
  var encodedData = window.btoa(login"+":"+password);
  var basicAuthToken = 'Basic '+encodedData;
  var header = {Authorization: basicAuthToken};
  sessionStorage.setItem('basicHeaderCSM', JSON.stringify(header));
  $http.defaults.headers.common.Authorization = basicAuthToken;
}
```

`window.btoa(...)`函数对提供的字符串进行 base64 编码。`$httpProvider.defaults.headers`配置对象也添加了一个新的标头，可能会被下一个 AJAX 请求使用。

当用户使用基本表单登录（也可以参见`account_management.js`和特别是从`auth_modal.html`模态调用的`LoginByUsernameAndPasswordController`）时，用户名和密码也是使用相同的方法存储的：

```java
httpAuth.setCredentials($scope.form.username, $scope.form.password);
```

现在，通过`httpAuth`抽象层，我们确保每次使用`$http`进行 API 调用时都设置了**Authorization**标头。

![使用基本认证](img/image00873.jpeg)

#### 使用 OAuth2

从`auth_modal.html`发起，使用 OAuth2 登录会创建一个 POST HTTP 请求到 API 处理程序`/api/signin/yahoo`（此处理程序位于抽象的`ProviderSignInController`中）。

登录请求被重定向到 Yahoo!身份验证屏幕。整个页面都会跳转到 Yahoo!直到完成。当 API 最终将请求重定向到门户的主页时，会添加一个`spi`请求参数：`http://cloudstreetmarket.com/portal/index?spi=F2YY6VNSXIU7CTAUB2A6U6KD7E`

这个`spi`参数是 Yahoo!用户 ID（GUID）。它被`DefaultController`（`cloudstreetmarket-webapp`）捕获并注入到模型中：

```java
@RequestMapping(value="/*", method={RequestMethod.GET,RequestMethod.HEAD})
public String fallback(Model model, @RequestParam(value="spi", required=false) String spi) {
  if(StringUtils.isNotBlank(spi)){
    model.addAttribute("spi", spi);
  }
  return "index";
}
```

`index.jsp`文件直接在顶部菜单的 DOM 中呈现该值：

```java
<div id="spi" class="hide">${spi}</div>
```

当`menuController`（绑定到顶部菜单）初始化自身时，会读取并将该值存储在`sessionStorage`中：

```java
$scope.init = function () {
  if($('#spi').text()){
    httpAuth.setSession('oAuthSpiCSM', $('#spi').text());
  }
}
```

在我们的`httpAuth`工厂（`http_authorized.js`）中，每次调用 API 之前调用的`refresh()`方法都会检查是否存在该值，并添加两个额外的标头：带有 GUID 值的`Spi`和**OAuthProvider**（在我们的情况下是雅虎）。代码如下：

```java
refresh: function(){
  var authBasicItem = sessionStorage.getItem('basicHeaderCSM');
  var oAuthSpiItem = sessionStorage.getItem('oAuthSpiCSM');
  if(authBasicItem){
    $http.defaults.headers.common.Authorization = $.parseJSON(authBasicItem).Authorization;
  }
  if(oAuthSpiItem){
    $http.defaults.headers.common.Spi = oAuthSpiItem;
    $http.defaults.headers.common.OAuthProvider = "yahoo";
  }
}
```

这里的屏幕截图显示了我们的一个 AJAX 请求的这两个标头：

![使用 OAuth2](img/image00874.jpeg)

### HTML5 SessionStorage

我们在客户端使用 SessionStorage 作为用户凭据和社交标识（GUID）的存储解决方案。

在 HTML5 中，网页可以使用 Web Storage 技术在浏览器中本地存储数据。存储在 Web Storage 中的数据可以从页面脚本中访问，值可以相对较大（最多 5MB），对客户端性能没有影响。

Web Storage 是按来源（协议、主机名和端口号的组合）进行的。来自一个来源的所有页面都可以存储和访问相同的数据。有两种类型的对象可以用于本地存储数据：

+   `window.localStorage`：这会存储没有过期日期的数据。

+   `window.sessionStorage`：这会为一个会话存储数据（在标签关闭时数据丢失）。

这两个对象可以直接从 window 对象中访问，并且它们都带有自解释的方法：

```java
setItem(key,value);
getItem(key);
removeItem(key);
clear();
```

根据[`www.w3schools.com/`](http://www.w3schools.com/)，localStorage 现在几乎被所有浏览器支持（根据市场情况在 94%到 98%之间）。以下表格显示了完全支持它的第一个版本：

![HTML5 SessionStorage](img/image00875.jpeg)

我们应该为不兼容的网络浏览器实现一个使用 cookies 的备用选项，或者至少在浏览器看起来过时时显示警告消息。

### SSL/TLS

在使用基本身份验证时必须设置加密通信协议。我们已经看到凭据用户名:密码和 Yahoo! GUID 被发送为请求头。即使这些凭据被编码为 base 64，这也不足以提供足够的保护。

### BCryptPasswordEncoder

在服务器端，我们不以明文形式存储`User`密码。我们只存储它们的编码描述（哈希）。因此，哈希函数被认为是不可逆的。

|   | *"哈希函数是任何可以用于将任意大小的数字数据映射到固定大小数字数据的函数。"* |   |
| --- | --- | --- |
|   | --*维基百科* |

让我们看一下以下映射：

![BCryptPasswordEncoder](img/image00876.jpeg)

这个图表显示了一个将`names`映射到 0 到 15 之间的`integers`的哈希函数。

我们在持久化和更新`Users`时手动调用了`PasswordEncoder`实现。`PasswordEncoder`也是 Spring Security 核心的一个接口。

```java
public interface PasswordEncoder {
  String encode(CharSequence rawPassword);
  boolean matches(CharSequence rawPassword, String encodedPassword);
}
```

Spring Security 提供了三种实现：`StandardPasswordEncoder`，`NoOpPasswordEncoder`和`BCryptPasswordEncoder`。

我们在新项目中推荐使用`BCryptPasswordEncoder`。`BCryptPasswordEncoder`使用更强大的哈希算法和随机生成的`salt`，而不是实现 MD5 或 SHA 哈希算法。

这允许为相同密码存储不同的哈希值。以下是`123456`值的不同`BCrypt`哈希的示例：

```java
$2a$10$Qz5slUkuV7RXfaH/otDY9udROisOwf6XXAOLt4PHWnYgOhG59teC6
$2a$10$GYCkBzp2NlpGS/qjp5f6NOWHeF56ENAlHNuSssSJpE1MMYJevHBWO
$2a$10$5uKS72xK2ArGDgb2CwjYnOzQcOmB7CPxK6fz2MGcDBM9vJ4rUql36
```

## 还有更多...

### 使用 AngularJS 设置 HTTP 头

由于我们已经设置了头部，请查看以下页面以获取有关使用 AngularJS 管理头部的更多信息：

[`docs.angularjs.org/api/ng/service/$http`](https://docs.angularjs.org/api/ng/service/%24http)

### localStorage 的浏览器支持

了解每个浏览器版本的整体支持情况：

[`caniuse.com/#search=localstorage`](http://caniuse.com/#search=localstorage)

### 关于 SSL 和 TLS

我们在生产服务器上安装了 SSL 证书。为了购买和颁发 SSL 证书，我们必须提供我们的 Web 服务器类型（Apache 2）和从 keytool 程序（嵌入在 JDK 中）生成的**证书签名请求**（**CSR**）。

+   [`arstechnica.com/information-technology/2012/11/securing-your-web-server-with-ssltls/`](http://arstechnica.com/information-technology/2012/11/securing-your-web-server-with-ssltls/)

+   [`en.wikipedia.org/wiki/Certificate_signing_request`](http://en.wikipedia.org/wiki/Certificate_signing_request)

+   [`www.namecheap.com/support/knowledgebase/article.aspx/9422/0/tomcat-using-keytool`](https://www.namecheap.com/support/knowledgebase/article.aspx/9422/0/tomcat-using-keytool)

# 对服务和控制器进行授权

在这个示例中，我们根据授予用户的权限限制对服务和控制器的访问。

## 准备工作

我们将在特定的 URL 路径和方法调用上安装拦截器，这将触发预定义的授权工作流程：`AbstractSecurityInterceptor`工作流程。

为了测试这些服务的限制，我们还稍微定制了 Swagger UI，以便在基本身份验证下使用它。

## 如何做...

1.  我们为这个新版本更新了我们的`CustomBasicAuthenticationEntryPoint`类，允许在从 Swagger UI 发出调用时提示浏览器原生的基本表单：

```java
public class CustomBasicAuthenticationEntryPoint extends BasicAuthenticationEntryPoint {
  @Override
  public void commence(HttpServletRequest request, HttpServletResponse response, AuthenticationException authException) throws IOException, ServletException {
    String referer = (String) request.getHeader("referer");
    if(referer != null && referer.contains(SWAGGER_UI_PATH)){
      super.commence(request, response, authException);
      return;
    }
    response.setHeader("WWW-Authenticate", "CSM_Basic realm=\" + getRealmName() + \");
    response.sendError( HttpServletResponse.SC_UNAUTHORIZED, authException.getMessage());
  }
}
```

1.  我们创建了一个`MonitoringController`（一个`RestController`），它提供了管理用户以进行管理目的的可能性。

1.  `GET`方法直接返回`User`对象（而不是`UserDTO`），其中包含有关用户的所有数据。此外，此位置还显示了一个`delete`方法。`MonitoringController`代码如下：

```java
@RestController
@RequestMapping(value="/monitoring", 	produces={"application/xml", "application/json"})
@PreAuthorize("hasRole('ADMIN')")
public class MonitoringController extends CloudstreetApiWCI{
  @Autowired
  private CommunityService communityService;
  @Autowired
  private SocialUserService socialUserService;
  @RequestMapping(value="/users/{username}", method=GET)
  @ResponseStatus(HttpStatus.OK)
  @ApiOperation(value = "Details one account", notes = )
  public User getUserDetails(@PathVariable String username){
    return communityService.findOne(username);
  }
  @RequestMapping(value="/users/{username}", method=DELETE)
  @ResponseStatus(HttpStatus.OK)
  @ApiOperation(value = "Delete user account", notes =)
  public void deleteUser(@PathVariable String username){
    communityService.delete(username);
  }
  @RequestMapping(value="/users", method=GET)
  @ResponseStatus(HttpStatus.OK)
  @ApiOperation(value = "List user accounts", notes =)
  public Page<User> getUsers(@ApiIgnore @PageableDefault(size=10, page=0) Pageable pageable){
    return communityService.findAll(pageable);
  }
}
```

1.  在`communityService`实现中，两个使用的方法（`findAll`，`delete`）已被保护：

```java
  @Override
  @Secured({"ROLE_ADMIN", "ROLE_SYSTEM"})
  public void delete(String userName) {
    userRepository.delete(userName);
  }
  @Override
  @Secured("ROLE_ADMIN")
  public Page<User> findAll(Pageable pageable) {
    return userRepository.findAll(pageable);
  }
```

1.  作为提醒，我们在`security-config.xml`中设置了全局方法安全性：

```java
<security:global-method-security secured-annotations"="enabled"" pre-post-annotations"="enabled"" authentication-manager-ref"="authenticationManager""/>
```

1.  现在让我们试一下。重新启动 Tomcat，并在您喜欢的浏览器中打开一个新窗口。打开**Swagger UI**（`http://cloudstreetmarket.com/api/index.html`），如下所示：![如何做...](img/image00877.jpeg)

1.  打开**监控**选项卡。尝试调用**GET /monitoring/users**方法以列出用户帐户。

1.  您的网络浏览器应提示如下的基本身份验证表单：![如何做...](img/image00878.jpeg)

1.  如果取消此表单，您应该收到**401（未经授权）**的响应代码。

1.  出于测试目的，在`communityController`中有一个未受任何注释保护的`delete`方法。还要记住，`communityController`路径没有定义特定的 URL 拦截器：

```java
@RequestMapping(value"="/{username"}", method=DELETE)
@ResponseStatus(HttpStatus.OK
@ApiOperation(value = "Delete a user account", notes =)
public void deleteUser(@PathVariable String username){
  communityService.delete(username);
}
```

1.  未登录的情况下，尝试从 Swagger UI 调用此处理程序。如下图所示，尝试删除名为**other10**的用户。![如何做...](img/image00879.jpeg)

1.  您应该收到**403（禁止）**的响应状态，因为底层服务方法受到了保护！

1.  您会发现您没有收到基本登录表单的提示。还要查看响应头。您不应该看到任何**WWW-Authenticate**头，这可能会触发此弹出窗口。

### 提示

如果用户未经身份验证，并且所请求的 HTTP 资源似乎受到了保护，则会调用`AuthenticationEntryPoint`。仅保护服务对于 Spring Security 来说不足以将 Controller 方法处理程序视为受保护的。

1.  尝试在**监控**选项卡中再次`GET`用户。您应该再次看到基本身份验证表单。用以下详细信息填写它：

```java
<User Name> admin
<Password> admin 
```

现在您应该收到以下响应，状态码为**200**：

![如何做...](img/image00880.jpeg)

1.  当我们请求 JSON 响应时，Swagger UI 无法美化正文，但一切都在那里。

### 注意

注意响应代码：**WWW-Authenticate: CSM_Basic realm"="cloudstreetmarket.com"**。

## 它是如何工作的...

我们将看到 Spring Security 授权过程的工作原理以及如何配置它。

### Spring Security 权限

`AuthenticationManager`实现将`GrantedAuthorities`存储到`SecurityContext`中的`Authentication`对象中。`AccessDecisionManager`将尝试读取这些`GrantedAuthorities`，并将它们与访问要求进行匹配。

`AccessDecisionManager`实现可以是本地的或外部的，这解释了为什么基础设施强制要求权限被呈现为字符串。

如果`getAuthority()`方法无法将`GrantedAuthority`表示为字符串，则应返回`null`，表示`AuthenticationManager`必须支持此类型的`Authority`。

这种机制将不同的`getAuthority()`实现约束为有限的责任。

### 配置属性

我们在介绍`GrantedAuthority`对象（*在 BASIC 方案上进行身份验证*配方）时提到了配置属性。

配置属性在`SecurityInterceptor`中起着关键作用，间接影响`AccessDecisionManager`的实现，因为`SecurityInterceptor`委托给`AccessDecisionManager`。配置属性实现了一个方法的`ConfigAttribute`接口：

```java
public interface ConfigAttribute extends Serializable {
  String getAttribute();
}
```

### 注意

配置属性被指定为受保护方法上的注释，或者作为受保护 URL（拦截 URL）上的访问属性。

我们在`security-config.xml`文件中定义了以下指令，告诉 Spring Security 在匹配`/basic.html`模式的 Web 请求上期望配置属性`ROLE_BASIC`：

```java
<security:intercept-url pattern="/basic.html" access="hasRole('BASIC')"/>
```

使用默认的`AccessDecisionManager`实现，任何具有匹配的`GrantedAuthority`的用户都将被授予访问权限。

基于投票者的`AccessDecisionManager`实现，以`ROLE_`开头的配置属性将被视为角色，并应由`RoleVoter`检查。我们将在接下来的部分中更多地了解`AccessDecisionManager`。

SecurityInterceptor 保护的安全对象是需要进行安全检查的对象或操作。框架处理的两种类型的安全对象：

+   Web 资源，如`ServletRequest`或`ServletResponse`。这些将由**FilterSecurityInterceptor**检查：一个核心过滤器，位于过滤器链的最后。

+   方法调用，这些是`org.aopalliance.intercept.MethodInvocation`的实现。这些将由**MethodSecurityInterceptor**检查。

安全拦截器（方法或 HTTP 请求）在实际到达资源之前异步拦截（基于事件）每个安全对象调用。Spring Security 在处理这些调用时总是应用简单的模式。这种模式来自于使用`AbstractSecurityInterceptor`子类。

`AbstractSecurityInterceptor`的检查对安全对象施加了一致的工作流程：

+   查找与.secure 对象关联的**配置属性**。

+   将安全对象、当前身份验证对象和配置属性提交给`AccessDecisionManager`接口进行授权决定。

+   可选地更改调用发生的`Authentication`对象。

+   允许安全对象调用继续（假设已授予访问权限）。

+   如果配置了，调用`AfterInvocationManager`接口，一旦调用返回。如果调用引发异常，则不会调用`AfterInvocationManager`。

这个工作流程可以用以下图表总结：

![配置属性](img/image00881.jpeg)

此图片的原始图来自 Spring Security 参考。它很有趣，因为它突出了`SecurityInterceptor`在检查安全对象时可以使用的不同元素。

### 注意

主要思想是委托给`AccessDecisionManager`接口，然后可选地委托给`AfterInvocationManager`接口，使用从`SecurityMetadaSource`中提取的属性，最终使用`AuthenticationManager`的能力进行身份验证。

在`SecurityInterceptor`上可以可选地添加`RunAsManager`依赖项，这种情况很少发生，其中`SecurityContext Authentication`对象可能需要被更改（*工作流程的第 3 步*）。该接口定义如下：

```java
public interface RunAsManager {
  Authentication buildRunAs(Authentication authentication, Object object, Collection<ConfigAttribute> attributes);
  boolean supports(ConfigAttribute attribute);
  boolean supports(Class<?> clazz);
}
```

如果未设置`RunAsManager`的依赖项，`SecurityInterceptor`将运行`NullRunAsManager`实现。可以可选地配置`AfterInvocationManager`接口，并用于更改调用返回的`statusToken`对象（*工作流程的第 5 步*）。

### 预调用处理

`AccessDecisionManager`决定是否允许访问。

#### AccessDecisionManager

`AccessDecisionManager` 接口由 `SecurityInterceptor`（在其工作流程的 *步骤 2* 中）调用，并负责做出最终的访问控制决策。

该接口由以下三个方法组成：

```java
public interface AccessDecisionManager {
  void decide(Authentication authentication, Object object, 				Collection<ConfigAttribute> configAttributes) throws AccessDeniedException, InsufficientAuthenticationException;
  boolean supports(ConfigAttribute attribute);
  boolean supports(Class<?> clazz);
}
```

如您所见，方法名非常明确：

+   `decide` 方法解决了提供的参数的访问控制决策。`Authentication` 对象代表调用该方法的调用者，对象是要检查的受保护对象，`configAttributes` 是与受保护对象关联的配置属性。当拒绝访问时，它还会抛出 `AccessDeniedException`。

+   `supports(ConfigAttribute attribute)` 方法在检查的早期阶段被调用，以确定 `AccessDecisionManager` 是否可以处理特定的 `ConfigAttribute`。

+   在调用之前，会调用 `supports(Class<?> clazz)` 方法，以确保配置的 `AccessDecisionManager` 支持将要呈现的安全对象类型。

### 提示

在使用命名空间配置时，Spring Security 会根据在 intercept-url 和 protect-pointcut 声明中指定的访问属性（以及在使用注释来保护方法时的注释）自动注册一个默认的 `AccessDecisionManager` 实例，用于评估方法调用和 Web 访问。

在以下情况下可以指定特定或自定义的 `AccessDecisionManager`：

+   在处理 Web 资源时的 **http** 命名空间：

```java
  <security:http ... access-decision-manager-ref"="xxx"">
  </security:http>
```

+   在处理方法调用时的 **global-method-security** 命名空间：

```java
  <security:global-method-security access-decision-manager-ref""=""... />
```

Spring Security 包括三个 `AccessDecisionManager` 实现（`AffirmativeBased`、`ConsensusBased` 和 `UnanimousBased`），这些实现是基于投票的。投票者是合格的 `AccessDecisionVoter` 实现。该接口定义如下：

```java
public interface AccessDecisionVoter<S> {
  boolean supports(ConfigAttribute attribute);
  boolean supports(Class<?> clazz);
  int vote(Authentication authentication, S object,
  Collection<ConfigAttribute> attributes);
}
```

一些 `AccessDecisionVoter` 实现与框架一起提供（`AuthenticatedVoter`、`Jsr250Voter`、`PreInvocationAuthorizationAdviceVoter`、`WebExpressionVoter`、`RoleVoter` 等）。在检查过程中，合格的 `AccessDecisionVoters` 将被轮询进行授权决策。投票者的合格性取决于其在 `AccessDecisionManager.decisionVoters` 属性中的注册，也取决于其支持的方法。

`AccessDecisionManager` 根据其对票数的评估决定是否应该抛出 `AccessDeniedException`。每个 `AccessDecisionVoter` 根据不同的标准评估安全对象。

|   | *"Spring Security 提供的最常用的 AccessDecisionVoter 是简单的 RoleVoter，它将配置属性视为简单的角色名称，并在用户被分配该角色时投票以授予访问权限。"* |   |
| --- | --- | --- |
|   | --*Spring Security reference* |

### 调用后处理

Spring Security 中只有一个 `AfterInvocationManager` 实现：`AfterInvocationProviderManager`。这个类将所有合格的 `AfterInvocationProvider` 实现对齐，让它们有机会改变 `SecurityInterceptor` 的结果。

与 `AccessDecisionManager` 接口类似，`AfterInvocationProvider` 接口如下所示：

```java
public interface AfterInvocationProvider {
  Object decide(Authentication authentication, Object object, Collection<ConfigAttribute> attributes, Object returnedObject) throws AccessDeniedException;
  boolean supports(ConfigAttribute attribute);
  boolean supports(Class<?> clazz);
}
```

### 基于表达式的访问控制

自从 Spring Security 3 开始，现在可以使用 Spring **Expression Language** (**EL**) 来定义 Web 安全和方法安全。

|   | *"表达式作为评估上下文的一部分与根对象一起进行评估。Spring Security 使用特定的类作为根对象，用于提供内置表达式和访问值，如当前主体。"* |   |
| --- | --- | --- |
|   | --*Spring Security reference* |

表达式根对象的基类是 `SecurityExpressionRoot`。这个抽象类提供了以下方法和属性，代表了常见的内置表达式：

| 表达式 | 描述 |
| --- | --- |
| `hasRole([role])` | 如果当前主体具有指定的角色，则返回`true`。默认情况下，如果提供的角色不以`ROLE_`开头，则将其添加。这可以通过修改`DefaultWebSecurityExpressionHandler`上的`defaultRolePrefix`进行自定义。 |
| `hasAnyRole([role1,role2])` | 如果当前主体具有所提供的角色中的任何一个（以逗号分隔的字符串列表形式给出）则返回`true`。默认情况下，如果提供的角色不以`ROLE_`开头，则将其添加。这可以通过修改`DefaultWebSecurityExpressionHandler`上的`defaultRolePrefix`进行自定义。 |
| `hasAuthority([authority])` | 如果当前主体具有指定的权限，则返回`true`。 |
| `hasAnyAuthority([authority1,authority2])` | 如果当前主体具有所提供的角色中的任何一个（以逗号分隔的字符串列表形式给出）则返回`true`。 |
| `principal` | 允许直接访问表示当前用户的主体对象。 |
| `authentication` | 允许直接访问从`SecurityContext`获取的当前`Authentication`对象。 |
| `permitAll` | 始终评估为`true`。 |
| `denyAll` | 始终评估为`false`。 |
| `isAnonymous()` | 如果当前主体是匿名用户，则返回`true`。 |
| `isRememberMe()` | 如果当前主体是记住我用户，则返回`true`。 |
| `isAuthenticated()` | 如果用户不是匿名用户，则返回`true`。 |
| `isFullyAuthenticated()` | 如果用户不是匿名用户或记住我用户，则返回`true`。 |
| `hasPermission(Object target, Object permission)` | 如果用户对给定权限的提供的目标有访问权限，则返回`true`。例如，`hasPermission(domainObject, 'read').`。 |
| `hasPermission(Object targetId, String targetType, Object permission)` | 如果用户对给定权限的提供的目标有访问权限，则返回`true`。例如，`hasPermission(1,'com.example.domain.Message', 'read')`。 |

#### Web 安全表达式

使用 Spring Security 命名空间，`<http>`块有一个`use-expression`属性，默认为 true。此属性使`intercept-url`元素中的访问属性期望表达式作为值。

对于 Web 安全，表达式根对象的基类是`WebSecurityExpressionRoot`，它继承了`SecurityExpressionRoot`的方法并提供了一个额外的方法：`hasIpAddress(…)`。

此外，`WebSecurityExpressionRoot`在评估上下文中公开了`HttpServletRequest`对象，可在名称为`request`下访问。

如果正在使用表达式，将向`AccessDecisionManager`添加`WebExpressionVoter`。

#### 方法安全表达式

Spring Security 3.0 引入了用于方法安全的表达式。四个安全注释支持表达式的使用：`@PreAuthorize`，`@PostAuthorize`，`@PreFilter`和`@PostFilter`。

##### 使用@PreAuthorize 和@PostAuthorize 进行访问控制

这些注释的使用必须在全局安全 bean 中激活：

```java
<security:global-method-security pre-post-annotations"="enabled"">
```

`@PreAuthorize`通常用于允许或禁止方法的调用。

我们已经在`MonitoringController`类上实现了这个注释：

```java
@PreAuthorize("hasRole('ADMIN')")
public class MonitoringController extends CloudstreetApiWCI{
  ...
}
```

指定的表达式`hasRole('ADMIN')`表示对控制器的访问仅允许具有`ROLE_ADMIN`角色的用户。

### 提示

您可以注意到`ROLE`_ 的自动前缀，避免了单词重复。这个很好的特性可以在表达式中使用，无论是在 Web 安全（intercept-url: access 属性）还是方法安全中。

让我们也考虑一下 Spring 安全参考文档中的这个例子：

```java
@PreAuthorize("hasPermission(#contact, 'admin')")
public void deletePermission(Contact contact, Sid recipient, Permission permission);
```

在这里，将方法参数传递到表达式中，以决定当前用户是否对给定联系人具有`admin`权限。

`@PostAuthorize`较少使用，但可以在方法调用后执行访问控制检查。要在表达式中访问`AccessDecisionManager`的返回值，请使用内置名称`returnObject`。

##### 使用@PreFilter 和@PostFilter 进行集合过滤

现在可以依靠 Spring Security 来过滤可能从方法调用返回的集合（使用表达式）。

考虑一下参考文档中的这个例子：

```java
@PreAuthorize("hasRole('USER')")
@PostFilter("hasPermission(filterObject, 'read') or hasPermission(filterObject, 'admin')")
public List<Contact> getAll();
```

Spring Security 遍历返回的集合，并删除供应的表达式为 false 的任何元素。名称过滤对象指的是集合中的当前对象。您还可以在方法调用之前进行过滤，使用`@PreFilter`，尽管这是一个不太常见的要求。

实际上，为了在表达式中使用`hasPermission()`，需要在应用程序上下文中显式配置`PermissionEvaluator`。以下代码是一个例子：

```java
<security:global-method-security...>
  <security:expression-handler ref="expressionHandler"/>
</security:global-method-security>
<bean id="expressionHandler" class="org.sfw.security.access.expression.method.DefaultMethod SecurityExpressionHandler">
  <property name="permissionEvaluator" ref="myPermissionEvaluator"/>
</bean>
```

`myPermissionEvaluator`是`PermissionEvaluator`的实现：

```java
public interface PermissionEvaluator extends AopInfrastructureBean {
  boolean hasPermission(Authentication authentication, Object targetDomainObject, Object permission);
  boolean hasPermission(Authentication authentication, Serializable targetId, String targetType, Object permission);
}
```

### JSR-250 和传统的方法安全

JSR-250 是一个 Java 规范请求，已于 2006 年发布。它指定了一组注解来解决常见的语义模式。在这些注解中，有些与安全有关：

| 注解名称 | 描述 |
| --- | --- |
| `RolesAllowed` | 指定允许访问应用程序中方法的安全角色 |
| `PermitAll` | 指定所有安全角色都可以访问被注解的方法，或者注解类中的所有方法 |
| `DenyAll` | 指定不允许任何安全角色调用指定的方法 |
| `DeclareRoles` | 用于指定应用程序的安全角色 |

Spring Security 支持这些注解，但必须激活此支持：

```java
<security:global-method-security jsr250-annotations"="enabled""…/>
```

Spring Security 还支持其传统的`@Secured`注解，如果启用：

```java
<security:global-method-security secured-annotations"="enabled""…/>
```

## 还有更多...

### 领域对象安全（ACL）

一些更复杂的应用程序可能需要根据实际的领域对象对授权决策进行处理，这些对象受到方法调用的影响：

[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#domain-acls`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#domain-acls)

### Spring EL

您可能需要查找有关 Spring EL 的额外信息：

[`docs.spring.io/spring/docs/current/spring-framework-reference/html/expressions.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/expressions.html)

### Spring 安全参考

Spring 和 Security 参考以及 Spring JavaDoc 一直是本文的主要信息来源。我们希望您喜欢我们的信息选择、分析和观点。

[`docs.spring.io/spring-security/site/docs/current/apidocs/`](http://docs.spring.io/spring-security/site/docs/current/apidocs/)

[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle)

## 另请参阅

+   层次角色和角色嵌套似乎是经常出现的要求：

[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#authz-hierarchical-roles`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#authz-hierarchical-roles)

# 第六章。实施 HATEOAS

本章包含以下配方：

+   将 DTO 转换为 Spring HATEOAS 资源

+   为超媒体驱动的 API 构建链接

+   选择暴露 JPA 实体的策略

+   使用 OAuth 从第三方 API 检索数据

# 介绍

什么是 HATEOAS？如果你以前从未见过这个词，它可能很难发音。有些人发音为 hate-ee-os；其他人说 hate O-A-S。重要的是要记住这个缩写代表**超媒体作为应用状态的引擎**（**HATEOAS**）。至少，你应该记住超媒体。超媒体作为资源嵌入节点，指向外部资源的能力。作为与其他资源连接的资源，超媒体资源也受到其领域的限制，因为它在技术上不能开发其他资源的领域（作为其一部分）。

把它想象成**维基百科**。如果我们创建一个页面，其各个部分不是在页面标题（域）中自包含的，如果其中一个部分已经在外部页面中涵盖，那么管理员几乎不可能提出这种情况。

HATEOAS 是适用于 REST 架构的约束。它对其资源施加域一致性，并同时对所有权者施加明确的自我文档化，以维护整体凝聚力。

## Richardson 成熟度模型

Richardson 成熟度模型（Leonard Richardson 编写）提供了一种通过 REST 约束级别对 REST API 进行评分和资格认定的方法：

![Richardson 成熟度模型](img/image00882.jpeg)

API 越符合 REST 标准，评分越高。

该模型中的初始状态是**Level 0**：**POX 的沼泽**。在这里，协议（通常是 HTTP）仅用于其传输功能（而不是用于其状态描述功能）。此外，这里没有特定于资源的 URI，只使用一个端点用于一个方法（通常是 HTTP 中的`POST`）。

**Level 1: 资源**的特征是实现特定于资源的 URI。资源标识符可以在 URI 中找到。然而，仍然只使用协议的一个方法（再次是 HTTP 的 POST）。

**Level 2: HTTP 动词**反映了对协议属性的改进使用。对于 HTTP，这实际上意味着 API 正在使用 HTTP 方法来实现其目的（`GET`用于读取，`POST`用于创建，`PUT`用于编辑，`DELETE`用于删除等）。此外，API 提供可靠地通知用户有关操作状态的响应代码。

**Level 3: 超媒体控制**是该模型中的最高级别。它指示使用 HATEOAS，为客户端提供 API 发现功能。

您可以在 Martin Fowler 的博客上阅读有关 Richardson 成熟度模型的更多信息：

[`martinfowler.com/articles/richardsonMaturityModel.html`](http://martinfowler.com/articles/richardsonMaturityModel.html)

# 将 DTO 转换为 Spring HATEOAS 资源

本教程介绍了如何创建 Spring HATEOAS 资源。即使这里的重点是一个特定资源——`IndexResource`（代替以前的`IndexOverviewDTO`），也可以随意浏览**cloudstreetmarket-api**和**cloudstreetmarket-core**以发现更多更改。

HATEOAS 原则已应用于构成我们业务核心的所有资源，这在很大程度上反映了 Yahoo!的财务数据结构（指数、报价、产品、历史数据、图表等）。

## 如何做…

1.  从 Eclipse 的**Git Perspective**中，检出`v6.x.x`分支的最新版本。然后，在**cloudstreetmarket-parent**模块上运行`maven clean install`命令（右键单击**Run as…**下的**Maven Clean**菜单，然后再次单击**Run as…**下的**Maven Install**菜单），然后单击**Maven Update Project**菜单以将 Eclipse 与 Maven 配置同步（右键单击模块，然后导航到**Maven** | **Update Project…**）。

### 注意

此分支包括使用来自 Yahoo!的真实财务数据预填充数据库的 SQL 脚本。

1.  在拉取的更改中，一个新的`/app`配置目录出现在与`cloudstreetmarket-parent`和`zipcloud-parent`相同级别。必须将此`/app`目录复制到您系统的主目录：

+   将其复制到`C:\Users\{system.username}\app`，如果您使用的是 Windows

+   如果您使用的是 Linux，请将其复制到`/home/usr/{system.username}/app`

+   如果您使用的是 Mac OS X，请将其复制到`/Users/{system.username}/app`

1.  Spring HATEOAS 附带以下依赖项。此依赖项已添加到**cloudstreetmarket-parent**、**cloudstreetmarket-core**和**cloudstreetmarket-api**`：`

```java
<dependency>
  <groupId>org.springframework.hateoas</groupId>
  <artifactId>spring-hateoas</artifactId>
  <version>0.17.0.RELEASE</version>
</dependency>
```

1.  正如教程标题所示，目标是摆脱以前使用 REST API 公开的现有 DTO。目前，我们已删除了 IndexOverviewDTO、MarketOverviewDTO、ProductOverviewDTO 和 StockProductOverviewDTO。

1.  这些 DTO 已被这些类替换：IndexResource，StockProductResource，ChartResource，ExchangeResource，IndustryResource 和 MarketResource。

1.  正如所示的 IndexResource，它如下所示，所有这些新类都继承了 Spring HATEOAS Resource 类：

```java
@XStreamAlias("resource")
public class IndexResource extends Resource<Index> {
  public static final String INDEX = "index";
  public static final String INDICES = "indices";
  public static final String INDICES_PATH = "/indices";

  public IndexResource(Index content, Link... links) {
    super(content, links);
  }
}
```

1.  正如您所看到的，使用 IndexResource，资源是从 JPA 实体（这里是 Index.java）创建的。这些实体存储在资源超类型中的 content 属性名称下。

1.  我们已经将 JPA 实体转换为实现`Identifiable`接口的抽象类：

```java
@Entity
@Table(name="index_value")
@XStreamAlias("index")
public class Index extends ProvidedId<String> {

  private String name;

  @Column(name="daily_latest_value")
  private BigDecimal dailyLatestValue;

  @Column(name="daily_latest_change")
  private BigDecimal dailyLatestChange;

  @Column(name="daily_latest_change_pc")
  private BigDecimal dailyLatestChangePercent;

  @Column(name = "previous_close")
  private BigDecimal previousClose;

  private BigDecimal open;

  private BigDecimal high;

  private BigDecimal low;

  @ManyToOne(fetch = FetchType.EAGER)
  @JsonSerialize(using=IdentifiableSerializer.class)
  @JsonProperty("exchangeId")
  @XStreamConverter(value=IdentifiableToIdConverter.class, strings={"id"})
  @XStreamAlias("exchangeId")
   private Exchange exchange;

  @JsonIgnore
  @XStreamOmitField
  @ManyToMany(fetch = FetchType.LAZY)
  @JoinTable(name = "stock_indices", joinColumns = 
  {@JoinColumn(name = "index_code") },
  inverseJoinColumns = {@JoinColumn(name = "stock_code")})
  private Set<StockProduct> components = new LinkedHashSet<>();

  @Column(name="last_update", insertable=false, columnDefinition="TIMESTAMP DEFAULT CURRENT_TIMESTAMP")

  @Temporal(TemporalType.TIMESTAMP)
  private Date lastUpdate;

  public Index(){}

  public Index(String indexId) {
    setId(indexId);
  }

  //getters & setters

    @Override
    public String toString() {
    return "Index [name=" + name + ", dailyLatestValue=" + dailyLatestValue + ", dailyLatestChange=" + dailyLatestChange + ", dailyLatestChangePercent=" + dailyLatestChangePercent + ", previousClose=" + previousClose + ", open=" + open + ", high=" + high + ", low=" + low + ", exchange=" + exchange + ", lastUpdate=" + lastUpdate + ", id=" + id + "]";
    }
  }
```

1.  以下是 ProvidedId 类的详细信息，它是我们可识别实现中的一个：

```java
@MappedSuperclass
public class ProvidedId<ID extends Serializable> implements Identifiable<ID> {
  @Id 
  protected ID id;
  @Override
  public ID getId() {
    return id;
  }
  public void setId(ID id) {
    this.id = id;
  }
  @Override
  public String toString() {
    return id;
  }
  @Override
  public int hashCode() {
    return Objects.hash(id);
  }
  @Override
  public boolean equals(Object obj) {
    if (this == obj)
      return true;
    if (obj == null)
      return false;
    if (getClass() != obj.getClass())
      return false;
    ProvidedId <?> other = (ProvidedId <?>) obj;
    return Objects.equals(this.id, other.id);
  }
}
```

## 它是如何工作的...

一个新的 Spring 依赖项，一些新的资源对象（Resource 子类），最后对我们的实体进行一些修改，以便它们实现`Identifiable`接口。让我们详细讨论所有这些。

### Spring HATEOAS 资源

正如在本章开头介绍的，HATEOAS 是关于链接的。可以说，作为框架的一部分，我们可以期望存在一种现有类型来支持和标准化链接的表示。

这就是`ResourceSupport`类（Spring HATEOAS 的一部分）的作用：支持附加到资源的链接的收集和管理。

另外，REST 资源也是一种内容。框架还提供了一个`Resource`类，它已经继承了`ResourceSupport`。

总之，使用 Spring HATEOAS，我们可以决定以两种不同的方式对我们的资源对象（`IndexResource`，`StockProductResource`等）进行建模：

+   我们可以通过直接让它们继承`ResourceSupport`来对它们进行建模。这样做的话，我们必须自己管理包装对象的资源内容。这里的内容对于框架来说是不受控制的。

+   我们还可以通过让它们继承泛型`Resource<T>`类来对它们进行建模，其中类型`T`对应于资源的`POJO`内容的类型。这是我们选择的策略。框架为我们的资源对象（`Inde3xResource`）提供了内容绑定、链接创建，甚至在控制器级别也是如此。我们很快就会看到这一切。

#### ResourceSupport 类

`ResourceSupport`类是一个实现`Identifiable<Link>`的对象：

```java
public class ResourceSupport extends Object implements Identifiable<Link>
```

以下是`ResourceSupport` JavaDoc 中的示例，它将为您提供有关其构造函数和方法的见解：

| 构造函数 |
| --- | --- |
| `ResourceSupport()` | 这将创建一个新的`ResourceSupport`类 |
| 方法 | 描述 |
| --- | --- |
| `Void add(Iterable<Link> links)` | 这将所有给定的链接添加到资源中 |
| `Void add(Link... links)` | 这将所有给定的链接添加到资源中 |
| `Void add(Link link)` | 这将添加给定的链接到资源中 |
| `Link getId()` | 这将返回具有`Link.REL_SELF`的`rel`的链接 |
| `Link getLink(String rel)` | 这将返回具有给定`rel`的链接 |
| `List<Link> getLinks()` | 这将返回资源中包含的所有链接 |
| `boolean hasLink(String rel)` | 这将返回资源是否包含具有给定`rel`的链接 |
| `boolean hasLinks()` | 这将返回资源是否包含链接 |
| `boolean removeLinks()` | 这将删除到目前为止添加到资源中的所有链接 |
| `Boolean equals(Object obj)` |   |
| `int hashCode()` |   |
| `String toString()` |   |

正如之前介绍的，这个类与链接有关！我们将看到 Spring HATEOAS 提供了围绕链接的一些小机制。

#### 资源类

`Resource`类是`POJO`的包装器。`POJO`存储在这个类的`content`属性中。`Resource`类本质上扩展了`ResourceSupport`：

```java
public class Resource<T> extends ResourceSupport
```

以下是`Resource` JavaDoc 中的示例，它提供了有关其构造函数和方法的见解：

| 构造函数 | 描述 |
| --- | --- |
| `Resource(T content, Iterable<Link> links)` | 这将使用给定的内容和链接创建一个新的资源 |
| `Resource(T content, Link... links)` | 这将使用给定的内容和链接（可选）创建一个新资源 |
| 方法 | 描述 |
| --- | --- |
| `TgetContent()` | 这将返回底层实体 |
| `void add(Iterable<Link> links)` | 这将所有给定的链接添加到资源中 |
| `void add(Link... links)` | 这将所有给定的链接添加到资源中 |
| `void add(Link link)` | 这将给定的链接添加到资源中 |
| `Link getId()` | 这将返回具有`Link.REL_SELF`的`rel`的链接 |
| `Link getLink(String rel)` | 这将返回具有给定`rel`的链接 |
| `List<Link> getLinks()` | 这将返回此资源中包含的所有链接 |
| `boolean hasLink(String rel)` | 这将返回资源是否包含具有给定`rel`的链接 |
| `boolean hasLinks()` | 这将返回资源是否包含任何链接 |
| `boolean removeLinks()` | 这将删除到目前为止添加到资源中的所有链接 |
| `Boolean equals(Object obj)` |   |
| `int hashCode()` |   |
| `String toString()` |   |

两个方便的构造函数，一个用于获取内容的 getter，以及所有与链接相关的辅助函数，这就是 Resource 类的组成部分。

### 可识别的接口

`Identifiable`接口在 Spring HATEOAS 中扮演着重要角色，因为关键类`Resource`、`ResourceSupport`、`Resources`和`PagedResources`类，我们稍后将介绍的这些类都是`Identifiable`的实现。稍后我们将介绍所有这些关键类。

`Identifiable`接口是 Spring HATEOAS 的一个单方法接口（通用接口），用于在对象中定义`Id`：

```java
public interface Identifiable<ID extends Serializable> {
  ID getId();
}
```

因此，框架使用这种方法来检索 ID，对传入对象的性质几乎没有要求。由于一个类可以实现多个接口的能力，向对象添加这样的限定符是没有成本的。此外，这个接口的契约是最小的。

框架对这个接口（和方法）最重要的用途是从`Resource`对象构建链接。看一下`LinkBuilderSupport`的`slash`方法。您会注意到，如果`ID`不是`Identifiable`的实例（这通常是最终结果），则`Link`将附加到`ID`类型的`toString()`表示。

### 提示

如果您考虑实现自定义 ID 类型，请记住这种行为。

### 抽象化实体的@Id

如果您计划坚持使用 Spring HATEOAS 而不将其扩展到 Spring Data REST，那么将基本实体与它们的`@Id`解耦可能并不是绝对必要的。至少不是我们所做的方式。

这种做法来自 Oliver Gierke，在他的`Spring RestBucks`应用程序中。Spring RestBucks 是一个展示现代 Spring REST 功能的示例应用程序。

### 注意

Oliver Gierke 是 Pivotal Software, Inc.的 Spring Data 首席开发人员。他还参与了 Spring HATEOAS。Spring Data 是一个令人惊叹的项目和产品。我们可以信任 Oliver Gierke 的愿景和决定。

在他的`AsbtractId`实现中，O. Gierke 将`Id`属性定义为私有，并将其注释为`@JsonIgnore`。他引导我们不将`Id`属性作为资源内容的一部分暴露出来。在 REST 中，资源的 ID 应该是其 URI。

如果您有机会查看 Spring Data REST，这种方法完全符合框架的一部分，它将 REST 资源与 Spring Data 存储库强烈相关联。

我们选择不在本书的范围内涵盖 Spring Data REST。然而，不暴露实体 ID 对我们的应用程序并不是关键的。出于这些原因，也因为我们希望在这一点上保持与第七章“开发 CRUD 操作和验证”一致，ID 将作为资源属性公开。

## 还有更多...

如果我们的 HATEOAS 介绍还不够清晰，无法让您了解原则，请阅读 Pivotal（[Spring.io](http://Spring.io)）的这个演示：

[`spring.io/understanding/HATEOAS`](https://spring.io/understanding/HATEOAS)

## 另请参阅

+   我们建议您访问 O. Gierke 的 Spring REST 展示应用，该应用展示了 Spring HATEOAS 的实践，无论是否与 Spring Data REST 配合使用，网址为[`github.com/olivergierke/spring-restbucks`](https://github.com/olivergierke/spring-restbucks)。

+   您可以在[`github.com/spring-projects/spring-hateoas/issues/66`](https://github.com/spring-projects/spring-hateoas/issues/66)找到一些关于 ID 暴露的讨论。

+   我们建议您阅读更多关于 Spring Data REST 的内容，因为我们只是介绍了一点点。Spring Data REST 在 Spring Data 存储库的基础上构建 REST 资源，并自动发布它们的 CRUD 服务。您可以在[`docs.spring.io/spring-data/rest/docs/current/reference/html`](http://docs.spring.io/spring-data/rest/docs/current/reference/html)了解更多信息。

# 为超媒体驱动的 API 构建链接

在这个示例中，我们将重点介绍如何使用 Spring HATEOAS 创建链接以及如何将它们绑定到资源上。

我们将详细介绍资源装配器，这些是可重用的过渡组件，用于从实体（如`Index`）到它们的资源（`IndexResource`）的转换。这些组件还提供了链接创建的支持。

## 如何做…

1.  创建的资源（IndexResource，ChartResource，ExchangeResource，IndustryResource，MarketResource 等）是从它们关联的实体（Index，ChartIndex，ChartStock，Exchange，Industry，Market 等）使用资源装配器注册为`@Component`创建的：

```java
import static org.sfw.hateoas.mvc.ControllerLinkBuilder.linkTo;
import static org.sfw.hateoas.mvc.ControllerLinkBuilder.methodOn;
import org.sfw.hateoas.mvc.ResourceAssemblerSupport;
import org.sfw.hateoas.EntityLinks;
import static edu.zc.csm.api.resources.ChartResource.CHART;
import static edu.zc.csm.api.resources.ExchangeResource.EXCHANGE;
import static edu.zc.csm.api.resources.StockProductResource.COMPONENTS;

@Component
public class IndexResourceAssembler extends ResourceAssemblerSupport<Index, IndexResource> {
  @Autowired
  private EntityLinks entityLinks;
  public IndexResourceAssembler() {
    super(IndexController.class, IndexResource.class);
  }
  @Override
  public IndexResource toResource(Index index) {
    IndexResource resource = createResourceWithId(index.getId(), index);
    resource.add(
      entityLinks.linkToSingleResource(index.getExchange ()).withRel(EXCHANGE)
);
  resource.add(
  linkTo(methodOn(ChartIndexController.class).get(in dex.getId(), ".png", null, null, null, null, null, 	null, null)).withRel(CHART)
);
  resource.add(
    linkTo(methodOn(StockProductController.class).getS everal(null, null, index.getId(), null, null, 	null, null)).withRel(COMPONENTS)
);
return resource;
  }
  @Override
  protected IndexResource instantiateResource(Index entity) {
    return new IndexResource(entity);
  }
}
```

### 提示

我们使用这些装配器来生成资源的链接。它们使用`ControllerLinkBuilder`的静态方法（`linkTo`和`methodOn`）和在资源本身中定义为常量的显式标签（`EXCHANGE`，`CHART`和`COMPONENTS`）。

1.  我们已经修改了之前的 SwaggerConfig 类，使得这个类可以用于 Swagger 以外的其他领域的基于注解的配置。这个类已经改名为 AnnotationConfig。

1.  我们还在 AnnotationConfig 类中添加了以下两个注解：

```java
@EnableHypermediaSupport(type = { HypermediaType.HAL })

@EnableEntityLinks 
```

（因为这两个注解目前还没有 XML 等效项）。

1.  这些转换器中的所有目标控制器都已经在类级别上用@ExposesResourceFor 注解进行了注释。

1.  这些控制器现在也返回创建的资源或资源页面：

```java
@RestController
@ExposesResourceFor(Index.class)
@RequestMapping(value=INDICES_PATH, produces={"application/xml", "application/json"})
public class IndexController extends CloudstreetApiWCI<Index> {
  @Autowired
  private IndexService indexService;
  @Autowired
  private IndexResourceAssembler assembler;
  @RequestMapping(method=GET)
  public PagedResources<IndexResource> getSeveral(
    @RequestParam(value="exchange", required=false) String exchangeId,@RequestParam(value="market", required=false) MarketId marketId, @PageableDefault(size=10, page=0, sort={"previousClose"}, direction=Direction.DESC) Pageable pageable){
      return pagedAssembler.toResource( indexService.gather(exchangeId,marketId, pageable), assembler);
  }
  @RequestMapping(value="/{index:[a-zA-Z0-9^.-]+}{extension:\\.[a-z]+}", method=GET)
  public IndexResource get(
    @PathVariable(value="index") String indexId, @PathVariable(value="extension") String extension){
    return assembler.toResource( indexService.gather(indexId));
}
}
```

1.  在这里，我们使 CloudstreetApiWCI 成为通用的。这样，CloudstreetApiWCI 可以有一个通用的 PagedResourcesAssembler @Autowired：

```java
@Component
@PropertySource("classpath:application.properties")
public class CloudstreetApiWCI<T extends Identifiable<?>> 
  extends WebContentInterceptor {
...
    @Autowired
    protected PagedResourcesAssembler<T> pagedAssembler;
...
}
```

### 提示

由于`WebCommonInterceptor`类的传统目的不是作为一个超级控制器共享属性和实用方法，我们将在控制器和`WebCommonInterceptor`之间创建一个中间组件。

1.  为了@Autowire PagedResourcesAssemblers，就像我们做的那样，我们在 dispatcher-servlet.xml 中注册了一个 PagedResourcesAssembler bean：

```java
  <bean class="org.sfw.data.web.PagedResourcesAssembler">
    <constructor-arg><null/></constructor-arg>
    <constructor-arg><null/></constructor-arg>
  </bean>
```

1.  因此，现在调用^GDAXI 指数代码的 API（http://cloudstreetmarket.com/api/indices/%5EGDAXI.xml）会产生以下输出：![如何做…](img/image00883.jpeg)

### 提示

作为链接，我们表达了端点和 URI 路径。从这些链接中，我们可以检索与指数相关的其他实体（如果我们想要公开它们的话）。

## 工作原理…

本节具体详细介绍了链接的创建。

### 资源装配器

这种专门的转换器（资源装配器）是为了可重用性而设计的。它们的主要功能如下：

+   实例化资源并用内容进行填充

+   从实体状态或静态全局设计创建资源的链接

该框架提供了一个`ResourceAssemblerSupport`超类，其作用是减少装配器职责中的样板代码。

`ResourceAssemblerSupport`类是一个抽象的泛型类。它通过提供一些额外的方法来丰富组装器。以`T`作为控制器的类或超级类型，其签名如下：

```java
public abstract class ResourceAssemblerSupport<T, D extends ResourceSupport> implements ResourceAssembler<T, D>
```

这里的表格提供了`ResourceAssemblerSupport`的 JavaDoc 的一瞥：

| 方法 | 描述 |
| --- | --- |
| `List<D> toResources(Iterable<? extends T> entities)` | 这将所有给定的实体转换为资源 |
| `protected D createResourceWithId(Object id, T entity)` | 这将创建一个带有给定 ID 的自链接的新资源 |
| `D createResourceWithId(Object id, T entity, Object... parameters)` | - |
| `protected D instantiateResource(T entity)` | 这将实例化资源对象。默认实现将假定一个`no-arg`构造函数并使用反射。但是，如果需要，可以重写它以手动设置对象实例（例如，以改善性能） |

`ResourceAssemblerSupport`类还实现了`ResourceAssembler`，这是一个单方法接口，强制组装器提供`toResource(T entity)`方法：

```java
public interface ResourceAssembler<T, D extends ResourceSupport> {
  D toResource(T entity);
} 
```

可以注意到我们在组装器中重写了`instantiateResource`方法。如 JavaDoc 中所述，不重写它会导致框架通过反射实例化资源，寻找资源中的`no-arg`构造函数。

我们更倾向于避免在我们的资源中使用这样的构造器，因为它们可能会有点超负荷。

### PagedResourcesAssembler

这个令人惊奇的通用超级组装器用于为客户端构建基于链接的资源页面。通过极少量的配置，Spring HATEOAS 为我们构建了一个完整且开箱即用的、完全填充的类型资源页面。

根据我们呈现的配置，您可以尝试调用以下 URL：

[`cloudstreetmarket.com/api/indices.xml`](http://cloudstreetmarket.com/api/indices.xml)

通过这样做，您应该获得以下输出：

![PagedResourcesAssembler](img/image00884.jpeg)

你能看到**next rel**链接吗？它是如何通过反射从我们的方法处理程序注解及其默认和使用的值构建的？尝试跟随**next**链接，看看导航如何更新并平滑增加。

在`IndexController.getSeveral()`方法处理程序（如下面的代码片段所示）中，我们确保每个单独的资源都通过使用我们自定义的`IndexResourceAssembler`来构建（内容和链接）：

```java
@RequestMapping(method=GET)
public PagedResources<IndexResource> getSeveral(
@RequestParam(value="exchange", required=false) String exchangeId,
@RequestParam(value="market", required=false) MarketId marketId,
@PageableDefault(size=10, page=0, sort={"previousClose"}, direction=Direction.DESC) Pageable pageable){
  return pagedAssembler.toResource(
  indexService.gather(exchangeId, marketId, pageable), 
  assembler);
}
```

### 构建链接

让我们看看我们在组装器中构建资源链接的方式。在`IndexResourceAssembler`中呈现的`toResource()`方法使用了两种不同的技术。

通过**EntityLinks**的第一种技术使用 JPA 实体；第二种技术通过`ControllerLinkBuilder`静态方法直接使用`Controllers`。

#### EntityLinks

通过在配置类中声明`@EnableEntityLinks`注解，会注册一个`EntityLinks`实现：`ControllerEntityLinks`。查找**ApplicationContext**的所有 Spring MVC 控制器，以寻找携带`@ExposesResourceFor(xxx.class)`注解的控制器。

Spring MVC 控制器上的`@ExposesResourceFor`注解公开了控制器管理的模型类型。这种注册使控制器和 JPA 实体之间的必要映射得以实现。

还必须注意，注册的`ControllerEntityLinks`实现假定控制器上有特定的`@RequestMapping`配置。`@RequestMapping`配置如下所示：

+   对于资源集合，期望有一个类级别的`@RequestMapping`注解。然后控制器必须暴露一个映射到空路径的方法处理程序，例如`@RequestMapping(method = RequestMethod.GET)`。

+   对于单个资源，这些资源使用所管理的 JPA 实体的`id`公开，例如`@RequestMapping("/{id}")`。

承认这些观点，`EntityLinks`实现（`ControllerEntityLinks`）从`@Autowiring`中使用以生成使用其提供的方法集的`Links`：

```java
public interface EntityLinks extends Plugin<Class<?>>{ 
  LinkBuilder linkFor(Class<?> type);
  LinkBuilder linkFor(Class<?> type, Object... parameters);
  LinkBuilder linkForSingleResource(Class<?> type, Object id);
  LinkBuilder linkForSingleResource(Identifiable<?> entity);
  Link linkToCollectionResource(Class<?> type);
  Link linkToSingleResource(Class<?> type, Object id);
  Link linkToSingleResource(Identifiable<?> entity);
}
```

#### ControllerLinkBuilder

正如介绍的那样，Spring HATEOAS 提供了`ControllerLinkBuilder`实用程序，它允许通过指向控制器类来创建链接：

```java
resource.add(
  linkTo(
  methodOn(StockProductController.class)
  .getSeveral(null, null, index.getId(), null, null, null, null)
  )
  .withRel(COMPONENTS)
);
```

如 Spring HATEOAS 参考中所指定的，`ControllerLinkBuilder`在底层使用 Spring 的`ServletUriComponentsBuilder`来从当前请求中获取基本 URI 信息。

如果我们的应用程序在`http://cloudstreetmarket/api`上运行，那么框架将在这个根 URI 的基础上构建`Links`，并将其附加到根控制器映射（`/indices`），然后再附加到后续方法处理程序特定的路径。

## 还有更多…

### 在@RequestMapping 中使用正则表达式

在`IndexController`、`StockProductController`、`ChartStockController`和`ChartIndexController`中，用于检索单个资源的`GET`方法处理程序具有特殊的`@RequestMapping`定义。

这是 IndexController 的`get()`方法：

```java
@RequestMapping(value="/{index:[a-zA-Z0-9^.-]+}{extension:\\.[a-z]+}", method=GET)
public IndexResource get(
  @PathVariable(value="index") String indexId, 
  @PathVariable(value="extension") String extension){
  return assembler.toResource(indexService.gather(indexId));
}
```

我们最终选择了这个选项，因为 Yahoo!的指数代码似乎比简单的字符串复杂一些。特别是考虑到这些代码可能携带一个或多个点。

这种情况导致 Spring MVC 无法正确区分`@PathVariable`索引和`extension`（在一半的情况下将它们剥离）。

幸运的是，Spring MVC 允许我们使用正则表达式定义 URI 模板模式。语法是`{varName:regex}`，其中第一部分定义变量名，第二部分定义正则表达式。

您将注意到我们为我们的指数定义的正则表达式：

`[a-zA-Z0-9^.-]+`表达式，特别允许`^`和`.`字符，在 Yahoo!的指数代码中通常使用。

## 另请参阅

+   要了解有关 Spring HATEOAS 的更多信息，请参考[`docs.spring.io/spring-hateoas/docs/current/reference/html/`](http://docs.spring.io/spring-hateoas/docs/current/reference/html/)。

+   介绍的 HATEOAS 表示实现了**Hypertext Application Language** (**HAL**)。 HAL 是 Spring HATEOAS 支持的默认渲染。在[`tools.ietf.org/html/draft-kelly-json-hal-06`](https://tools.ietf.org/html/draft-kelly-js)和[`stateless.co/hal_specification.html`](http://stateless.co/hal_specification.html)了解更多关于 HAL 规范的信息。

# 选择一种公开 JPA 实体的策略

在资源中公开的`content`对象是 JPA 实体。将 JPA 实体包装在资源中的有趣之处在于实体本身的低级性质，它据说代表了一个受限的可识别领域。这个定义理想情况下应该完全转换为公开的 REST 资源。

那么，我们如何在 REST HATEOAS 中表示一个实体？我们如何安全而统一地表示 JPA 关联？

这个示例提供了一种简单而保守的方法来回答这些问题。

## 如何做到这一点…

1.  我们介绍了一个用作资源的实体（`Index.java`）。这里还有另一个用到的实体：`Exchange.java`。这个实体提供了一种类似的策略来公开其 JPA 关联：

```java
import edu.zc.csm.core.converters.IdentifiableSerializer;
import edu.zc.csm.core.converters.IdentifiableToIdConverter;

@Entity
public class Exchange extends ProvidedId<String> {
  private String name;

  @ManyToOne(fetch = FetchType.EAGER)
  @JoinColumn(name = "market_id", nullable=true)
  @JsonSerialize(using=IdentifiableSerializer.class)
  @JsonProperty("marketId")
  @XStreamConverter(value=IdentifiableToIdConverter.class, strings={"id"})
  @XStreamAlias("marketId")
  private Market market;

  @OneToMany(mappedBy = "exchange", cascade = CascadeType.ALL, fetch=FetchType.LAZY)
  @JsonIgnore
  @XStreamOmitField
  private Set<Index> indices = new LinkedHashSet<>();

  @OneToMany(mappedBy = "exchange", cascade = CascadeType.ALL, fetch=FetchType.LAZY)
  @JsonIgnore
  @XStreamOmitField
  private Set<StockProduct> stocks = new LinkedHashSet<>();

  public Exchange(){}
  public Exchange(String exchange) {
    setId(exchange);
  }

  //getters & setters

  @Override
      public String toString() {
        return "Exchange [name=" + name + ", market=" + market + ", id=" + id+ "]";
      }
} 
```

1.  `Exchange.java`实体引用了两个自定义实用程序类，用于以特定的方式转换外部实体作为主实体渲染的一部分（JSON 或 XML）。这些实用程序类是`IdentifiableSerializer`和`IdentifiableToIdConverter`：

+   `IdentifiableSerializer`类用于 JSON marshalling：

```java
import org.springframework.hateoas.Identifiable;
import com.fasterxml.jackson.core.JsonGenerator;
import com.fasterxml.jackson.core.JsonProcessingException;
import com.fasterxml.jackson.databind.JsonSerializer;
import com.fasterxml.jackson.databind.SerializerProvider;
public class IdentifiableSerializer extends JsonSerializer<Identifiable<?>> {
   @Override
   public void serialize(Identifiable<?> value, JsonGenerator jgen, SerializerProvider provider) throws IOException, JsonProcessingException {
    provider.defaultSerializeValue(value.getId(), jgen);
   }
}
```

+   `IdentifiableToIdConverter`类用于 XML marshlling，并且构建了 XStream 依赖项：

```java
import com.thoughtworks.xstream.converters.Converter;
public class IdentifiableToIdConverter implements Converter {
    private final Class <Identifiable<?>> type;
    public IdentifiableToIdConverter(final Class <Identifiable<?>> type, final Mapper mapper, final ReflectionProvider reflectionProvider, final ConverterLookup lookup, final String valueFieldName) {
        this(type, mapper, reflectionProvider, lookup, valueFieldName, null);
    }
  public IdentifiableToIdConverter(final Class<Identifiable<?>> type, final Mapper mapper, final ReflectionProvider reflectionProvider, final ConverterLookup lookup, final String valueFieldName, Class valueDefinedIn) {
        this.type = type;
        Field field = null;
        try {
  field = (valueDefinedIn != null? valueDefinedIn : type.getSuperclass()).getDeclaredField("id");
  if (!field.isAccessible()) {
    field.setAccessible(true);
    }
      } catch (NoSuchFieldException e) {
        throw new IllegalArgumentException( 	e.getMessage()+": "+valueFieldName);
          }
      }
      public boolean canConvert(final Class type) {
        return type.isAssignableFrom(this.type);
    }
    public void marshal(final Object source, final HierarchicalStreamWriter writer,final 	MarshallingContext context) {
          if(source instanceof Identifiable){
            writer.setValue( ((Identifiable<?>)source).getId() .toString()
          );
        }
      }
    public Object unmarshal(final HierarchicalStreamReader reader, final UnmarshallingContext context) {
      return null;
    }
}
```

## 它是如何工作的…

让我们了解一下这个策略是如何工作的。

### REST CRUD 原则

REST 的一个架构约束是提供统一的接口。通过从可以从不同的 HTTP 方法（如果适用）针对的端点公开资源来实现统一的接口。

资源也可以以多种表示形式（`json`，`xml`等）公开，并且信息或错误消息必须是自描述的。 HATEOAS 的实现为 API 的自解释特性提供了巨大的奖励。

在 REST 中，越直观和可推断的事物越好。从这个角度来看，作为 Web/UI 开发人员，我应该能够假设以下内容：

+   我从端点的`GET`调用接收到的对象的结构将是我必须在`PUT`调用（对象的编辑）中发送回去的预期结构

+   类似地，相同的结构应该用于创建新对象（`POST`方法）

在不同的 HTTP 方法之间保持一致的有效负载结构是在捍卫 API 利益时使用的*SOLID*和保守的论点。*捍卫 API 利益几乎总是时候*。

### 暴露最少

在重构本章期间，暴露最少量的信息是核心思想。通常这是确保一个端点不会用于暴露初始控制器之外的信息数据的好方法。

JPA 实体可以与其他实体（`@OneToOne`，`@OneToMany`，`@ManyToOne`或`@ManyToMany`）关联。

其中一些关联已经用`@JsonIgnore`（和`@XStreamOmitField`）进行了注释，另一些关联已经用`@JsonSerialize`和`@JsonProperty`（和`@XStreamConverter`和`@XStreamAlias`）进行了注释。

#### 如果实体不拥有关系

在这种情况下，实体的数据库表没有指向目标第二实体表的外键。

这里的策略是完全忽略 REST 中的关系，以反映数据库状态。

`ignore`指令取决于支持的表示和选择的实现。

对于`json`，我们使用`Jackson`，解决方案是：`@JsonIgnore`。

对于`xml`，我们使用`XStream`，解决方案是：`@XstreamOmitField`。

#### 如果实体拥有关系

在这里，实体的数据库表具有指向目标第二实体表的外键。

如果我们计划更新此表的实体，该实体依赖于另一个表的实体，我们将不得不为该实体提供此外键。

然后的想法是将这个外键作为专用字段公开，就像数据库表的所有其他列一样。再次，实现此的解决方案取决于支持的表示和配置的编组器。

对于`json`和`Jackson`，我们使用以下代码片段完成了这一点：

```java
@JsonSerialize(using=IdentifiableSerializer.class)
@JsonProperty("marketId")
```

正如您所看到的，我们重命名属性以表明我们正在呈现（并期望）一个 ID。我们创建了`IdentifiableSerializer`类，从实体（从`Identifiable`接口）中提取`ID`，并将仅此`ID`放入属性的值中。

对于`xml`和`XStream`，它已经是：

```java
@XStreamConverter(value=IdentifiableToIdConverter.class, strings={"id"})
@XStreamAlias("marketId")
```

同样，我们重命名属性以表明我们正在呈现一个`ID`，并且我们针对自定义转换器`IdentifiableToIdConverter`，该转换器也仅选择实体的**ID**作为属性的值。

这是`xml`表示示例的`^AMBAPT`索引的示例：

![如果实体拥有关系](img/image00885.jpeg)

### 资源的分离

这种策略促进了资源之间的明确分离。每个资源的显示字段完全匹配数据库模式。这是 Web 开发中的标准做法，以保持不同 HTTP 方法的 HTTP 请求有效负载不变。

当采用 HATEOAS 时，我们应该充分鼓励使用链接来访问相关实体，而不是嵌套视图。

以前的配方*为超媒体驱动的 API 构建链接*提供了使用链接访问（使用链接）与`@...ToOne`和`@...ToMany`相关联的实体的示例。以下是在先前的配方中实现的公开实体中的这些链接的示例：

![资源的分离](img/image00886.jpeg)

## 还有更多…

我们在这里详细介绍了实现的编组器的官方信息来源。

### Jackson 自定义序列化器

您可以在以下位置找到这些序列化器的官方 wiki 页面指南：

[`wiki.fasterxml.com/JacksonHowToCustomSerializers`](http://wiki.fasterxml.com/JacksonHowToCustomSerializers)

### XStream 转换器

XStream 已从[codehaus.org](http://codehaus.org)迁移到**Github**。要查看有关 XStream 转换器的官方教程，请转到：

[`x-stream.github.io/converter-tutorial.html`](http://x-stream.github.io/converter-tutorial.html)

# 使用 OAuth 从第三方 API 检索数据

在使用 OAuth2 对用户进行身份验证后，了解如何使用用户的 OAuth2 帐户调用远程第三方 API 是很有用的。

## 如何做…

1.  您可能已经注意到`IndexController`，`StockProductController`，`ChartIndexController`和`ChartStockController`调用了名为`gather(…)`的底层服务方法。这个概念表明对第三方提供商（Yahoo!）的查找是进行的。

1.  例如，在`IndexServiceImpl`中，您可以找到`gather(String indexId)`方法：

```java
@Override
public Index gather(String indexId) {
    Index index = indexRepository.findOne(indexId);
    if(AuthenticationUtil.userHasRole(Role.ROLE_OAUTH2)){
      updateIndexAndQuotesFromYahoo(index != null ? Sets.newHashSet(index) : Sets.newHashSet(new Index(indexId)));
      return indexRepository.findOne(indexId);
    }
  return index;
}
```

1.  真正起到了服务层与第三方 API 之间的桥梁的是`updateIndexAndQuotesFromYahoo(…)`方法：

```java
  @Autowired
  private SocialUserService usersConnectionRepository;

  @Autowired
  private ConnectionRepository connectionRepository;

  private void updateIndexAndQuotesFromYahoo(Set<Index> askedContent) {
      Set<Index> recentlyUpdated = askedContent.stream()
      .filter(t -> t.getLastUpdate() != null && DateUtil.isRecent(t.getLastUpdate(), 1))
        .collect(Collectors.toSet());

    if(askedContent.size() != recentlyUpdated.size()){
      String guid = AuthenticationUtil.getPrincipal().getUsername();
    String token = usersConnectionRepository .getRegisteredSocialUser(guid) .getAccessToken();
    Connection<Yahoo2> connection = connectionRepository .getPrimaryConnection(Yahoo2.class);
    if (connection != null) {
      askedContent.removeAll(recentlyUpdated);
        List<String> updatableTickers = askedContent.stream()
         .map(Index::getId)
         .collect(Collectors.toList());
     List<YahooQuote> yahooQuotes = connection.getApi() .financialOperations().getYahooQuotes(updatableTickers, token);

     Set<Index> upToDateIndex = yahooQuotes.stream()
       .map(t -> yahooIndexConverter.convert(t))
       .collect(Collectors.toSet());

      final Map<String, Index> persistedStocks = indexRepository.save(upToDateIndex) 	.stream()
        .collect(Collectors.toMap(Index::getId, Function.identity()));

     yahooQuotes.stream()
      .map(sq -> new IndexQuote(sq, persistedStocks.get(sq.getId())))
        .collect(Collectors.toSet());
      indexQuoteRepository.save(updatableQuotes);
    }
  }
} 
```

1.  在 Facebook、Twitter 或 LinkedIn 的情况下，您应该能够找到一个完整的 API 适配器，以执行对其 API 的调用，而无需进行修改。在我们的情况下，我们不得不开发所需的适配器，以便从 Yahoo!中检索和利用财务数据。

1.  我们在`FinancialOperations`接口中添加了两个方法，如下所示：

```java
public interface FinancialOperations {
  List<YahooQuote> getYahooQuotes(List<String> tickers, String accessToken) ;
  byte[] getYahooChart(String indexId, ChartType type, ChartHistoSize histoSize, ChartHistoMovingAverage histoAverage, ChartHistoTimeSpan histoPeriod, Integer intradayWidth, Integer intradayHeight, String token);
}
```

1.  这个接口有一个`FinancialTemplate`实现，如下所示：

```java
public class FinancialTemplate extends AbstractYahooOperations implements FinancialOperations {
    private RestTemplate restTemplate;
  public FinancialTemplate(RestTemplate restTemplate, boolean isAuthorized, String guid) {
    super(isAuthorized, guid);
    this.restTemplate = restTemplate;
    this.restTemplate.getMessageConverters() add( new YahooQuoteMessageConverter( MediaType.APPLICATION_OCTET_STREAM));
    }
  @Override
  public List<YahooQuote> getYahooQuotes(List<String> tickers, String token)  {
      requiresAuthorization();
      final StringBuilder sbTickers = new StringBuilder();
      String url = "quotes.csv?s=";
      String strTickers = "";
      if(tickers.size() > 0){
        tickers.forEach(t -> strTickers = sbTickers.toString();
          strTickers = strTickers.substring(0, strTickers.length()-1);
      }
       HttpHeaders headers = new HttpHeaders();
       headers.set("Authorization", "Bearer "+token);
       HttpEntity<?> entity = new HttpEntity<>(headers);
       return restTemplate.exchange(buildUri(FINANCIAL, url.concat(strTickers).concat("&f=snopl1c1p2hgbavx	c4")), HttpMethod.GET, entity , QuoteWrapper.class).getBody();
  } 
  ...
}
```

1.  `FinancialTemplate`类作为全局`Yahoo2Template`的一部分进行初始化，并在`IndexServiceImpl`的`connection.getApi()`调用中返回。

1.  使用这种技术，不仅可以从 Yahoo!中检索指数和股票报价，还可以检索图表，现在我们能够显示来自 25000 多支股票和 30000 多个指数的实时数据。![如何做…](img/image00887.jpeg)

1.  客户端能够使用随每个结果元素一起提供的 HATEOAS 链接。它使用这些链接来呈现详细视图，如**指数详情**或**股票详情**（新屏幕）。![如何做…](img/image00888.jpeg)

## 它是如何工作的…

让我们了解这个配方背后的理论。

### 介绍 Yahoo!的财务数据

在我们的应用程序环境中，仍然有一个需要解释的重构。这是关于历史数据和图表的。

Yahoo!财务 API 提供了历史数据。这些数据可以用来构建图表，最初计划是这样做的。现在，Yahoo!也生成图表（用于历史和盘中数据），这些图表是相当可定制的（时间段、平均线、图表或股票的显示选项等）。

我们决定放弃历史部分，这在技术上与报价检索（数据快照）非常相似，专门使用由 Yahoo!生成的图表。

#### 图表生成/显示

我们的实现提供了一个有趣的 REST 图像服务示例。看看`ChartIndexController`（或`ChartStockController`）并看看图像如何以字节数组返回。

还要看一下`home_financial_graph.js`文件，了解接收到的内容是如何设置到 HTML `<img…>`标记中的。

### 财务数据是如何拉取/刷新的？

这里的想法是依赖于 OAuth 认证的用户。雅虎！为经过身份验证和未经身份验证的用户提供不同的费率和限制。雅虎！认为来自我们 IP 的调用太多，这将是一个问题。但是，如果有太多来自特定用户的调用，雅虎！将限制该用户，而不会影响应用程序的其余部分（应用程序可以进一步通过应用程序恢复）。

正如您所看到的，潜在处理雅虎！金融数据的方法处理程序通过名为`gather()`的方法调用适当的底层服务。

在这些`gather()`方法中，雅虎第三方 API 介入了我们的数据库和我们的控制器之间。

如果用户使用 OAuth2 进行了身份验证，则底层服务会检查数据是否存在于数据库中，以及是否已经更新到足够近的时间来匹配数据类型的预定义缓冲期（`indices`和`stocks`为一分钟）：

+   如果答案是肯定的，则将这些数据返回给客户端

+   如果答案是否定的，则从雅虎！请求预期的数据，转换，存储在数据库中，并返回给客户端

目前没有计划针对未经 OAuth 认证的用户，但我们可以想象很容易使用通用的雅虎！OAuth 账户来创建它们。

### 调用第三方服务

对于所呈现的配方，这部分是在`updateIndexAndQuotesFromYahoo`方法中完成的。我们的 Spring 配置定义了一个`connectionRepository` bean，为每个用户创建了一个`request`范围。`connectionRepository`实例是从我们的`SocialUserServiceImpl`的`createConnectionRepository`工厂方法创建的。

基于此，我们在服务层中`@Autowire`这两个 bean：

```java
@Autowired
private SocialUserService usersConnectionRepository;
@Autowired
private ConnectionRepository connectionRepository;
```

然后，`updateIndexAndQuotesFromYahoo`方法从 Spring Security 中获取已登录的`userId`（`guid`）：

```java
String guid = AuthenticationUtil.getPrincipal().getUsername();
```

访问令牌从`SocialUser`实体（来自数据库）中提取：

```java
String token = usersConnectionRepository .getRegisteredSocialUser(guid).getAccessToken();
```

从数据库中检索雅虎！连接：

```java
Connection<Yahoo2> connection = connectionRepository.getPrimaryConnection(Yahoo2.class);
```

如果连接不为空，则从连接对象调用第三方 API：

```java
List<YahooQuote> yahooQuotes = connection.getApi() .financialOperations().getYahooQuotes(updatableTickers, token);
```

再次，我们不得不开发实际的`FinancialTemplate`（雅虎！金融 API 的 Java 表示），但是您应该能够为您的第三方提供商找到这样的现有实现。

## 还有更多...

本节提供了许多现有的开源 Spring Social 适配器的列表，我们可以在我们的项目中使用

### Spring Social - 现有的 API 提供商

以下地址提供了连接支持和 API 绑定到许多热门服务提供商的 Spring 社交扩展的最新聚合：

[`github.com/spring-projects/spring-social/wiki/Api-Providers`](https://github.com/spring-projects/spring-social/wiki/Api-Providers)

## 另请参阅

+   **雅虎！金融股票代码**：我们已经在数据库中预先填充了一组对雅虎的金融引用（股票引用和指数引用），这使我们能够指向和搜索可以通过雅虎 API 第二次更新的资源。这组引用来自**Samir Khan**在他的博客[`investexcel.net/all-yahoo-finance-stock-tickers`](http://investexcel.net/all-yahoo-finance-stock-tickers)上发布的伟大工作。然后，我们使用基本文本编辑器和宏将这些 XLS 数据转换为 SQL。

# 第七章。开发 CRUD 操作和验证

到目前为止，我们已经看到了如何构建 API 的只读 HTTP 方法。Spring MVC 控制器中的这些方法要求您掌握或至少了解一些技术的呈现。开发非只读的 HTTP 方法会引发一系列新的基础主题。每个主题都直接影响客户体验，因此每个主题都很重要。我们引入以下四个配方作为涵盖主题的框架：

+   将 REST 处理程序扩展到所有 HTTP 方法

+   使用 bean 验证支持验证资源

+   为 REST 国际化消息和内容

+   使用 HTML5 和 AngularJS 验证客户端表单

# 介绍

在这个阶段开发 CRUD 操作和验证结果是最广泛的主题之一。

我们的应用程序将在许多方面进行转变，从交易管理标准化到错误（和内容）的国际化，通过 REST 处理程序、HTTP 合规性。

与前几章和本书的全局策略一致，我们专注于 Spring MVC 在可伸缩性和微服务通信方面的最佳实践。决定跳过一些内容是一个艰难的选择，但框架不断适应新的设计和挑战。本书试图在现代、可持续和可伸缩的应用程序中呈现 Spring MVC 的一致集成。

这里介绍了四个配方。第一个配方将两个控制器转换为支持其各自资源的 CRUD 操作。这样做需要对数据库事务和 HTTP 规范进行审查。

本章介绍了 Spring MVC 支持的两种验证策略。由于验证错误通常需要以多种语言呈现，我们确保我们的应用程序支持国际化。我们简要介绍了 AngularJS 如何在这个视角中使用，以及如何用它来处理前端验证，这总是必要的，以将客户体验限制在业务特定数据管理的现实中。

# 将 REST 处理程序扩展到所有 HTTP 方法

这是本章的核心配方。我们将详细介绍如何使用 Spring MVC 方法处理程序处理我们尚未涵盖的 HTTP 方法：非只读方法。

## 准备就绪

我们将看到返回的状态代码和驱动`PUT`、`POST`和`DELETE`方法使用的 HTTP 标准。这将使我们配置符合 HTTP 规范的 Spring MVC 控制器。

我们还将审查请求负载映射注释，如`@RequestBody`是如何在幕后工作的，以及如何有效地使用它们。

最后，我们将打开 Spring 事务的窗口，因为这本身是一个广泛而重要的主题。

## 如何做…

以下步骤将介绍对两个控制器、一个服务和一个存储库所应用的更改：

1.  从 Eclipse 的**Git Perspective**中，检出分支`v7.x.x`的最新版本。然后，在`cloudstreetmarket-parent`模块上运行`maven clean install`（右键单击模块，转到**Run as…** | **Maven Clean**，然后再次转到**Run as…** | **Maven Install**），然后进行`Maven Update`项目以使 Eclipse 与 maven 配置同步（右键单击模块，然后转到**Maven** | **Update Project…**）。

1.  在`zipcloud-parent`和`cloudstreetmarket-parent`上运行`Maven clean`和`Maven install`命令。然后，转到**Maven** | **Update Project**。

1.  在本章中，我们专注于两个 REST 控制器：`UsersController`和新创建的`TransactionController`。

### 注意

`TransactionController`允许用户处理财务交易（从而购买或出售产品）。

1.  这里提供了`UserController`的简化版本：

```java
@RestController
@RequestMapping(value=USERS_PATH, produces={"application/xml", "application/json"})
public class UsersController extends CloudstreetApiWCI{
  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
  public void create(@RequestBody User user, 
  @RequestHeader(value="Spi", required=false) String 	guid, @RequestHeader(value="OAuthProvider", required=false) String provider,
  HttpServletResponse response) throws IllegalAccessException{
  ...
  response.setHeader(LOCATION_HEADER, USERS_PATH + user.getId());
  }
  @RequestMapping(method=PUT)
  @ResponseStatus(HttpStatus.OK)
  public void update(@RequestBody User user, 
    BindingResult result){
    ...
  }
  @RequestMapping(method=GET)
  @ResponseStatus(HttpStatus.OK)
  public Page<UserDTO> getAll(@PageableDefault(size=10, page=0) Pageable pageable){
  return communityService.getAll(pageable);
  }
  @RequestMapping(value="/{username}", method=GET)
  @ResponseStatus(HttpStatus.OK)
  public UserDTO get(@PathVariable String username){
    return communityService.getUser(username);
  }
  @RequestMapping(value="/{username}", method=DELETE)
  @ResponseStatus(HttpStatus.NO_CONTENT)
  public void delete(@PathVariable String username){
    communityService.delete(username);
  }
}
```

1.  这里以简化版本呈现了**TransactionController**：

```java
@RestController
@ExposesResourceFor(Transaction.class)
@RequestMapping(value=ACTIONS_PATH + TRANSACTIONS_PATH, produces={"application/xml", "application/json"})
public class TransactionController extends CloudstreetApiWCI<Transaction> {
```

（这里提供的`GET`方法处理程序来自先前的配方。）

```java
  @RequestMapping(method=GET)
  @ResponseStatus(HttpStatus.OK)
  public PagedResources<TransactionResource> search(
    @RequestParam(value="user", required=false) String userName,
    @RequestParam(value="quote:[\\d]+", required=false) Long quoteId,
    @RequestParam(value="ticker:[a-zA-Z0-9-:]+", required=false) String ticker,
    @PageableDefault(size=10, page=0, sort={"lastUpdate"}, direction=Direction.DESC) Pageable pageable){
    Page<Transaction> page = transactionService.findBy(pageable, userName, quoteId, ticker);
      return pagedAssembler.toResource(page, assembler);
  }
  @RequestMapping(value="/{id}", method=GET)
  @ResponseStatus(HttpStatus.OK)
public TransactionResource get(@PathVariable(value="id") Long transactionId){
  return assembler.toResource(
    transactionService.get(transactionId));
  }
```

（这里介绍的`PUT`和`DELETE`方法处理程序是非只读方法。）

```java
  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
public TransactionResource post(@RequestBody Transaction transaction) {
    transactionService.hydrate(transaction);
    ...
  TransactionResource resource = assembler.toResource(transaction);
  response.setHeader(LOCATION_HEADER, resource.getLink("self").getHref());
    return resource;
  }
  @PreAuthorize("hasRole('ADMIN')")
  @RequestMapping(value="/{id}", method=DELETE)
  @ResponseStatus(HttpStatus.NO_CONTENT)
public void delete(@PathVariable(value="id") Long transactionId){
    transactionService.delete(transactionId);
  }
}
```

1.  在`post`方法中调用`hydrate`方法，为底层服务使用准备实体。它从请求有效负载中接收的 ID 填充了它的关系。

### 注意

这种技术将应用于用于 CRUD 的所有 REST 资源。

1.  这里是`transactionServiceImpl`中`hydrate`方法的详细信息：

```java
@Override
public Transaction hydrate(final Transaction transaction) {

  if(transaction.getQuote().getId() != null){
    transaction.setQuote(
      stockQuoteRepository.findOne(
        transaction.getQuote().getId()));
  }
  if(transaction.getUser().getId() != null){
   transaction.setUser(userRepository.findOne(transaction.getUser().getId()));
  }
  if(transaction.getDate() == null){
    transaction.setDate(new Date());
  }
  return transaction;
}
```

### 注意

这里没有什么惊人的；主要是为了构建我们的实体以满足我们的需求。可以创建一个接口来标准化这种做法。

1.  所有服务层都经过审查，以驱动统一的数据库事务。

1.  服务实现现在默认使用`@Transactional(readOnly = true)`进行注释。检查以下`TransactionServiceImpl`示例：

```java
@Service
@Transactional(readOnly = true)
public class TransactionServiceImpl implements TransactionService{
  ...
}
```

1.  这些服务实现的非只读方法使用`@Transactional`注解覆盖了类定义：

```java
  @Override
  @Transactional
  public Transaction create(Transaction transaction) {
  if(!transactionRepository.findByUserAndQuote(transaction.getUser(), transaction.getQuote()).isEmpty()){
      throw new DataIntegrityViolationException("A transaction for the quote and the user already exists!");
    }
    return transactionRepository.save(transaction);
  }
```

1.  这个原则也适用于自定义存储库实现（如`IndexRepositoryImpl`）：

```java
@Repository
@Transactional(readOnly = true)
public class IndexRepositoryImpl implements IndexRepository{
  @PersistenceContext 
  private EntityManager em;

  @Autowired
  private IndexRepositoryJpa repo;
  ...
  @Override
  @Transactional
  public Index save(Index index) {
    return repo.save(index);
  }
  ...
}
```

## 工作原理...

首先，让我们快速回顾一下本文中控制器中介绍的不同 CRUD 服务。以下表格对它们进行了总结：

| URI | 方法 | 目的 | 正常响应代码 |
| --- | --- | --- | --- |
| `/actions/transactions` | GET | 搜索交易 | 200 OK |
| `/actions/transactions/{id}` | GET | 获取交易 | 200 OK |
| `/actions/transactions` | POST | 创建交易 | 201 Created |
| `/actions/transactions/{id}` | DELETE | 删除交易 | 204 No Content |
| `/users/login` | POST | 登录用户 | 200 OK |
| `/users` | GET | 获取所有 | 200 OK |
| `/users/{username}` | GET | 获取用户 | 200 OK |
| `/users` | POST | 创建用户 | 201 Created |
| `/users/{username}` | PUT | 更新用户 | 200 OK |
| `/users/{username}` | DELETE | 删除用户 | 204 No Content |

### HTTP/1.1 规范 - RFC 7231 语义和内容

要理解本文中所做的一些决定（并合理化它们），我们必须对 HTTP 规范的一些要点进行一些解释。

在开始之前，可以随意访问与语义和内容相关的**HTTP 1/1**的互联网标准跟踪文档（RFC 7231）：

[`tools.ietf.org/html/rfc7231`](https://tools.ietf.org/html/rfc7231)

#### 基本要求

在 HTTP 规范文档中，请求方法概述（第 4.1 节）规定服务器必须支持`GET`和`HEAD`方法。所有其他请求方法都是可选的。

同一节还指定，使用已识别的方法名（`GET`、`POST`、`PUT`、`DELETE`等）进行的请求，但不匹配任何方法处理程序的请求应该以`405 Not supported`状态代码进行响应。同样，使用未识别的方法名（非标准）进行的请求应该以`501 Not implemented`状态代码进行响应。这两个语句都受 Spring MVC 的本地支持和自动配置。

#### 安全和幂等方法

该文档介绍了可以用来描述请求方法的安全和幂等限定符。安全方法基本上是只读方法。使用这种方法的客户端不会显式请求状态更改，并且不能期望请求的结果会导致状态更改。

正如“安全”一词所暗示的那样，这样的方法可以信任不会对系统造成任何伤害。

一个重要的元素是我们正在考虑客户端的观点。安全方法的概念不会阻止系统实施“潜在”有害的操作或过程，这些操作或过程实际上并非只读。无论发生什么，客户端都不会对此负责。在所有 HTTP 方法中，只有`GET`、`HEAD`、`OPTIONS`和`TRACE`方法被定义为安全方法。

规范使用幂等限定符来识别 HTTP 请求，当完全重复时，总是产生与第一个请求相同的后果。这里必须考虑客户端的观点。

幂等的 HTTP 方法是`GET`，`HEAD`，`OPTIONS`，`TRACE`（安全方法），以及`PUT`和`DELETE`。

方法的幂等性保证客户端，例如，即使在接收到任何响应之前发生连接问题，发送**PUT**请求也可以重复。

### 注意

客户端知道重复请求将产生相同的预期效果，即使原始请求成功，响应可能会有所不同。

#### 其他特定于方法的约束

`POST`方法通常与在服务器上创建资源相关联。因此，该方法应返回`201（已创建）`状态码，并提供一个标识符来创建资源的位置头字段。

然而，如果没有创建资源，`POST`方法（实际上）可能返回除`206（部分内容）`，`304（未修改）`和`416（范围不可满足）`之外的所有类型的状态码。

`POST`的结果有时可能是现有资源的表示。在这种情况下，例如，客户端可以通过`303`状态码和`Location`头字段重定向到该资源。作为`POST`方法的替代，`PUT`方法通常被选择来更新或更改现有资源的状态，并向客户端发送`200（OK）`或`204（无内容）`。

不一致匹配的边缘情况会引发`409（冲突）`或`415（不支持的媒体类型）`错误。

更新时找不到匹配项的边缘情况应该引发使用`201（已创建）`状态码创建资源。

另一组约束适用于成功接收的`DELETE`请求。这些请求应返回`204（无内容）`状态码，或者如果删除已经被处理，则返回`200（OK）`。如果没有，则状态码应为`202（已接受）`。

### 使用@RequestBody 映射请求有效载荷

在第四章中，*为无状态架构构建 REST API*，我们介绍了`RequestMappingHandlerAdapter`。我们已经看到 Spring MVC 委托给这个 bean 来提供对`@RequestMapping`注解的扩展支持。

从这个角度来看，`RequestMappingHandlerAdapter`是访问和重写`HttpMessageConverters`的中心组件，通过`getMessageConverters()`和`setMessageConverters(List<HttpMessageConverter<?>> messageConverters)`。

`@RequestBody`注解的作用与`HttpMessageConverters`紧密耦合。我们现在将介绍`HttpMessageConverters`。

### HttpMessageConverters

`HttpMessageConverters`，自定义或本机，绑定到特定的 MIME 类型。它们在以下情况下使用：

+   将 Java 对象转换为 HTTP 响应有效载荷。从`Accept`请求头 MIME 类型中选择，它们为`@ResponseBody`注解的目的提供服务（间接地为抽象`@ResponseBody`注解的`@RestController`注解提供服务）。

+   将 HTTP 请求有效载荷转换为 Java 对象。从`Content-Type`请求头 MIME 类型中选择，这些转换器在方法处理程序参数上存在`@RequestBody`注解时被调用。

更一般地说，`HttpMessageConverters`匹配以下`HttpMessageConverter`接口：

```java
public interface HttpMessageConverter<T> {
  boolean canRead(Class<?> clazz, MediaType mediaType);
  boolean canWrite(Class<?> clazz, MediaType mediaType);
  List<MediaType> getSupportedMediaTypes();
  T read(Class<? extends T> clazz, HttpInputMessage inputMessage) throws IOException, HttpMessageNotReadableException;
  void write(T t, MediaType contentType, HttpOutputMessage outputMessage) throws IOException, HttpMessageNotWritableException;
}
```

`getSupportedMediaTypes()`方法返回特定转换器支持的`mediaTypes`（MIME 类型）列表。这个方法主要用于报告目的和`canRead`和`canWrite`实现。这些`canRead`和`canWrite`资格方法由框架在运行时使用，首先选择`HttpMessageConverter`，它要么：

+   匹配客户端提供的`Content-Type`请求头，针对`@RequestBody`指定的 Java 类。

+   匹配客户端提供的`Accept`请求头，以便 HTTP 响应有效载荷对应于`@ResponseBody`指定的 Java 类（`@ResponseBody`指定的类型）。

#### 提供了 HttpMessageConverters

| 在最新版本的 Spring MVC（4+）中，一些额外的`HttpMessageConverters`与框架一起自然而然地出现。我们认为总结它们会有所帮助。以下表格表示了所有本地的`HttpMessageConverters`，mime 类型以及它们可以关联的 Java 类型。大部分来自 JavaDoc 的简短描述更多地揭示了它们的特点。 |

| URI | 支持的媒体类型（默认） | 转换为/从 |
| --- | --- | --- |
| `FormHttpMessage Converter` | 可以读/写 application/x-www-form-urlencoded，可以读取 multipart/form-data。 | `MultiValueMap<String, ?>` |
| 对于部分转换，默认还嵌入了`ByteArrayHttpMessageConverter`、`StringHttpMessageConverter`和`ResourceHttpMessageConverter`。 |
| `AllEncompassing FormHttpMessage Converter` | 可以读/写 application/x-www-form-urlencoded，可以读取 multipart/form-data。 | `MultiValueMap<String, ?>` |
| 这个转换器扩展了`FormHttpMessageConverter`，通过在类路径上找到 XML/JSON-based 部分的 JAXB 或 Jackson 来嵌入额外的`HttpMessageConverters`。 |
| `XmlAwareFormHttp MessageConverter` | 可以读/写 application/x-www-form-urlencoded，可以读取 multipart/form-data。 | `MultiValueMap<String, ?>` |
| 这个转换器扩展了`FormHttpMessageConverter`，通过`SourceHttpMessageConverter`添加了对基于 XML 的部分的支持。 |
| `BufferedImageHttp MessageConverter` | 可以读取所有已注册的图像阅读器支持的媒体类型。可以写入第一个可用的已注册图像写入器的媒体类型。 | `java.awt.image.BufferedImage` |
| `ByteArrayHttp MessageConverter` | 可以读取*/*，可以写入 application/octet-stream。 | `byte[]` |
| `GsonHttpMessage Converter` | 可以读/写 application/json, application/*+json。 | `java.lang.Object` |
| 使用 Google Gson 库的`Gson`类。这个转换器可以用来绑定带有类型的 bean 或无类型的 HashMap。 |
| `Jaxb2Collection HttpMessage Converter` | 可以读取 XML 集合。 | `T extends java.util.Collection` |
| 这个转换器可以读取包含带有`XmlRootElement`和`XmlType`注释的类的集合。请注意，这个转换器不支持写入。（JAXB2 必须存在于类路径上。） |
| `Jaxb2RootElement HttpMessage Converter` | 可以读/写 XML | `java.lang.Object` |
| 这个转换器可以读取带有`XmlRootElement`和`XmlType`注释的类，并写入带有`XmlRootElement`或其子类注释的类。（JAXB2 必须存在于类路径上。） |
| `MappingJackson2 HttpMessage Converter` | 可以读/写 application/json, application/*+json。 | `java.lang.Object` |
| 使用 Jackson 2.x ObjectMapper。这个转换器可以用来绑定带有类型的 bean 或无类型的 HashMap 实例。（Jackson 2 必须存在于类路径上。） |
| `MappingJackson2 XmlHttpMessage Converter` | 可以读/写 application/xml, text/xml, application/*+xml。 | `java.lang.Object` |
| 这使用了 Jackson 2.x 扩展组件来读取和写入 XML 编码的数据（[`github.com/FasterXML/jackson-dataformat-xml`](https://github.com/FasterXML/jackson-dataformat-xml)）。（Jackson 2 必须存在于类路径上。） |
| `MarshallingHttp MessageConverter` | 可以读/写 text/xml application/xml。 | `java.lang.Object` |
| 这使用了 Spring 的 Marshaller 和 Unmarshaller 抽象（OXM）。 |
| `ObjectToStringHttp MessageConverter` | 可以读/写 text/plain。 | `java.lang.Object` |
| 这使用`StringHttpMessageConverter`来读取和写入内容，并使用`ConversionService`来将字符串内容转换为目标对象类型和从目标对象类型转换为字符串内容。（必须进行配置。） |
| `ProtobufHttp MessageConverter` | 可以读取 application/json, application/xml, text/plain 和 application/x-protobuf。可以写入 application/json, application/xml, text/plain 和 application/x-protobuf, text/html。 | `javax.mail.Message` |
| 使用 Google 协议缓冲区（[`developers.google.com/protocol-buffers`](https://developers.google.com/protocol-buffers)）生成消息 Java 类，您需要安装`protoc`二进制文件。 |
| `ResourceHttp MessageConverter` | 可以读取/写入*/*。 | `org.springframework.core.io.Resource` |
| 如果可用，**Java 激活框架**（**JAF**）用于确定写入资源的内容类型。如果 JAF 不可用，则使用 application/octet-stream。 |
| `RssChannelHttp MessageConverter` | 可以读取/写入 application/rss+xml。 | `com.rometools.rome.feed.rss.Channel` |
| 此转换器可以处理来自 ROME 项目（[`github.com/rometools`](https://github.com/rometools)）的 Channel 对象。（ROME 必须存在于类路径上。） |
| `AtomFeedHttp MessageConverter` | 可以读取/写入 application/atom+xml。 | `com.rometools.rome.feed.atom.Feed` |
| 这可以处理来自 ROME 项目（[`github.com/rometools`](https://github.com/rometools)）的 Atom feeds。（ROME 必须存在于类路径上。） |
| `SourceHttpMessageConverter` | 可以读取/写入 text/xml，application/xml，application/*-xml。 | `javax.xml.transform.Source` |
| `StringHttpMessageConverter` | 可以读取/写入*/*。 | `java.lang.String` |

#### 使用 MappingJackson2HttpMessageConverter

在这个示例中，`MappingJackson2HttpMessageConverter`被广泛使用。我们将此转换器用于财务交易创建/更新方面和用户首选项更新方面。

或者，我们使用 AngularJS 将 HTML 表单映射到构建的 json 对象，其属性与我们的实体匹配。通过这种方式，我们将`json`对象作为`application/json`媒体类型进行`POST`/`PUT`。

之所以选择这种方法而不是发布`application/x-www-form-urlencoded`表单内容，是因为我们实际上可以将对象映射到实体。在我们的情况下，表单与后端资源完全匹配。这是 REST 设计的一个有益结果（和约束）。

### 使用@RequestPart 上传图像

`@RequestPart`注解可用于将`multipart/form-data`请求的一部分与方法参数关联起来。它可以与参数类型一起使用，例如`org.springframework.web.multipart.MultipartFile`和`javax.servlet.http.Part`。

对于任何其他参数类型，部分内容都会像`@RequestBody`一样通过`HttpMessageConverter`传递。

`@RequestBody`注解已被实现以处理用户个人资料图片。以下是我们从`UserImageController`的示例实现：

```java
    @RequestMapping(method=POST, produces={"application/json"})
    @ResponseStatus(HttpStatus.CREATED)
    public String save( @RequestPart("file") MultipartFile file, HttpServletResponse response){
    String extension = ImageUtil.getExtension(file.getOriginalFilename());
    String name = UUID.randomUUID().toString().concat(".").concat(extension);
    if (!file.isEmpty()) {
       try {
                byte[] bytes = file.getBytes();
                Path newPath = Paths.get(pathToUserPictures);
                Files.write(newPath, bytes, 	StandardOpenOption.CREATE);
       ...
  ...
  response.addHeader(LOCATION_HEADER, env.getProperty("pictures.user.endpoint").concat(name));
  return "Success";
  ...
  }
```

请求的文件部分被注入为参数。从请求文件的内容在服务器文件系统上创建一个新文件。响应中添加了一个新的`Location`头，其中包含指向创建的图像的链接。

在客户端上，此标头被读取并注入为我们 div 的`background-image` CSS 属性（请参见`user-account.html`）。

### 事务管理

该示例突出了我们在处理 REST 架构不同层之间的事务时应用的基本原则。事务管理本身是一个完整的章节，我们在这里只能呈现概述。

#### 简单的方法

在构建事务管理时，我们牢记 Spring MVC 控制器不是事务性的。在这种情况下，我们不能期望在控制器的同一方法处理程序中通过两个不同的服务调用进行事务管理。每个服务调用都会启动一个新的事务，并且预期该事务在返回结果时终止。

我们将服务定义为`@Transactional(readonly="true")`在类型级别，然后需要写访问权限的方法会在方法级别覆盖此定义，添加额外的`@Transactional`注解。我们的示例的第十步介绍了`TransactionServiceImpl`服务上的事务更改。使用默认传播，事务在事务性服务、存储库或方法之间得到维护和重用。

默认情况下，抽象的 Spring Data JPA 存储库是事务性的。我们只需要为我们的自定义存储库指定事务行为，就像我们为我们的服务所做的那样。

我们的配方的*第十一步*显示了对自定义存储库`IndexRepositoryImpl`进行的事务更改。

## 还有更多…

如前所述，我们在应用程序的不同层上配置了一致的事务管理。

### 事务管理

我们的覆盖范围有限，如果您对以下主题不熟悉，我们建议您寻找外部信息。

#### ACID 属性

有四个属性/概念经常用于评估事务的可靠性。因此，在设计事务时将它们牢记在心是有用且重要的。这些属性是原子性，一致性，隔离性和持久性。在维基百科页面上了解更多关于 ACID 事务的信息：

[`en.wikipedia.org/wiki/ACID`](https://en.wikipedia.org/wiki/ACID)

#### 全局与本地事务

我们只在应用程序中定义了本地事务。本地事务是在应用程序级别管理的，不能在多个 Tomcat 服务器之间传播。此外，当涉及多个事务资源类型时，本地事务无法确保一致性。例如，在与消息相关的数据库操作的用例中，当我们回滚无法传递的消息时，我们可能还需要回滚之前发生的相关数据库操作。只有实现了两阶段提交的全局事务才能承担这种责任。全局事务由 JTA 事务管理器实现处理。

在这个 Spring 参考文档中了解更多关于这个差异：

[`docs.spring.io/spring/docs/2.0.8/reference/transaction.html`](http://docs.spring.io/spring/docs/2.0.8/reference/transaction.html)

从历史上看，JTA 事务管理器是由 J2EE/JEE 容器专门提供的。现在，我们有其他选择，如 Atomikos ([`www.atomikos.com`](http://www.atomikos.com))，Bitronix ([`github.com/bitronix/btm`](https://github.com/bitronix/btm))或 JOTM ([`jotm.ow2.org/xwiki/bin/view/Main/WebHome`](http://jotm.ow2.org/xwiki/bin/view/Main/WebHome))等应用级 JTA 事务管理器实现，以确保 J2SE 环境中的全局事务。

Tomcat（7+）也可以与应用级 JTA 事务管理器实现一起工作，以反映容器中的事务管理，使用`TransactionSynchronizationRegistry`和 JNDI 数据源。

[`codepitbull.wordpress.com/2011/07/08/tomcat-7-with-full-jta`](https://codepitbull.wordpress.com/2011/07/08/tomcat-7-with-full-jta)

## 另请参阅

这三个标头可以从中获得性能和有用的元数据优势，这些在配方中没有详细说明。

+   **Cache-Control，ETag 和 Last-Modified**：Spring MVC 支持这些标头，作为入口点，我们建议您查看 Spring 参考：[`docs.spring.io/spring-framework/docs/current/spring-framework-reference/html/mvc.html#mvc-caching-etag-lastmodified`](http://docs.spring.io/spring-framework/docs/current/spring-framework-reference/html/mvc.html#mvc-caching-etag-lastmodified)

# 使用 bean 验证支持来验证资源

在介绍请求有效负载数据绑定过程之后，我们必须谈论验证。

## 准备工作

这个配方的目标是展示如何让 Spring MVC 拒绝不满足 bean 验证（JSR-303）或不满足定义的 Spring 验证器实现约束的请求体有效负载。

在 Maven 和 Spring 配置之后，我们将看到如何将验证器绑定到传入请求，如何定义验证器执行自定义规则，如何设置 JSR-303 验证，以及如何处理验证结果。

## 如何做…

1.  我们添加了一个 Maven 依赖项到 hibernate 验证器：

```java
<dependency>
  <groupId>org.hibernate</groupId>
  <artifactId>hibernate-validator</artifactId>
  <version>4.3.1.Final</version>
</dependency>
```

1.  在我们的`dispatcher-servlet.xml`（`cloudstreetmarket-api`）中注册了一个`LocalValidatorFactoryBean`：

```java
<bean id="validator" class="org.sfw.validation.beanvalidation.LocalValidatorFactoryBean"/>
```

1.  `UsersController`和`TransactionController`的`POST`和`PUT`方法签名已经改变，增加了`@Valid`注释在`@RequestBody`参数上：

```java
  @RequestMapping(method=PUT)
  @ResponseStatus(HttpStatus.OK)
  public void update(@Valid @RequestBody User user, 
  BindingResult result){
    ValidatorUtil.raiseFirstError(result);
    user = communityService.updateUser(user);
  }
```

### 注意

注意这里作为方法参数注入的`BindingResult`对象。我们将在大约一分钟内介绍`ValidatorUtil`类。

1.  我们的两个 CRUD 控制器现在有了一个新的`@InitBinder`注释的方法：

```java
  @InitBinder
    protected void initBinder(WebDataBinder binder) {
        binder.setValidator(new UserValidator());
    }
```

1.  这个方法将一个创建的验证器实现的实例绑定到请求。查看创建的`UserValidator`，它是`Validator`的实现：

```java
package edu.zipcloud.cloudstreetmarket.core.validators;
import java.util.Map;
import javax.validation.groups.Default;
import org.springframework.validation.Errors;
import org.springframework.validation.Validator;
import edu.zc.csm.core.entities.User;
import edu.zc.csm.core.util.ValidatorUtil;
public class UserValidator implements Validator {
  @Override
  public boolean supports(Class<?> clazz) {
    return User.class.isAssignableFrom(clazz);
  }
  @Override
  public void validate(Object target, Errors err) {
    Map<String, String> fieldValidation = ValidatorUtil.validate((User)target, Default.class);
    fieldValidation.forEach(
      (k, v) -> err.rejectValue(k, v)
    );
  }
}
```

1.  在`User`实体中，添加了一些特殊的注释：

```java
@Entity
@Table(name="users")
public class User extends ProvidedId<String> implements UserDetails{
  ...
  private String fullName;
  @NotNull
  @Size(min=4, max=30)
  private String email;
  @NotNull
  private String password;
  private boolean enabled = true;
  @NotNull
  @Enumerated(EnumType.STRING)
  private SupportedLanguage language;
  private String profileImg;

  @Column(name="not_expired")
  private boolean accountNonExpired;
  @Column(name="not_locked")
  private boolean accountNonLocked;

  @NotNull
  @Enumerated(EnumType.STRING)
  private SupportedCurrency currency;

  private BigDecimal balance;
  ...
}
```

1.  我们创建了`ValidatorUtil`类，以使这些验证更容易，并减少样板代码的数量：

```java
package edu.zipcloud.cloudstreetmarket.core.util;
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;
import java.util.Set;
import javax.validation.ConstraintViolation;
import javax.validation.Validation;
import javax.validation.Validator;
import javax.validation.ValidatorFactory;
import javax.validation.groups.Default;
import org.springframework.validation.BindingResult;

public class ValidatorUtil {
    private static Validator validator;
    static {
      ValidatorFactory factory = Validation.buildDefaultValidatorFactory();
      validator = factory.getValidator();
    }
```

以下的`validate`方法允许我们从任何可能需要的位置调用 JSR 验证：

```java
public static <T> Map<String, String> validate(T object, Class<?>... groups) {
  Class<?>[] args = Arrays.copyOf(groups, groups.length + 1);
  args[groups.length] = Default.class;
  return extractViolations(validator.validate(object, args));
}
private static <T> Map<String, String> extractViolations(Set<ConstraintViolation<T>> violations) {
  Map<String, String> errors = new HashMap<>();
  for (ConstraintViolation<T> v: violations) {
    errors.put(v.getPropertyPath().toString(), "["+v.getPropertyPath().toString()+"] " + StringUtils.capitalize(v.getMessage()));
  }
  return errors;
  }
```

以下的`raiseFirstError`方法不是特定标准的，这是我们向客户端呈现服务器端错误的方式：

```java
  public static void raiseFirstError(BindingResult result) {
    if (result.hasErrors()) {
      throw new IllegalArgumentException(result.getAllErrors().get(0).getCode());
    }
else if (result.hasGlobalErrors()) {
throw new IllegalArgumentException(result.getGlobalError().getDefaultMessage());
       }
}
}
```

1.  根据第四章，*为无状态架构构建 REST API*，cloudstreetmarket-api 的`RestExceptionHandler`仍然配置为处理`IllegalArgumentExceptions`，并以`ErrorInfo`格式化的响应呈现它们：

```java
@ControllerAdvice
public class RestExceptionHandler extends ResponseEntityExceptionHandler {
  @Autowired
  private ResourceBundleService bundle;
   @Override
  protected ResponseEntity<Object> handleExceptionInternal(Exception ex, Object body,
    HttpHeaders headers, HttpStatus status, WebRequest request) {
    ErrorInfo errorInfo = null;
    if(body!=null && bundle.containsKey(body.toString())){
        String key = body.toString();
        String localizedMessage = bundle.get(key);
        errorInfo = new ErrorInfo(ex, localizedMessage, key, status);
    }
    else{
      errorInfo = new ErrorInfo(ex, (body!=null)? body.toString() : null, null, status);
    }
return new ResponseEntity<Object>(errorInfo, headers, status);
}
  @ExceptionHandler({ InvalidDataAccessApiUsageException.class, DataAccessException.class, IllegalArgumentException.class })
  protected ResponseEntity<Object> handleConflict(final RuntimeException ex, final WebRequest request) {
      return handleExceptionInternal(ex, I18N_API_GENERIC_REQUEST_PARAMS_NOT_VALID, new HttpHeaders(), BAD_REQUEST, request);
    }
}
```

1.  在 UI 改进中浏览，您会注意到一个用于更新用户**首选项**的新表单。通过**登录**菜单可以访问这个表单，如下面的截图所示：![如何做…](img/image00889.jpeg)![如何做…](img/image00890.jpeg)

1.  在这个用户**首选项**表单中，当前端验证被停用（前端验证将在本章的最后一个配方中开发），不填写电子邮件字段会导致以下（可定制的）`ErrorInfo`对象在 HTTP 响应中：

```java
{"error":"[email] Size must be between 4 and 30",
"message":"The request parameters were not valid!",
"i18nKey":"error.api.generic.provided.request.parameters.not.valid",
"status":400,
"date":"2016-01-05 05:59:26.584"}
```

1.  在前端，为了处理这个错误，`accountController`（在`account_management.js`中）实例化时依赖于一个自定义的`errorHandler`工厂。代码如下：

```java
cloudStreetMarketApp.controller('accountController', function ($scope, $translate, $location, errorHandler, accountManagementFactory, httpAuth, genericAPIFactory){
      $scope.form = {
      id: "",
    email: "",
    fullName: "",
    password: "",
    language: "EN",
    currency: "",
    profileImg: "img/anon.png"
      };
  ...
}
```

1.  `accountController`有一个`update`方法，调用`errorHandler.renderOnForm`方法：

```java
  $scope.update = function () {
    $scope.formSubmitted = true;

    if(!$scope.updateAccount.$valid) {
        return;
    }
      httpAuth.put('/api/users', JSON.stringify($scope.form)).success(
      function(data, status, headers, config) {
        httpAuth.setCredentials($scope.form.id, $scope.form.password);
      $scope.updateSuccess = true;
      }
    ).error(function(data, status, headers, config) {
        $scope.updateFail = true;
        $scope.updateSuccess = false;
        $scope.serverErrorMessage = errorHandler.renderOnForms(data);
      }
    );
  };
```

1.  `main_menu.js`中定义了`errorHandler`如下。它具有从`i18n`代码中提取翻译消息的能力：

```java
cloudStreetMarketApp.factory("errorHandler", ['$translate', function ($translate) {
    return {
        render: function (data) {
        if(data.message && data.message.length > 0){
          return data.message;
        }
        else if(!data.message && data.i18nKey && data.i18nKey.length > 0){
          return $translate(data.i18nKey);
          }
        return $translate("error.api.generic.internal");
        },
        renderOnForms: function (data) {
        if(data.error && data.error.length > 0){
          return data.error;
        }
        else if(data.message && data.message.length > 0){
          return data.message;
        }
        else if(!data.message && data.i18nKey && data.i18nKey.length > 0){
          return $translate(data.i18nKey);
        }
        return $translate("error.api.generic.internal");
        }
    }
}]);
```

**首选项**表单如下所示：

![如何做…](img/image00891.jpeg)

### 提示

正如我们所说，要模拟这个错误，前端验证需要被停用。这可以通过在`user-account.html`中的`<form name="updateAccount" … novalidate>`标记中添加一个`novalidate`属性来实现。

1.  在服务器端，我们还为财务交易实体创建了一个自定义验证器。这个验证器利用了 Spring 的`ValidationUtils`：

```java
@Component
public class TransactionValidator implements Validator {
  @Override
  public boolean supports(Class<?> clazz) {
    return Transaction.class.isAssignableFrom(clazz);
  }
  @Override
  public void validate(Object target, Errors errors) {
    ValidationUtils.rejectIfEmpty(errors, "quote", " transaction.quote.empty");
    ValidationUtils.rejectIfEmpty(errors, "user", " transaction.user.empty");
    ValidationUtils.rejectIfEmpty(errors, "type", " transaction.type.empty");
  }
}
```

## 工作原理...

### 使用 Spring 验证器

Spring 提供了一个`Validator`接口(`org.sfw.validation.Validator`)，用于创建要注入或实例化在我们想要的层中的组件。因此，Spring 验证组件可以在 Spring MVC 控制器中使用。`Validator`接口如下：

```java
public interface Validator {
  boolean supports(Class<?> clazz);
  void validate(Object target, Errors errors);
}
```

`supports(Class<?> clazz)`方法用于评估`Validator`实现的域，也用于限制其使用到特定类型或超类型。

`validate(Object target, Errors errors)`方法规定了其标准，使得验证器的验证逻辑存在于这个位置。传递的`target`对象被评估，验证的结果存储在`org.springframework.validation.Errors`接口的实例中。这里显示了`Errors`接口的部分预览：

```java
public interface Errors {
  ...
  void reject(String errorCode);
  void reject(String errorCode, String defaultMessage);
void reject(String errorCode, Object[] errorArgs, String defaultMessage);
void rejectValue(String field, String errorCode); void rejectValue(String field, String errorCode, String defaultMessage);
void rejectValue(String field, String errorCode, Object[] errorArgs, String defaultMessage);
  void addAllErrors(Errors errors);
  boolean hasErrors();
  int getErrorCount();
  List<ObjectError> getAllErrors();
  ...
}
```

使用 Spring MVC，我们有可能将`Validator`绑定和触发到特定的方法处理程序。框架会寻找绑定到传入请求的验证器实例。我们在*第四步*的配方中配置了这样的绑定：

```java
  @InitBinder
    protected void initBinder(WebDataBinder binder) {
        binder.setValidator(new UserValidator());
    }
```

### 提示

我们已经使用了 `@InitBinder` 注解将其他对象（格式化程序）附加到传入请求（参见第四章 *构建无状态架构的 REST API* 中的 *绑定请求，编组响应* 教程）。

`Binders` (`org.springframework.validation.DataBinder`) 允许将属性值设置到目标对象上。Binders 还提供了对验证和绑定结果分析的支持。

`DataBinder.validate()` 方法在每个绑定步骤之后被调用，这个方法调用了附加到 `DataBinder` 的主验证器的 `validate`。

绑定过程填充了一个结果对象，这是 `org.springframework.validation.BindingResult` 接口的一个实例。可以使用 `DataBinder.getBindingResult()` 方法检索此结果对象。

实际上，`BindingResult` 实现也是一个 `Errors` 实现（如此处所示）。我们之前介绍过 `Errors` 接口。查看以下代码：

```java
public interface BindingResult extends Errors {
  Object getTarget();
  Map<String, Object> getModel();
  Object getRawFieldValue(String field);
  PropertyEditor findEditor(String field, Class<?> valueType);
  PropertyEditorRegistry getPropertyEditorRegistry();
  void addError(ObjectError error);
  String[] resolveMessageCodes(String errorCode);
  String[] resolveMessageCodes(String errorCode, String field);
  void recordSuppressedField(String field);
  String[] getSuppressedFields();
}
```

整个设计可以总结如下：

我们创建了一个验证器实现。当特定控制器方法处理程序的传入请求到达时，请求有效负载将转换为由 `@RequestBody` 注解（在我们的案例中是一个 `Entity`）所针对的类的实例。我们的验证器实现的一个实例绑定到注入的 `@RequestBody` 对象上。如果注入的 `@RequestBody` 对象使用 `@Valid` 注解定义，框架会要求 `DataBinder` 在每个绑定步骤上验证对象，并将错误存储在 `DataBinder` 的 `BindingResultobject` 中。

最后，这个 `BindingResult` 对象被注入为方法处理程序的参数，因此我们可以决定如何处理它的错误（如果有的话）。在绑定过程中，缺少字段和属性访问异常被转换为 `FieldErrors`。这些 `FieldErrors` 也被存储到 `Errors` 实例中。以下错误代码用于 `FieldErrors`：

```java
Missing field error: "required"
Type mismatch error: "typeMismatch"
Method invocation error: "methodInvocation"
```

当需要为用户返回更好的错误消息时，`MessageSource` 帮助我们处理查找并从 `MessageSourceResolvable` 实现中检索正确的本地化消息，方法如下：

```java
MessageSource.getMessage(org.sfw.context.MessageSourceResolvable, java.util.Locale). 
```

### 提示

`FieldError` 扩展了 `ObjectError`，而 `ObjectError` 扩展了 `DefaultMessageSourceResolvable`，它是 `MessageSourceResolvable` 的实现。

#### ValidationUtils

`ValodationUtils` 实用程序类 (`org.sfw.validation.ValidationUtils`) 提供了一些方便的静态方法，用于调用验证器和拒绝空字段。这些实用方法允许一行断言，同时处理 `Errors` 对象的填充。在这个教程中，第 14 步详细介绍了我们的 `TransactionValidator` 如何使用 `ValidationUtils`。

#### I18n 验证错误

下一个教程将专注于错误和内容的国际化。然而，让我们看看我们如何从控制器捕获错误以及如何显示它们。`UserController` 的 `update` 方法在第一行有这个自定义方法调用：

```java

ValidatorUtil.raiseFirstError(result);
```

我们为我们的需求创建了 `ValidatorUtil` 支持类；想法是对我们的验证器可以检测到的任何类型的错误抛出 `IllegalArgumentException`。`ValidatorUtil.raiseFirstError(result)` 方法调用也可以在 `TransactionController.update(…)` 方法处理程序中找到。这个方法处理程序依赖于 *第 14 步* 中介绍的 `TransactionValidator`。

如果你还记得这个 `TransactionValidator`，当财务交易对象中不存在报价对象时，它会创建一个带有 `transaction.quote.empty` 消息代码的错误。然后会抛出一个带有 `transaction.quote.empty` 消息详细信息的 `IllegalArgumentException`。

在下一个教程中，我们将重新审视如何构建并从 `IllegalArgumentException` 发送适当的国际化 JSON 响应给客户端。

### 使用 JSR-303/JSR-349 Bean 验证

Spring Framework 4 及以上版本支持 bean 验证 1.0（JSR-303）和 bean 验证 1.1（JSR-349）。它还将此 bean 验证适配到`Validator`接口，并允许使用注解创建类级验证器。

JSR-303 和 JSR-349 这两个规范定义了一组适用于 bean 的约束，作为`javax.validation.constraints`包中的注解。

通常，使用规范中的代码而不是实现中的代码的一个很大的优势是我们不必知道使用的是哪个实现。此外，实现总是可以潜在地被另一个实现替换。

Bean 验证最初是为持久性 bean 设计的。即使规范与 JPA 的耦合度相对较低，参考实现仍然是 Hibernate 验证器。具有支持这些验证规范的持久性提供程序绝对是一个优势。现在有了 JPA2，持久性提供程序在持久化之前会自动调用 JSR-303 验证。确保来自两个不同层（控制器和模型）的这些验证会提高我们的信心水平。

#### 字段约束注解

我们在所呈现的`User`实体上定义了`@NotNull`和`@Size` JSR-303 注解。显然，在规范中可以找到的注解不止两个。

这里是 JEE7 中`javax.validation.constraints`注解包的摘要表：

| 注解类型 | 描述 |
| --- | --- |
| `AssertFalse` | 被注释的元素必须为 false。 |
| `AssertFalse.List` | 在同一个元素上定义了几个`AssertFalse`注解。 |
| `AssertTrue` | 被注释的元素必须为 true。 |
| `AssertTrue.List` | 在同一个元素上定义了几个`AssertTrue`注解。 |
| `DecimalMax` | 被注释的元素必须是一个数，其值必须低于或等于指定的最大值。 |
| `DecimalMax.List` | 在同一个元素上定义了几个`DecimalMax`注解。 |
| `DecimalMin` | 被注释的元素必须是一个数，其值必须高于或等于指定的最小值。 |
| `DecimalMin.List` | 在同一个元素上定义了几个`DecimalMin`注解。 |
| `Digits` | 被注释的元素必须是在接受范围内的数字。支持的类型有：`BigDecimal`、`BigInteger`、`CharSequence`、`byte`、`short`、`int`、`long`及其相应的包装类型。但是，`null`元素被视为有效。 |
| `Digits.List` | 在同一个元素上定义了几个`Digits`注解。 |
| `Future` | 被注释的元素必须是将来的日期。 |
| `Future.List` | 在同一个元素上定义了几个`Future`注解。 |
| `Max` | 被注释的元素必须是一个数，其值必须低于或等于指定的最大值。 |
| `Max.List` | 在同一个元素上定义了几个`Max`注解。 |
| `Min` | 被注释的元素必须是一个数，其值必须高于或等于指定的最小值。 |
| `Min.List` | 在同一个元素上定义了几个`Min`注解。 |
| `NotNull` | 被注释的元素不得为`null`。 |
| `NotNull.List` | 在同一个元素上定义了几个`NotNull`注解。 |
| `Past` | 被注释的元素必须是过去的日期。 |
| `Past.List` | 在同一个元素上定义了几个`Past`注解。 |
| `Pattern` | 被注释的`CharSequence`必须匹配指定的正则表达式。 |
| `Pattern.List` | 在同一个元素上定义了几个`Pattern`注解。 |
| `Size` | 被注释的元素大小必须在指定的边界之间（包括在内）。 |
| `Size.List` | 在同一个元素上定义了几个`Size`注解。 |

##### 特定于实现的约束

Bean 验证实现也可以超出规范，并提供它们自己的一组额外验证注释。Hibernate 验证器有一些有趣的注释，如`@NotBlank`，`@SafeHtml`，`@ScriptAssert`，`@CreditCardNumber`，`@Email`等。这些都列在 hibernate 文档中，可在以下 URL 访问

[`docs.jboss.org/hibernate/validator/4.3/reference/en-US/html_single/#table-custom-constraints`](http://docs.jboss.org/hibernate/validator/4.3/reference/en-US/html_single/#table-custom-constraints)

#### LocalValidator（可重用）

我们在 Spring 上下文中定义了以下验证器 bean：

```java
<bean id="validator" class="org.sfw.validation.beanvalidation.LocalValidatorFactoryBean"/>
```

此 bean 生成实现 JSR-303 和 JSR-349 的验证器实例。您可以在这里配置特定的提供程序类。默认情况下，Spring 在类路径中查找 Hibernate Validator JAR。一旦定义了这个 bean，它就可以被注入到需要的任何地方。

我们已经在我们的`UserValidator`中注入了这样的验证器实例，这使其符合 JSR-303 和 JSR-349。

对于国际化，验证器生成其一组默认消息代码。这些默认消息代码和值看起来像下面这样：

```java
javax.validation.constraints.Max.message=must be less than or equal to {value}
javax.validation.constraints.Min.message=must be greater than or equal to {value}
javax.validation.constraints.Pattern.message=must match "{regexp}"
javax.validation.constraints.Size.message=size must be between {min} and {max}
```

请随意在您自己的资源文件中覆盖它们！

## 还有更多…

在本节中，我们突出了一些我们没有解释的验证概念和组件。

### ValidationUtils

`ValidationUtils` Spring 实用程序类提供了方便的静态方法，用于调用`Validator`并拒绝填充错误对象的空字段，一行中的错误对象：

[`docs.spring.io/spring/docs/3.1.x/javadoc-api/org/springframework/validation/ValidationUtils.html`](http://docs.spring.io/spring/docs/3.1.x/javadoc-api/org/springframework/validation/ValidationUtils.html)

### 分组约束

我们可以将约束耦合到多个字段上，以定义一组更高级的约束：

[`beanvalidation.org/1.1/spec/#constraintdeclarationvalidationpr ocess-groupsequence`](http://beanvalidation.org/1.1/spec/#constraintdeclarationvalidationpr%20ocess-groupsequence)

[`docs.jboss.org/hibernate/stable/validator/reference/en-US/ html_single/#chapter-groups`](http://docs.jboss.org/hibernate/stable/validator/reference/en-US/%20html_single/#chapter-groups)

### 创建自定义验证器

有时创建一个具有自己注释的特定验证器可能很有用。检查链接，它应该带我们到：

[`howtodoinjava.com/2015/02/12/spring-mvc-custom-validator-example/`](http://howtodoinjava.com/2015/02/12/spring-mvc-custom-validator-example/)

### 关于验证的 Spring 参考

最好的信息来源仍然是 Spring 关于`Validation`的参考。检查链接，它应该带我们到：

[`docs.spring.io/spring/docs/current/spring-framework-reference/html/validation.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/validation.html)

## 另请参阅

+   整个 bean 验证规范（JSR-303 和 JSR-349）都有自己的网站：[`beanvalidation.org/1.1/spec`](http://beanvalidation.org/1.1/spec)。

# 为 REST 国际化消息和内容

在谈论国际化内容和消息之前，有必要谈论验证。对于全球和基于云的服务，仅支持一种语言的内容通常是不够的。

在这个示例中，我们提供了一个适合我们设计的实现，因此继续满足我们的可扩展性标准，不依赖于 HTTP 会话。

我们将看到如何定义`MessageSource` bean 来获取给定位置的最合适的消息。我们将看到如何序列化资源属性，使其可用于前端。我们将在前端使用 AngularJS 和 angular-translate 实现内容的动态翻译。

## 如何做…

在这个示例中，既有后端工作，也有前端工作。

### 后端

1.  以下 bean 已在核心上下文（`csm-core-config.xml`）中注册：

```java
<bean id="messageBundle" class="edu.zc.csm.core.i18n.SerializableResourceBundleMessageSource">
<property name="basenames" value="classpath:/META-INF/i18n/messages,classpath:/META-INF/i18n/errors"/>
  <property name="fileEncodings" value="UTF-8" />
  <property name="defaultEncoding" value="UTF-8" />
</bean>
```

1.  这个 bean 引用了一个创建的`SerializableResourceBundleMessageSource`，它收集资源文件并提取属性：

```java
/**
 * @author rvillars
 * {@link https://github.com/rvillars/bookapp-rest} 
 */
public class SerializableResourceBundleMessageSource extends ReloadableResourceBundleMessageSource {
   public Properties getAllProperties(Locale locale) {
      clearCacheIncludingAncestors();
      PropertiesHolder propertiesHolder = getMergedProperties(locale);
      Properties properties = propertiesHolder.getProperties();
    return properties;
  }
}
```

1.  这个 bean 包从两个地方访问：

新创建的`PropertiesController`公开（序列化）特定位置（这里只是语言）的所有消息和错误：

```java
@RestController
@ExposesResourceFor(Transaction.class)
@RequestMapping(value="/properties")
public class PropertiesController{
  @Autowired
  protected SerializableResourceBundleMessageSource messageBundle;
  @RequestMapping(method = RequestMethod.GET, produces={"application/json; charset=UTF-8"})
  @ResponseBody
  public Properties list(@RequestParam String lang) {
    return messageBundle.getAllProperties(new Locale(lang));
  }
}
```

已构建了一个特定的服务层，用于轻松地在控制器和服务之间提供消息和错误：

```java
@Service
@Transactional(readOnly = true)
public class ResourceBundleServiceImpl implements ResourceBundleService {
  @Autowired
protected SerializableResourceBundleMessageSource messageBundle;
  private static final Map<Locale, Properties> localizedMap = new HashMap<>();
  @Override
  public Properties getAll() {
    return getBundleForUser();
  }
  @Override
  public String get(String key) {
    return getBundleForUser().getProperty(key);
  }
  @Override
  public String getFormatted(String key, String... arguments) {
    return MessageFormat.format( getBundleForUser().getProperty(key), arguments
    );
  }
  @Override
  public boolean containsKey(String key) {
    return getAll().containsKey(key);
  }
  private Properties getBundleForUser(){
    Locale locale = AuthenticationUtil.getUserPrincipal().getLocale();
    if(!localizedMap.containsKey(locale)){
      localizedMap.put(locale, messageBundle.getAllProperties(locale));
    }
    return localizedMap.get(locale);
}
}
```

### 注意

`ResourceBundleServiceImpl`目前使用相同的`SerializableResourceBundleMessageSource`。它还从已登录用户（Spring Security）中提取区域设置，如果失败则回退到英语。

1.  这个`ResourceBundleServiceImpl`服务被注入到我们的`WebContentInterceptor` `CloudstreetApiWCI:`中

```java
  @Autowired
  protected ResourceBundleService bundle;
```

1.  例如，在`TransactionController`中，bundle 被定位以提取错误消息：

```java
if(!transaction.getUser().getUsername()
    .equals(getPrincipal().getUsername())){
  throw new AccessDeniedException( bundle.get(I18nKeys.I18N_TRANSACTIONS_USER_FORBIDDEN)
);
}
```

1.  `I18nKeys`只是一个承载资源键的常量的类：

```java
public class I18nKeys {
  //Messages
public static final String I18N_ACTION_REGISTERS = "webapp.action.feeds.action.registers";
public static final String I18N_ACTION_BUYS = "webapp.action.feeds.action.buys";
public static final String I18N_ACTION_SELLS = "webapp.action.feeds.action.sells";
 ...
}
```

1.  资源文件位于核心模块中：![后端](img/image00892.jpeg)

### 前端

1.  在`index.jsp`中添加了两个 angular-translate 的依赖项：

```java
<script src="img/angular-translate.min.js"></script>
<script src="img/angular-translate-loader-url.min.js"></script>
```

1.  在`index.jsp`中配置翻译模块如下：

```java
cloudStreetMarketApp.config(function ($translateProvider) {
   	$translateProvider.useUrlLoader('/api/properties.json');
  $translateProvider.useStorage('UrlLanguageStorage');
  $translateProvider.preferredLanguage('en');
  $translateProvider.fallbackLanguage('en');
});
```

### 注意

您可以看到它定位到我们的 API 端点，只提供消息和错误。

1.  用户语言是从主菜单(`main_menu.js`)中设置的。用户被加载，并且语言从用户对象中提取（默认为 EN）：

```java
cloudStreetMarketApp.controller('menuController',  function ($scope, $translate, $location, modalService, httpAuth, genericAPIFactory) {
    $scope.init = function () {
    ...
  genericAPIFactory.get("/api/users/"+httpAuth.getLoggedInUser()+".json")
  .success(function(data, status, headers, config) {
      $translate.use(data.language);
      $location.search('lang', data.language);
  });
  }
  ...
  }
```

1.  在 DOM 中，i18n 内容直接引用通过翻译指令进行翻译。例如，在`stock-detail.html`文件中查看：

```java
<span translate="screen.stock.detail.will.remain">Will remain</span>
```

`index-detail.html`文件中的另一个例子如下：

```java
<td translate>screen.index.detail.table.prev.close</td>
```

在`home.html`中，您可以找到其值如下翻译的作用域变量：

```java
{{value.userAction.presentTense | translate}}
```

1.  在应用程序中，更新您的个人偏好设置，并将您的语言设置为**法语**。例如，尝试访问可以从**stock-search**结果到达的**stock-detail**页面：![前端](img/image00893.jpeg)

1.  从**stock-detail**页面，您可以处理一个交易（用法语！）：![前端](img/image00894.jpeg)

## 它是如何工作的...

让我们来看看后端的变化。您首先需要了解的是自动装配的`SerializableResourceBundleMessageSource` bean，从中使用消息键提取国际化消息。

这个 bean 扩展了特定的`MessageSource`实现。存在几种类型的`MessageSource`，重要的是要理解它们之间的区别。我们将重新访问从用户那里提取`Locale`的方式，并看看如何使用`LocaleResolver`根据不同的可读性路径（会话、Cookie、接受标头等）来读取或猜测用户语言。

### MessageSource beans

首先，`MessageSource`是一个 Spring 接口（`org.sfw.context.MessageSource`）。`MessageSource`对象负责从不同的参数解析消息。

最有趣的参数是我们想要的消息的键和`Locale`（语言/国家组合），它将驱动正确的语言选择。如果没有提供`Locale`，或者`MessageSource`无法解析匹配的语言/国家文件或消息条目，它将退回到更通用的文件，并再次尝试，直到达到成功的解析。

如图所示，`MessageSource`实现仅公开`getMessage(…)`方法：

```java
public interface MessageSource {
  String getMessage(String code, Object[] args, String defaultMessage, Locale locale);
  String getMessage(String code, Object[] args, Locale locale) throws NoSuchMessageException;
  String getMessage(MessageSourceResolvable resolvable, Locale locale) throws NoSuchMessageException;
}
```

这个轻量级接口由 Spring 中的几个对象实现（特别是在上下文组件中）。但是，我们特别寻找`MessageSource`实现，Spring 4+中有三个特别值得一提。

#### ResourceBundleMessageSource

这个`MessageSource`实现使用指定的基本名称访问资源包。它依赖于底层 JDK 的`ResourceBundle`实现，结合 JDK 的标准消息解析提供的`MessageFormat`(`java.text.MessageFormat`)。

对于每条消息，访问的`ResourceBundle`实例和生成的`MessageFormat`都被缓存。`ResourceBundleMessageSource`提供的缓存比`java.util.ResourceBundle`类的内置缓存要快得多。

使用`java.util.ResourceBundle`时，当 JVM 正在运行时无法重新加载 bundle。因为`ResourceBundleMessageSource`依赖于`ResourceBundle`，它面临着相同的限制。

#### ReloadableResourceBundleMessageSource

与`ResourceBundleMessageSource`相比，这个类使用`Properties`实例作为消息的自定义数据结构。它通过使用 Spring Resource 对象的`PropertiesPersister`策略加载它们。

这种策略不仅能够根据时间戳更改重新加载文件，还能以特定字符编码加载属性文件。

`ReloadableResourceBundleMessageSource`支持使用`cacheSeconds`设置重新加载属性文件，并支持以编程方式清除属性缓存。

用于识别资源文件的基本名称是使用`basenames`属性（在 ReloadableResourceBundleMessageSource 配置中）定义的。定义的基本名称遵循基本的`ResourceBundle`约定，不指定文件扩展名或语言代码。我们可以引用任何 Spring 资源位置。使用`classpath`前缀，资源仍然可以从类路径加载，但在这种情况下，除了`-1`（永久缓存）之外的`cacheSeconds`值将不起作用。

#### StaticMessageSource

`StaticMessageSource`是一个简单的实现，允许以编程方式注册消息。它适用于测试而不是在生产中使用。

### 我们的 MessageSource bean 定义

我们实现了一个特定的控制器，用于序列化和公开我们资源包属性文件（错误和消息）的整个聚合，传递给作为查询参数的特定语言。

为了实现这一点，我们创建了一个自定义的`SerializableResourceBundleMessageSource`对象，借鉴了 Roger Villars 的*bookapp-rest*应用程序（[`github.com/rvillars/bookapp-rest`](https://github.com/rvillars/bookapp-rest)）。

这个自定义的`MessageSource`对象扩展了`ReloadableResourceBundleMessageSource`。我们已经用以下定义将其作为 Spring bean：

```java
<bean id="messageBundle" class="edu.zc.csm.core.i18n.SerializableResourceBundleMessageSource">
<property name="basenames" value="classpath:/META-INF/i18n/messages,classpath:/META-INF/i18n/errors"/>
  <property name="fileEncodings" value="UTF-8" />
  <property name="defaultEncoding" value="UTF-8" />
</bean>
```

我们已经在类路径中具体指定了资源文件的路径。这可以通过上下文中的全局资源 bean 来避免：

```java
<resources location="/, classpath:/META-INF/i18n" mapping="/resources/**"/>
```

请注意，Spring MVC 默认情况下期望 i18n 资源文件位于`/WEB-INF/i18n`文件夹中。

### 使用 LocaleResolver

在我们的应用程序中，为了将`Locale`切换到另一种语言/国家，我们通过用户偏好屏幕。这意味着我们以某种方式将这些信息持久化到数据库中。这使得`LocaleResolution`变得容易，实际上是在客户端上操作，读取用户数据并异步调用语言偏好的国际化消息。

然而，一些其他应用程序可能希望在服务器端操作`LocaleResolution`。为此，必须注册一个`LocaleResolver` bean。

`LocaleResolver`是一个 Spring 接口（`org.springframework.web.servlet.LocaleResolver`）：

```java
public interface LocaleResolver {
  Locale resolveLocale(HttpServletRequest request);
  void setLocale(HttpServletRequest request, HttpServletResponse response, Locale locale);
}
```

在 Spring MVC（版本四及以上）中有四种具体的实现：

#### AcceptHeaderLocaleResolver

AcceptHeaderLocaleResolver 利用 HTTP 请求的`Accept-Language`头。它提取值中包含的第一个 Locale。这个值通常由客户端的 Web 浏览器设置，从操作系统配置中读取。

#### FixedLocaleResolver

这个解析器总是返回一个固定的默认 Locale，可选地带有一个时区。默认的 Locale 是当前 JVM 的默认 Locale。

#### SessionLocaleResolver

当应用程序实际上使用用户会话时，这个解析器是最合适的。它读取并设置一个会话属性，其名称仅用于内部使用：

```java
public static final String LOCALE_SESSION_ATTRIBUTE_NAME = SessionLocaleResolver.class.getName() + ".LOCALE";
```

默认情况下，它从默认的`Locale`或`Accept-Language`头部设置值。会话还可以可选地包含一个关联的时区属性。或者，我们可以指定一个默认时区。

在这些情况下的最佳实践是创建一个额外的特定的 Web 过滤器。

#### CookieLocaleResolver

`CookieLocaleResolver`是一个适用于像我们这样的无状态应用程序的解析器。可以使用`cookieName`属性自定义 cookie 名称。如果在内部定义的请求参数中找不到`Locale`，它会尝试读取 cookie 值，并回退到`Accept-Language`头部。

cookie 还可以可选地包含一个关联的时区值。我们也可以指定一个默认时区。

## 还有更多...

### 使用 angular-translate.js 在客户端进行翻译

我们使用`angular-translate.js`来处理翻译，并从客户端端切换用户区域设置。`angular-translate.js`库非常完整并且有很好的文档。作为一个依赖项，它非常有用。

这个产品的主要点是提供：

+   组件（过滤器/指令）来翻译内容

+   异步加载 i18n 数据

+   使用`MessageFormat.js`支持复数形式

+   通过易于使用的接口进行扩展

这个图中显示了**angular-translate**的简要概述：

![使用 angular-translate.js 在客户端进行翻译](img/image00895.jpeg)

国际资源可以从 API 端点动态拉取（就像我们所做的那样），也可以从发布在 Web 应用程序路径上的静态资源文件中拉取。这些特定区域设置的资源存储在客户端上，可以使用`LocalStorage`或`cookies`。

存储的数据对应于一个变量（在我们的情况下是`UrlLanguageStorage`），该变量可以在任何可能需要翻译功能的模块中访问和注入。

如下例所示，`translate`指令可用于实际呈现翻译的消息：

```java
  <span translate>i18n.key.message</span> or  
  <span translate=" i18n.key.message" >fallBack translation in English (better for Google indexes) </span>
```

或者，我们可以使用预定义的翻译过滤器来在 DOM 中翻译我们的翻译键，而不让任何控制器或服务知道它们：

```java
{{data.type.type == 'BUY' ? 'screen.stock.detail.transaction.bought' : 'screen.stock.detail.transaction.sold' | translate}}
```

您可以在他们非常完善的文档中了解更多关于 angular-translate 的信息：

[`angular-translate.github.io`](https://angular-translate.github.io)

# 使用 HTML5 AngularJS 验证客户端表单

验证提交的数据在前端和后端都是一个很好的实践。谈到验证，区分用户体验和数据完整性保护也是很好的。这两者是两个不同的责任，可能由不同的团队负责。

我们相信*前端*验证已经取代了以前由*后端*管理的表单验证。在一个 API 与 Web 内容解耦的可扩展环境中，验证体验现在是客户端界面的责任，可以是多个（甚至由第三方实现）如网站、移动网站、移动应用等。

在这个示例中，我们将专注于表单验证，更具体地说是 AngularJS 表单验证。

## 如何做...

1.  让我们再次考虑**用户首选项**表单。这是 HTML 定义（`user-account.html`）：

```java
<form name="updateAccount" action="#" ng-class="formSubmitted ? 'submitted':''">
  <fieldset>
    <div class="clearfix span">
      <label for="id" translate> screen.preference.field.username</label>
        <div class="input">
<input type="text" name="id" placeholder="Username" ng-model="form.id" ng-minlength="4" ng-maxlength="15" readonly required/>
<span class="text-error" ng-show="formSubmitted && updateAccount.id.$error.required" translate>   error.webapp.user.account.username.required</span>
        </div>
<label for="email" translate> screen.preference.field.email</label>
      <div class="input">
<input type="email" name="email" placeholder="Email" ng-model="form.email"/>
<span class="text-error" ng-show="formSubmitted && 
  updateAccount.email.$error" translate>error.webapp.user.account.email</span>
      </div>
<label for="password" translate> screen.preference.field.password</label>
      <div class="input">
<input type="password" name="password" ng-minlength="5" placeholder="Please type again" ng-model="form.password" required/>
<span class="text-error" ng-show="formSubmitted && updateAccount.password.$error.required" translate>   error.webapp.user.account.password.type.again</span>
<span class="text-error" ng-show="formSubmitted && updateAccount.password.$error.minlength" translate>   error.webapp.user.account.password.too.short</span>
</div>   
<label for="fullname" translate>   screen.preference.field.full.name</label>
        <div class="input" >
<input type="text" name="fullname" placeholder="Full name" ng-model="form.fullname"/>
        </div>
<label for="currencySelector" translate>   screen.preference.field.preferred.currency</label>
        <div class="input">
<select class="input-small"  id="currencySelector" ng-model="form.currency" ng-init="form.currency='USD'" ng-selected="USD" ng-change="updateCredit()">
        <option>USD</option><option>GBP</option>
        <option>EUR</option><option>INR</option>
        <option>SGD</option><option>CNY</option>
        </select>
        </div>
<label for="currencySelector" translate>   screen.preference.field.preferred.language</label>
        <div class="input">
      <div class="btn-group">
<button onclick="return false;" class="btn" tabindex="-1"><span class="lang-sm lang-lbl" lang="{{form.language | lowercase}}"></button>
<button class="btn dropdown-toggle" data-toggle="dropdown" tabindex="-1">
        <span class="caret"></span>
        </button>
       <ul class="dropdown-menu">
<li><a href="#" ng-click="setLanguage('EN')"><span class="lang-sm lang-lbl-full" lang="en"></span></a></li>
<li><a href="#" ng-click="setLanguage('FR')">  <span class="lang-sm lang-lbl-full" lang="fr"></span></a></li>
        </ul>
        </div>
        </div>
     </div>
  </fieldset>
</form>
```

1.  `account_management.js`控制器中的 JavaScript 部分包括两个引用函数和四个变量，用于控制表单验证及其样式：

```java
  $scope.update = function () {
      	$scope.formSubmitted = true;
      if(!$scope.updateAccount.$valid) {
       return;
  }
httpAuth.put('/api/users', JSON.stringify($scope.form)).success(
    function(data, status, headers, config) {
      httpAuth.setCredentials(
        $scope.form.id, $scope.form.password);
        $scope.updateSuccess = true;
        }).error(function(data,status,headers,config) {
          $scope.updateFail = true;
          $scope.updateSuccess = false;
$scope.serverErrorMessage = errorHandler.renderOnForms(data);
    });
 };
    $scope.setLanguage = function(language) {
    $translate.use(language);
    $scope.form.language = language;
   }

   //Variables initialization
   $scope.formSubmitted = false;
   $scope.serverErrorMessage ="";
   $scope.updateSuccess = false;
   $scope.updateFail = false;
```

已创建两个 CSS 类以正确呈现字段上的错误：

```java
.submitted  input.ng-invalid{
  border: 2px solid #b94a48;
  background-color: #EBD3D5;!important;
} 
.submitted .input .text-error {
  font-weight:bold;
  padding-left:10px;
}
```

1.  如果您尝试输入错误的电子邮件或者尝试在不输入密码的情况下提交表单，您应该观察到以下验证控件：![如何做...](img/image00896.jpeg)

## 它是如何工作的...

AngularJS 提供了设置客户端表单验证的工具。与 AngularJS 一样，这些工具与现代 HTML5 技术和标准很好地集成在一起。

HTML5 表单提供了本地验证，可以使用标签和属性在不同的表单元素（输入、选择...）上定义基本字段验证（最大长度、必填...）

AngularJS 从一开始就完善和扩展了这些标准定义，使它们具有交互性和响应性，而且没有额外开销。

### 验证约束

让我们更仔细地看一下可以放置在表单控件上的可用验证选项。

#### 必填

`input`字段可以被标记为`required`（HTML5 标签）：

```java
<input type="text" required /> 
```

#### 最小/最大长度

`ng-minlength`指令可用于断言输入字符的数量是否达到给定的阈值：

```java
<input type="text" ng-minlength="3" /> 
```

同样，`ng-maxlength`可以大大限制输入字符的数量到最大值：

```java
<input type="text" ng-maxlength="15" /> 
```

#### 正则表达式模式

`ng-pattern`指令通常用于确保输入的数据与预定义的形状匹配：

```java
<input type="text" ng-pattern="[a-zA-Z]" />
```

#### 数字/电子邮件/URL

这些 HTML5 输入类型由 AngularJS 处理，以便限制在它们所代表的格式内：

```java
<input type="number" name="quantity" ng-model="form.quantity" />
<input type="email" name="email" ng-model=" form.email" />
<input type="url" name="destination" ng-model=" form.url" />
```

### 表单中的控制变量

AngularJS 在包含的`$scope`上发布属性，以匹配 DOM 中的表单状态。这使得 JavaScript 表单验证非常容易控制错误并呈现状态。

这些属性可以从以下结构中访问：

```java
  formName.inputFieldName.property
```

#### 修改/未修改状态

可以使用以下属性来评估这种状态：

```java
formName.inputFieldName.$pristine;
formName.inputFieldName.$dirty;
```

#### 有效/无效状态

可以根据字段或全局定义的验证来评估表单的有效状态：

```java
formName.inputFieldName.$valid;
formName.inputFieldName.$invalid;
formName.$valid;
formName.$invalid;
```

#### 错误

在我们之前定义的有效性评估之后，可以从`$error`属性中提取有关出现了什么问题的更多信息：

```java
myForm.username.$error.pattern
myForm.username.$error.required
myForm.username.$error.minlength
```

`$error`对象包含特定表单的所有验证信息，并反映这些验证是否令人满意。

### 表单状态转置和样式

与 AngularJS 一样，转置是为了将 DOM 状态与作用域绑定。因此，表单状态和控件状态会实时反映在 CSS 类中。这些 CSS 类可以被定义/覆盖，以便定义全局验证样式：

```java
input.ng-invalid {
  border: 1px solid red;
}
input.ng-valid {
  border: 1px solid green;
}
```

## 参见

+   **AngularJS 表单文档**：了解有关 AngularJS 表单验证功能的更多信息（我们只是在这里介绍了它们）：[`docs.angularjs.org/guide/forms`](https://docs.angularjs.org/guide/forms)

# 第八章。通过 WebSockets 和 STOMP 进行通信

本章涵盖了四个配方。它们都充分拥抱了我们的 CloudStreet Market 应用程序。通过改进，使其更具反应性，更具互动性。

这些配方有以下标题：

+   使用 STOMP 通过 SockJS 流式传输社交事件

+   使用 RabbitMQ 作为多协议消息代理

+   在 RabbitMQ 中堆叠和消费任务与 AMQP

+   使用 Spring Session 和 Redis 保护消息

# 介绍

让我们快速回顾一下在前几章中希望你已经学到的内容。逐章，你必须已经发现：

+   如何启动一个项目，以及如何依赖标准来保持代码库的可扩展性和适应性。这些标准来自于一系列工具的选择，例如 Maven 或 Java Persistence API。所呈现的标准还伴随着一系列常见实践，例如在客户端，使用 AngularJS MVC 模式或 Bootstrap Framework UI。

+   如何在面对现代挑战时充分利用 Spring MVC。Spring MVC 已被证明是一个 Web MVC 框架（具有其请求流程、内容协商、视图解析、模型绑定、异常处理等），但也作为 Spring 环境中集成的 Spring 组件进行了演示。它是一个集成框架，能够传递 Spring Security 身份验证或 Spring Social 抽象。它还能够提供 Spring Data 分页工具以及对 HTTP 规范的竞争性实现。

+   如何设计一个实现高级无状态和超媒体 API 的微服务架构，促进职责的分离。前端和后端之间的职责分离，以及组件的功能可分割性（水平可伸缩性）在独立的 Web 存档（`.war`）中的职责分离。

本章重点介绍新兴的 WebSocket 技术以及为我们的应用程序构建**面向消息的中间件**（**MOM**）。这是一个罕见的展示，它在 Spring 中实现了如此多关于 WebSocket 的内容。从使用默认的嵌入式 WebSocket 消息代理到完整功能的 RabbitMQ 代理（使用 STOMP 和 AMQP 协议）。我们将看到如何向多个客户端广播消息并推迟执行耗时任务，提供显著的可伸缩性优势。

通过一个专门用于需要访问常见数据库服务器的 WebSockets 的新 Java 项目，并且在类似生产环境的角度上，我们将用 MySQL 服务器替换 HSQLDB。

我们将看到如何动态创建私有队列以及如何让经过身份验证的客户端从这些私有队列中发布和接收消息。我们将做所有这些，以在我们的应用程序中实现真正的应用程序功能。

为了实现 WebSocket 身份验证和消息认证，我们将使 API 有状态。有状态意味着 API 将使用 HTTP 会话在用户请求之间保持用户经过身份验证。借助 Spring Session 的支持和高度可集群化的 Redis 服务器的使用，会话将在多个 Web 应用程序之间共享。

# 使用 STOMP 通过 SockJS 流式传输社交事件

在这个示例中，我们使用 STOMP 通过 SockJS 广播用户活动（事件）。SockJS 提供了 WebSocket 的自定义实现。

## 准备工作

有一些配置工作需要事先完成，特别是在 Apache HTTP 代理上。之后，我们将看到如何在客户端使用 SockJS 和 AngularJS 初始化 WebSocket。

我们的 WebSocket 将订阅通过 Spring 从`cloudstreetmarket-api`模块发布的主题（用于广播）。

## 如何做…

1.  在 Eclipse 的**Git Perspective**中，检出`v8.1.x`分支的最新版本。

1.  在`zipcloud-parent`项目上运行`Maven clean`和`Maven install`命令（右键单击项目，选择**Run as…** | **Maven Clean**，然后选择**Run as…** | **Maven Install)**。之后，进行**Maven | Update** **Project**以使 Eclipse 与 Maven 配置同步（右键单击项目，然后单击**Maven** | **Update Project…**）。

1.  类似地，在`cloudstreetmarket-parent`上运行**Maven clean**和**Maven install**命令，然后运行**Maven** | **Update Project…**（以更新所有`cloudstreetmarket-parent`模块）。

### Apache HTTP 代理配置

1.  在 Apache `httpd.conf`文件中，更改`VirtualHost`定义为：

```java
<VirtualHost cloudstreetmarket.com:80>
  ProxyPass        /portal http://localhost:8080/portal
  ProxyPassReverse /portal http://localhost:8080/portal
  ProxyPass        /api  	http://localhost:8080/api
  ProxyPassReverse /api  	http://localhost:8080/api
  RewriteEngine on
  RewriteCond %{HTTP:UPGRADE} ^WebSocket$ [NC]
  RewriteCond %{HTTP:CONNECTION} ^Upgrade$ [NC]
  RewriteRule .* ws://localhost:8080%{REQUEST_URI} [P]
  RedirectMatch ^/$ /portal/index
</VirtualHost>
```

1.  在`httpd.conf`中，取消注释以下行：

```java
LoadModule proxy_wstunnel_module modules/mod_proxy_wstunnel.so
```

### 前端

1.  在`cloudstreetmarket-webapp`模块的`index.jsp`文件中，导入了两个额外的 JavaScript 文件：

```java
<script src="img/sockjs-1.0.2.min.js"></script>
<script src="img/stomp-2.3.3.js"></script> 
```

### 注意

这两个文件已经被本地复制，但最初，两者都是在线找到的：

[`cdnjs.cloudflare.com/ajax/libs/sockjs-client/1.0.2/sockjs.min.js`](https://cdnjs.cloudflare.com/ajax/libs/sockjs-client/1.0.2/sockjs.min.js)

[`cdnjs.cloudflare.com/ajax/libs/stomp.js/2.3.3/stomp.js`](https://cdnjs.cloudflare.com/ajax/libs/stomp.js/2.3.3/stomp.js)

1.  对于这个示例，客户端方面的所有更改都与文件`src/main/webapp/js/home/home_community_activity.js`有关（它驱动着登陆页面上**用户活动**的反馈）。这个文件与模板`/src/main/webapp/html/home.html`相关联。

1.  在`homeCommunityActivityController`的`init()`函数中，添加了以下部分：

```java
cloudStreetMarketApp.controller('homeCommunityActivityController', function ($scope, $rootScope, httpAuth, modalService, communityFactory, genericAPIFactory, $filter){
  var $this = this,
  socket = new SockJS('/api/users/feed/add'),
  stompClient = Stomp.over(socket);
  pageNumber = 0;
  $scope.communityActivities = {};
  $scope.pageSize=10;
  $scope.init = function () {
    $scope.loadMore();
    socket.onclose = function() {
      stompClient.disconnect();
    };
    stompClient.connect({}, function(frame) {
    stompClient.subscribe('/topic/actions', 	function(message){
     var newActivity = $this.prepareActivity( JSON.parse(message.body)
       );
        $this.addAsyncActivityToFeed(newActivity);
        $scope.$apply();
    });
    });
  ...
  }
...
```

1.  `loadMore()`函数仍然被调用以在滚动到底部时拉取新的活动。但是现在，因为新的活动可以异步插入，`communityActivities`变量不再是数组，而是一个用作映射的对象，其中活动 ID 作为键。这样做可以让我们将同步结果与异步结果合并：

```java
  $scope.loadMore = function () {
    communityFactory.getUsersActivity(pageNumber, $scope.pageSize).then(function(response) {
      var usersData = response.data,
      status = response.status,
      headers  = response.headers,
      config = response.config;
      $this.handleHeaders(headers);
      if(usersData.content){
        if(usersData.content.length > 0){
          pageNumber++;
        }
        $this.addActivitiesToFeed(usersData.content);
      }
    });
  };
```

1.  与以前一样（自第四章，“为无状态架构构建 REST API”），我们循环遍历社区活动以构建活动源。现在，每个活动都带有一定数量的**喜欢**和**评论**。目前，如果用户已经通过身份验证，他就有能力看到**喜欢**的数量：![前端](img/image00897.jpeg)

1.  与点赞图像绑定的 Angular 化 HTML 如下：

```java
    <span ng-if="userAuthenticated() && value.amountOfLikes == 0">
    <img ng-src="img/{{image}}" class="like-img" 
      ng-init="image='img/icon-finder/1441189591_1_like.png'"
      ng-mouseover="image='img/icon-finder/1441188631_4_like.png'"
      ng-mouseleave="image='img/icon-finder/1441189591_1_like.png'"
      ng-click="like(value.id)"/>
  </span>
```

1.  在控制器中，`like()`作用域函数支持此 DOM 元素来创建一个新的`like`活动，该活动针对原始活动：

```java
  $scope.like = function (targetActionId){
    var likeAction = {
      id: null,
      type: 'LIKE',
      date: null,
      targetActionId: targetActionId,
      userId: httpAuth.getLoggedInUser()
    };
    genericAPIFactory.post("/api/actions/likes", likeAction);
  }
```

1.  相反的逻辑也可以找到**不喜欢**一个活动。

### 后端

1.  已添加以下 Maven 依赖项到`cloudstreetmarket-api`：

```java
    <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-websocket</artifactId>
      <version>${spring.version}</version>
   </dependency>
   <dependency>
      <groupId>org.springframework</groupId>
      <artifactId>spring-messaging</artifactId>
      <version>${spring.version}</version>
   </dependency>
```

1.  在`web.xml`文件（来自`cloudstreetmarket-api`），必须将以下属性添加到我们的 servlet 及其每个过滤器中：

```java
<async-supported>true</async-supported>
```

1.  已创建以下专用配置 bean：

```java
@Configuration
@ComponentScan("edu.zipcloud.cloudstreetmarket.api")
@EnableWebSocketMessageBroker
public class WebSocketConfig extends AbstractWebSocketMessageBrokerConfigurer {

   @Override
   public void registerStompEndpoints(final StompEndpointRegistry registry) {
         registry.addEndpoint("/users/feed/add")
            .withSockJS();
    }
   @Override
   public void configureMessageBroker(final MessageBrokerRegistry registry) {
      registry.setApplicationDestinationPrefixes("/app");
       registry.enableSimpleBroker("/topic");
    }
}
```

已添加新的控制器`ActivityFeedWSController`如下：

```java
@RestController
public class ActivityFeedWSController extends CloudstreetApiWCI{
    @MessageMapping("/users/feed/add")
    @SendTo("/topic/actions")
    public UserActivityDTO handle(UserActivityDTO message) throws Exception{
        return message;
    }
    @RequestMapping(value="/users/feed/info", method=GET)
    public String infoWS(){
        return "v0";
    }
}
```

1.  作为 Spring 配置，我们已将以下 bean 添加到`dispatcher-servlet.xml`中：

```java
<bean
  class="org.sfw.web.socket.server.support.OriginHandshakeInterceptor">
    <property name="allowedOrigins">
      <list>
      <value>http://cloudstreetmarket.com</value>
      </list>
    property>
</bean>
```

在`security-config.xml`中，已将以下配置添加到 http Spring Security 命名空间：

```java
    <security:http create-session="stateless" 
        entry-point-ref="authenticationEntryPoint" authentication-manager-ref="authenticationManager">
    ...
    <security:headers>
      <security:frame-options policy="SAMEORIGIN"/>
    </security:headers>
    ...
    </security:http>
```

现在让我们看看事件是如何生成的。

1.  创建新的财务交易时，会向主题`/topic/actions`发送消息。这是在`TransactionController`中完成的：

```java
@RestController
@ExposesResourceFor(Transaction.class)
@RequestMapping(value=ACTIONS_PATH + TRANSACTIONS_PATH, produces={"application/xml", "application/json"})
public class TransactionController extends CloudstreetApiWCI<Transaction> {
  @Autowired
  private SimpMessagingTemplate messagingTemplate;
  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
  public TransactionResource post(@Valid @RequestBody Transaction transaction, HttpServletResponse response, BindingResult result) {
    ...
   messagingTemplate.convertAndSend("/topic/actions", new UserActivityDTO(transaction));
    ...
  }
}
```

同样，当创建一个`like`活动时，也会向`/topic/actions`主题发送消息，这是在`LikeActionController`中完成的：

```java
 @RequestMapping(method=POST)
@ResponseStatus(HttpStatus.CREATED)
public LikeActionResource post(@RequestBody LikeAction likeAction, HttpServletResponse response) {
   ...
    likeAction = likeActionService.create(likeAction);
   messagingTemplate.convertAndSend("/topic/actions", new UserActivityDTO(likeAction));
   ...
}
```

1.  现在启动 Tomcat 服务器。使用 Yahoo! Oauth2 和您的个人 Yahoo!帐户登录应用程序（如果您还没有，请创建一个）。为`Cloudstreet Market`应用程序注册一个新用户。

1.  在您的网络浏览器中，使用已登录的用户在应用程序中打开两个不同的选项卡。将其中一个选项卡保留在登陆页面上。

1.  使用另一个选项卡，导航到**价格和市场** | **所有价格搜索**菜单。搜索一个股票代码，比如 Facebook，并购买三股。

1.  等待接收信息消息：![后端](img/image00898.jpeg)

然后检查浏览器的第一个选项卡（您没有使用的选项卡）。

![后端](img/image00899.jpeg)

您会注意到活动源在顶部收到了一个新元素！

1.  此外，在控制台中，您应该有以下日志跟踪：![后端](img/image00900.jpeg)

1.  同样，**like**事件会实时刷新：![后端](img/image00901.jpeg)

## 它是如何工作的...

在这里，我们将在介绍 Spring-WebSocket 支持工具之前，看一下关于 WebSocket、STOMP 和 SockJS 的一些一般概念。

### WebSocket 简介

WebSocket 是基于 TCP 的全双工通信协议。全双工通信系统允许两方通过双向通道同时*发言*和*被听到*。电话对话可能是全双工系统的最佳例子。

这项技术特别适用于需要利用新 HTTP 连接引起的开销的应用程序。自 2011 年以来，WebSocket 协议一直是互联网标准（[`tools.ietf.org/html/rfc6455`](https://tools.ietf.org/html/rfc6455)）。

#### WebSocket 生命周期

在建立 WebSocket 连接之前，客户端发起握手 HTTP 请求，服务器做出响应。握手请求还代表了一个协议升级请求（从 HTTP 到 WebSocket），用`Upgrade`头正式化。服务器通过响应中相同的`Upgrade`头（和值）确认了这个协议升级。除了`Upgrade`头之外，为了防范缓存代理攻击，客户端还发送了一个 base-64 编码的随机密钥。对此，服务器在`Sec-WebSocket-Accept`头中发送了这个密钥的哈希。

以下是我们应用程序中发生的握手的示例：

![WebSocket 生命周期](img/image00902.jpeg)

该协议生命周期可以通过以下序列图进行总结：

![WebSocket 生命周期](img/image00903.jpeg)

#### 两个专用的 URI 方案

该协议为`WebSockets ws://`和`wss://`定义了两个 URI 方案（`wss`允许加密连接）。

### STOMP 协议

**STOMP**代表**简单文本定向消息协议**。该协议提供了一种基于帧的可互操作格式，允许 STOMP 客户端与 STOMP 消息代理通信。

这是一个需要并信任现有的双向流式网络协议的消息协议。WebSocket 提供基于帧的数据传输，WebSocket 帧确实可以是 STOMP 格式的帧。

以下是一个 STOMP 帧的示例：

```java
CONNECTED
session:session-4F_y4UhJTEjabe0LfFH2kg
heart-beat:10000,10000
server:RabbitMQ/3.2.4
version:1.1
user-name:marcus
```

帧具有以下结构：

![STOMP 协议](img/image00904.jpeg)

STOMP 协议规范定义了一组客户端命令（`SEND`，`SUBSCRIBE`，`UNSUBSCRIBE`，`BEGIN`，`COMMIT`，`ABORT`，`ACK`，`NACK`，`DISCONNECT`，`CONNECT`和`STOMP`）和服务器命令（`CONNECTED`，`MESSAGE`，`RECEIPT`和`ERROR`）。

只有`SEND`，`MESSAGE`和`ERROR`帧可以有主体。协议规范可以在网上找到：[`stomp.github.io/stomp-specification-1.2.html`](http://stomp.github.io/stomp-specification-1.2.html)。

在客户端，我们使用了 JavaScript 库**STOMP Over WebSocket**，文件名为`stomp.js`。该库将 STOMP 格式的帧映射到 WebSocket 帧。默认情况下，它查找 web 浏览器的`WebSocket`类，以使 STOMP 客户端创建 WebSocket。

该库还可以从自定义的`WebSocket`实现中创建 STOMP 客户端。从 SockJS WebSockets，我们可以这样创建 STOMP 客户端：

```java
    var socket = new SockJS('/app/users/feed/add');
    var stompClient = Stomp.over(socket);
        stompClient.connect({}, function(frame) {
  ...
    });
    socket.onclose = function() {
    stompClient.disconnect();
  };
```

### SockJS

WebSockets 现在几乎被所有浏览器支持。但是，我们无法控制客户使用的版本。在许多情况下，对 7%到 15%的受众隐藏这样的技术根本不是一个选择。

在客户端，SockJS 提供了一个自定义实现，可以看作是浏览器原生`WebSocket`实现的装饰器。通过一个简单而方便的库，SockJS 确保了跨浏览器的兼容性。通过一系列回退传输选项（`xhr-streaming`，`xdr-streaming`，`iframe-eventsource`，`iframe-htmlfile`，`xhr-polling`等），它尽可能地模拟了 WebSockets。

对于服务器实现，为了匹配客户端的回退行为，SockJS 还定义了自己的协议：

[`sockjs.github.io/sockjs-protocol/sockjs-protocol-0.3.3.html`](http://sockjs.github.io/sockjs-protocol/sockjs-protocol-0.3.3.html)

### Spring WebSocket 支持

根据 Java WebSocket API 规范（JSR-356），Spring 4+提供了一个解决方案，该解决方案打包在模块`spring-websocket`和`spring-messaging`中。但是 Spring 提供的不仅仅是 JSR-356 的实现。例如，基于以下事实：

+   没有使用消息协议的 WebSocket 太低级，无法直接在应用程序中使用，需要自定义处理框架：Spring 团队选择提供和支持消息协议实现（STOMP）。

+   WebSockets 目前并不受所有浏览器支持：Spring 还通过其实现的 SockJS 协议提供了 WebSocket 回退支持。

#### 一体化配置

我们已经启用了 WebSocket 引擎，并为 SockJS 和 STOMP 配置了一个配置 bean——`WebSocketConfig`：

```java
@Configuration
@ComponentScan("edu.zipcloud.cloudstreetmarket.api")
@EnableWebSocketMessageBroker
public class WebSocketConfig extends   AbstractWebSocketMessageBrokerConfigurer {

  @Override
  public void registerStompEndpoints(final StompEndpointRegistry registry) {
        registry.addEndpoint("/users/feed/add")
        .withSockJS();
  }

  @Override
  public void configureMessageBroker(final MessageBrokerRegistry registry) {
        registry.setApplicationDestinationPrefixes("/app");
        registry.enableSimpleBroker("/topic");
  }
}
```

WebSocket 端点定义为上下文路径`/users/feed/add`。它在客户端端匹配了定义的 SockJS 客户端构造函数参数：

```java
var socket = new SockJS('/api/users/feed/add');
```

从端点（`clientInboundChannel`）到消息处理程序的路由，WebSocket 引擎需要选择将消息路由到何处，我们在这里有两个选项。根据情况和我们想要实现的目标，我们可以将消息定位到应用内消费者（消息处理程序）或直接将消息路由到消息代理，以便将消息分发给订阅的客户端。

这个分割是通过定义两个不同的目的地前缀来配置的。在我们的情况下，我们决定使用`/app`前缀将消息路由到相应的消息处理程序，使用`/topic`前缀来识别准备分发给客户端的消息。

现在让我们看看如何定义消息处理程序以及如何使用它们。

#### 通过@MessageMapping 定义消息处理程序

`@MessageMapping`注解用于 Spring MVC 控制器方法，标记它们可用作消息处理程序方法。

从`clientInboundChannel`中的消息到路由到消息处理程序，WebSocket 引擎根据它们配置的值缩小到正确的`@MessageMapping`方法。

与 Spring MVC 一样，这个值可以用 Ant 样式（例如`/targets/**`）来定义。然而，与`@RequestParam`和`@PathVariable`注解一样，模板变量也可以通过在方法参数上使用`@DestinationVariable`注解来传递（目标模板定义如下：`/targets/{target}`）。

### 发送消息以进行分发

必须配置消息代理。在这个示例中，我们使用了一个`simple`消息代理（`simpMessageBroker`），我们已经从`MessageBrokerRegistry`中启用了它。这种内存中的代理适用于在没有外部代理（RabbitMQ、ActiveMQ 等）的情况下堆叠 STOMP 消息。当有可用性将消息分发给 WebSocket 客户端时，这些消息被发送到`clientOutboundChannel`。

我们已经看到，当消息目的地以`/topic`为前缀时（就像我们的情况一样），消息会直接发送到消息代理。但是当我们在消息处理程序方法或后端代码的其他地方发送调度消息时怎么办？我们可以使用下一节中描述的`SimpMessagingTemplate`来实现这一点。

#### SimpMessagingTemplate

我们在 CSMReceiver 类中自动装配了一个`SimpMessagingTemplate`，稍后我们将使用它将 AMQP 消息的有效载荷转发给 WebSocket 客户端。

`SimpMessagingTemplate`与 Spring 的`JmsTemplate`具有相同的目的（如果您熟悉它），但它适用于简单的消息协议（如 STOMP）。

一个方便且继承自著名的方法是`convertAndSend`方法，它尝试识别并使用`MessageConverter`来序列化一个对象，并将其放入一个新消息中，然后将此消息发送到指定的目的地：

```java
simpMessagingTemplate.convertAndSend(String destination, Object message);
```

这个想法是为消息代理目标（在我们的情况下是带有`/topic`前缀）定位。

#### @SendTo 注解

这个注解使我们不必显式使用`SimpMessagingTemplate`。目的地被指定为注解值。这个方法还将处理从有效载荷到消息的转换：

```java
@RestController
public class ActivityFeedWSController extends CloudstreetApiWCI{

  @MessageMapping("/users/feed/add")
  @SendTo("/topic/actions")
  public UserActivityDTO handle(UserActivityDTO payload) throws Exception{
        return payload;
 }
}
```

## 还有更多...

在本节中，我们提供了与 SockJS 回退选项相关的额外信息来源。

正如之前介绍的，Spring 提供了 SockJS 协议实现。在 Spring 中使用`withSockJS()`功能方法配置 SockJS 很容易，在`StompEndPoint`注册期间。这个小小的配置片段告诉 Spring 在我们的端点上激活 SockJS 回退选项。

SockJS 客户端对服务器的第一个调用是一个 HTTP 请求，到端点路径连接`/info`以评估服务器配置。如果此 HTTP 请求不成功，则不会尝试任何其他传输（甚至不会尝试 WebSocket）。

如果您想了解 SockJS 客户端如何查询服务器以获取合适的回退选项，可以在 Spring 参考指南中阅读更多内容：

[`docs.spring.io/spring/docs/current/spring-framework-reference/html/websocket.html#websocket-server-handshake`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/websocket.html#websocket-server-handshake)

## 另请参阅

+   **JSR-356**：您可以在线找到规范文档，了解有关 Java WebSocket 规范的更多信息，spring-websocket 正在遵循该规范：[`jcp.org/en/jsr/detail?id=356`](https://jcp.org/en/jsr/detail?id=356)

# 使用 RabbitMQ 作为多协议消息代理

安装和使用外部 RabbitMQ 作为功能齐全的消息代理可以开启新的技术机会，并设计类似生产环境的基础设施。

## 准备工作

在本教程中，我们将安装 RabbitMQ 作为独立服务器，并配置它以支持 STOMP 消息。

我们还将更新我们的 WebSocket Spring 配置，以依赖于这个功能齐全的消息代理，而不是内部简单的消息代理。

## 如何做…

1.  在 Eclipse 的**Git Perspective**中，这次检出`v8.2.x`分支。

1.  已添加了两个新的 Java 项目，必须导入。从 Eclipse 中，选择**File** | **Import…**菜单。

1.  **导入**向导打开，以便您可以在层次结构中选择项目类型。打开**Maven**类别，选择**Existing Maven Projects**选项，然后单击**Next**。

1.  **导入 Maven 项目**向导打开。选择（或输入）工作区位置（应为`<home-directory>/workspace`）作为根目录。

1.  如下截图所示，选择以下两个**pom.xml**文件：**cloudstreetmarket-shared/pom.xml**和**cloudstreetmarket-websocket/pom.xml**。![如何做…](img/image00905.jpeg)

1.  两个项目`cloudstreetmarket-shared`和`cloudstreetmarket-websocket`必须显示在项目层次结构中。

1.  在 Web 模块上定位运行时环境，按照以下说明操作：在 Eclipse 中，右键单击**cloudmarket-websocket**项目，选择**Properties**菜单，在导航面板中选择**Targeted Runtimes**。在中央窗口中，勾选服务器**Apache Tomcat v8.0**的复选框。

1.  在`/app`目录中，`cloudstreetmarket.properties`文件已更新。反映在位于`<home-directory>/app/cloudstreetmarket.properties`的文件中的更改。

1.  在`zipcloud-parent`上运行`Maven clean`和`Maven install`命令，然后在`cloudstreetmarket-parent`上运行，然后在所有模块上运行**Maven** | **Update Project**。

1.  以我们想要的方式运行 RabbitMQ，需要我们下载并安装该产品作为独立产品。

1.  根据本地机器的配置，不同的操作方式适用。您将在 RabbitMQ 网站上找到适当的链接和安装指南：[`www.rabbitmq.com/download.html`](https://www.rabbitmq.com/download.html)

### 提示

如果您使用 Windows 操作系统，请注意，下载和安装 Erlang（[`www.erlang.org/download.html`](http://www.erlang.org/download.html)）是先决条件。

1.  一旦安装了 RabbitMQ 并且其服务正在运行，打开您喜欢的 Web 浏览器，以检查 RabbitMQ 是否作为 Web 控制台运行在 URL：`http://localhost:15672`（就像下面的截图中一样）。![如何做…](img/image00906.jpeg)

### 注意

我们将在稍后回来设置 RabbitMQ 配置。现在，只需记住这个控制台可以用于监视消息和管理连接、队列、主题和交换。

1.  需要激活 RabbitMQ STOMP 插件。这是从`rabbitmq_server-x.x.x\sbin`目录中执行以下命令行完成的：

```java
rabbitmq-plugins enable rabbitmq_stomp
```

1.  已添加以下 Maven 依赖项：

```java
<dependency>
  <groupId>org.springframework.amqp</groupId>
  <artifactId>spring-rabbit</artifactId>
  <version>1.4.0.RELEASE</version>
</dependency>
<dependency>
  <groupId>io.projectreactor</groupId>
  <artifactId>reactor-core</artifactId>
  <version>2.0.5.RELEASE</version>
</dependency>
<dependency>
  <groupId>io.projectreactor</groupId>
  <artifactId>reactor-net</artifactId>
  <version>2.0.5.RELEASE</version>
</dependency>
<dependency>
  <groupId>io.projectreactor.spring</groupId>
  <artifactId>reactor-spring-context</artifactId>
  <version>2.0.5.RELEASE</version>
</dependency>
<dependency>
  <groupId>io.netty</groupId>
  <artifactId>netty-all</artifactId>
  <version>4.0.31.Final</version>
</dependency>
```

1.  在`cloudstreetmarket-api`模块的`dispatcher-servlet.xml`中，已添加以下 bean，使用`rabbit`命名空间：

```java
<beans 

   ...

   xsi:schemaLocation="http://www.sfw.org/schema/beans
   ...
   http://www.sfw.org/schema/rabbit
  http://www.sfw.org/schema/rabbit/spring-rabbit-1.5.xsd">
    ...
  <rabbit:connection-factory id="connectionFactory" host="localhost" username="guest" password="guest" />
  <rabbit:admin connection-factory="connectionFactory" />
  <rabbit:template id="messagingTemplate" connection-factory="connectionFactory"/>
</beans>
```

1.  在`csmcore-config.xml`文件（在`cloudstreetmarket-core`中），以下 bean 已添加了`task`命名空间：

```java
<beans 

    ...
    xmlns:task=http://www.sfw.org/schema/task
    http://www.sfw.org/schema/task/spring-task-4.0.xsd">
    ...
    <task:annotation-driven scheduler="wsScheduler"/>
    <task:scheduler id="wsScheduler" pool-size="1000"/>
    <task:executor id="taskExecutor"/>
</beans>
```

1.  在 Spring 配置方面，我们的`AnnotationConfig` bean（`cloudstreetmarket-api`的主配置 bean）已添加了两个注释：

```java
@EnableRabbit
@EnableAsync
public class AnnotationConfig {
	...
}
```

1.  最后，`WebSocketConfig` bean 也已更新；特别是经纪人注册。我们现在使用的是`StompBrokerRelay`而不是简单的经纪人：

```java
@Configuration
@ComponentScan("edu.zipcloud.cloudstreetmarket.api")
@EnableWebSocketMessageBroker
@EnableScheduling
@EnableAsync
public class WebSocketConfig extends AbstractWebSocketMessageBrokerConfigurer {
...
    @Override
    public void configureMessageBroker(final MessageBrokerRegistry registry) {
     registry.setApplicationDestinationPrefixes( WEBAPP_PREFIX_PATH);
     registry.enableStompBrokerRelay(TOPIC_ROOT_PATH);
    }
}
```

### 提示

就是这样！一切都准备好使用 RabbitMQ 作为我们系统的外部代理。但是，请注意，如果您现在尝试启动服务器，代码将期望 MySQL 已安装以及 Redis 服务器。这两个第三方系统将在接下来的两个配方中详细介绍。

## 它是如何工作的…

### 使用全功能消息代理

与简单消息代理相比，使用 RabbitMQ 等全功能消息代理提供了有趣的好处，我们现在将讨论这些好处。

#### 集群性-RabbitMQ

RabbitMQ 代理由一个或多个 Erlang 节点组成。这些节点分别代表 RabbitMQ 的一个实例，并可以独立启动。节点可以使用命令行工具`rabbitmqctl`相互链接。例如，`rabbitmqctl join_cluster rabbit@rabbit.cloudstreetmarket.com`实际上会将一个节点连接到现有的集群网络。RabbitMQ 节点使用 cookie 相互通信。为了连接到同一个集群，两个节点必须具有相同的 cookie。

#### 更多的 STOMP 消息类型

与简单消息代理相比，使用全功能消息代理（而不是简单消息代理）支持额外的 STOMP 帧命令。例如，简单消息代理不支持`ACK`和`RECEIPT`。

### StompMessageBrokerRelay

在上一个配方中，我们讨论了消息在 Spring WebSocket 引擎中经过的流程。如下图所示，当切换到外部消息代理中继时，这个流程不受影响。

![StompMessageBrokerRelay](img/image00907.jpeg)

只有 RabbitMQ 外部消息代理显示为额外的部分。`BrokerMessageHandler`（`StompBrokerRelayMessageHandler`）只充当一个代理，将目标定位到幕后的 RabbitMQ 节点。`StompBrokerRelay`和其消息代理之间只维护一个 TCP 连接。`StompBrokerRelay`通过发送心跳消息来维护连接。

## 另请参阅

+   **RabbitMQ 指南和文档**：这个配方只是一个概述，但 RabbitMQ 文档做得很好，非常完整。这是一个很好的信息来源，你可以在这里找到：

[`www.rabbitmq.com/documentation.html`](http://www.rabbitmq.com/documentation.html)

[`www.rabbitmq.com/stomp.html`](http://www.rabbitmq.com/stomp.html)

# 使用 RabbitMQ 和 AMQP 堆叠和消费任务

这个配方将演示如何实现**面向消息的中间件**（**MoM**）。这是一种基于组件之间异步通信的可伸缩性技术。

## 准备工作

我们已经介绍了新的`cloudstreetmarket-shared`和`cloudstreetmarket-websocket` Java 项目。现在，WebSockets 已从`cloudstreetmarket-api`中分离出来，但`cloudstreetmarket-websocket`和`cloudstreetmarket-api`仍将使用消息进行通信。

为了将次要任务（如事件生成）与请求线程解耦，您需要学习如何使用 RabbitMQ 配置和使用 AMQP 消息模板和监听器。

## 如何做…

1.  访问 RabbitMQ Web 控制台`http://localhost:15672`。

### 注意

如果由于某种原因无法访问网络控制台，请返回到先前的教程，在那里可以找到下载和安装指南。

1.  在网络控制台的**队列**选项卡中，创建一个名为`AMQP_USER_ACTIVITY`的新队列。使用**持久**和**自动删除: "否"**参数创建它：![如何做…](img/image00908.jpeg)

### 发送方

当 API 被请求执行操作，如**创建交易**或**创建喜欢活动**时，我们会产生事件。

### 提示

通过非常少的调整，我们现在使用`RabbitTemplate`而不是以前的`SimpMessagingTemplate`，并且将目标定位到一个中间的 AMQP 队列，而不是最终的 STOMP 客户端。

在`TransactionController`中，POST 处理程序已更新如下：

```java
import org.springframework.amqp.rabbit.core.RabbitTemplate;
@RestController
public class TransactionController extends CloudstreetApiWCI<Transaction> {
  @Autowired
  private RabbitTemplate messagingTemplate;

  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
  public TransactionResource post(@Valid @RequestBody Transaction transaction, HttpServletResponse response, BindingResult result) {
   ...
   messagingTemplate.convertAndSend("AMQP_USER_ACTIVITY", new UserActivityDTO(transaction));
   ...
   return resource;
  }
}
```

在`LikeActionController`中，POST 处理程序已更新如下：

```java
import org.springframework.amqp.rabbit.core.RabbitTemplate;

@RestController
public class LikeActionController extends CloudstreetApiWCI<LikeAction> {
  @Autowired
  private RabbitTemplate messagingTemplate;
  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
  public LikeActionResource post(@RequestBody LikeAction likeAction, HttpServletResponse response) {
  ...
   messagingTemplate.convertAndSend("AMQP_USER_ACTIVITY", new UserActivityDTO(likeAction));
   ...
   return resource;
  }
}
```

### 消费方

如前所述，`cloudstreetmarket-websocket`模块现在监听`AMQP_USER_ACTIVITY`队列。

1.  必要的配置设置在`displatcher-servlet.xml`（`cloudstreetmarket-websocket`）中。在那里，我们创建了一个`rabbitConnectionFactory`和一个`rabbitListenerContainerFactory` bean：

```java
<rabbit:connection-factory id="rabbitConnectionFactory" username="guest" host="localhost" password="guest"/>
<bean id="rabbitListenerContainerFactory" class="org.sfw.amqp.rabbit.config.SimpleRabbitListenerContainerFactory">
    <property name="connectionFactory" ref="rabbitConnectionFactory"/>
    <property name="concurrentConsumers" value="3"/>
    <property name="maxConcurrentConsumers" value="10"/>
    <property name="prefetchCount" value="12"/>
</bean>
```

1.  最后，监听器 bean 的创建如下，使用`CSMReceiver`类：

```java
@Component
public class CSMReceiver {
  @Autowired
  private SimpMessagingTemplate simpMessagingTemplate;

  @RabbitListener(queues = "AMQP_USER_ACTIVITY_QUEUE")
  public void handleMessage(UserActivityDTO payload) {
  simpMessagingTemplate.convertAndSend("/topic/actions", payload);
  }
} 
```

### 提示

您可以在这里识别使用的`SimpMessagingTemplate`，将传入的消息负载转发给最终的 STOMP 客户端。

1.  在`cloudstreetmarket-websocket`中创建了一个新的`WebSocketConfig` bean。这个 bean 与我们在`cloudstreetmarket-api`中的 bean 非常相似。

### 客户端

我们在客户端（`cloudstreetmarket-webapp`）上没有改变太多东西，因为我们目前仍专注于着陆页（`home_community_activity.js`）。

主要区别在于 STOMP 端点现在将目标定位到`/ws`上下文路径。WebSockets 在 5 秒延迟后从`init()`函数中启动。此外，`SockJS`套接字和 STOMP 客户端现在集中在全局变量（使用`Window`对象）中，以简化用户导航期间的 WebSockets 生命周期：

```java
var timer = $timeout( function(){ 
  window.socket = new SockJS('/ws/channels/users/broadcast');
  window.stompClient = Stomp.over(window.socket);
    window.socket.onclose = function() {
        window.stompClient.disconnect();
      };
  window.stompClient.connect({}, function(frame) {
    window.stompClient.subscribe('/topic/actions', function(message){
        var newActivity = $this.prepareActivity(JSON.parse(message.body));
        $this.addAsyncActivityToFeed(newActivity);
        $scope.$apply();
      });
    });
     $scope.$on(
      "$destroy",
        function( event ) {
          $timeout.cancel( timer );
          window.stompClient.disconnect();
          }
      );
                }, 5000);
```

## 它是如何工作的...

这种类型的基础设施以一种松散但可靠的方式将应用程序组件耦合在一起。

### 消息架构概述

在这个教程中，我们给我们的应用程序添加了一个 MoM。主要想法是尽可能地将进程与客户端请求生命周期解耦。

为了使我们的 REST API 专注于资源处理，一些业务逻辑显然是次要的，比如：

+   通知社区有新用户注册了一个帐户

+   通知社区用户执行了特定交易

+   通知社区用户已喜欢另一个用户的动作

我们决定创建一个专门处理 WebSockets 的新 webapp。我们的 API 现在通过向`ws` web app 发送消息与之通信。

消息负载是社区`Action`对象（来自`Action.java`超类）。从`cloudstreetmarket-api` web app 到`cloudstreetmarket-websocket` webapp，这些动作对象被序列化并包装在 AMQP 消息中。一旦发送，它们被堆叠在一个单一的 RabbitMQ 队列（`AMQP_USER_ACTIVITY`）中。

发送方和接收方部分都是 AMQP 实现（`RabbitTemplate`和`RabbitListener`）。这种逻辑现在将以`websocket` web app 可以承受的速度进行处理，而不会对用户体验产生影响。当在`cloudstreetmarket-websocket`端接收到时，消息负载将作为 STOMP 消息即时发送到 WebSocket 客户端。

在这里直接性能的好处是值得商榷的（在这个例子中）。毕竟，我们大部分时间都是通过额外的消息传递层推迟了次要事件的发布。然而，在设计清晰度和业务组件分离方面的好处是无价的。

#### 可扩展的模型

我们已经谈论了保持 web 应用程序无状态的好处。这是我们迄今为止尝试做的事情，我们为此感到自豪！

没有 HTTP 会话，我们很容易就能对`api`网络应用程序或`portal`网络应用程序的流量激增做出反应。在 Apache HTTP 代理上，我们可以很容易地使用`mod_proxy_balancer`设置负载均衡器来处理 HTTP 连接。

您可以在 Apache HTTP 文档中了解更多信息：[`httpd.apache.org/docs/2.2/mod/mod_proxy_balancer.html`](http://httpd.apache.org/docs/2.2/mod/mod_proxy_balancer.html)

![可扩展模型](img/image00909.jpeg)

对于 WebSocket 网络应用程序，它在无状态时基本上是一样的。在 Apache HTTP 配置中，配置的`mod_proxy_wstunnel`应该处理 WebSocket 的负载平衡，并提供应用程序故障转移。

### AMQP 还是 JMS？

**高级消息队列协议**（AMQP）定义了一种**线级**协议，并保证了发送方和消费方之间的互操作性。符合该协议的任何一方都可以创建和解释消息，因此可以与任何其他符合该协议的组件进行互操作，而不受底层技术的影响。

相比之下，JMS 是 Java 平台**企业版（EE）**的一部分。随着 JSR-914 的到来，JMS 是一个定义 API 应该如何创建、发送、接收和读取消息的标准。JMS 不提供线级指导，也不保证各方之间的互操作性。

AMQP 控制消息的格式和这些消息经过的流程，而 JMS 控制边界（操作员）的技术实现。当我们在一个潜在复杂的环境中寻求通信一致性时，AMQP 似乎是 MoM 协议的一个不错的选择。

## 还有更多...

本节提供了扩展您对 AMQP 和事件发布方法的知识的外部资源。

### Pivotal 公司对 AMQP 的很好介绍

如果您想更好地了解 AMQP 及其与 JMS 的区别，请查看[spring.io](http://spring.io)网站上的以下文章：

[`spring.io/understanding/AMQP`](https://spring.io/understanding/AMQP)

### 发布应用程序事件的更好方法

现在，我们还没有实现一个适当的模式来发布事件。下面链接的文章来自[spring.io](http://spring.io)博客。它介绍了在 Spring 4.2+中发布事件的最佳实践：

[`spring.io/blog/2015/02/11/better-application-events-in-spring-framework-4-2`](https://spring.io/blog/2015/02/11/better-application-events-in-spring-framework-4-2)

## 另请参阅

+   **负载均衡 WebSockets**：在以下文章中了解更多关于这个主题的内容，作者是 Arun Gupta（当时在红帽公司）：

[`blog.arungupta.me/load-balance-websockets-apache-httpd-techtip48`](http://blog.arungupta.me/load-balance-websockets-apache-httpd-techtip48)

# 使用 Spring Session 和 Redis 保护消息

总之，到目前为止，我们已经看到了如何向 StockJS 客户端广播 STOMP 消息，如何在外部多协议代理中堆叠消息，以及如何与这个代理（RabbitMQ）在 Spring 生态系统中进行交互。

## 准备工作

这个示例是关于实现专用队列，而不再是主题（广播），以便用户可以接收与他们正在查看的特定内容相关的实时更新。这也演示了 SockJS 客户端如何将数据发送到他们的私有队列。

对于私有队列，我们必须保护消息和队列访问。我们已经打破了我们对 API 的无状态原则，以利用 Spring Session。这扩展了`cloudstreetmarket-api`执行的身份验证，并在`cloudstreetmarket-websocket`中重用了 Spring Security 上下文。

## 如何做到这一点...

### Apache HTTP 代理配置

因为`v8.2.x`分支引入了新的`cloudstreetmarket-websocket`网络应用程序，Apache HTTP 代理配置需要更新以完全支持我们的 WebSocket 实现。我们的`VirtualHost`定义现在是：

```java
<VirtualHost cloudstreetmarket.com:80>
  ProxyPass        /portal http://localhost:8080/portal
  ProxyPassReverse /portal http://localhost:8080/portal
  ProxyPass        /api  	http://localhost:8080/api
  ProxyPassReverse /api  	http://localhost:8080/api
  ProxyPass        /ws  	http://localhost:8080/ws
  ProxyPassReverse /ws  	http://localhost:8080/ws
  RewriteEngine on
  RewriteCond %{HTTP:UPGRADE} ^WebSocket$ [NC]
  RewriteCond %{HTTP:CONNECTION} ^Upgrade$ [NC]
  RewriteRule .* ws://localhost:8080%{REQUEST_URI} [P]
  RedirectMatch ^/$ /portal/index
</VirtualHost>
```

### Redis 服务器安装

1.  如果您使用的是基于 Linux 的机器，请在[`redis.io/download`](http://redis.io/download)下载最新稳定版本（3+）。要下载的存档格式是`tar.gz`。按照页面上的说明进行安装（解包，解压缩，并使用 make 命令构建）。

安装完成后，要快速启动 Redis，请运行：

```java
$ src/redis-server
```

1.  如果您使用的是基于 Windows 的机器，我们建议使用此存储库：[`github.com/ServiceStack/redis-windows`](https://github.com/ServiceStack/redis-windows)。请按照`README.md`页面上的说明进行操作。运行 Microsoft 的 Redis 本机端口允许您在没有任何其他第三方安装的情况下运行 Redis。

要快速启动 Redis 服务器，运行以下命令：

```java
$ redis-server.exe redis.windows.conf
```

1.  当 Redis 运行时，您应该能够看到以下欢迎屏幕：![Redis 服务器安装](img/image00910.jpeg)

1.  在 Eclipse 中更新 Tomcat 配置以使用本地 Tomcat 安装。要这样做，请双击当前服务器（**服务器**选项卡）：![Redis 服务器安装](img/image00911.jpeg)

1.  这将打开以下配置面板：![Redis 服务器安装](img/image00912.jpeg)

确保**使用 Tomcat 安装**单选按钮已被选中。

### 提示

如果面板变灰，右键单击当前服务器，然后单击**添加**，**删除**...从服务器中删除三个部署的 web 应用程序，然后再次右键单击服务器，然后单击**发布**。

1.  现在，下载以下 jar 包：

+   **jedis-2.5.2.jar**：一个小型的 Redis Java 客户端库

+   **commons-pool2-2.2.jar**：Apache 通用对象池库

您可以分别从[`central.maven.org/maven2/redis/clients/jedis/2.5.2/jedis-2.5.2.jar`](http://%20http://central.maven.org/maven2/redis/clients/jedis/2.5.2/jedis-2.5.2.jar)和[`central.maven.org/maven2/org/apache/commons/commons-pool2/2.2/commons-pool2-2.2.jar`](http://central.maven.org/maven2/org/apache/commons/commons-pool2/2.2/commons-pool2-2.2.jar)下载它们。

你也可以在`chapter_8/libs`目录中找到这些 jar 包。

1.  在`chapter_8/libs`目录中，您还将找到**tomcat-redis-session-manager-2.0-tomcat-8.jar**存档。将三个 jar 包`tomcat-redis-session-manager-2.0-tomcat-8.jar`，`commons-pool2-2.2.jar`和`jedis-2.5.2.jar`复制到 Eclipse 引用的本地 Tomcat 安装的`lib`目录中。如果我们在第一章中的说明已经被遵循，那么这应该是`C:\tomcat8\lib`或`/home/usr/{system.username}/tomcat8/lib`。

1.  现在在你的工作空间中，打开**Server**项目的**context.xml**文件。![Redis 服务器安装](img/image00913.jpeg)

1.  添加以下`Valve`配置：

```java
<Valve asyncSupported="true" className="edu.zipcloud.catalina.session.RedisSessionHandlerValve"/>
<Manager className="edu.zipcloud.catalina.session.RedisSessionManager"
      host="localhost" 
      port="6379" 
      database="0" 
      maxInactiveInterval="60"/>
```

### MySQL 服务器安装

在创建新的`cloudstreetmarket-websocket`web 应用程序时，我们还将数据库引擎从 HSQLDB 更改为了 MySQL。这样做使我们能够在`api`和`websocket`模块之间共享数据库。

1.  本节的第一步是从[`dev.mysql.com/downloads/mysql`](http://dev.mysql.com/downloads/mysql)下载并安装 MySQL 社区服务器。下载适合您系统的通用版本。如果您使用的是 MS Windows，我们建议安装安装程序。

1.  您可以按照 MySQL 团队在[`dev.mysql.com/doc/refman/5.7/en/installing.html`](http://dev.mysql.com/doc/refman/5.7/en/installing.html)提供的安装说明进行操作。

我们现在要为模式用户和数据库名称定义一个通用配置。

1.  创建一个以您选择的密码为密码的根用户。

1.  创建一个技术用户（具有管理员角色），应用程序将使用该用户。此用户需要被称为`csm_tech`，并且需要有密码`csmDB1$55`：![MySQL 服务器安装](img/image00914.jpeg)

1.  启动 MySQL 客户端（命令行工具），如下所示：

+   在 MS Windows 上，启动 MySQL 服务器安装目录中的`mysql.exe`程序：`\MySQL Server 5.6\bin\mysql.exe`

+   在 Linux 或 Mac OS 上，从终端调用`mysql`命令

在两个平台上，第一步是提供之前选择的 root 密码。

1.  使用 MySQL Workbench 或 MySQL 客户端创建`csm`数据库：

```java

mysql> CREATE DATABASE csm; 

```

1.  选择`csm`数据库作为当前数据库：

```java

mysql> USE csm;

```

1.  从 Eclipse 启动本地 Tomcat 服务器。一旦它启动，您可以再次关闭它；这一步只是为了让 Hibernate 生成模式。

1.  然后我们需要手动插入数据。为此，依次执行以下导入命令：

```java

mysql> csm < <home-directory>\cloudstreetmarket-parent\cloudstreetmarket-core\src\main\resources\META-INF\db\currency_exchange.sql;
mysql> csm < <home-directory>\cloudstreetmarket-parent\cloudstreetmarket-core\src\main\resources\META-INF\db\init.sql;
mysql> csm < <home-directory>\cloudstreetmarket-parent\cloudstreetmarket-core\src\main\resources\META-INF\db\stocks.sql;
mysql> csm < <home-directory>\cloudstreetmarket-parent\cloudstreetmarket-core\src\main\resources\META-INF\db\indices.sql;

```

### 应用级别的更改

1.  在`cloudstreetmarket-api`和`cloudstreetmarket-websocket`中，已向`web.xml`文件添加了以下过滤器。此过滤器必须在 Spring Security 链定义之前放置：

```java
<filter>
  <filter-name>springSessionRepositoryFilter</filter-name>
  <filter-class>
  org.springframework.web.filter.DelegatingFilterProxy
  </filter-class>
  <async-supported>true</async-supported>
</filter>
<filter-mapping>
  <filter-name>springSessionRepositoryFilter</filter-name>
  <url-pattern>/*</url-pattern>
</filter-mapping>
```

1.  还添加了一些 Maven 依赖项到`cloudstreetmarket-api`：

```java
<!-- Spring Session -->
<dependency>
  <groupId>org.springframework.session</groupId>
  <artifactId>spring-session</artifactId>
  <version>1.0.2.RELEASE</version>
</dependency>
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-pool2</artifactId>
  <version>2.2</version>
</dependency>
<dependency>
  <groupId>org.springframework.session</groupId>
  <artifactId>spring-session-data-redis</artifactId>
  <version>1.0.2.RELEASE</version>
</dependency>
<!-- Spring Security -->
<dependency>
  <groupId>org.springframework.security</groupId>
  <artifactId>spring-security-messaging</artifactId>
  <version>4.0.2.RELEASE</version>
</dependency>
  <dependency>
    <groupId>commons-io</groupId>
    <artifactId>commons-io</artifactId>
    <version>2.4</version>
  </dependency>
```

1.  再次在`cloudstreetmarket-api`中，`security-config.xml`已更新以反映 Spring Security 过滤器链中的以下更改：

```java
<security:http create-session="ifRequired" 
  authentication-manager-ref="authenticationManager" entry-point-ref="authenticationEntryPoint">
 <security:custom-filter ref="basicAuthenticationFilter" after="BASIC_AUTH_FILTER" />
   <security:csrf disabled="true"/>
 <security:intercept-url pattern="/oauth2/**" access="permitAll"/>
 <security:intercept-url pattern="/basic.html" access="hasRole('ROLE_BASIC')"/>
   <security:intercept-url pattern="/**" access="permitAll"/>
 <security:session-management session-authentication-strategy-ref="sas"/>
</security:http>
<bean id="sas" class="org.springframework.security.web.authentication.session.SessionFixationProtectionStrategy" />
```

1.  同时，`security-config.xml`文件和`cloudstreetmarket-websocket`中的`security-config.xml`文件现在定义了三个额外的 bean：

```java
<bean class="org.springframework.data.redis.connection.jedis.JedisConnectionFactory" p:port="6379"/>
<bean class="org.springframework.session.data.redis.config.annotation.web.http.RedisHttpSessionConfiguration"/>
<bean class="edu.zipcloud.cloudstreetmarket.core.util.RootPath CookieHttpSessionStrategy"/>
```

1.  在`cloudstreetmarket-webapp`中小心翼翼地不要创建会话。我们希望会话只在`cloudstreetmarket-api`中创建。我们通过向`cloudstreetmarket-webapp`中的`web.xml`文件添加以下配置来实现这一点：

```java
<session-config>
    <session-timeout>1</session-timeout>
    <cookie-config>
        <max-age>0</max-age>
    </cookie-config>
</session-config>
```

1.  关于 Spring Security，`cloudstreetmarket-websocket`具有以下配置：

```java
<bean id="securityContextPersistenceFilter" class="org.springframework.security.web.context.SecurityContextPersistenceFilter"/>
<security:http create-session="never" 
authentication-manager-ref="authenticationManager" entry-point-ref="authenticationEntryPoint">
  <security:custom-filter ref="securityContextPersistenceFilter" before="FORM_LOGIN_FILTER" />
  <security:csrf disabled="true"/>
  <security:intercept-url pattern="/channels/private/**" access="hasRole('OAUTH2')"/>
  <security:headers>
      <security:frame-options policy="SAMEORIGIN" />
  </security:headers>
</security:http>
<security:global-method-security secured-annotations="enabled" pre-post-annotations="enabled" authentication-manager-ref="authenticationManager"/>
```

1.  `cloudstreetmarket-websocket`中的两个配置 bean 完成了 XML 配置：

在`edu.zipcloud.cloudstreetmarket.ws.config`中定义的`WebSocketConfig` bean 如下：

```java
@EnableScheduling
@EnableAsync
@EnableRabbit
@Configuration
@EnableWebSocketMessageBroker
public class WebSocketConfig extends   AbstractSessionWebSocketMessageBrokerConfigurer<Expiring Session> {
  @Override
  protected void configureStompEndpoints(StompEndpointRegistry registry) {
          registry.addEndpoint("/channels/users/broadcast")
          .setAllowedOrigins(protocol.concat(realmName))
          .withSockJS()
          .setClientLibraryUrl( Constants.SOCKJS_CLIENT_LIB);

        registry.addEndpoint("/channels/private")
          .setAllowedOrigins(protocol.concat(realmName))
          .withSockJS()
          .setClientLibraryUrl( Constants.SOCKJS_CLIENT_LIB);
  }

  @Override
  public void configureMessageBroker(final MessageBrokerRegistry registry) {
        registry.enableStompBrokerRelay("/topic", "/queue");
        registry.setApplicationDestinationPrefixes("/app");
  }

  @Override
  public void configureClientInboundChannel(ChannelRegistration registration) {
        registration.taskExecutor() corePoolSize(Runtime.getRuntime().availableProcessors() *4);
  }

  @Override
  //Increase number of threads for slow clients
  public void configureClientOutboundChannel( 
     ChannelRegistration registration) {
        registration.taskExecutor().corePoolSize( Runtime.getRuntime().availableProcessors() *4);
  }
  @Override
  public void configureWebSocketTransport(  
    WebSocketTransportRegistration registration) {
        registration.setSendTimeLimit(15*1000) 
          .setSendBufferSizeLimit(512*1024); 
  }
}
```

在`edu.zipcloud.cloudstreetmarket.ws.config`中定义的`WebSocketSecurityConfig` bean 如下：

```java
@Configuration
public class WebSocketSecurityConfig extends AbstractSecurityWebSocketMessageBrokerConfigurer {
    @Override
    protected void configureInbound( MessageSecurityMetadataSourceRegistry messages) {
    messages.simpMessageDestMatchers("/topic/actions", "/queue/*", "/app/queue/*").permitAll();
    }
    @Override
    protected boolean sameOriginDisabled() {
    return true;
    }
}
```

1.  `ActivityFeedWSController`类已复制到`cloudstreetmarket-websocket`以广播用户活动。它仍然不需要任何特定的角色或身份验证：

```java
@RestController
public class ActivityFeedWSController extends CloudstreetWebSocketWCI{

    @MessageMapping("/channels/users/broadcast")
    @SendTo("/topic/actions")
    public UserActivityDTO handle(UserActivityDTO message) throws Exception {
        return message;
    }

    @RequestMapping(value="/channels/users/broadcast/info", produces={"application/json"})
    @ResponseBody
    public String info(HttpServletRequest request) {
      return "v0";
    }
}
```

1.  一个额外的控制器将消息（即最新的股票价值）发送到私有队列：

```java
@RestController
public class StockProductWSController extends CloudstreetWebSocketWCI<StockProduct>{

  @Autowired
  private StockProductServiceOffline stockProductService;

  @MessageMapping("/queue/CSM_QUEUE_{queueId}")
  @SendTo("/queue/CSM_QUEUE_{queueId}")
  @PreAuthorize("hasRole('OAUTH2')")
  public List<StockProduct> sendContent(@Payload List<String> tickers, @DestinationVariable("queueId") String queueId) throws Exception {
      String username = extractUserFromQueueId(queueId);
      if(!getPrincipal().getUsername().equals(username)){
        throw new IllegalAccessError("/queue/CSM_QUEUE_"+queueId);
      }
      return stockProductService.gather(username,      tickers.toArray(new String[tickers.size()]));
  }

  @RequestMapping(value=PRIVATE_STOCKS_ENDPOINT+"/info", produces={"application/xml", "application/json"})
  @ResponseBody
  @PreAuthorize("hasRole('OAUTH2')")
  public String info(HttpServletRequest request) {
      return "v0";
  }

  private static String extractUserFromQueueId(String token){
        Pattern p = Pattern.compile("_[0-9]+$");
        Matcher m = p.matcher(token);
        String sessionNumber = m.find() ? m.group() : "";
        return token.replaceAll(sessionNumber, "");
	}
}
```

1.  在客户端上，新的 WebSockets 是从股票搜索屏幕（股票结果列表）发起的。特别是在`stock_search.js`和`stock_search_by_market.js`中，已添加以下块，以便定期请求对已显示给经过身份验证的用户的结果集的数据更新：

```java
if(httpAuth.isUserAuthenticated()){
  window.socket = new SockJS('/ws/channels/private');
  window.stompClient = Stomp.over($scope.socket);
  var queueId = httpAuth.generatedQueueId();

  window.socket.onclose = function() {
    window.stompClient.disconnect();
  };
  window.stompClient.connect({}, function(frame) {
    var intervalPromise = $interval(function() {
      window.stompClient.send( '/app/queue/CSM_QUEUE_'+queueId, {}, JSON.stringify($scope.tickers)); 
    }, 5000);

    $scope.$on(
        "$destroy",
        function( event ) {
          $interval.cancel(intervalPromise);
          window.stompClient.disconnect();
        }
    );

  window.stompClient.subscribe('/queue/CSM_QUEUE_'+queueId, function(message){
    var freshStocks = JSON.parse(message.body);
    $scope.stocks.forEach(function(existingStock) {
      //Here we update the currently displayed stocks
    });

    $scope.$apply();
    dynStockSearchService.fadeOutAnim(); //CSS animation   
      //(green/red backgrounds…)
     });
    });
};
```

`httpAuth.generatedQueueId()`函数基于经过身份验证的用户名生成一个随机队列名称（有关详细信息，请参见`http_authorized.js`）。

### RabbitMQ 配置

1.  打开 RabbitMQ WebConsole，选择**Admin**选项卡，然后选择**Policy**菜单（也可以从`http://localhost:15672/#/policies` URL 访问）。

1.  添加以下策略：![RabbitMQ 配置](img/image00915.jpeg)

此策略（命名为`PRIVATE`）适用于所有与模式`CSM_QUEUE_*`匹配的自动生成的队列，自动过期时间为 24 小时。

### 结果

1.  让我们来看看...在启动 Tomcat 服务器之前，请确保：

+   MySQL 正在加载数据运行

+   Redis 服务器正在运行

+   RabbitMQ 正在运行

+   Apache HTTP 已重新启动/重新加载

1.  当所有这些信号都是绿色时，启动 Tomcat 服务器。

1.  使用 Yahoo!帐户登录应用程序，注册新用户，并导航到屏幕：**价格和市场** | **按市场搜索**。如果您选择的市场可能在您的时间开放，您应该能够注意到结果列表上的实时更新：![结果](img/image00916.jpeg)

## 它是如何工作的...

### Redis 服务器

Redis 是一个开源的内存数据结构存储。日复一日，它越来越受欢迎，作为 NoSQL 数据库和键值存储。

它能够存储具有可选过期时间和非常高的可用性（在其显著的集群中）的键，使其成为会话管理器实现的非常可靠的底层技术。这正是我们通过 Spring Session 所做的使用。

### Spring 会话

Spring Session 是一个相对较新的 Spring 项目，但它旨在成长并在 Spring 生态系统中占据重要位置，特别是最近的微服务和物联网趋势。该项目由 Pivotal inc 的 Rob Winch 管理。正如之前介绍的，Spring Session 提供了一个 API 来管理不同 Spring 组件的用户会话。

Spring Session 最有趣和显著的特性是其能够与容器（Apache Tomcat）集成，以提供`HttpSession`的自定义实现。

#### SessionRepositoryFilter

为了使用自定义的`HttpSession`实现，Spring Session 完全替换了`HttpServletRequest`，使用自定义包装器（`SessionRepositoryRequestWrapper`）。这个操作是在`SessionRepositoryFilter`内执行的，它是需要在`web.xml`中配置的 servlet 过滤器，以拦截请求流（在 Spring MVC 之前）。

为了完成其工作，`SessionRepositoryFilter`必须有一个`HttpSession`实现。在某个时候，我们注册了`RedisHttpSessionConfiguration` bean。这个 bean 定义了其他几个 bean，其中包括一个`sessionRepository`，它是一个`RedisOperationsSessionRepository`。

看到`SessionRepositoryFilter`如何对跨应用程序的所有执行的会话操作进行桥接，以实际执行这些操作的引擎实现。

##### RedisConnectionFactory

为了生成适合连接到 Redis 的连接，需要一个`RedisConnectionFactory`实现。在选择`RedisConnectionFactory`实现时，我们一直遵循 Spring 团队的选择，这似乎是`JedisConnectionFactory`。这个`RedisConnectionFactory`依赖于 Jedis（一个轻量级的 Redis Java 客户端）。[`github.com/xetorthio/jedis`](https://github.com/xetorthio/jedis)。

#### CookieHttpSessionStrategy

我们已经注册了一个`HttpSessionStrategy`实现：`RootPathCookieHttpSessionStrategy`。这个类是我们代码库中 Spring `CookieHttpSessionStrategy`的定制版本。

因为我们想要将 cookie 从`cloudstreetmarket-api`传递到`cloudstreetmarket-websocket`，所以 cookie 路径（cookie 的属性）需要设置为根路径（而不是 servlet 上下文路径）。Spring Session 1.1+应该提供可配置的路径功能。

[`github.com/spring-projects/spring-session/issues/155`](https://github.com/spring-projects/spring-session/issues/155)

目前，我们的`RootPathCookieHttpSessionStrategy`（基本上是`CookieHttpSessionStrategy`）生成并期望带有**SESSION**名称的 cookie：

![CookieHttpSessionStrategy](img/image00917.jpeg)

目前，只有`cloudstreetmarket-api`生成这样的 cookie（其他两个 web 应用程序在生成 cookie 时受到限制，以免干扰我们的会话）。

#### Spring Data Redis 和 Spring Session Data Redis

你还记得我们的好朋友 Spring Data JPA 吗？现在，Spring Data Redis 遵循类似的目的，但用于 Redis NoSQL 键值存储：

|   | *"Spring Data Redis（框架通过消除与 Spring 的出色基础设施支持交互所需的冗余任务和样板代码，使编写使用 Redis 键值存储的 Spring 应用程序变得容易。"* |   |
| --- | --- | --- |
|   | --*Spring Data Redis 参考* |

Spring Session Data Redis 是专门为 Spring Session 管理目的实现 Spring Data Redis 的 Spring 模块。

### Tomcat 的 Redis 会话管理器

Apache Tomcat 本身提供了集群和会话复制功能。然而，这些功能依赖于负载均衡器的粘性会话。粘性会话在可伸缩性方面有利有弊。作为缺点，我们可以记住当服务器宕机时会话可能丢失。此外，会话的粘性可能会在我们实际需要应对交通激增时导致加载时间缓慢。

我们还使用了 James Coleman 的一个开源项目，允许 Tomcat 服务器在会话创建时立即将非粘性会话存储在 Redis 中，以供其他 Tomcat 实例使用。这个开源项目可以在以下地址找到：

[`github.com/jcoleman/tomcat-redis-session-manager`](https://github.com/jcoleman/tomcat-redis-session-manager)

然而，这个项目并不正式支持 Tomcat 8。因此，另一个分支在 Tomcat 发布过程中更进一步，并且更接近 Tomcat 8 的要求：

[`github.com/rmohr/tomcat-redis-session-manager`](https://github.com/rmohr/tomcat-redis-session-manager)

我们分叉了这个存储库，并为 Tomcat 8 提供了一个适配器，网址是 https://github.com/alex-bretet/tomcat-redis-session-manager。

`tomcat-redis-session-manager-2.0-tomcat-8.jar`复制到`tomcat/lib`来自这个存储库。

### 注意

Tomcat 8 仍然很新，外围工具需要时间来跟进发布。我们不提供`tomcat-redis-session-manager-2.0-tomcat-8.jar`供生产使用。

### 在 Redis 中查看/清除会话

在 Redis 的主安装目录中，可以找到一个命令行工具（`Cli`）的可执行文件。可以从命令行启动这个可执行文件：

```java

$ src/redis-cli

```

或者：

```java

$ redis-cli.exe

```

这个可执行文件可以访问 Redis 控制台。例如，`KEY *`命令列出所有活动会话：

```java
127.0.0.1:6379> keys *
1) "spring:session:sessions:4fc39ce3-63b3-4e17-b1c4-5e1ed96fb021"
2) "spring:session:expirations:1418772300000"
```

`FLUSHALL`命令清除所有活动会话：

```java
redis 127.0.0.1:6379> FLUSHALL
OK
```

### 提示

通过在线教程了解 Redis 客户端语言，网址是[`try.redis.io`](http://try.redis.io)。

### securityContextPersistenceFilter

我们在`cloudstreetmarket-websocket` Spring Security 过滤器链中使用这个过滤器。它的作用是从配置的`SecurityContextRepository`中将外部 Spring Security 上下文注入到`SecurityContextHolder`中：

```java
<bean id="securityContextPersistenceFilter" class="org.sfw.security.web.context.SecurityContextPersistence Filter">
    <constructor-arg name="repo" ref="httpSessionSecurityContextRepo" />
</bean>

<bean id="httpSessionSecurityContextRepo" class='org.sfw.security.web.context.HttpSessionSecurityContext Repository'>operty name='allowSessionCreation' value='false' />
</bean> 
```

这个过滤器与`SecurityContextRepository`交互，以便在过滤器链完成后持久化上下文。结合 Spring Session，当您需要重用在另一个组件（在我们的情况下是另一个 Web 应用程序）中执行的身份验证时，这个过滤器非常有用。

在这一点上，我们还能够声明一个`global-method-security`元素（Spring Security 命名空间的一部分），允许我们在`@MessageMapping`注释的方法（我们的消息处理方法）中使用`@PreAuthorize`注释：

```java
<global-method-security secured-annotations="enabled" pre-post-annotations="enabled" />
```

### AbstractSessionWebSocketMessageBrokerConfigurer

这是一个很长的标题。我们使用这个抽象类为我们的`WebSocketConfig`提供以下功能：

+   确保会话在传入的 WebSocket 消息上保持活动状态

+   确保 WebSocket 会话在会话终止时被销毁

### AbstractSecurityWebSocketMessageBrokerConfigurer

以类似的方式，这个抽象类为我们的`WebSocketSecurityConfig` bean 提供了授权功能。有了它，`WebSocketSecurityConfig` bean 现在控制着允许传入消息的目的地。

## 还有更多...

### Spring Session

再次推荐 Spring Session 的 Spring 参考文档，非常好。请查看：

[`docs.spring.io/spring-session/docs/current/reference/html5`](http://docs.spring.io/spring-session/docs/current/reference/html5)

### Apache HTTP 代理额外配置

在`httpd.conf`中添加的几行用于在 WebSocket 握手期间将 WebSocket 方案重写为`ws`。不这样做会导致 SockJS 退回到其**XHR**选项（WebSocket 模拟）。

### Spring Data Redis

此外，我们建议您阅读有关 Spring Data Redis 项目的更多信息（在其参考文档中）：

[`docs.spring.io/spring-data/data-redis/docs/current/reference/html`](http://docs.spring.io/spring-data/data-redis/docs/current/reference/html)

## 另请参阅

+   **深入了解 Spring WebSockets** by Sergi Almar: 这是在 SpringOne2GX 2014 上进行的演示：

[`www.slideshare.net/sergialmar/websockets-with-spring-4`](http://www.slideshare.net/sergialmar/websockets-with-spring-4)

+   **Spring-websocket-portfolio，展示应用程序**：我们还必须强调 Rossen Stoyanchev 的 Spring WebSocket 展示应用程序：

[`github.com/rstoyanchev/spring-websocket-portfolio`](https://github.com/rstoyanchev/spring-websocket-portfolio)

# 第九章。测试和故障排除

通过列出的以下配方，本章介绍了一套用于维护、调试和改进应用程序状态的常见实践：

+   使用 Flyway 自动化数据库迁移

+   使用 Mockito 和 Maven Surefire 进行单元测试

+   使用 Cargo、Rest-assured 和 Maven Failsafe 进行集成测试

+   在集成测试中注入 Spring Bean

+   使用 Log4j2 进行现代应用程序日志记录

# 介绍

随着我们现在接近这段旅程的结束，我们必须看到如何巩固工作。在现实世界中，测试必须在开发功能之前编写（或至少同时进行）。在软件开发中编写自动化测试传达了对应用程序状态的巨大信心。这是确保没有遗漏的最佳方式。拥有一个能够通过现代持续集成工具自行测试的系统，确保功能不会在任何时候受到损害。

通过 UI 进行手动测试不能被信任来覆盖开发人员必须考虑的每一个边缘情况。开发人员有责任确保所有漏洞并覆盖所有可能的路径，这是一个很大的责任。

我们的开发人员工作是一项了不起的工作。永恒的技术提升为我们每个人设定了无与伦比的步伐-保持竞争，应对市场，有时引领市场。

我们的工作是长时间的高度专注、搜索信息、设计、重新设计等。编写测试为周期带来了健康的稳定性。它使我们能够在开发的功能上完成一天，甚至在几周和几个月后也是如此。

# 使用 FlyWay 自动化数据库迁移

在交付生命周期中，跨版本和多个环境维护数据库可能会成为一个真正的头疼事。Flyway 是对模式更改可能引起的熵的肯定保护。管理和自动化迁移，Flyway 是软件制造商的一项非常有价值的资产。

## 准备就绪

在这个配方中，我们审查了 Flyway 配置。我们特别审查了它与 Maven 的集成。这将使每个构建都升级（如果有必要）相应的数据库，以使其达到期望水平。

## 如何做…

1.  在 Eclipse 的**Git Perspective**中，检出分支`v9.x.x`的最新版本。

1.  在您的工作区的`/app`目录中，`cloudstreetmarket.properties`文件已更新。此外，还出现了一个额外的`db/migration`目录，其中包含一个`Migration-1_0__init.sql`文件，以及一个新的`/logs`目录。

1.  请确保将所有这些更改反映到位于您的操作系统用户`home` `directory`中的 app 目录中：`<home-directory>/app`。

1.  还要确保您的**MySQL 服务器**正在运行。

1.  在`zipcloud-parent`项目上运行**Maven clean**和**Maven install**命令（右键单击项目**Run as…** | **Maven Clean**，然后**Run as…** | **Maven Install**）。

1.  现在，在`cloudstreetmarket-parent`项目上运行**Maven clean**和**Maven install**命令。

1.  在堆栈跟踪的顶部（在 Maven 阶段的包），您应该看到以下日志：![如何做…](img/image00918.jpeg)

1.  在这个阶段，数据库应该已经被重置，以匹配结构和数据的标准状态。

1.  如果您重新运行构建，现在应该看到以下日志：![如何做…](img/image00919.jpeg)

1.  在父`pom.xml`（在`cloudstreetmarket-parent`中），您可以注意到一个新的插件定义：

```java
<plugin>
  <groupId>com.googlecode.flyway</groupId>
  <artifactId>flyway-maven-plugin</artifactId>
  <version>2.3.1</version>
  <inherited>false</inherited>
  <executions>
      <execution>
      <id>package</id>
      <goals>
      <goal>migrate</goal>
      </goals>
      </execution>
  </executions>
  <configuration>
    <driver>${database.driver}</driver>
    <url>${database.url}</url>
    <serverId>${database.serverId}</serverId>
    <schemas>
      <schema>${database.name}</schema>
      </schemas>
    <locations>
      <location>
        filesystem:${user.home}/app/db/migration
        </location>
      </locations>
      <initOnMigrate>true</initOnMigrate>
        <sqlMigrationPrefix>Migration-</sqlMigrationPrefix>
        <placeholderPrefix>#[</placeholderPrefix>
        <placeholderSuffix>]</placeholderSuffix>
        placeholderReplacement>true</placeholderReplacement>
        <placeholders>
        <db.name>${database.name}</db.name>
        </placeholders>
  </configuration>
  <dependencies>
        <dependency>
        <groupId>mysql</groupId>
        <artifactId>mysql-connector-java</artifactId>
        <version>5.1.6</version>
        </dependency>
  </dependencies>
  </plugin>
```

1.  一些变量（例如`${database.driver}`）在此定义中使用的默认属性对应于`pom.xml`的顶层设置：

```java
  <database.name>csm</database.name>
  <database.driver>com.mysql.jdbc.Driver</database.driver>
  <database.url>jdbc:mysql://localhost</database.url>
  <database.serverId>csm_db</database.serverId>
```

1.  `database.serverId`必须与 Maven `settings.xml`文件中的新`Server`条目匹配（在下一点中描述）。

1.  编辑 Maven `settings.xml`文件（您必须在第一章中创建的*企业 Spring 应用程序的设置例程*中找到位于`<home-directory>/.m2/settings.xml`）。在根节点的某个位置添加以下块：

```java
  <servers>
      <server>  
      <id>csm_db</id>
      <username>csm_tech</username>
      <password>csmDB1$55</password>
      </server>
  </servers>
```

1.  在父`pom.xml`（在`cloudstreetmarket-parent`中），已添加了一个新的`Profile`，用于可选地覆盖此`pom.xml`的默认属性：

```java
<profiles>
  <profile>
  <id>flyway-integration</id>
  <properties>
  <database.name>csm_integration</database.name>
  <database.driver>com.mysql.jdbc.Driver</database.driver>
  <database.url>jdbc:mysql://localhost</database.url>
  <database.serverId>csm_db</database.serverId>
  </properties>
  </profile>
</profiles>
```

### 提示

使用`csm_integration`配置文件运行`Maven Clean Install`（`mvn clean install –Pcsm_integration`）在这种情况下会升级`csm_integration`数据库（如果有必要）。

## 它是如何工作的…

Flyway 是一个数据库版本控制和迁移工具，采用 Apache v2 许可证（免费软件）。它是 Boxfuse GmbH 公司的注册商标。

Flyway 不是这个类别中唯一的产品，但在行业中以其简单性和易配置性而广泛存在。迁移脚本可以用普通的 SQL 编写，并支持许多提供程序。从传统的 RDBMS（Oracle、MySQL、SQL Server 等）到内存数据库（HSQLDB、solidDB 等），甚至云解决方案（AWS Redshift、SQL Azure 等）都得到支持。

### 有限数量的命令

Flyway 提供了以下六个命令，用于报告和操作目的。

#### 迁移

`Migrate`命令是我们集成到 Maven 打包阶段的目标。它查找类路径或文件系统以执行潜在的迁移。可以配置多个`locations`（脚本存储库）。在 Flyway Maven 插件中，这些`locations`在根`configuration`节点中定义。设置模式以保留特定的文件名。

#### 清理

`Clean`命令还原了数据库模式的原始状态。使用此命令删除所有对象（表、视图、函数等）。

#### 信息

`Info`命令提供有关给定模式的当前状态和迁移历史的反馈。如果您查看本地 MySQL 服务器，在`csm`模式中，您会注意到已创建一个名为`schema_version`的元数据表。Flyway 使用以下表来比较脚本存储库状态与数据库状态，并填补差距。

| 版本 | 描述 | 脚本 | 安装于 | 成功 |
| --- | --- | --- | --- | --- |
| `0` | `<< Flyway 模式创建 >>` | `'csm'` | `2015 年 11 月 12 日 18:11` | `1` |
| `1` | `删除并创建` | `/Migration-1_0__drop_and_create.sql` | `2015 年 11 月 12 日 18:11` | `1` |

`Info`命令基本上将此表打印为报告。

#### 验证

`Validate`命令可用于确保在数据库上执行的迁移实际上与当前存储库中的脚本相对应。

#### Baseline

当我们有一个尚未由 Flyway 管理的现有数据库时，可以使用`Baseline`命令。创建一个 Baseline 版本来标记数据库的状态，并使其准备好与即将到来的版本一起使用。在此 Baseline 之前的版本将被简单地忽略。

#### 修复

`Repair`命令可以清理元数据表的损坏状态。为此，Flyway 删除了失败的迁移条目，并重置了存储的校验和以匹配脚本的校验和。

### 关于 Flyway Maven 插件

Flyway Maven 插件提供了 Maven 控制 Flyway 程序的接口。我们对插件的配置如下：

```java
<plugin>
    <groupId>com.googlecode.flyway</groupId>
    <artifactId>flyway-maven-plugin</artifactId>
    <version>2.3.1</version>
    <inherited>false</inherited>
    <executions>
      <execution>
        <id>package</id>
        <goals>
          <goal>migrate</goal>
        </goals>
      </execution>
    </executions>
    <configuration>
      <driver>${database.driver}</driver>
    <url>${database.url}</url>
    <serverId>${database.serverId}</serverId>
    <schemas>
       <schema>${database.name}</schema>
    </schemas>
    <locations>
      <location>
          filesystem:${user.home}/app/db/migration
        </location>
        </locations>
    <initOnMigrate>true</initOnMigrate>
      <sqlMigrationPrefix>Migration-</sqlMigrationPrefix>
      <placeholderPrefix>#[</placeholderPrefix>
      <placeholderSuffix>]</placeholderSuffix>
      <placeholderReplacement>true</placeholderReplacement>
      <placeholders>
      <db.name>${database.name}</db.name>
     </placeholders>
  </configuration>
</plugin>
```

与 Maven 插件一样，执行部分允许将 Maven 阶段绑定到插件的一个或多个目标。对于 Flyway Maven 插件，目标是先前介绍的 Flyway 命令。我们告诉 Maven 何时考虑插件以及在该插件中调用什么。

我们的`configuration`部分介绍了在迁移期间检查的一些参数。例如，`locations`指定要递归扫描的迁移存储库（它们可以以`classpath`:或`filesystem:`开头）。`schemas`定义了 Flyway 管理的整套迁移的模式列表。第一个模式将成为迁移中的默认模式。

一个有趣的功能是能够在迁移脚本中使用变量，以便这些脚本可以用作多个环境的模板。变量名称使用`placeholders`定义，并且脚本中标识变量的方式可以通过`placeholderPrefix`和`placeholderSuffix`进行配置。

整个配置参数列表可以在以下位置找到：

[`flywaydb.org/documentation/maven/migrate.html`](http://flywaydb.org/documentation/maven/migrate.html)。

## 还有更多…

### 官方文档

Flyway 有很好的文档，并得到其社区的积极支持。在[`flywaydb.org`](http://flywaydb.org)上在线阅读有关该产品的更多信息。

您还可以通过 GitHub 存储库[`github.com/flyway/flyway`](https://github.com/flyway/flyway)来关注或贡献该项目。

## 另请参阅

+   **Liquibase**：Flyway 的主要竞争对手可能是 Liquibase。Liquibase 不使用纯 SQL 来编写脚本；它有自己的多重表示 DSL。有关更多信息，请访问：

[`www.liquibase.org`](http://www.liquibase.org)。

# 使用 Mockito 和 Maven Surefire 进行单元测试

单元测试对于监视组件的实现非常有用。Spring 的传统理念促进了应用程序范围内可重用的组件。这些组件的核心实现可能会改变状态（瞬时对象的状态）或触发与其他组件的交互。

单元测试中使用模拟特别评估了组件方法的行为，以及与其他组件的关系。当开发人员习惯于使用模拟时，令人惊讶的是设计在多大程度上受到了不同层和逻辑外部化的影响。同样，对象名称和方法名称变得更加重要。因为它们总结了在其他地方发生的事情，模拟节省了下一个开发人员在代码区域操作时的精力。

开发单元测试在本质上是企业政策。由于测试覆盖的代码百分比可以很容易地反映产品的成熟度，这种代码覆盖率也正在成为评估公司及其产品的标准参考。还必须指出，作为开发流程进行代码审查的公司从拉取请求中获得了有价值的见解。当拉取请求通过测试突出显示行为变化时，潜在变化的影响变得更加清晰。

## 如何做…

1.  在`cloudstreetmarket-parent`项目上重新运行`Maven Install`，就像在上一个示例中一样。当构建过程开始构建核心模块时，您应该看到以下日志，表明在**test**阶段（在**compile**和**package**之间）执行了单元测试：![如何做…](img/image00920.jpeg)

1.  这些测试可以在`cloudstreetmarket-core`模块中找到，特别是在`src/test/java`源文件夹中：![如何做…](img/image00921.jpeg)

单元测试和集成测试都使用 JUnit：

```java
    <dependency>
         <groupId>junit</groupId>
         <artifactId>junit</artifactId>
         <version>4.9</version>
    </dependency>
```

1.  JUnit 在 Eclipse IDE 中得到了原生支持，该 IDE 提供了从类或方法外部运行和调试测试的处理程序：![如何做…](img/image00922.jpeg)

1.  一个非常简单的 JUnit 测试类是`IdentifiableToIdConverterTest`（见下面的代码）。该类断言所有注册的实体都可以通过`IdentifiableToIdConverter`进行转换，以成为`Identifiable`实现（记住 HATEOAS）：

```java
import static org.junit.Assert.*;
import org.junit.Test;
import edu.zipcloud.cloudstreetmarket.core.entities.*;

public class IdentifiableToIdConverterTest {

  private IdentifiableToIdConverter converter;

  @Test
  public void canConvertChartStock(){
    converter = new IdentifiableToIdConverter(ChartStock.class);
    assertTrue(converter.canConvert(ChartStock.class));
    }

  @Test
  public void canConvertAction(){
    converter = new IdentifiableToIdConverter(Action.class);
    assertTrue(converter.canConvert(Action.class));
  }
}
```

1.  更高级的单元测试使用 Mockito 库。例如，在以下`YahooQuoteToCurrencyExchangeConverterTest`中：

```java
@RunWith(MockitoJUnitRunner.class)
public class YahooQuoteToCurrencyExchangeConverterTest {
  @InjectMocks
  private YahooQuoteToCurrencyExchangeConverter converter;
  @Mock
  private CurrencyExchangeRepository currencyExchangeRepository;
  @Test
  public void transferCriticalData(){
      when(currencyExchangeRepository.findOne(
      any(String.class))
      )
      .thenReturn(new CurrencyExchange("WHATEVER_ID""));
    CurrencyExchange currencyExchange = converter.convert(buildYahooQuoteInstance());
    assertEquals("WHATEVER_ID"",currencyExchange.getId());
    assertEquals("USDGBP=X"", currencyExchange.getName());
    assertEquals(BigDecimal.valueOf(10), 
      currencyExchange.getBid());
    ...
    assertEquals(BigDecimal.valueOf(17), 
    currencyExchange.getOpen());	
    verify(currencyExchangeRepository, times(1))
      .findOne(any(String.class));
  }
  ...
}
```

在这里，突出显示的`transferCriticalData()`测试获取了一个未使用真实的`@Autowired CurrencyExchangeRepository`而是使用**Mock**的`YahooQuoteToCurrencyExchangeConverter`实例。转换器使用`convert()`方法调用`YahooQuote`实例。

### 注意

Mock 被告知在其`convert()`方法内调用其`findOne`(`String s`)方法时返回特定的`CurrencyExchange`实例。然后，返回的`currencyExchange`对象逐个字段进行评估，以确保它们与各自的期望匹配。

1.  已在不同的模块中添加了对 Mockito 的 Maven 依赖项：

```java
    <dependency>
      <groupId>org.mockito</groupId>
      <artifactId>mockito-all</artifactId>
      <version>1.9.5<version>
    </dependency>
```

1.  在`CommunityServiceImplTest`中可以找到对 Mockito 的更广泛使用。例如，在以下示例中，`registerUser_generatePasswordAndEncodeIt`测试使用了`ArgumentCaptor`：

```java
@Test
public void registerUser_generatesPasswordAndEncodesIt() {
  when(communityServiceHelper.generatePassword())
    .thenReturn("newPassword");
  when(passwordEncoder.encode("newPassword"))
    .thenReturn("newPasswordEncoded");
  ArgumentCaptor<User>userArgumentCaptor = 
    ArgumentCaptor.forClass(User.class);
  userA.setPassword(null);
  communityServiceImpl.registerUser(userA);
  verify(userRepository, times(1))
    .save(userArgumentCaptor.capture());
  verify(passwordEncoder, times(1))
    .encode("newPassword");
  String capturedGeneratedPassword = 
    userArgumentCaptor.getValue().getPassword();
  assertEquals("newPasswordEncoded", capturedGeneratedPassword);
}
```

## 它是如何工作的...

### @Test 注释

`@Test`注释必须放置在 public void 方法上，以便 JUnit 将其视为测试用例。在这些方法中引发的异常将被视为测试失败。因此，没有引发任何异常的执行代表成功。

`@Test`注释可以通过传递以下两个可选参数进行自定义。

#### 预期和超时参数

`@Test`注释上的**expected**参数指定测试预期引发特定类型的异常才能成功。当引发不同类型的异常或根本没有引发异常时，JUnit 必须将执行视为失败。当测试用例在其`@Test`注释中提供了**timeout**参数时，当执行时间超过指定时间时，此测试将失败。

### @RunWith 注释

如配方中介绍的，`@RunWith`注释允许使用外部测试运行器（而不是默认的`BlockJUnit4ClassRunner`）。顺便说一句，指定默认 JUnit 运行器的声明性技术可能是将`@RunWith`定位到`JUnit4.class`，如下所示：`@RunWith(JUnit4.class)`。

| | *运行器运行测试并在执行过程中通知`RunNotifier`发生重要事件* | |
| --- | --- | --- |
| | --*JUnit.org Javadoc* |

自定义的`Runner`必须实现`org.junit.runner.Runner`中的抽象方法，例如`run(RunNotifier notifier)`和`getDescription()`。它还必须跟进核心 JUnit 函数，例如驱动测试执行流程。JUnit 具有一组注释，例如`@BeforeClass`，`@Before`，`@After`和`@AfterClass`，这些注释由`org.junit.runner.ParentRunner`本地处理。我们将在下面讨论这些注释。

### @Before 和@After 注释

在包含多个测试用例的测试类中，尝试使测试逻辑尽可能清晰是一个很好的做法。从这个角度来看，变量初始化和上下文重新初始化是人们经常尝试外部化以实现可重用性的操作。`@Before`注释可以定义在`public void`方法上，以便 Runner 在**每个单独的测试**之前执行它们。同样，`@After`注释标记了`public void`方法，以便在**每个测试**之后执行（通常用于清理资源或销毁上下文）。

关于继承，父类的`@Before`方法将在当前类的`@Before`方法之前运行。同样，超类中声明的`@After`方法将在当前类的`@After`方法之后运行。

Javadoc 中的另一个有趣的点指定了**所有**`@After`方法都保证会运行，**即使**`@Before`或`@Test`注释的方法引发异常。

### @BeforeClass 和 @AfterClass 注解

`@BeforeClass` 和 `@AfterClass` 注解可以应用于**public static void** 方法。`@BeforeClass` 使方法在测试生命周期中运行**一次**。该方法将在任何其他 `@Test` 或 `@Before` 标注的方法之前运行。

一个被标注为 `@AfterClass` 的方法保证在所有测试之后运行**一次**，并且在所有 `@BeforeClass`，`@Before` 或 `@After` 标注的方法之后运行，即使其中一个抛出异常。

`@BeforeClass` 和 `@AfterClass` 对于处理与测试上下文准备相关的消耗性能的操作（数据库连接管理和前/后业务处理）是有价值的工具。

关于继承，超类中标注为 `@BeforeClass` 的方法将在当前类的方法**之前**执行，而超类中标注为 `@AfterClass` 的方法将在当前类的方法**之后**执行。

### 使用 Mockito

Mockito 是一个支持测试驱动开发和行为驱动开发的开源测试框架。它允许创建双对象（模拟对象）并有助于隔离被测试系统。

#### MockitoJUnitRunner

我们一直在谈论自定义运行器。`MockitoJUnitRunner` 在实现上实际上是在默认的 `JUnitRunner` 周围实现了一个装饰模式。

这种设计使得使用这个运行器是可选的（所有提供的服务也可以用 Mockito 声明式地实现）。

`MockitoJUnitRunner` 自动初始化 `@Mock` 注解的依赖项（这样我们就不需要在 `@Before` 标注的方法中调用 `MockitoAnnotations.initMocks(this)`）。

`initMocks(java.lang.Object testClass)`

|   | *为给定的 testClass 初始化使用 Mockito 注解标注的对象：`@Mock`* |   |
| --- | --- | --- |
|   | --*Javadoc* |

`MockitoJUnitRunner` 也通过在每个测试方法之后调用 `Mockito.validateMockitoUsage()` 来验证我们实现框架的方式。这种验证通过明确的错误输出使我们更有效地使用库。

#### transferCriticalData 示例

被测试系统是 `YahooQuoteToCurrencyExchangeConverter`。`@InjectMocks` 注解告诉 Mockito 在每个测试之前使用初始化的 Mock 对象对目标转换器执行依赖注入（构造函数注入、属性设置器或字段注入）。

`Mockito.when(T methodCall)` 方法，结合 `thenReturn(T value)`，允许在 `converter.convert(...)` 测试方法内部实际调用 `currencyExchangeRepository.findOne` 时定义一个假的 `CurrencyExchange` 返回对象。

`Mockito verify` 方法与 `verify(currencyExchangeRepository, times(1)).findOne(any(String.class))` 告诉 Mockito 验证被测试的 `convert` 方法如何与 Mock(s) 交互。在下面的例子中，我们希望 `convert` 方法只调用了存储库一次。

#### registerUser 示例

更具体地，在 `registerUser_generatesPasswordAndEncodesIt` 测试中，我们使用 `MockitoArgumentCaptor` 手动对被调用的模拟方法的对象进行更深入的分析。

当我们没有中间层并且结果被重用来调用其他方法时，`MockitoArgumentCaptor` 是很有用的。

比表面的（但仍然非常有用的）类型检查更多的内省工具可能是必需的（例如，`any(String.class)`）。解决方案是在测试方法中使用 `ArgumentCaptor` 与额外的局部变量。

### 提示

记住，实现方法中的局部变量和瞬态状态总是增加相关测试的复杂性。更短、明确和内聚的方法总是更好的选择。

## 还有更多…

### 关于 Mockito

我们建议查看 Mockito 的 Javadoc，它非常完善并且包含了很多实用的例子。

[`docs.mockito.googlecode.com/hg/org/mockito/Mockito.html`](http://docs.mockito.googlecode.com/hg/org/mockito/Mockito.html)

### JUnit 规则

到目前为止，我们还没有涵盖 JUnit 规则。JUnit 提供了`@Rule`注解，可以应用于测试类字段，以抽象出重复的业务特定准备工作。通常用于准备测试上下文对象（固定装置）。

[`www.codeaffine.com/2012/09/24/junit-rules`](http://www.codeaffine.com/2012/09/24/junit-rules)

[`junit.org/javadoc/latest/org/junit/Rule.html`](http://junit.org/javadoc/latest/org/junit/Rule.html)

## 另请参阅

+   **代码覆盖率，JaCoCo**：JaCoCo 是一个库，用于帮助维护和增加应用程序中测试覆盖的代码百分比；它位于：[`eclemma.org/jacoco`](http://eclemma.org/jacoco)。

+   在以下位置阅读有关 JaCoCo Maven 插件的更多信息：

[`eclemma.org/jacoco/trunk/doc/maven.html`](http://eclemma.org/jacoco/trunk/doc/maven.html)

# 使用 Cargo、Rest-assured 和 Maven failsafe 进行集成测试

集成测试与单元测试一样重要。它们从更高的层面验证功能，并同时涉及更多的组件或层。当环境需要快速演变时，集成测试（IT 测试）变得更加重要。设计过程通常需要迭代，而单元测试有时会严重影响我们重构的能力，而高级别测试相对来说受到的影响较小。

## 准备就绪

本文介绍了如何开发重点放在 Spring MVC Web 服务上的自动化 IT 测试。这些 IT 测试不是行为测试，因为它们根本不评估用户界面。要测试行为，需要更高的测试级别，模拟用户通过应用程序界面的旅程。

我们将配置 Cargo Maven 插件，作为 pre-integration-test Maven 阶段的一部分来建立一个测试环境。在 integration-test 阶段，我们将让 Maven failsafe 插件执行我们的 IT 测试。这些 IT 测试将使用 Rest-assured 库对测试环境运行 HTTP 请求并断言 HTTP 响应。

## 如何做…

1.  我们已经在`cloudstreetmarket-api`模块中设计了集成测试。这些测试旨在测试 API 控制器方法。![如何做…](img/image00923.jpeg)

1.  伟大的 Rest-assured 库附带以下 Maven 依赖项：

```java
  <dependency>
    <groupId>com.jayway.restassured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>2.7.0</version>
  </dependency>
```

1.  使用 REST-assured 进行 IT 测试的典型示例是`UserControllerIT.createUserBasicAuth()`：

```java
public class UserControllerIT extends AbstractCommonTestUser{
  private static User userA;
  @Before
  public void before(){
    userA = new User.Builder()
      .withId(generateUserName())
      .withEmail(generateEmail())
      .withCurrency(SupportedCurrency.USD)
      .withPassword(generatePassword())
      .withLanguage(SupportedLanguage.EN)
      .withProfileImg(DEFAULT_IMG_PATH)
      .build();
  }
  @Test
  public void createUserBasicAuth(){
    Response responseCreateUser = given()
      .contentType("application/json;charset=UTF-8")
      .accept("application/json"")
      .body(userA)
      .expect
      .when()
      .post(getHost() + CONTEXT_PATH + "/users");
  String location = 
      responseCreateUser.getHeader("Location");
  assertNotNull(location);
  Response responseGetUser = given()
      .expect().log().ifError()
      .statusCode(HttpStatus.SC_OK)
      .when()
      .get(getHost() + CONTEXT_PATH + location + 
      		JSON_SUFFIX);
    UserDTO userADTO = 
      deserialize(responseGetUser.getBody().asString());
    assertEquals(userA.getId(), userADTO.getId());
    assertEquals(userA.getLanguage().name(), 
    userADTO.getLanguage());
    assertEquals(HIDDEN_FIELD, userADTO.getEmail());
    assertEquals(HIDDEN_FIELD, userADTO.getPassword());
    assertNull(userA.getBalance());
  }
}
```

1.  因为它们需要更长的时间来执行，我们希望将 IT 测试的执行与主 Maven 生命周期解耦。我们已将这些 IT 测试关联到名为`integration`的 Maven 配置文件。

### 注意

Maven 配置文件提供了使用额外生命周期绑定来丰富 Maven 构建的可能性。例如，我们的集成配置文件是通过在通常的命令中传递此配置文件 ID 作为`Profile`参数来激活的：

`$ mvn clean install -P integration`

1.  对于我们的 API IT 测试，我们已将特定于配置文件的配置放在了`cloudstreetmarket-api pom.xml`文件中：

```java
<profiles>
  <profile>
  <id>integration</id>
  <build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-failsafe-plugin</artifactId>
      <version>2.12.4</version>
      <configuration>
      <includes>
        <include>**/*IT.java</include>
      </includes>
      <excludes>
        <exclude>**/*Test.java</exclude>
      </excludes>
   </configuration>
   <executions>
      <execution>
        <id>integration-test</id>
        <goals>
          <goal>integration-test</goal>
        </goals>
      </execution>
      <execution>
        <id>verify</id>
        <goals><goal>verify</goal></goals>
      </execution>
   </executions>
 </plugin>
 <plugin>
  <groupId>org.codehaus.cargo</groupId>
  <artifactId>cargo-maven2-plugin</artifactId>
  <version>1.4.16</version>
      <configuration>
      <wait>false</wait>
      <container>
      <containerId>tomcat8x</containerId>
            <home>${CATALINA_HOME}</home>
      <logLevel>warn</logLevel>
      </container>
      <deployer/>
      <type>existing</type>
      <deployables>
      <deployable>
      <groupId>edu.zc.csm</groupId>
      <artifactId>cloudstreetmarket-api</artifactId>
      <type>war</type>
        <properties>
          <context>api</context>
        </properties>
      </deployable>
      </deployables>
    </configuration>
    <executions>
      <execution>
        <id>start-container</id>
        <phase>pre-integration-test</phase>
        <goals>
         <goal>start</goal>
         <goal>deploy</goal>
      </goals>
    </execution>
    <execution>
      <id>stop-container</id>
      <phase>post-integration-test</phase>
      <goals>
         <goal>undeploy</goal>
         <goal>stop</goal>
      </goals>
         </execution>
      </executions>
    </plugin>
  </plugins>
  </build>
  </profile>
</profiles>
```

1.  在尝试在您的计算机上运行它们之前，请检查您的**CATALINA_HOME**环境变量是否指向 Tomcat 目录。如果没有，您必须创建它。要设置的变量应该是以下内容（如果您已经按照第一章进行了设置，则应该是）：

+   `C:\tomcat8`：在 MS Windows 上

+   `/home/usr/{system.username}/tomcat8`：在 Linux 上

+   `/Users/{system.username}/tomcat8`：在 Mac OS X 上

1.  此外，请确保 Apache HTTP、Redis 和 MySQL 在您的本地计算机上运行正常（如果您跳过了上一章，请参阅上一章）。 

1.  准备就绪后：

+   在终端中执行以下 Maven 命令（如果 Maven 目录在您的路径中）：

```java

 mvn clean verify -P integration

```

+   或者在 Eclipse IDE 中从**Run** | **Run Configurations…**菜单中创建此自定义构建的快捷方式。要创建的构建配置如下：

![如何做…](img/image00924.jpeg)

1.  运行此命令（或快捷方式）应该：

1.  将**api.war**部署到本地 Tomcat 服务器

1.  启动本地 Tomcat

1.  执行与**/*IT.java 模式匹配的测试类

如果所有测试都通过，您应该看到`[INFO] BUILD SUCCESS`消息。

1.  在构建到 API 时，您应该看到以下一小段堆栈跟踪，表明我们的 IT 测试成功执行：![如何做…](img/image00925.jpeg)

## 它是如何工作的…

我们将在本节中解释为什么我们引入了 Maven failsafe 插件，Cargo 插件配置如何满足我们的需求，我们如何使用 REST-assured，以及这个 REST-assured 库有多有用。

### Maven Failsafe 与 Maven Surefire

我们使用 Maven failsafe 来运行集成测试，使用 Maven Surefire 来运行单元测试。这是使用这些插件的标准方式。以下表反映了这一点，插件的默认命名模式用于测试类：

|   | Maven Surefire | Maven Failsafe |
| --- | --- | --- |
| **默认测试包含模式** |

```java

**/Test*.java
**/*Test.java
**/*TestCase.java

```

|

```java

**/IT*.java
**/*IT.java
**/*ITCase.java

```

|

| **默认输出目录** |
| --- |

```java

${basedir}/target/surefire-reports

```

|

```java

${basedir}/target/failsafe-reports

```

|

| **绑定到构建阶段** |
| --- |

```java

test

```

|

```java

pre-integration-test
integration-test
post-integration-test
verify

```

|

对于 Maven Failsafe，您可以看到我们覆盖的模式包含/排除是可选的。关于绑定到 Maven 构建阶段，我们选择在`integration-test`和`verify`阶段触发我们的集成测试的执行。

### Code Cargo

Cargo 是一个轻量级库，为操作多个支持的容器（Servlet 和 JEE 容器）提供标准 API。覆盖的 API 操作示例包括部署构件、远程部署和容器启动/停止。当通过 Maven、Ant 或 Gradle 使用时，它主要用于提供对集成测试的支持，但也可以用于其他范围。

#### Cargo Maven 插件

我们通过其 Maven 插件`org.codehaus.cargo:cargo-maven2-plugin`使用 Cargo 自动准备一个集成环境，我们可以对其运行集成测试。在集成测试之后，我们期望此环境关闭。

##### 绑定到 Maven 阶段

以下执行已声明为`cargo-maven2-plugin`配置的一部分：

```java
<executions>
  <execution>
    <id>start-container</id>
    <phase>pre-integration-test</phase>
    <goals>
      <goal>start</goal>
    <goal>deploy</goal>
      </goals>
  </execution>
  <execution>
        <id>stop-container</id>
    <phase>post-integration-test</phase>
      <goals>
      <goal>undeploy</goal>
      <goal>stop</goal>
        </goals>
  </execution>
</executions>
```

让我们看看执行`mvn install`命令时会发生什么。

`install`是默认 Maven 生命周期的一个阶段。如第一章中所解释的*企业 Spring 应用程序的设置例程*，默认生命周期有 23 个构建阶段，从`validate`到`deploy`。`install`阶段是第 22 个阶段，因此会检查 22 个阶段，看是否有插件目标可以附加到它们上面。

在这里，`pre-integration-test`阶段（出现在默认生命周期的`validate`和`install`之间）将触发位于我们的 maven Cargo 插件的`start`和`deploy`目标下的进程。与此相同的逻辑是`post-integration-test`触发`undeploy`和`stop`目标。

在执行 IT 测试之前，我们启动和部署 Tomcat 服务器。这些 IT 测试在`integration-test`阶段使用 Maven failsafe 进行处理。最后，Tomcat 服务器被取消部署并停止。

IT 测试也可以在`verify`阶段执行（如果服务器在默认 Maven 生命周期之外启动）。

##### 使用现有的 Tomcat 实例

在 Cargo Maven 插件配置中，我们针对现有的 Tomcat 实例。我们的应用当前依赖于 MySQL、Redis、Apache HTTP 和自定义会话管理。我们决定 IT 测试执行将需要在适当的集成环境中运行。

如果没有这些依赖关系，我们将让 Cargo 下载 Tomcat 8 实例。

### Rest assured

REST-assured 是一个由 Jayway 公司支持的 Apache v2 许可的开源库。它是用 Groovy 编写的，允许通过其独特的功能 DSL 进行 HTTP 请求和验证 JSON 或 XML 响应，从而大大简化了 REST 服务的测试。

#### 静态导入

为了有效地使用 REST-assured，文档建议添加以下包的静态导入：

+   `com.jayway.restassured.RestAssured.*`

+   `com.jayway.restassured.matcher.RestAssuredMatchers.*`

+   `org.hamcrest.Matchers.*`

#### 一种给定、当、然后的方法

要了解 REST-assured DSL 的基础知识，让我们考虑我们的一个测试（在`UserControllerIT`中），它提供了 REST-assured 使用的简要概述：

```java
  @Test
  public void createUserBasicAuthAjax(){
    Response response = given()
    .header("X-Requested-With", "XMLHttpRequest")
    .contentType("application/json;charset=UTF-8")
    .accept("application/json\")
    .body(userA)
    .when()
    .post(getHost() + CONTEXT_PATH + "/users");
    assertNotNull(response.getHeader("Location"));
  }
```

语句的`given`部分是 HTTP 请求规范。使用 REST-assured，一些请求头，如`Content-Type`或`Accept`，可以以直观的方式使用`contentType(…)`和`accept(…)`来定义。其他**头部**可以通过通用的`.header(…)`来访问。请求参数和身份验证也可以以相同的方式定义。

对于`POST`和`PUT`请求，有必要向请求传递一个 body。这个`body`可以是普通的 JSON 或 XML，也可以直接是 Java 对象（就像我们在这里做的那样）。这个`body`作为 Java 对象，将根据规范中定义的`content-type`（JSON 或 XML）由库进行转换。

在 HTTP 请求规范之后，`when()`语句提供了有关实际 HTTP 方法和目的地的信息。

在这个阶段，返回的对象允许我们从`then()`块中定义期望，或者像我们在这里做的那样，从中检索`Response`对象，从中可以单独定义约束。在我们的测试用例中，预期`Response`的`Location`头部应该被填充。

## 还有更多…

更多信息可以在以下 Cargo 和 REST-assured 各自的文档中找到：

### 关于 Cargo

有关产品及其与第三方系统集成的更多信息，请参阅[`codehaus-cargo.github.io/cargo/Home.html`](https://codehaus-cargo.github.io/cargo/Home.html)。

### 更多 REST-assured 示例

有关更多示例，REST-assured 在线 Wiki 提供了大量信息：

[`github.com/jayway/rest-assured/wiki/Usage`](https://github.com/jayway/rest-assured/wiki/Usage)

# 将 Spring Bean 注入集成测试

这个示例是如何将 Spring 管理的 bean 注入到集成测试类中的一个示例。即使对于其首要目标是将后端作为黑匣子进行评估的 IT 测试，有时也需要从中间层访问技术对象。

## 准备工作

我们将看到如何重用 Spring 管理的`datasource`实例，将其注入到我们的测试类中。这个`datasource`将帮助我们构建一个`jdbcTemplate`的实例。从这个`jdbcTemplate`，我们将查询数据库并模拟/验证否则无法测试的过程。

## 如何做…

1.  我们在我们的`UserControllerIT`测试中`@Autowired`了一个`dataSource` SpringBean。这个 bean 在测试特定的 Spring 配置文件（`spring-context-api-test.xml`）`resources`目录（`cloudstreetmarket-api`）中定义：![如何做…](img/image00926.jpeg)

```java
<context:property-placeholderlocation="
  file:${user.home}/app/cloudstreetmarket.properties""/>
<bean id="dataSource" 		
  class="org.apache.commons.dbcp2.BasicDataSource" 	
  destroy-method="close"">
  <property name="driverClassName"">
     <value>com.mysql.jdbc.Driver</value>
  </property>
  <property name="url"">
    <value>${db.connection.url}</value>
  </property>
<property name="username"">
  <value>${db.user.name}</value>
</property>
<property name="password"">
  <value>${db.user.passsword}</value>
</property>
<property name="defaultReadOnly">
  <value>false</value>
</property>
</bean>
```

在`UserControllerIT`类中，从`@Autowired dataSource` bean 创建了一个`jdbcTemplate`实例：

```java
    @Autowired
    private JdbcTemplate jdbcTemplate;
    @Autowired
    public void setDataSource(DataSource dataSource) {
    	this.jdbcTemplate = new JdbcTemplate(dataSource);
    }
```

1.  我们使用`jdbcTemplate`直接在数据库中插入和删除`Social Connections`（参见第五章，“使用 Spring MVC 进行身份验证”）。这使我们能够绕过并模拟成功的用户 OAuth2 身份验证流程（通常通过 Web 浏览器进行）。

对于删除社交连接，我们创建了以下私有方法，根据需要由测试调用：

```java
    private void deleteConnection(String spi, String id) {
    	this.jdbcTemplate.update("delete from userconnection where providerUserId = ? and userId = "?", new Object[] {spi, id});
   }
```

1.  在`UserControllerIT`类的顶部，可以注意到以下两个注解：

+   `@RunWith(SpringJUnit4ClassRunner.class)`告诉 JUnit 使用 JUnit 的自定义扩展（`SpringJUnit4ClassRunner`）来运行，支持 Spring`TestContext`框架。

+   `@ContextConfiguration("classpath:spring-context-api-test.xml")`指定了加载和配置 Spring 应用程序上下文的位置和方式：

```java
    @RunWith(SpringJUnit4ClassRunner.class)
    @ContextConfiguration("classpath:spring-context-api-test.xml"")
    public class UserControllerIT extends AbstractCommonTestUser{
    private static User userA;
    private static User userB;
    ...
    }
```

## 它是如何工作的...

### SpringJUnit4ClassRunner

在设计上，`SpringJUnit4ClassRunner`是 JUnit 的`BlockJUnit4ClassRunner`的直接子类。`SpringJUnit4ClassRunner`在加载`TestContextManager`时初始化。`TestContextManager`管理`TestContext`的生命周期，并且还可以将测试事件反映给注册的`TestExecutionListeners`（来自`@BeforeClass`、`@AfterClass`、`@Before`和`@After`注解）。

通过加载 Spring 上下文，`SpringJUnit4ClassRunner` Spring 上下文，`SpringJUnit4ClassRunner`使得在测试类中可以使用 Spring 管理的 bean。`SpringJUnit4ClassRunner`还支持一组注解（来自 JUnit 或 Spring 测试），可以在测试类中使用。可以信任这些注解的使用，以便随后为上下文定义的对象提供适当的生命周期管理。

这些注解是`@Test`（带有其`expected`和`timeout`注解参数）、`@Timed`、`@Repeat`、`@Ignore`、`@ProfileValueSourceConfiguration`和`@IfProfileValue`。

### @ContextConfiguration 注解

这个类级别的注解是特定于 Spring 测试的。它定义了如何以及从哪里加载 Spring 上下文用于测试类。

我们在配方中的定义针对特定的 Spring XML 配置文件`@ContextConfiguration("classpath:spring-context-api-test.xml")`。

然而，自 Spring 3.1 以来，上下文可以以编程方式定义，`@ContextConfiguration`也可以以以下方式针对配置类：

`@ContextConfiguration(classes={AnnotationConfig.class,` `WebSocketConfig.class})`

如下面的片段所示，两种声明类型可以组合在同一个注解中：

`@ContextConfiguration(classes={AnnotationConfig.class,` `WebSocketConfig.class}, locations={`"`classpath:spring-context-api-test.xml`"`})`

## 还有更多...

我们将在本节中更多地了解为测试目的而使用的 Spring JdbcTemplate。

### JdbcTemplate

在*第一章，企业 Spring 应用程序的设置例程*中，我们介绍了使 Spring 框架成为今天的样子的不同模块。其中一组模块是**数据访问和集成**。这个组包含了 JDBC、ORM、OXM、JMS 和事务模块。

`JdbcTemplate`是 Spring JDBC 核心包的关键部分。它可靠地允许使用简单的实用方法执行数据库操作，并为大量的模板代码提供了抽象。再次，这个工具节省了我们的时间，并提供了设计高质量产品的模式。

### 模板逻辑的抽象

让我们以我们的测试类中删除连接的方法为例：

```java
jdbcTemplate.update("delete from userconnection where 
  providerUserId = ? and userId = "?", new Object[] {spi, id});
```

使用`jdbcTemplate`，删除数据库元素是一条指令。它在内部创建一个`PreparedStatement`，根据我们实际传递的值选择正确的类型，并为我们管理数据库连接，确保无论发生什么都关闭这个连接。

`jdbcTemplate.update`方法被设计用于发出单个 SQL 更新操作。它可以用于插入、更新，也可以删除。

就像在 Spring 中经常发生的那样，`jdbcTemplate`也会将产生的已检查异常（如果有的话）转换为未检查异常。在这里，潜在的`SQLExceptions`将被包装在`RuntimeException`中。

#### 自动生成 ID 的提取

`jdbcTemplate.update`方法还提供其他参数类型：

```java
jdbcTemplate.update(final PreparedStatementCreator psc, final
  KeyHolder generatedKeyHolder);
```

在插入的情况下，可以在需要时调用此方法来读取并可能重用生成的 ID（在查询执行之前是未知的）。

在我们的示例中，如果我们想要在插入新连接时重用生成的连接 ID，我们将这样做：

```java
KeyHolder keyHolder = new GeneratedKeyHolder();
jdbcTemplate.update(
  new PreparedStatementCreator() {
    public PreparedStatement createPreparedStatement(Connection 
    connection) throws SQLException {
    PreparedStatement ps = connection.prepareStatement("insert into userconnection (accessToken, ... , secret, userId ) values (?, ?, ... , ?, ?)", new String[] {"id""});
    ps.setString(1, generateGuid());
    ps.setDate(2, new Date(System.currentTimeMillis()));
    ...
    return ps;
    }
  }, keyHolder);
  Long Id = keyHolder.getKey().longValue();
```

但我们并没有明确要求这样的用例。

# 使用 Log4j2 的现代应用程序日志记录

在 Java 生态系统的 20 年演变之后，日志记录的方式已经看到了不同的策略、趋势和架构。如今，可以在使用的第三方依赖项中找到几种日志框架。我们必须支持它们所有来调试应用程序或跟踪运行时事件。

## 准备就绪

这个配方为`CloudStreet Market`应用程序提供了一个未来的`Log4j2`实现。它需要将几个 Maven 依赖项添加到我们的模块中。作为解决方案，它可能看起来相当复杂，但实际上需要支持的日志框架数量有限，`Log4j2`迁移背后的逻辑相当简单。

## 如何做...

1.  已将以下 Maven 依赖项添加到父模块（`cloudstreetmarket-parent`）的依赖项管理部分：

```java
    <!-- Logging dependencies -->
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-api</artifactId>
      <version>2.4.1</version>
    </dependency>
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-core</artifactId>
      <version>2.4.1</version>
    </dependency>
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-slf4j-impl</artifactId>
      <version>2.4.1</version>
    </dependency>
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-1.2-api</artifactId>
      <version>2.4.1</version>
    </dependency>
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-jcl</artifactId>
      <version>2.4.1</version>
      </dependency>
    <dependency>
      <groupId>org.apache.logging.log4j</groupId>
      <artifactId>log4j-web</artifactId>
        <scope>runtime</scope>
      <version>2.4.1</version>
    </dependency>
    <dependency>
      <groupId>org.slf4j</groupId>
      artifactId>slf4j-api</artifactId>
      <version>${slf4j.version}</version>
    </dependency>
```

### 提示

最后一个依赖项管理，`org.slf4j`，允许我们确保`slf4j`的一个版本将在所有地方使用。

1.  然后在`api`，`ws`和`core`模块中添加了以下依赖项：`log4j-api`，`log4j-core`，`log4j-slf4j-impl`，`log4j-1.2-api`和`log4j-jcl`。

1.  在 web 模块（`api`，`ws`和`webapp`）中，已添加了`log4j-web`。

1.  请注意，`slf4j-api`仅用于依赖项管理。

1.  使用**额外的 JVM 参数**启动 Tomcat 服务器：

```java
-Dlog4j.configurationFile=<home-directory>\app\log4j2.xml.
```

### 提示

将`<home-directory>`替换为您在计算机上实际使用的路径。

1.  用户主目录中的应用程序目录现在包含`log4j2`配置文件：

```java
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="OFF" monitorInterval="30">
<Appenders
  <Console name="Console" target="SYSTEM_OUT">
    <PatternLayout pattern"="%d{HH:mm:ss.SSS} %-5level %logger{36} - %msg%n""/>
  </Console>
  <RollingFile name="FileAppender" fileName="${sys:user.home}/app/logs/cloudstreetmarket.log"
        filePattern="${sys:user.home}/app/logs/${date:yyyy-MM}/cloudstreetmarket-%d{MM-dd-yyyy}-%i.log.gz">
      <PatternLayout>
        <Pattern>%d %p %C{1} %m%n</Pattern>
      </PatternLayout>
      <Policies>
        <TimeBasedTriggeringPolicy />
        <SizeBasedTriggeringPolicy size="250 MB"/>
      </Policies>
  </RollingFile>
</Appenders>
<Loggers>
  <Logger name="edu.zipcloud" level="INFO"/>
  <Logger name="org.apache.catalina" level="ERROR"/>
  <Logger name="org.springframework.amqp" level="ERROR"/>
  <Logger name="org.springframework.security" level="ERROR"/>

  <Root level="WARN">
    <AppenderRef ref="Console"/>
  <AppenderRef ref="FileAppender"/>
  </Root>
</Loggers>
</Configuration>
```

1.  作为备选方案，每个单个模块的类路径（`src/main/resources`）中也存在一个`log4j2.xml`文件。

1.  已在不同的类中放置了一些日志说明，以跟踪用户的旅程。

在`SignInAdapterImpl`中记录说明：

```java
    import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

@Transactional
public class SignInAdapterImpl implements SignInAdapter{
  private static final Logger logger = 
    LogManager.getLogger(SignInAdapterImpl.class);
  ...
  public String signIn(String userId, Connection<?>connection, NativeWebRequest request) {
  ...
  communityService.signInUser(user);
  logger.info("User {} logs-in with OAUth2 account", user.getId());
  return view;
  }
}
```

在`UsersController`中记录说明：

```java
@RestController
@RequestMapping(value=USERS_PATH, produces={"application/xml", "application/json"})
public class UsersController extends CloudstreetApiWCI{
  private static final Logger logger = LogManager.getLogger(UsersController.class);
  ...
  @RequestMapping(method=POST)
  @ResponseStatus(HttpStatus.CREATED)
  public void create(@Valid @RequestBody User user, 
    @RequestHeader(value="Spi", required=false) String guid, 
  @RequestHeader(value="OAuthProvider", required=false) String provider, HttpServletResponse response) throws IllegalAccessException{
      if(isNotBlank(guid)){
      ...
      communityService.save(user);
      logger.info("User {} registers an OAuth2 account: "{}", user.getId(), guid);
      }
      else{
    user = communityService.createUser(user, ROLE_BASIC);
    ...
    logger.info("User registers a BASIC account"", user.getId());
      }
    ...
  }
  ...
}
```

1.  启动本地 Tomcat 服务器，并简要浏览应用程序。与以下示例一样，您应该能够在聚合文件`<home-directory>/apps/logs/cloudstreetmarket.log`中观察到客户活动的跟踪：![如何做...](img/image00927.jpeg)

### 提示

通过我们制作的`log4j2.xml`配置，`cloudstreetmarket.log`文件将在达到 250MB 时自动被压缩并分类到目录中。

## 工作原理...

我们主要将在本节中审查 Log4j2 如何设置与其他日志框架一起工作。配置的其他部分（此处未涵盖）被认为更直观。

### Apache Log4j2 和其他日志框架

Log4j1+作为一个项目正在消亡，因为它不再与 Java 5+兼容。

Log4j 2 是作为 log4j 代码库的一个分支构建的。从这个角度来看，它与 Logback 项目竞争。Logback 最初是 Log4j 的合法继续。

Log4j 2 实际上实现了 Logback 的许多改进，但也修复了 Logback 架构固有的问题。

Logback 提供了很好的性能改进，特别是在多线程方面。相比之下，Log4j 2 提供了类似的性能。

#### SLF4j 的情况

SLF4j 本身不是一个日志框架；它是一个抽象层，允许用户在部署时插入任何日志系统。

SLF4j 在类路径中需要一个 SLF4j 绑定。绑定的示例如下：

+   `slf4j-log4j12-xxx.jar`：（log4j 版本 1.2），

+   `slf4j-jdk14-xxx.jar`：（来自 jdk 1.4 的`java.util.logging`），

+   `slf4j-jcl-xxx.jar`：（Jakarta Commons Logging）

+   `logback-classic-xxx.jar`。

它通常还需要目标日志框架的核心库。

### 迁移到 log4j 2

Log4j2 不提供对 Log4j1+的向后兼容性。 这可能听起来像一个问题，因为应用程序（如`CloudStreetMarket`）经常使用嵌入其自己的日志框架的第三方库。 例如，Spring 核心具有对 Jakarta Commons Logging 的传递依赖。

为了解决这种情况，Log4j 2 提供了适配器，确保内部日志不会丢失，并将桥接到加入 log4j 2 日志流的日志。 几乎所有可能产生日志的系统都有适配器。

#### Log4j 2 API 和核心

Log4j 2 带有 API 和实现。 两者都是必需的，并且具有以下依赖项：

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-api</artifactId>
  <version>2.4.1</version>
</dependency>
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-core</artifactId>
  <version>2.4.1</version>
</dependency>
```

#### Log4j 2 适配器

如前所介绍，一组**适配器**和**桥接**可用于为我们的应用程序提供向后兼容性。

##### Log4j 1.x API 桥接

当在特定模块中注意到对 Log4j 1+的传递依赖时，应添加以下桥接：

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-1.2-api</artifactId>
  <version>2.4.1</version>
</dependency>
```

##### Apache Commons Logging 桥接

当在特定模块中注意到对 Apache（Jakarta）Commons Logging 的传递依赖时，应添加以下桥接：

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-jcl</artifactId>
  <version>2.4.1</version>
</dependency>
```

##### SLF4J 桥接

相同的逻辑适用于覆盖 slf4j 的使用；应添加以下桥接：

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-slf4j-impl</artifactId>
  <version>2.4.1</version>
</dependency>
```

##### Java Util Logging 适配器

我们的应用程序中没有注意到对`java.util.logging`的传递依赖，但如果有的话，我们将使用以下桥接：

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-jul</artifactId>
  <version>2.4.1</version>
</dependency>
```

##### Web Servlet 支持

Apache Tomcat 容器有自己的一组库，也会产生日志。 在 Web 模块上添加以下依赖项是确保容器日志路由到主 Log4j2 管道的一种方法。

```java
<dependency>
  <groupId>org.apache.logging.log4j</groupId>
  <artifactId>log4j-web</artifactId>
  <version>2.4.1</version>
  <scope>runtime</scope>
</dependency>
```

### 配置文件

此食谱的第六步详细介绍了我们的 log4j2 配置。 它由不同的可配置的`Appenders`（基本上是输出通道）组成。 我们正在使用控制台和基于文件的`Appender`，但是 Log4j 2 具有关于`Appenders`的基于插件的架构，如果需要，可以使用外部输出通道（SMTP，打印机，数据库等）。

## 还有更多...

作为外部信息源，我们指出了有趣的 Log4j2 自动配置，该配置由级联查找配置文件、官方文档和用于直接记录到 Redis 的`Appender`组成。

### 自动配置

Log4j2 实现级联查找以定位 log4j2 配置文件。 从查找提供的`log4j.configurationFile`系统属性开始，到类路径中的`log4j2-test.xml`和`log4j2.xml`文件，官方文档详细介绍了所有遵循的级联步骤。 此文档可在以下地址找到：

[`logging.apache.org/log4j/2.x/manual/configuration.html`](https://logging.apache.org/log4j/2.x/manual/configuration.html)

### 官方文档

官方文档非常完善，可在以下地址找到：

[`logging.apache.org/log4j/2.x.`](https://logging.apache.org/log4j/2.x.)

### 有趣的 Redis Appender 实现

以下地址介绍了一个 Apache 许可的项目，该项目提供了一个 Log4j2 **Appender**，可以直接记录到 Redis 中：

[`github.com/pavlobaron/log4j2redis`](https://github.com/pavlobaron/log4j2redis)

# 第三部分。 模块 3

> **精通 Spring MVC 4**
> 
> *掌握使用 Spring MVC 框架设计真实世界的 Web 应用程序的专业知识*

# 第一章。 掌握 MVC 架构

在本章中，我们将讨论 MVC 架构原则，并了解 Spring MVC 如何实现这些原则。

我们的目标是设计一个简单的页面，用户可以在其中搜索符合某些条件的推文，并将它们显示给我们的用户。

为了实现这一点，我们将使用 Spring Social Twitter 项目，该项目可在[`projects.spring.io/spring-social-twitter/`](http://projects.spring.io/spring-social-twitter/)上找到。

我们将看到如何使 Spring MVC 与现代模板引擎 Thymeleaf 配合工作，并尝试理解框架的内部机制。我们将引导用户通过不同的视图，最后，我们将使用 WebJars 和 Materialize（[`materializecss.com`](http://materializecss.com)）为我们的应用程序提供出色的外观。

# MVC 架构

我希望 MVC 首字母缩略词的含义对大多数人来说是熟悉的。它代表模型视图控制器，被认为是一种非常流行的通过解耦数据和表示层构建用户界面的方式。

![MVC 架构](img/image00928.jpeg)

MVC 模式在从 Smalltalk 世界中出现并进入 Ruby on Rails 框架后变得非常流行。

这种架构模式包括三个层：

+   **模型**：这包括应用程序了解的数据的各种表示形式。

+   **视图**：这由将显示给用户的数据的几种表示形式组成。

+   **控制器**：这是应用程序处理用户交互的部分。它是模型和视图之间的桥梁。

MVC 背后的理念是将视图与模型解耦。模型必须是自包含的，并且对 UI 一无所知。这基本上允许相同的数据在多个视图中重复使用。这些视图是查看数据的不同方式。深入或使用不同的渲染器（HTML，PDF）是这一原则的很好的例证。

控制器充当用户和数据之间的中介。它的作用是控制最终用户可用的操作，以及在应用程序的不同视图之间进行路由。

# MVC 的批评和最佳实践

虽然 MVC 仍然是设计 UI 的首选方法，但随着其流行，出现了许多批评。大多数批评者实际上是在指责模式的错误使用。

## 贫血领域模型

Eric Evans 的具有影响力的书籍《领域驱动设计》，也缩写为**DDD**，定义了一组架构规则，以实现更好地将业务领域整合到代码中。

其中一个核心思想是利用领域对象内的面向对象范例。违背这一原则有时被称为**贫血领域模型**。这个问题的一个很好的定义可以在 Martin Fowler 的博客上找到（[`www.martinfowler.com/bliki/AnemicDomainModel.html`](http://www.martinfowler.com/bliki/AnemicDomainModel.html)）。

贫血模型通常表现出以下症状：

+   模型由非常简单的**普通的 Java 对象**（**POJO**）组成，只有 getter 和 setter

+   所有业务逻辑都在服务层内处理

+   模型的验证在模型之外，例如在控制器中

这取决于您的业务领域的复杂性，这可能是一种不良实践。一般来说，领域驱动设计（DDD）实践需要额外的努力来将领域与应用程序逻辑隔离开来。

架构始终是一种权衡。值得注意的是，设计 Spring 应用程序的典型方式可能会导致在某个时候出现复杂的维护。

如何避免领域贫血在这里有解释：

+   服务层适用于应用级抽象，如事务处理，而不是业务逻辑。

+   您的领域应始终处于有效状态。使用验证器或 JSR-303 的验证注释将验证留在表单对象内。

+   将输入转化为有意义的领域对象。

+   将数据层视为具有领域查询的存储库（例如参考 Spring Data 规范）

+   将领域逻辑与底层持久性框架解耦

+   尽可能使用真实对象。例如，操作`FirstName`类而不是字符串。

领域驱动设计比这些简单的规则要复杂得多：实体、值类型、通用语言、有界上下文、洋葱架构和防腐层。我强烈鼓励您自行研究这些原则。就我们而言，通过本书，我们将努力记住前面列出的指导方针，因为我们打造我们的 Web 应用程序时，这些问题将变得更加熟悉。

## 从源代码中学习

如果您熟悉 Spring，您可能已经访问过 Spring 的网站[`spring.io`](http://spring.io)。它完全由 Spring 制作，好消息是它是开源的。

该项目的代号是 sagan。它有许多有趣的特性：

+   一个 gradle 多模块项目

+   安全集成

+   Github 集成

+   Elasticsearch 集成

+   一个 JavaScript 前端应用程序

与该项目相关的 GitHub 维基非常详细，将帮助您轻松开始使用该项目。

### 注意

如果您对 Spring 的真实世界应用程序架构感兴趣，请访问以下网址：

[`github.com/spring-io/sagan`](https://github.com/spring-io/sagan)

# Spring MVC 1-0-1

在 Spring MVC 中，模型是 Spring MVC 的`Model`或`ModelAndView`类中封装的简单映射。它可以来自数据库、文件、外部服务等。由您定义如何获取数据并将其放入模型。与数据层交互的推荐方式是通过 Spring Data 库：Spring Data JPA、Spring Data MongoDB 等。有数十个与 Spring Data 相关的项目，我鼓励您查看[`projects.spring.io/spring-data`](http://projects.spring.io/spring-data)。

Spring MVC 的控制器端通过使用`@Controller`注解来处理。在 Web 应用程序中，控制器的作用是响应 HTTP 请求。使用`@Controller`注解标记的类将被 Spring 捕获，并有机会处理即将到来的请求。

通过`@RequestMapping`注解，控制器声明处理特定请求，基于它们的 HTTP 方法（例如`GET`或`POST`方法）和它们的 URL。然后控制器决定是直接在 Web 响应中写入内容，还是将应用程序路由到视图并将属性注入该视图。

一个纯粹的 RESTful 应用程序将选择第一种方法，并使用`@ResponseBody`注解直接在 HTTP 响应中公开模型的 JSON 或 XML 表示。在 Web 应用程序的情况下，这种类型的架构通常与前端 JavaScript 框架（如 Backbone.js、AngularJS 或 React）相关联。在这种情况下，Spring 应用程序将仅处理 MVC 模型的模型层。我们将在第三章中学习这种类型的架构，*文件上传和错误处理*。

通过第二种方法，模型被传递到视图，由模板引擎呈现，然后写入响应。

视图通常与模板方言相关联，这将允许在模型内进行导航。用于模板的流行方言包括 JSP、FreeMarker 或 Thymeleaf。

混合方法可以利用模板引擎与应用程序的某些方面进行交互，然后将视图层委托给前端框架。

# 使用 Thymeleaf

Thymeleaf 是一个模板引擎，受到 Spring 社区的特别关注。

它的成功主要归功于其友好的语法（它几乎看起来像 HTML）和它可以轻松扩展的特性。

Spring Boot 有各种可用的扩展和集成：

| 支持 | 依赖 |
| --- | --- |
| 布局 | `nz.net.ultraq.thymeleaf:thymeleaf-layout-dialect` |
| HTML5 data-* 属性 | `com.github.mxab.thymeleaf.extras:thymeleaf-extras-data-attribute` |
| Internet Explorer 条件注释 | `org.thymeleaf.extras:thymeleaf-extras-conditionalcomments` |
| 支持 spring 安全 | `org.thymeleaf.extras:thymeleaf-extras-springsecurity3` |

Thymeleaf 与 Spring 集成的非常好的教程可以在[`www.thymeleaf.org/doc/tutorials/2.1/thymeleafspring.html`](http://www.thymeleaf.org/doc/tutorials/2.1/thymeleafspring.html)找到。

不多说了，让我们添加`spring-boot-starter-thymeleaf`依赖项来启动 thymeleaf 模板引擎：

```java
buildscript {
    ext {
        springBootVersion = '1.2.5.RELEASE'
    }
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}") 
        classpath("io.spring.gradle:dependency-management-plugin:0.5.1.RELEASE")
    }
}

apply plugin: 'java'
apply plugin: 'eclipse'
apply plugin: 'idea'
apply plugin: 'spring-boot' 
apply plugin: 'io.spring.dependency-management' 

jar {
    baseName = 'masterSpringMvc'
    version = '0.0.1-SNAPSHOT'
}
sourceCompatibility = 1.8
targetCompatibility = 1.8

repositories {
    mavenCentral()
}

dependencies {
    compile 'org.springframework.boot:spring-boot-starter-web'
    compile 'org.springframework.boot:spring-boot-starter-thymeleaf'
    testCompile 'org.springframework.boot:spring-boot-starter-test'
}

eclipse {
    classpath {
         containers.remove('org.eclipse.jdt.launching.JRE_CONTAINER')
         containers 'org.eclipse.jdt.launching.JRE_CONTAINER/org.eclipse.jdt.internal.debug.ui.launcher.StandardVMType/JavaSE-1.8'
    }
}

task wrapper(type: Wrapper) {
    gradleVersion = '2.3'
}
```

## 我们的第一个页面

现在我们将第一个页面添加到我们的应用程序中。它将位于`src/main/resources/templates`。让我们把文件命名为`resultPage.html`：

```java
<!DOCTYPE html>
<html >
<head lang="en">
    <meta charset="UTF-8"/>
    <title>Hello thymeleaf</title>
</head>
<body>
    <span th:text="|Hello thymeleaf|">Hello html</span>
</body>
</html>
```

我们从一开始就可以看到 Thymeleaf 与 html 完美地集成在一起，它的语法几乎感觉自然。

`th:text`的值放在管道符号之间。这意味着文本中的所有值将被连接起来。

起初可能有点尴尬，但实际上，在我们的页面中很少会硬编码文本；因此，Thymeleaf 在这里做出了一个有见地的设计决定。

Thymeleaf 对于网页设计师有一个很大的优势：模板中的所有动态内容都可以在没有运行服务器的情况下回退到默认值。资源 URL 可以相对指定，每个标记都可以包含占位符。在我们之前的例子中，当视图在我们的应用程序的上下文中呈现时，文本"Hello html"将不会被显示，但如果文件直接在 Web 浏览器中打开，它将会被显示。

为了加快开发速度，将这个属性添加到你的`application.properties`文件中：

```java
spring.thymeleaf.cache=false
```

这将禁用视图缓存，并导致模板在每次访问时重新加载。

当然，当我们进入生产阶段时，这个设置将需要被禁用。我们将在第七章中看到这一点，*优化您的请求*。

### 提示

**重新加载视图**

禁用缓存后，只需在 eclipse 中保存你的视图，或者在 IntelliJ 中使用`Build > Make Project`操作来在更改后刷新视图。

最后，我们需要修改我们的`HelloController`类。现在，它不再显示纯文本，而是必须路由到我们新创建的视图。为了实现这一点，我们将删除`@ResponseBody`注解。这样做并且仍然返回一个字符串将告诉 Spring MVC 将这个字符串映射到一个视图名称，而不是直接在响应中显示特定的模型。

我们的控制器现在看起来像这样：

```java
@Controller
public class HelloController {

    @RequestMapping("/")
    public String hello() {
        return "resultPage";
    }
}
```

在这个例子中，控制器将重定向用户到视图名称`resultPage`。`ViewResolver`接口将把这个名称与我们的页面关联起来。

让我们再次启动我们的应用程序，然后转到`http://localhost:8080`。

你将看到以下页面：

![我们的第一个页面](img/image00929.jpeg)

# Spring MVC 架构

让我们从这个令人惊叹的新的"Hello World"中退一步，试着理解我们的 Web 应用程序内部发生了什么。为了做到这一点，我们将追溯浏览器发送的 HTTP 请求的旅程，以及它从服务器得到的响应。

## DispatcherServlet

每个 Spring Web 应用程序的入口点是`DispatcherServlet`。下图说明了 Dispatcher Servlet 的架构：

![DispatcherServlet](img/image00930.jpeg)

这是一个经典的`HttpServlet`类，它将 HTTP 请求分派给 HandlerMapping。**HandlerMapping**是资源（URL）和控制器的关联。

然后在 Controller 上调用带有`@RequestMapping`注解的适当方法。在这个方法中，控制器设置模型数据并返回视图名称给分派程序。

`DispatcherServlet`然后将询问`ViewResolver`接口以找到视图的相应实现。

在我们的情况下，`ThymeleafAutoConfiguration`类已经为我们设置了视图解析器。

您可以在`ThymeleafProperties`类中看到，我们视图的默认前缀是`classpath:/templates/`，默认后缀是`.html`。

这意味着，鉴于视图名称`resultPage`，视图解析器将在我们类路径的模板目录中查找名为`resultPage.html`的文件。

在我们的应用程序中，`ViewResolver`接口是静态的，但更高级的实现可以根据请求标头或用户的区域设置返回不同的结果。

视图最终将被呈现，并将结果写入响应。

## 将数据传递给视图

我们的第一个页面完全是静态的；它实际上并没有充分利用 Spring MVC 的强大功能。让我们稍微调整一下。如果“Hello World”字符串不是硬编码的，而是来自服务器呢？

你说这仍然是一个无聊的“hello world”？是的，但它将开启更多的可能性。让我们修改我们的`resultPage.html`文件，以显示来自模型的消息：

```java
<!DOCTYPE html>
<html >
<head lang="en">
    <meta charset="UTF-8"/>
    <title>Hello thymeleaf</title>
</head>
<body>
    <span th:text="${message}">Hello html</span>
</body>
</html>
```

然后，让我们修改我们的控制器，以便将此消息放入此模型中：

```java
@Controller
public class HelloController {

    @RequestMapping("/")
    public String hello(Model model) {
        model.addAttribute("message", "Hello from the controller");
        return "resultPage";
    }
}
```

我知道，悬念让你着急！让我们看看`http://localhost:8080`是什么样子。

![将数据传递给视图](img/image00931.jpeg)

首先要注意的是，我们向控制器的方法传递了一个新的参数，`DispatcherServlet`为我们提供了正确的对象。实际上，控制器的方法可以注入许多对象，例如`HttpRequest`或`HttpResponse`，`Locale`，`TimeZone`和`Principal`，代表经过身份验证的用户。此类对象的完整列表可在文档中找到，网址为[`docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-arguments`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html#mvc-ann-arguments)。

# Spring 表达式语言

使用`${}`语法时，实际上使用的是**Spring 表达式语言**（**SpEL**）。在野外有几种变体的 EL 可用；SpEl 是最强大的变体之一。

以下是其主要特点的概述：

| 功能 | 语法 | 解释 |
| --- | --- | --- |
| 访问列表元素 | `list[0]` |   |
| 访问映射条目 | `map[key]` |   |
| 三元运算符 | `condition ? 'yes' : 'no'` |   |
| Elvis 运算符 | `person ?: default` | 如果 person 的值为 null，则返回 default |
| 安全导航 | `person?.name` | 如果 person 或她的姓名为 null，则返回 null |
| 模板化 | `'Your name is #{person.name}'` | 将值注入到字符串中 |
| 投影 | `${persons.![name]}` | 提取所有人的姓名并将它们放入列表中 |
| 选择 | `persons.?[name == 'Bob']'` | 从列表中检索姓名为 Bob 的人 |
| 函数调用 | `person.sayHello()` |   |

### 注意

有关完整参考，请查看[`docs.spring.io/spring/docs/current/spring-framework-reference/html/expressions.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/expressions.html)的手册。

SpEl 的用法不仅限于视图。您还可以在 Spring 框架内的各个地方使用它，例如，在使用`@Value`注解将属性注入到 bean 中时。

## 使用请求参数获取数据

我们能够在视图中显示来自服务器的数据。但是，如果我们想要从用户那里获取输入怎么办？使用 HTTP 协议，有多种方法可以做到这一点。最简单的方法是将查询参数传递给我们的 URL。

### 注意

**查询参数**

您肯定知道查询参数。它们在 URL 中的`?`字符之后找到。它们由名称和值的列表组成，由&符号（和号）分隔，例如，`page?var1=value1&var2=value2`。

我们可以利用这种技术来询问用户的姓名。让我们再次修改我们的`HelloController`类：

```java
@Controller
public class HelloController {

    @RequestMapping("/")
    public String hello(@RequestParam("name") String userName, Model model) {
        model.addAttribute("message", "Hello, " + userName);
        return "resultPage";
    }
}
```

如果我们导航到`localhost:8080/?name=Geoffroy`，我们可以看到以下内容：

![使用请求参数获取数据](img/image00932.jpeg)

默认情况下，请求参数是必需的。这意味着如果我们导航到`localhost:8080`，我们将看到错误消息。

查看`@RequestParam`代码，我们可以看到除了值参数之外，还有两个可能的属性：`required`和`defaultValue`。

因此，我们可以更改我们的代码，并为我们的参数指定默认值，或指示它不是必需的：

```java
@Controller
public class HelloController {

    @RequestMapping("/")
    public String hello(@RequestParam(defaultValue = "world") String name, Model model) {
        model.addAttribute("message", "Hello, " + name);
        return "resultPage";
    }
}
```

### 提示

在 Java 8 中，可以不指定值参数。在这种情况下，将使用带注释的方法参数的名称。

# 够了，Hello World，让我们获取推文！

好了，这本书的名字毕竟不是“精通 Hello Worlds”。使用 Spring，查询 Twitter 的 API 真的很容易。

## 注册您的应用程序

在开始之前，您必须在 Twitter 开发者控制台中注册您的应用程序。

转到[`apps.twitter.com`](https://apps.twitter.com)并创建一个新应用程序。

随便给它起个名字。在网站和回调 URL 部分，只需输入`http://127.0.0.1:8080`。这将允许您在本地开发环境中测试应用程序。

![注册您的应用程序](img/image00933.jpeg)

现在，转到密钥，访问令牌，并复制**Consumer Key**和**Consumer Secret**。我们马上会用到这个。看一下下面的屏幕截图：

![注册您的应用程序](img/image00934.jpeg)

默认情况下，我们的应用程序具有只读权限。这对我们的应用程序足够了，但如果您愿意，可以进行调整。

## 设置 Spring Social Twitter

我们将在我们的`build.gradle`文件中添加以下依赖项：

```java
compile 'org.springframework.boot:spring-boot-starter-social-twitter'
```

### 注意

**Spring Social**是一组项目，提供对各种社交网络的公共 API 的访问。Spring Boot 默认提供与 Twitter、Facebook 和 LinkedIn 的集成。Spring Social 总共包括约 30 个项目，可以在[`projects.spring.io/spring-social/`](http://projects.spring.io/spring-social/)找到。

将以下两行添加到`application.properties`中：

```java
spring.social.twitter.appId= <Consumer Key>
spring.social.twitter.appSecret= <Consumer Secret>
```

这些是与我们刚创建的应用程序相关联的密钥。

您将在第五章中了解有关 OAuth 的更多信息，*保护您的应用程序*。目前，我们将只使用这些凭据代表我们的应用程序向 Twitter 的 API 发出请求。

## 访问 Twitter

现在我们可以在我们的控制器中使用 Twitter。让我们将其名称更改为`TweetController`，以便更好地反映其新的责任：

```java
@Controller
public class HelloController {

    @Autowired
    private Twitter twitter;

    @RequestMapping("/")
    public String hello(@RequestParam(defaultValue = "masterSpringMVC4") String search, Model model) {
        SearchResults searchResults = twitter.searchOperations().search(search);
        String text = searchResults.getTweets().get(0).getText();
        model.addAttribute("message", text);
        return "resultPage";
    }
}
```

如您所见，该代码搜索与请求参数匹配的推文。如果一切顺利，您将在屏幕上看到第一条推文的文本被显示出来：

![访问 Twitter](img/image00935.jpeg)

当然，如果搜索没有结果，我们笨拙的代码将会出现`ArrayOutOfBoundException`错误。所以，不要犹豫，发推文来解决问题！

如果我们想要显示一系列推文怎么办？让我们修改`resultPage.html`文件：

```java
<!DOCTYPE html>
<html >
<head lang="en">
    <meta charset="UTF-8"/>
    <title>Hello twitter</title>
</head>
<body>
    <ul>
 <li th:each="tweet : ${tweets}" th:text="${tweet}">Some tweet</li>
 </ul>
</body>
</html>
```

### 注意

`th:each`是 Thymeleaf 中定义的一个标签，允许它遍历集合并将每个值分配给循环内的变量。

我们还需要更改我们的控制器：

```java
@Controller
public class TweetController {

    @Autowired
    private Twitter twitter;

    @RequestMapping("/")
    public String hello(@RequestParam(defaultValue = "masterSpringMVC4") String search, Model model) {
        SearchResults searchResults = twitter.searchOperations().search(search);
        List<String> tweets =
 searchResults.getTweets()
 .stream()
 .map(Tweet::getText)
 .collect(Collectors.toList());
 model.addAttribute("tweets", tweets);
        return "resultPage";
    }
}
```

请注意，我们正在使用 Java 8 流来仅收集推文中的消息。`Tweet`类包含许多其他属性，例如发送者、转发计数等。但是，目前我们将保持简单，如下面的屏幕截图所示：

![访问 Twitter](img/image00936.jpeg)

# Java 8 流和 lambda

你可能还不熟悉 lambda。在 Java 8 中，每个集合都有一个默认方法`stream()`，它可以访问函数式操作。

这些操作可以是返回流的中间操作，从而允许链接，也可以是返回值的终端操作。

最著名的中间操作如下：

+   `map`：这将对列表中的每个元素应用一个方法，并返回结果列表

+   `filter`：这返回与谓词匹配的每个元素的列表

+   `reduce`：这使用操作和累加器将列表投影到单个值

Lambda 是函数表达式的简写语法。它们可以被强制转换为 Single Abstract Method，即只有一个函数的接口。

例如，您可以按照以下方式实现`Comparator`接口：

```java
Comparator<Integer> c = (e1, e2) -> e1 - e2;
```

在 lambda 中，return 关键字隐式地是其最后的表达式。

我们之前使用的双冒号运算符是获取类上函数引用的快捷方式，

```java
Tweet::getText
```

上述等同于以下内容：

```java
(Tweet t) -> t.getText()
```

`collect`方法允许我们调用终端操作。`Collectors`类是一组终端操作，它将结果放入列表、集合或映射中，允许分组、连接等。

调用`collect(Collectors.toList())`方法将产生一个包含流中每个元素的列表；在我们的例子中，是推文名称。

# 使用 WebJars 的 Material 设计

我们的应用程序已经很棒了，但在美学方面确实还有些不足。您可能听说过 Material 设计。这是谷歌对扁平设计的看法。

我们将使用 Materialize ([`materializecss.com`](http://materializecss.com))，一个外观极佳的响应式 CSS 和 JavaScript 库，就像 Bootstrap 一样。

![使用 WebJars 的 Material 设计](img/image00937.jpeg)

我们现在将使用 WebJars。将 jQuery 和 Materialize CSS 添加到我们的依赖项中：

```java
compile 'org.webjars:materializecss:0.96.0'
compile 'org.webjars:jquery:2.1.4'
```

WebJar 的组织方式是完全标准化的。您将在`/webjars/{lib}/{version}/*.js`中找到任何库的 JS 和 CSS 文件。

例如，要将 jQuery 添加到我们的页面，可以在网页中添加以下内容：

```java
<script src="img/jquery.js"></script>
```

让我们修改我们的控制器，以便它给我们一个所有推文对象的列表，而不是简单的文本：

```java
package masterSpringMvc.controller;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.twitter.api.SearchResults;
import org.springframework.social.twitter.api.Tweet;
import org.springframework.social.twitter.api.Twitter;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestParam;

import java.util.List;

@Controller
public class TweetController {

    @Autowired
    private Twitter twitter;

    @RequestMapping("/")
    public String hello(@RequestParam(defaultValue = "masterSpringMVC4") String search, Model model) {
        SearchResults searchResults = twitter.searchOperations().search(search);
        List<Tweet> tweets = searchResults.getTweets();
        model.addAttribute("tweets", tweets);
        model.addAttribute("search", search);
        return "resultPage";
    }
}
```

让我们在视图中包含 materialize CSS：

```java
<!DOCTYPE html>
<html >
<head lang="en">
    <meta charset="UTF-8"/>
    <title>Hello twitter</title>

    <link href="/webjars/materializecss/0.96.0/css/materialize.css" type="text/css" rel="stylesheet" media="screen,projection"/>
</head>
<body>
<div class="row">

    <h2 class="indigo-text center" th:text="|Tweet results for ${search}|">Tweets</h2>

    <ul class="collection">
        <li class="collection-item avatar" th:each="tweet : ${tweets}">
            <img th:src="img/${tweet.user.profileImageUrl}" alt="" class="circle"/>
            <span class="title" th:text="${tweet.user.name}">Username</span>
            <p th:text="${tweet.text}">Tweet message</p>
        </li>
    </ul>

</div>

<script src="img/jquery.js"></script>
<script src="img/materialize.js"></script>
</body>
</html>
```

结果看起来已经好多了！

![使用 WebJars 的 Material 设计](img/image00938.jpeg)

## 使用布局

我们想要做的最后一件事是将我们的 UI 的可重用部分放入模板中。为此，我们将使用`thymeleaf-layout-dialect`依赖项，该依赖项包含在我们项目的`spring-boot-starter-thymeleaf`依赖项中。

我们将在`src/main/resources/templates/layout`中创建一个名为`default.html`的新文件。它将包含我们将从页面到页面重复的代码：

```java
<!DOCTYPE html>
<html 
      >
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, user-scalable=no"/>
    <title>Default title</title>

    <link href="/webjars/materializecss/0.96.0/css/materialize.css" type="text/css" rel="stylesheet" media="screen,projection"/>
</head>
<body>

<section layout:fragment="content">
    <p>Page content goes here</p>
</section>

<script src="img/jquery.js"></script>
<script src="img/materialize.js"></script>
</body>
</html>
```

我们现在将修改`resultPage.html`文件，使其使用布局，这将简化其内容：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Hello twitter</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center" th:text="|Tweet results for ${search}|">Tweets</h2>

    <ul class="collection">
        <li class="collection-item avatar" th:each="tweet : ${tweets}">
            <img th:src="img/${tweet.user.profileImageUrl}" alt="" class="circle"/>
            <span class="title" th:text="${tweet.user.name}">Username</span>

            <p th:text="${tweet.text}">Tweet message</p>
        </li>
    </ul>
</div>
</body>
</html>
```

`layout:decorator="layout/default"`将指示我们的布局的位置。然后我们可以将内容注入到布局的不同`layout:fragment`部分中。请注意，每个模板都是有效的 HTML 文件。您也可以非常容易地覆盖标题。

## 导航

我们有一个很好的推文显示应用程序，但是我们的用户应该如何找出他们需要提供一个“搜索”请求参数呢？

如果我们为我们的应用程序添加一个小表单会很好。

让我们做一些类似这样的事情：

![导航](img/image00939.jpeg)

首先，我们需要修改我们的`TweetController`，以在我们的应用程序中添加第二个视图。搜索页面将直接在我们的应用程序的根目录下可用，当在`search`字段中按下回车时，结果页面将可用：

```java
@Controller
public class TweetController {

    @Autowired
    private Twitter twitter;

    @RequestMapping("/")
    public String home() {
        return "searchPage";
    }

    @RequestMapping("/result")
    public String hello(@RequestParam(defaultValue = "masterSpringMVC4") String search, Model model) {
        SearchResults searchResults = twitter.searchOperations().search(search);
        List<Tweet> tweets = searchResults.getTweets();
        model.addAttribute("tweets", tweets);
        model.addAttribute("search", search);
        return "resultPage";
    }
}
```

我们将在`templates`文件夹中添加另一个页面，名为`searchPage.html`文件。它将包含一个简单的表单，通过`get`方法将搜索词传递到结果页面：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Search</title>
</head>
<body>

<div class="row" layout:fragment="content">

    <h4 class="indigo-text center">Please enter a search term</h4>

    <form action="/result" method="get" class="col s12">
        <div class="row center">
            <div class="input-field col s6 offset-s3">
                <i class="mdi-action-search prefix"></i>
                <input id="search" name="search" type="text" class="validate"/>
                <label for="search">Search</label>
            </div>
        </div>
    </form>
</div>

</body>
</html>
```

这是非常简单的 HTML，它完美地工作。您现在可以尝试一下。

如果我们想要禁止某些搜索结果怎么办？假设我们想要在用户输入`struts`时显示错误消息。

实现这一点的最佳方法是修改表单以发布数据。在控制器中，我们可以拦截所发布的内容，并相应地实现这个业务规则。

首先，我们需要更改`searchPage`中的表单，如下所示：

```java
<form action="/result" method="get" class="col s12">
```

现在，我们将表单更改为：

```java
<form action="/postSearch" method="post" class="col s12">
```

我们还需要在服务器上处理这个发布。将这个方法添加到`TweetController`中：

```java
@RequestMapping(value = "/postSearch", method = RequestMethod.POST)
public String postSearch(HttpServletRequest request,
    RedirectAttributes redirectAttributes) {
        String search = request.getParameter("search");
        redirectAttributes.addAttribute("search", search);
        return "redirect:result";
}
```

这里有几个新奇之处：

+   在请求映射注解中，我们指定了要处理的 HTTP 方法，即`POST`。

+   我们直接将两个属性作为方法参数注入。它们是请求和`RedirectAttributes`。

+   我们检索请求上发布的值，并将其传递给下一个视图。

+   我们不再返回视图的名称，而是重定向到一个 URL。

`RedirectAttributes`是一个 Spring 模型，将专门用于在重定向场景中传播值。

### 注意

**重定向/转发**是 Java Web 应用程序上下文中的经典选项。它们都会改变用户浏览器上显示的视图。不同之处在于`Redirect`将发送一个触发浏览器内导航的 302 标头，而`Forward`不会导致 URL 更改。在 Spring MVC 中，您可以通过简单地在方法返回字符串前加上`redirect:`或`forward:`来使用任一选项。在这两种情况下，您返回的字符串不会像我们之前看到的那样解析为视图，而是会触发导航到特定的 URL。

前面的例子有点牵强，我们将在下一章中看到更智能的表单处理。如果您在`postSearch`方法中设置断点，您将看到它将在我们的表单发布后立即被调用。

那么错误消息呢？

让我们修改`postSearch`方法：

```java
@RequestMapping(value = "/postSearch", method = RequestMethod.POST)
public String postSearch(HttpServletRequest request,
    RedirectAttributes redirectAttributes) {
        String search = request.getParameter("search");
        if (search.toLowerCase().contains("struts")) {
                redirectAttributes.addFlashAttribute("error", "Try using spring instead!");
                return "redirect:/";
        }
        redirectAttributes.addAttribute("search", search);
        return "redirect:result";
}
```

如果用户的搜索词包含"struts"，我们将重定向他们到`searchPage`并使用 flash 属性添加一条小错误消息。

这些特殊类型的属性仅在请求的时间内存在，并且在刷新页面时会消失。当我们使用`POST-REDIRECT-GET`模式时，这是非常有用的，就像我们刚才做的那样。

我们需要在`searchPage`结果中显示这条消息：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Search</title>
</head>
<body>

<div class="row" layout:fragment="content">

    <h4 class="indigo-text center">Please enter a search term</h4>

 <div class="col s6 offset-s3">
 <div id="errorMessage" class="card-panel red lighten-2" th:if="${error}">
 <span class="card-title" th:text="${error}"></span>
 </div>

        <form action="/postSearch" method="post" class="col s12">
            <div class="row center">
                <div class="input-field">
                    <i class="mdi-action-search prefix"></i>
                    <input id="search" name="search" type="text" class="validate"/>
                    <label for="search">Search</label>
                </div>
            </div>
        </form>
    </div>
</div>

</body>
</html>
```

现在，如果用户尝试搜索"struts2"的推文，他们将得到一个有用且合适的答案：

![导航](img/image00940.jpeg)

# 检查点

在本章结束时，您应该有一个控制器，`TweetController`，处理搜索和未经修改的生成配置类`MasterSpringMvcApplication`，在`src/main/java`目录中：

![检查点](img/image00941.jpeg)

在`src/main/resources`目录中，您应该有一个默认布局和两个使用它的页面。

在`application.properties`文件中，我们添加了 Twitter 应用程序凭据，以及一个属性告诉 Spring 不要缓存模板以便开发：

![检查点](img/image00942.jpeg)

# 摘要

在本章中，您了解了构建良好的 MVC 架构需要什么。我们看到了 Spring MVC 的一些内部工作原理，并且使用了 Spring Social Twitter，几乎没有配置。现在，我们可以设计一个美丽的 Web 应用程序，这要归功于 WebJars。

在下一章中，我们将要求用户填写他们的个人资料，以便我们可以自动获取他们可能喜欢的推文。这将让您有机会了解更多关于表单、格式化、验证和国际化的知识。

# 第二章。处理表单和复杂的 URL 映射

我们的应用程序，尽管看起来很漂亮，但会受益于更多关于我们用户的信息。

我们可以要求他们提供他们感兴趣的主题。

在本章中，我们将构建一个个人资料页面。它将具有服务器端和客户端验证以及用于个人资料图片上传的文件上传。我们将保存该信息在用户会话中，并通过将应用程序翻译成多种语言来确保我们的受众尽可能广泛。最后，我们将显示与用户口味匹配的 Twitter 活动摘要。

听起来不错吧？让我们开始吧，我们有一些工作要做。

# 个人资料页面 - 一个表单

表单是每个 Web 应用程序的基石。自互联网诞生以来，它们一直是获取用户输入的主要方式！

我们在这里的第一个任务是创建一个像这样的个人资料页面：

![个人资料页面 - 一个表单](img/image00943.jpeg)

它将允许用户输入一些个人信息以及一系列口味。然后，这些口味将被提供给我们的搜索引擎。

让我们在`templates/profile/profilePage.html`中创建一个新页面：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Your profile</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center">Personal info</h2>

    <form th:action="@{/profile}" method="post" class="col m8 s12 offset-m2">

        <div class="row">
            <div class="input-field col s6">
                <input id="twitterHandle" type="text"/>
                <label for="twitterHandle">Last Name</label>
            </div>
            <div class="input-field col s6">
                <input id="email" type="text"/>
                <label for="email">Email</label>
            </div>
        </div>
        <div class="row">
            <div class="input-field col s6">
                <input id="birthDate" type="text"/>
                <label for="birthDate">Birth Date</label>
            </div>
        </div>
        <div class="row s12">
            <button class="btn waves-effect waves-light" type="submit" name="save">Submit
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
</body>
</html>
```

请注意`@{}`语法，它将通过将服务器上下文路径（在我们的情况下为`localhost:8080`）前置到其参数来构造资源的完整路径。

我们还将在`profile`包中创建名为`ProfileController`的相关控制器：

```java
package masterspringmvc4.profile;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

@Controller
public class ProfileController {

    @RequestMapping("/profile")
    public String displayProfile() {
        return "profile/profilePage";
    }
}
```

现在，您可以转到`http://localhost:8080`，看到一个漂亮的表单，什么也不做。这是因为我们没有将任何操作映射到 post URL。

让我们在与我们的控制器相同的包中创建一个**数据传输对象**（**DTO**）。我们将其命名为`ProfileForm`。它的作用将是映射我们的 Web 表单字段并描述验证规则：

```java
package masterSpringMvc.profile;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

public class ProfileForm {
    private String twitterHandle;
    private String email;
    private LocalDate birthDate;
    private List<String> tastes = new ArrayList<>();

    // getters and setters
}
```

这是一个常规的**普通旧 Java 对象**（**POJO**）。不要忘记生成 getter 和 setter，否则我们的数据绑定将无法正常工作。请注意，我们有一个口味列表，我们现在不会填充，稍后再填充。

由于我们使用的是 Java 8，我们的用户的出生日期将使用新的 Java 日期时间 API（JSR 310）。这个 API 比旧的`java.util.Date` API 要好得多，因为它在人类日期的所有细微差别之间做出了明确的区分，并使用了流畅的 API 和不可变的数据结构。

在我们的示例中，`LocalDate`类是一个简单的没有与之关联的时间的日期。它可以与`LocalTime`类区分开，后者表示一天内的时间，`LocalDateTime`类表示两者，或者`ZonedDateTime`类使用时区。

### 注意

如果您想了解更多关于 Java 8 日期时间 API 的信息，请参考 Oracle 教程，网址为[`docs.oracle.com/javase/tutorial/datetime/TOC.html`](https://docs.oracle.com/javase/tutorial/datetime/TOC.html)。

### 提示

一个好的建议是始终生成我们的数据对象的`toString`方法，就像这个表单一样。这对于调试非常有用。

为了指示 Spring 将我们的字段绑定到此 DTO，我们必须在`profilePage`中添加一些元数据：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Your profile</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center">Personal info</h2>

    <form th:action="@{/profile}" th:object="${profileForm}" method="post" class="col m8 s12 offset-m2">

        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.twitterHandle}" id="twitterHandle" type="text"/>
                <label for="twitterHandle">Last Name</label>
            </div>
            <div class="input-field col s6">
                <input th:field="${profileForm.email}" id="email" type="text"/>
                <label for="email">Email</label>
            </div>
        </div>
        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.birthDate}" id="birthDate" type="text"/>
                <label for="birthDate">Birth Date</label>
            </div>
        </div>
        <div class="row s12">
            <button class="btn waves-effect waves-light" type="submit" name="save">Submit
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
</body>
</html>
```

您会注意到两件事：

+   表单中的`th:object`属性

+   所有字段中的`th:field`属性

第一个将通过其类型将对象绑定到控制器。第二个将将实际字段绑定到我们的表单 bean 属性。

为了使`th:object`字段起作用，我们需要在我们的请求映射方法中添加一个`ProfileForm`类型的参数：

```java
@Controller
public class ProfileController {

    @RequestMapping("/profile")
    public String displayProfile(ProfileForm profileForm) {
        return "profile/profilePage";
    }

    @RequestMapping(value = "/profile", method = RequestMethod.POST)
    public String saveProfile(ProfileForm profileForm) {
        System.out.println("save ok" + profileForm);
        return "redirect:/profile";
    }
}
```

我们还添加了一个`POST`方法的映射，当表单提交时将被调用。此时，如果您尝试使用日期（例如 1980 年 10 月 10 日）提交表单，它将完全不起作用，并且会给您一个 400 错误和没有有用的日志信息。

### 提示

**Spring Boot 中的日志记录**

使用 Spring Boot，日志配置非常简单。只需在`application.properties`文件中添加`logging.level.{package} = DEBUG`，其中`{package}`是应用程序中一个类或包的完全限定名称。当然，您可以将 debug 替换为任何您想要的日志级别。您还可以添加经典的日志配置。有关更多信息，请参阅[`docs.spring.io/spring-boot/docs/current/reference/html/howto-logging.html`](http://docs.spring.io/spring-boot/docs/current/reference/html/howto-logging.html)。

我们需要稍微调试我们的应用程序以了解发生了什么。将此行添加到您的文件`application.properties`中：

```java
logging.level.org.springframework.web=DEBUG
```

`org.springframework.web`包是 Spring MVC 的基本包。这将允许我们查看 Spring web 生成的调试信息。如果您再次提交表单，您将在日志中看到以下错误：

```java
Field error in object 'profileForm' on field 'birthDate': rejected value [10/10/1980]; codes [typeMismatch.profileForm.birthDate,typeMismatch.birthDate,typeMismatch.java.time.LocalDate,typeMismatch]; … nested exception is org.springframework.core.convert.ConversionFailedException: Failed to convert from type java.lang.String to type java.time.LocalDate for value '10/10/1980'; nested exception is java.time.format.DateTimeParseException: Text '10/10/1980' could not be parsed, unparsed text found at index 8]
```

为了了解发生了什么，我们需要查看 Spring 的`DateTimeFormatterRegistrar`类。

在这个类中，您将看到半打 JSR 310 的解析器和打印机。它们都将回退到短格式日期格式，如果您住在美国，则为`MM/dd/yy`，否则为`dd/MM/yy`。

这将指示 Spring Boot 在我们的应用程序启动时创建一个`DateFormatter`类。

在我们的情况下，我们需要做同样的事情，并创建我们自己的格式化程序，因为用两位数写年份有点奇怪。

Spring 中的`Formatter`是一个可以同时`print`和`parse`对象的类。它将用于解码和打印值从和到字符串。

我们将在`date`包中创建一个非常简单的格式化程序，名为`USLocalDateFormatter`：

```java
public class USLocalDateFormatter implements Formatter<LocalDate> {
    public static final String US_PATTERN = "MM/dd/yyyy";
    public static final String NORMAL_PATTERN = "dd/MM/yyyy";

    @Override public LocalDate parse(String text, Locale locale) throws ParseException {
        return LocalDate.parse(text, DateTimeFormatter.ofPattern(getPattern(locale)));
    }

    @Override public String print(LocalDate object, Locale locale) {
        return DateTimeFormatter.ofPattern(getPattern(locale)).format(object);
    }

    public static String getPattern(Locale locale) {
        return isUnitedStates(locale) ? US_PATTERN : NORMAL_PATTERN;
    }

    private static boolean isUnitedStates(Locale locale) {
        return Locale.US.getCountry().equals(locale.getCountry());
    }
}
```

这个小类将允许我们以更常见的格式（年份为四位数）解析日期，根据用户的语言环境。

让我们在`config`包中创建一个名为`WebConfiguration`的新类：

```java
package masterSpringMvc.config;

import masterSpringMvc.dates.USLocalDateFormatter;
import org.springframework.context.annotation.Configuration;
import org.springframework.format.FormatterRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurerAdapter;

import java.time.LocalDate;

@Configuration
public class WebConfiguration extends WebMvcConfigurerAdapter {

    @Override public void addFormatters(FormatterRegistry registry) {
        registry.addFormatterForFieldType(LocalDate.class, new USLocalDateFormatter());
    }
}
```

这个类扩展了`WebMvcConfigurerAdapter`，这是一个非常方便的类，可以自定义 Spring MVC 配置。它提供了许多常见的扩展点，您可以通过覆盖方法来访问，比如`addFormatters()`方法。

这一次，提交我们的表单不会导致任何错误，除非您没有使用正确的日期格式输入日期。

目前，用户无法看到他们应该输入出生日期的格式，所以让我们将这些信息添加到表单中。

在`ProfileController`中，让我们添加一个`dateFormat`属性：

```java
@ModelAttribute("dateFormat")
public String localeFormat(Locale locale) {
    return USLocalDateFormatter.getPattern(locale);
}
```

`@ModelAttribute`注释将允许我们将属性暴露给网页，就像我们在上一章中看到的`model.addAttribute()`方法一样。

现在，我们可以通过为我们的日期字段添加占位符来在我们的页面中使用这些信息：

```java
<div class="row">
    <div class="input-field col s6">
        <input th:field="${profileForm.birthDate}" id="birthDate" type="text" th:placeholder="${dateFormat}"/>
        <label for="birthDate">Birth Date</label>
    </div>
</div>
```

这些信息现在将显示给用户：

![个人资料页面-表单](img/image00944.jpeg)

# 验证

我们不希望用户输入无效或空信息，这就是为什么我们需要向我们的`ProfileForm`添加一些验证逻辑。

```java
package masterspringmvc4.profile;

import org.hibernate.validator.constraints.Email;
import org.hibernate.validator.constraints.NotEmpty;

import javax.validation.constraints.NotNull;
import javax.validation.constraints.Past;
import javax.validation.constraints.Size;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;

public class ProfileForm {
    @Size(min = 2)
    private String twitterHandle;

    @Email
    @NotEmpty
    private String email;

   @NotNull
    private Date birthDate;

    @NotEmpty
    private List<String> tastes = new ArrayList<>();
}
```

如您所见，我们添加了一些验证约束。这些注释来自 JSR-303 规范，该规范指定了 bean 验证。这个规范最流行的实现是`hibernate-validator`，它包含在 Spring Boot 中。

您可以看到，我们使用来自`javax.validation.constraints`包（在 API 中定义）的注释和一些来自`org.hibernate.validator.constraints`包（附加约束）的注释。两者都有效，我鼓励您查看这些包中在`validation-api`和`hibernate-validator`中可用的内容。

您还可以在[`docs.jboss.org/hibernate/stable/validator/reference/en-US/html_single/#section-builtin-constraints`](http://docs.jboss.org/hibernate/stable/validator/reference/en-US/html_single/#section-builtin-constraints)的文档中查看 hibernate 验证器中可用的约束。

我们需要添加一些其他内容才能使验证工作。首先，控制器需要声明它希望在表单提交时获得一个有效的模型。通过向表示表单的参数添加`javax.validation.Valid`注释来实现这一点：

```java
@RequestMapping(value = "/profile", method = RequestMethod.POST)
public String saveProfile(@Valid ProfileForm profileForm, BindingResult bindingResult) {
    if (bindingResult.hasErrors()) {
        return "profile/profilePage";
    }

    System.out.println("save ok" + profileForm);
    return "redirect:/profile";
}
```

请注意，如果表单包含任何错误，我们不会重定向用户。这将允许我们在同一网页上显示它们。

说到这一点，我们需要在网页上添加一个地方来显示这些错误。

在`profilePage.html`的表单标签的开头添加以下行：

```java
<ul th:if="${#fields.hasErrors('*')}" class="errorlist">
    <li th:each="err : ${#fields.errors('*')}" th:text="${err}">Input is incorrect</li>
</ul>
```

这将遍历表单中发现的每个错误，并在列表中显示它们。如果您尝试提交空表单，您将看到一堆错误：

![验证](img/image00945.jpeg)

请注意，对于口味的`@NotEmpty`检查将阻止表单被提交。事实上，我们还没有提供一种方法来提供它们。

## 自定义验证消息

这些错误消息对我们的用户来说还不是很有用。我们需要做的第一件事是将它们正确地与它们各自的字段关联起来。让我们修改`profilePage.html`：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Your Profile</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center">Personal info</h2>

    <form th:action="@{/profile}" th:object="${profileForm}" method="post" class="col m8 s12 offset-m2">

        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.twitterHandle}" id="twitterHandle" type="text" th:errorclass="invalid"/>
                <label for="twitterHandle">Twitter handle</label>

                <div th:errors="*{twitterHandle}" class="red-text">Error</div>
            </div>
            <div class="input-field col s6">
                <input th:field="${profileForm.email}" id="email" type="text" th:errorclass="invalid"/>
                <label for="email">Email</label>

                <div th:errors="*{email}" class="red-text">Error</div>
            </div>
        </div>
        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.birthDate}" id="birthDate" type="text" th:errorclass="invalid" th:placeholder="${dateFormat}"/>
                <label for="birthDate">Birth Date</label>

                <div th:errors="*{birthDate}" class="red-text">Error</div>
            </div>
        </div>
        <div class="row s12">
            <button class="btn indigo waves-effect waves-light" type="submit" name="save">Submit
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
</body>
</html>
```

您会注意到我们在表单中的每个字段下面添加了一个`th:errors`标签。我们还为每个字段添加了一个`th:errorclass`标签。如果字段包含错误，则相关的 css 类将添加到 DOM 中。

验证看起来已经好多了：

自定义验证消息

我们需要做的下一件事是自定义错误消息，以更好地反映我们应用程序的业务规则。

记住，Spring Boot 会为我们创建一个消息源 bean？这个消息源的默认位置在`src/main/resources/messages.properties`中。

让我们创建这样一个包，并添加以下文本：

```java
Size.profileForm.twitterHandle=Please type in your twitter user name
Email.profileForm.email=Please specify a valid email address
NotEmpty.profileForm.email=Please specify your email address
PastLocalDate.profileForm.birthDate=Please specify a real birth date
NotNull.profileForm.birthDate=Please specify your birth date

typeMismatch.birthDate = Invalid birth date format.
```

### 提示

在开发中，将消息源配置为始终重新加载我们的包可能非常方便。在`application.properties`中添加以下属性：

`spring.messages.cache-seconds=0`

0 表示始终重新加载，而-1 表示永不重新加载。

在 Spring 中负责解析错误消息的类是`DefaultMessageCodesResolver`。在字段验证的情况下，该类尝试按照给定的顺序解析以下消息：

+   代码+“。”+对象名称+“。”+字段

+   代码+“。”+字段

+   代码+“。”+字段类型

+   代码

在前面的规则中，代码部分可以是两种情况：注释类型，如`Size`或`Email`，或异常代码，如`typeMismatch`。还记得我们因日期格式不正确而引发异常吗？相关的错误代码确实是`typeMismatch`。

在前面的消息中，我们选择了非常具体的方式。一个好的做法是定义默认消息如下：

```java
Size=the {0} field must be between {2} and {1} characters long
typeMismatch.java.util.Date = Invalid date format.
```

注意占位符；每个验证错误都有与之关联的一些参数。

声明错误消息的最后一种方式将涉及直接在验证注释中定义错误消息，如下所示：

```java
@Size(min = 2, message = "Please specify a valid twitter handle")
private String twitterHandle;
```

然而，这种方法的缺点是它与国际化不兼容。

## 自定义验证的自定义注释

对于 Java 日期，有一个名为`@Past`的注释，它确保日期是过去的日期。

我们不希望我们的用户假装他们来自未来，所以我们需要验证出生日期。为此，我们将在`date`包中定义我们自己的注释：

```java
package masterSpringMvc.date;

import javax.validation.Constraint;
import javax.validation.ConstraintValidator;
import javax.validation.ConstraintValidatorContext;
import javax.validation.Payload;
import java.lang.annotation.*;
import java.time.LocalDate;

@Target({ElementType.FIELD})
@Retention(RetentionPolicy.RUNTIME)
@Constraint(validatedBy = PastLocalDate.PastValidator.class)
@Documented
public @interface PastLocalDate {
    String message() default "{javax.validation.constraints.Past.message}";

    Class<?>[] groups() default {};

    Class<? extends Payload>[] payload() default {};

    class PastValidator implements ConstraintValidator<PastLocalDate, LocalDate> {
        public void initialize(PastLocalDate past) {
        }

        public boolean isValid(LocalDate localDate, ConstraintValidatorContext context) {
            return localDate == null || localDate.isBefore(LocalDate.now());
        }
    }
}
```

简单吧？这段代码将验证我们的日期确实是过去的日期。

现在我们可以将其添加到个人资料表单中的`birthDate`字段中：

```java
@NotNull
@PastLocalDate
private LocalDate birthDate;
```

# 国际化

国际化，通常缩写为 i18n，是设计可以翻译成各种语言的应用程序的过程。

通常，这涉及将翻译放在名称后缀为目标区域设置的属性包中，例如，`messages_en.properties`，`messages_en_US.properties`和`messages_fr.properties`文件。

正确的属性包是通过首先尝试最具体的区域设置，然后回退到不太具体的区域设置来解析的。

对于美国英语，如果尝试从名为`x`的包中获取翻译，应用程序首先会查找`x_en_US.properties`文件，然后是`x_en.properties`文件，最后是`x.properties`文件。

我们要做的第一件事是将我们的错误消息翻译成法语。为此，我们将现有的`messages.properties`文件重命名为`messages_en.properties`。

我们还将创建一个名为`messages_fr.properties`的第二个包：

```java
Size.profileForm.twitterHandle=Veuillez entrer votre identifiant Twitter
Email.profileForm.email=Veuillez spécifier une adresse mail valide
NotEmpty.profileForm.email=Veuillez spécifier votre adresse mail
PastLocalDate.profileForm.birthDate=Veuillez donner votre vraie date de naissance
NotNull.profileForm.birthDate=Veuillez spécifier votre date de naissance

typeMismatch.birthDate = Date de naissance invalide.
```

默认情况下，Spring Boot 使用固定的`LocaleResolver`接口。`LocaleResolver`是一个简单的接口，有两个方法：

```java
public interface LocaleResolver {

    Locale resolveLocale(HttpServletRequest request);

    void setLocale(HttpServletRequest request, HttpServletResponse response, Locale locale);
}
```

Spring 提供了一堆这个接口的实现，比如`FixedLocaleResolver`。这个本地解析器非常简单；我们可以通过属性配置应用程序的区域设置，一旦定义就无法更改。要配置我们应用程序的区域设置，让我们在`application.properties`文件中添加以下属性：

```java
spring.mvc.locale=fr
```

这将在法语中添加我们的验证消息。

如果我们看一下 Spring MVC 中捆绑的不同`LocaleResolver`接口，我们会看到以下内容：

+   `FixedLocaleResolver`：这会固定在配置中定义的区域设置。一旦固定，就无法更改。

+   `CookieLocaleResolver`：这允许从 cookie 中检索和保存区域设置。

+   `AcceptHeaderLocaleResolver`：这使用用户浏览器发送的 HTTP 标头来查找区域设置。

+   `SessionLocaleResolver`：这在 HTTP 会话中查找并存储区域设置。

这些实现涵盖了许多用例，但在更复杂的应用程序中，可以直接实现`LocaleResolver`以允许更复杂的逻辑，例如从数据库获取区域设置并回退到浏览器区域设置。

## 更改区域设置

在我们的应用程序中，区域设置与用户相关联。我们将在会话中保存他们的个人资料。

我们将允许用户使用一个小菜单更改站点的语言。这就是为什么我们将使用`SessionLocaleResolver`。让我们再次编辑`WebConfiguration`：

```java
package masterSpringMvc.config;

import masterSpringMvc.date.USLocalDateFormatter;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.format.FormatterRegistry;
import org.springframework.web.servlet.LocaleResolver;
import org.springframework.web.servlet.config.annotation.InterceptorRegistry;
import org.springframework.web.servlet.config.annotation.WebMvcConfigurerAdapter;
import org.springframework.web.servlet.i18n.LocaleChangeInterceptor;
import org.springframework.web.servlet.i18n.SessionLocaleResolver;

import java.time.LocalDate;

@Configuration
public class WebConfiguration extends WebMvcConfigurerAdapter {

    @Override
    public void addFormatters(FormatterRegistry registry) {
        registry.addFormatterForFieldType(LocalDate.class, new USLocalDateFormatter());
    }

    @Bean
    public LocaleResolver localeResolver() {
        return new SessionLocaleResolver();
    }

    @Bean
    public LocaleChangeInterceptor localeChangeInterceptor() {
        LocaleChangeInterceptor localeChangeInterceptor = new LocaleChangeInterceptor();
        localeChangeInterceptor.setParamName("lang");
        return localeChangeInterceptor;
    }

    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        registry.addInterceptor(localeChangeInterceptor());
    }
}
```

我们声明了一个`LocaleChangeInterceptor` bean 作为 Spring MVC 拦截器。它将拦截对`Controller`的任何请求，并检查`lang`查询参数。例如，导航到`http://localhost:8080/profile?lang=fr`将导致区域设置更改。

### 提示

**Spring MVC 拦截器**可以与 Web 应用程序中的 Servlet 过滤器进行比较。拦截器允许自定义预处理，跳过处理程序的执行以及自定义后处理。过滤器更强大，例如，它们允许交换传递给链的请求和响应对象。过滤器在`web.xml`文件中配置，而拦截器在应用程序上下文中声明为 bean。

现在，我们可以通过输入正确的 URL 来更改区域设置，但最好是添加一个导航栏，允许用户更改语言。我们将修改默认布局（`templates/layout/default.html`）以添加一个下拉菜单：

```java
<!DOCTYPE html>
<html 
      >
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1.0, user-scalable=no"/>
    <title>Default title</title>

    <link href="/webjars/materializecss/0.96.0/css/materialize.css" type="text/css" rel="stylesheet" media="screen,projection"/>
</head>
<body>

<ul id="lang-dropdown" class="dropdown-content">
    <li><a href="?lang=en_US">English</a></li>
    <li><a href="?lang=fr">French</a></li>
</ul>
<nav>
    <div class="nav-wrapper indigo">
        <ul class="right">
            <li><a class="dropdown-button" href="#!" data-activates="lang-dropdown"><i class="mdi-action-language right"></i> Lang</a></li>
        </ul>
    </div>
</nav>

<section layout:fragment="content">
    <p>Page content goes here</p>
</section>

<script src="img/jquery.js"></script>
<script src="img/materialize.js"></script>
<script type="text/javascript">
    $(".dropdown-button").dropdown();
</script>
</body>
</html>
```

这将允许用户在两种支持的语言之间进行选择。

![更改区域设置](img/image00947.jpeg)

## 翻译应用程序文本

为了使我们的应用程序完全支持双语，我们需要做的最后一件事是翻译应用程序的标题和标签。为此，我们将编辑我们的网页并使用`th:text`属性，例如在`profilePage.html`中：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Your profile</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center" th:text="#{profile.title}">Personal info</h2>

    <form th:action="@{/profile}" th:object="${profileForm}" method="post" class="col m8 s12 offset-m2">

        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.twitterHandle}" id="twitterHandle" type="text" th:errorclass="invalid"/>
                <label for="twitterHandle" th:text="#{twitter.handle}">Twitter handle</label>

                <div th:errors="*{twitterHandle}" class="red-text">Error</div>
            </div>
            <div class="input-field col s6">
                <input th:field="${profileForm.email}" id="email" type="text" th:errorclass="invalid"/>
                <label for="email" th:text="#{email}">Email</label>

                <div th:errors="*{email}" class="red-text">Error</div>
            </div>
        </div>
        <div class="row">
            <div class="input-field col s6">
                <input th:field="${profileForm.birthDate}" id="birthDate" type="text" th:errorclass="invalid"/>
                <label for="birthDate" th:text="#{birthdate}" th:placeholder="${dateFormat}">Birth Date</label>

                <div th:errors="*{birthDate}" class="red-text">Error</div>
            </div>
        </div>
        <div class="row s12 center">
            <button class="btn indigo waves-effect waves-light" type="submit" name="save" th:text="#{submit}">Submit
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
</body>
</html>
```

`th:text`属性将使用表达式替换 HTML 元素的内容。在这里，我们使用`#{}`语法，表示我们要显示来自属性源（如`messages.properties`）的消息。

让我们向我们的英语包中添加相应的翻译：

```java
NotEmpty.profileForm.tastes=Please enter at least one thing
profile.title=Your profile
twitter.handle=Twitter handle
email=Email
birthdate=Birth Date
tastes.legend=What do you like?
remove=Remove
taste.placeholder=Enter a keyword
add.taste=Add taste
submit=Submit
```

现在是法语的：

```java
NotEmpty.profileForm.tastes=Veuillez saisir au moins une chose
profile.title=Votre profil
twitter.handle=Pseudo twitter
email=Email
birthdate=Date de naissance
tastes.legend=Quels sont vos goûts ?
remove=Supprimer
taste.placeholder=Entrez un mot-clé
add.taste=Ajouter un centre d'intérêt
submit=Envoyer
```

一些翻译尚未使用，但很快就会用到。Et voilà！法国市场已经准备好迎接 Twitter 搜索风暴。

## 表单中的列表

现在，我们希望用户输入一个“品味”列表，实际上是一个我们将用于搜索推文的关键字列表。

将显示一个按钮，允许用户输入新关键字并将其添加到列表中。该列表的每个项目将是可编辑的输入文本，并且可以通过删除按钮进行删除：

![表单中的列表](img/image00948.jpeg)

在表单中处理列表数据可能是一项繁琐的工作，但是使用 Spring MVC 和 Thymeleaf 相对来说比较简单，只要你理解了原则。

在`profilePage.html`文件中添加以下行，就在包含出生日期的行下方，正好在提交按钮上方：

```java
<fieldset class="row">
    <legend th:text="#{tastes.legend}">What do you like?</legend>
    <button class="btn teal" type="submit" name="addTaste" th:text="#{add.taste}">Add taste
        <i class="mdi-content-add left"></i>
    </button>

    <div th:errors="*{tastes}" class="red-text">Error</div>

    <div class="row" th:each="row,rowStat : *{tastes}">
        <div class="col s6">
            <input type="text" th:field="*{tastes[__${rowStat.index}__]}" th:placeholder="#{taste.placeholder}"/>
        </div>

        <div class="col s6">
            <button class="btn red" type="submit" name="removeTaste" th:value="${rowStat.index}" th:text="#{remove}">Remove
                <i class="mdi-action-delete right waves-effect"></i>
            </button>
        </div>
    </div>
</fieldset>
```

此片段的目的是对我们的`LoginForm`的`tastes`变量进行迭代。这可以通过`th:each`属性实现，它看起来很像 Java 中的`for…in`循环。

与我们之前看到的搜索结果循环相比，迭代存储在两个变量中而不是一个。第一个变量实际上将包含数据的每一行。`rowStat`变量将包含有关迭代当前状态的附加信息。

新代码片段中最奇怪的事情是：

```java
th:field="*{tastes[__${rowStat.index}__]}"
```

这是一个相当复杂的语法。你可以自己想出一些更简单的东西，比如：

```java
th:field="*{tastes[rowStat.index]}"
```

好吧，那行不通。`${rowStat.index}`变量代表迭代循环的当前索引，需要在表达式的其余部分之前进行评估。为了实现这一点，我们需要使用预处理。

双下划线包围的表达式将被预处理，这意味着它将在正常处理阶段之前进行处理，允许它被评估两次。

现在我们的表单上有两个新的提交按钮。它们都有一个名称。我们之前有的全局提交按钮称为`save`。两个新按钮分别称为`addTaste`和`removeTaste`。

在控制器端，这将使我们能够轻松区分来自我们表单的不同操作。让我们在`ProfileController`中添加两个新的操作：

```java
@Controller
public class ProfileController {

    @ModelAttribute("dateFormat")
    public String localeFormat(Locale locale) {
        return USLocalDateFormatter.getPattern(locale);
    }

    @RequestMapping("/profile")
    public String displayProfile(ProfileForm profileForm) {
        return "profile/profilePage";
    }

    @RequestMapping(value = "/profile", params = {"save"}, method = RequestMethod.POST)
    public String saveProfile(@Valid ProfileForm profileForm, BindingResult bindingResult) {
        if (bindingResult.hasErrors()) {
            return "profile/profilePage";
        }
        System.out.println("save ok" + profileForm);
        return "redirect:/profile";
    }

    @RequestMapping(value = "/profile", params = {"addTaste"})
    public String addRow(ProfileForm profileForm) {
        profileForm.getTastes().add(null);
        return "profile/profilePage";
    }

    @RequestMapping(value = "/profile", params = {"removeTaste"})
    public String removeRow(ProfileForm profileForm, HttpServletRequest req) {
        Integer rowId = Integer.valueOf(req.getParameter("removeTaste"));
        profileForm.getTastes().remove(rowId.intValue());
        return "profile/profilePage";
    }
}
```

我们为每个提交操作添加了一个`param`参数以加以区分。我们之前使用的那个现在绑定到`save`参数。

当我们单击按钮时，其名称将自动添加到浏览器发送的表单数据中。请注意，我们在删除按钮中指定了一个特定值：`th:value="${rowStat.index}"`。该属性将指示相关参数应具体采用哪个值。如果不存在此属性，将发送空值。这意味着当我们单击删除按钮时，将向`POST`请求添加一个`removeTaste`参数，其中包含我们想要删除的行的索引。然后我们可以在`Controller`中使用以下代码获取它：

```java
Integer rowId = Integer.valueOf(req.getParameter("removeTaste"));
```

这种方法的唯一缺点是每次单击按钮时都会发送整个表单数据，即使并不严格需要。我们的表单足够小，因此可以接受这种折衷方案。

就是这样！表单现在已经完成，可以添加一个或多个口味。

# 客户端验证

作为额外的奖励，客户端验证现在变得非常容易，因为 HTML5 表单验证规范。如果你的目标浏览器是 Internet Explorer 10 及以上版本，添加客户端验证就像指定正确的输入类型一样容易，而不仅仅是使用文本。

通过添加客户端验证，我们可以预先验证表单，并避免向服务器发送我们知道是不正确的请求。有关客户端验证规范的更多信息，请访问[`caniuse.com/#search=validation`](http://caniuse.com/#search=validation)。

我们可以修改我们的输入以启用简单的客户端验证。之前的输入，如下面的代码所示：

```java
<input th:field="${profileForm.twitterHandle}" id="twitterHandle" type="text" th:errorclass="invalid"/>
<input th:field="${profileForm.email}" id="email" type="text" th:errorclass="invalid"/>
<input th:field="${profileForm.birthDate}" id="birthDate" type="text" th:errorclass="invalid"/>
<input type="text" th:field="*{tastes[__${rowStat.index}__]}" th:placeholder="#{taste.placeholder}"/>
```

变成了：

```java
<input th:field="${profileForm.twitterHandle}" id="twitterHandle" type="text" required="required" th:errorclass="invalid"/>
<input th:field="${profileForm.email}" id="email" type="email" required="required" th:errorclass="invalid"/>
<input th:field="${profileForm.birthDate}" id="birthDate" type="text" required="required" th:errorclass="invalid"/>
<input type="text" required="required" th:field="*{tastes[__${rowStat.index}__]}" th:placeholder="#{taste.placeholder}"/>
```

通过这种方法，您的浏览器将在提交表单时检测并根据其类型验证每个属性。`required`属性强制用户输入非空值。`email`类型对相应字段强制执行基本的电子邮件验证规则。

![客户端验证](img/image00949.jpeg)

还有其他类型的验证器。请查看[`www.the-art-of-web.com/html/html5-form-validation`](http://www.the-art-of-web.com/html/html5-form-validation)。

这种方法的缺点是我们的添加口味和删除口味按钮现在会触发验证。为了解决这个问题，我们需要在默认布局的底部包含一个脚本，就在 jQuery 声明之后。

然而，最好只在个人资料页面上包含它。为了做到这一点，我们可以在`layout/default.html`页面中，在 body 标签结束之前添加一个新的片段部分：

```java
<script type="text/javascript" layout:fragment="script">
</script>
```

这将允许我们在需要时在每个页面上包含额外的脚本。

现在，我们可以在个人资料页面中添加以下脚本，就在关闭 body 标签之前：

```java
<script layout:fragment="script">
    $('button').bind('click', function(e) {
        if (e.currentTarget.name === 'save') {
            $(e.currentTarget.form).removeAttr('novalidate');
        } else {
            $(e.currentTarget.form).attr('novalidate', 'novalidate');
        }
    });
</script>
```

当表单上存在`novalidate`属性时，表单验证不会被触发。这个小脚本将动态地移除`novalidate`属性，如果表单的操作名称是`save`，如果输入的名称不同，`novalidate`属性将始终被添加。因此，验证只会被保存按钮触发。

# 检查点

在进入下一章之前，让我们检查一下是否一切就绪。

在 Java 源代码中，你应该有以下内容：

+   一个新的控制器，`ProfileController`

+   与日期相关的两个新类：日期格式化程序和验证`LocalDate`的注释

+   一个新的`WebConfiguration`文件夹来自定义 Spring MVC 的配置

![检查点](img/image00950.jpeg)

在资源中，你应该有一个新的模板在 profile 目录下和两个新的包：

![检查点](img/image00951.jpeg)

# 摘要

在本章中，您学会了如何制作一个完整的表单。我们使用 Java 8 日期创建了一个模型，并学会了如何格式化来自用户的信息并相应地显示它。

我们确保表单填写了有效的信息，包括我们自己的验证器注解。此外，我们通过包括一些客户端验证非常容易地阻止明显不正确的信息甚至触及服务器。

最后，我们甚至将整个应用程序翻译成了英语和法语，包括日期格式！

在下一章中，我们将建立一个空间，用户将能够上传他们的图片，并了解更多关于 Spring MVC 应用程序中的错误处理。

# 第三章。文件上传和错误处理

在本章中，我们将使用户能够上传个人资料图片。我们还将看到如何在 Spring MVC 中处理错误。

# 上传文件

我们现在将使用户能够上传个人资料图片。这将在以后的个人资料页面上可用，但现在，我们将简化事情，并在`profile/uploadPage.html`目录下的模板目录中创建一个新页面：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Profile Picture Upload</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center">Upload</h2>

    <form th:action="@{/upload}" method="post" enctype="multipart/form-data" class="col m8 s12 offset-m2">

        <div class="input-field col s6">
            <input type="file" id="file" name="file"/>
        </div>

        <div class="col s6 center">
            <button class="btn indigo waves-effect waves-light" type="submit" name="save" th:text="#{submit}">Submit
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
</body>
</html>
```

除了表单上的`enctype`属性外，没有什么可看的。文件将通过`POST`方法发送到`upload` URL。我们现在将在`profile`包中的`ProfileController`旁边创建相应的控制器：

```java
package masterSpringMvc.profile;

import org.apache.tomcat.util.http.fileupload.IOUtils;
import org.springframework.core.io.FileSystemResource;
import org.springframework.core.io.Resource;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.multipart.MultipartFile;

import java.io.*;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

@Controller
public class PictureUploadController {
    public static final Resource PICTURES_DIR = new FileSystemResource("./pictures");

    @RequestMapping("upload")
    public String uploadPage() {
        return "profile/uploadPage";
    }

    @RequestMapping(value = "/upload", method = RequestMethod.POST)
    public String onUpload(MultipartFile file) throws IOException {
        String filename = file.getOriginalFilename();
        File tempFile = File.createTempFile("pic", getFileExtension(filename), PICTURES_DIR.getFile());

        try (InputStream in = file.getInputStream();
             OutputStream out = new FileOutputStream(tempFile)) {
            IOUtils.copy(in, out);
        }

        return "profile/uploadPage";
    }

    private static String getFileExtension(String name) {
        return name.substring(name.lastIndexOf("."));
    }
}
```

这段代码将做的第一件事是在`pictures`目录中创建一个临时文件，该目录位于项目的根目录内；因此，请确保它存在。在 Java 中，临时文件只是一个方便的方法，用于在文件系统上获取唯一的文件标识符。用户可以选择删除它。

在项目的根目录下创建一个 pictures 目录，并添加一个名为`.gitkeep`的空文件，以确保您可以在 Git 中提交它。

### 提示

**Git 中的空目录**

Git 是基于文件的，不可能提交一个空目录。一个常见的解决方法是在目录中提交一个空文件，比如`.gitkeep`，以强制 Git 将其纳入版本控制。

用户上传的文件将作为`MultipartFile`接口注入到我们的控制器中。该接口提供了几种方法来获取文件的名称、大小和内容。

这里特别感兴趣的方法是`getInputStream()`。我们确实将复制这个流到一个`fileOutputStream`方法，感谢`IOUtils.copy`方法。将输入流写入输出流的代码非常无聊，所以在类路径中有 Apache Utils 很方便（它是`tomcat-embedded-core.jar`文件的一部分）。

我们大量使用了相当酷的 Spring 和 Java 7 NIO 功能：

+   字符串的资源类是一个实用类，表示可以以不同方式找到的资源的抽象

+   `try…with`块将自动关闭我们的流，即使出现异常，删除了编写`finally`块的样板

通过上述代码，用户上传的任何文件都将被复制到`pictures`目录中。

Spring Boot 中有一些可用的属性来自定义文件上传。看一下`MultipartProperties`类。

最有趣的是：

+   `multipart.maxFileSize`：这定义了上传文件的最大文件大小。尝试上传更大的文件将导致`MultipartException`类。默认值为`1Mb`。

+   `multipart.maxRequestSize`：这定义了多部分请求的最大大小。默认值为`10Mb`。

默认值对我们的应用程序已经足够好了。经过几次上传后，我们的图片目录将如下所示：

![上传文件](img/image00952.jpeg)

等等！有人上传了一个 ZIP 文件！我简直不敢相信。我们最好在我们的控制器中添加一些检查，以确保上传的文件是真实的图片：

```java
package masterSpringMvc.profile;

import org.apache.tomcat.util.http.fileupload.IOUtils;
import org.springframework.core.io.FileSystemResource;
import org.springframework.core.io.Resource;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.multipart.MultipartFile;
import org.springframework.web.servlet.mvc.support.RedirectAttributes;

import java.io.*;

@Controller
public class PictureUploadController {
    public static final Resource PICTURES_DIR = new FileSystemResource("./pictures");

    @RequestMapping("upload")
    public String uploadPage() {
        return "profile/uploadPage";
    }

    @RequestMapping(value = "/upload", method = RequestMethod.POST)
    public String onUpload(MultipartFile file, RedirectAttributes redirectAttrs) throws IOException {

 if (file.isEmpty() || !isImage(file)) {
 redirectAttrs.addFlashAttribute("error", "Incorrect file. Please upload a picture.");
 return "redirect:/upload";
 }

        copyFileToPictures(file);

        return "profile/uploadPage";
    }

    private Resource copyFileToPictures(MultipartFile file) throws IOException {
        String fileExtension = getFileExtension(file.getOriginalFilename());
        File tempFile = File.createTempFile("pic", fileExtension, PICTURES_DIR.getFile());
        try (InputStream in = file.getInputStream();
             OutputStream out = new FileOutputStream(tempFile)) {

            IOUtils.copy(in, out);
        }
        return new FileSystemResource(tempFile);
    }

    private boolean isImage(MultipartFile file) {
 return file.getContentType().startsWith("image");
 }

    private static String getFileExtension(String name) {
        return name.substring(name.lastIndexOf("."));
    }
}
```

很简单！`getContentType()`方法返回文件的**多用途互联网邮件扩展**（**MIME**）类型。它将是`image/png`，`image/jpg`等等。因此，我们只需检查 MIME 类型是否以"image"开头。

我们在表单中添加了一个错误消息，因此我们应该在我们的网页中添加一些内容来显示它。将以下代码放在`uploadPage`标题下方：

```java
<div class="col s12 center red-text" th:text="${error}" th:if="${error}">
    Error during upload
</div>
```

下次您尝试上传 ZIP 文件时，将会收到错误！如下截图所示：

![上传文件](img/image00953.jpeg)

## 将图像写入响应

上传的图片不是从静态目录中提供的。我们需要采取特殊措施来在我们的网页中显示它们。

让我们在我们的上传页面上方添加以下行，就在表单上方：

```java
<div class="col m8 s12 offset-m2">
    <img th:src="img/uploadedPicture}" width="100" height="100"/>
</div>
```

这将尝试从我们的控制器获取图像。让我们在`PictureUploadController`类中添加相应的方法：

```java
@RequestMapping(value = "/uploadedPicture")
public void getUploadedPicture(HttpServletResponse response) throws IOException {
    ClassPathResource classPathResource = new ClassPathResource("/images/anonymous.png");
    response.setHeader("Content-Type", URLConnection.guessContentTypeFromName(classPathResource.getFilename()));
    IOUtils.copy(classPathResource.getInputStream(), response.getOutputStream());
}
```

这段代码将直接将`src/main/resources/images/anonymous.png`目录中找到的图像写入响应！多么令人兴奋！

如果我们再次转到我们的页面，我们会看到以下图片：

![将图像写入响应](img/image00954.jpeg)

### 提示

我在 iconmonstr（[`iconmonstr.com/user-icon`](http://iconmonstr.com/user-icon)）上找到了匿名用户图片，并将其下载为 128 x 128 的 PNG 文件。

## 管理上传属性

在这一点上，一个好的做法是允许通过`application.properties`文件配置上传目录和匿名用户图片的路径。

让我们在新创建的`config`包内创建一个`PicturesUploadProperties`类：

```java
package masterSpringMvc.config;

import org.springframework.boot.context.properties.ConfigurationProperties;
import org.springframework.core.io.DefaultResourceLoader;
import org.springframework.core.io.Resource;

import java.io.IOException;
@ConfigurationProperties(prefix = "upload.pictures")
public class PicturesUploadProperties {
    private Resource uploadPath;
    private Resource anonymousPicture;

    public Resource getAnonymousPicture() {
        return anonymousPicture;
    }

    public void setAnonymousPicture(String anonymousPicture) {
        this.anonymousPicture = new DefaultResourceLoader().getResource(anonymousPicture);
    }

    public Resource getUploadPath() {
        return uploadPath;
    }

    public void setUploadPath(String uploadPath) {
        this.uploadPath = new DefaultResourceLoader().getResource(uploadPath);
    }
}
```

在这个类中，我们使用了 Spring Boot 的`ConfigurationProperties`。这将告诉 Spring Boot 以类型安全的方式自动映射类路径中发现的属性（默认情况下，在`application.properties`文件中）。

请注意，我们定义了以'String'作为参数的 setter，但可以自由地让 getter 返回任何类型是最有用的。

现在我们需要将`PicturesUploadProperties`类添加到我们的配置中：

```java
@SpringBootApplication
@EnableConfigurationProperties({PictureUploadProperties.class})
public class MasterSpringMvc4Application extends WebMvcConfigurerAdapter {
  // code omitted
}
```

现在我们可以在`application.properties`文件中添加属性值：

```java
upload.pictures.uploadPath=file:./pictures
upload.pictures.anonymousPicture=classpath:/images/anonymous.png
```

因为我们使用了 Spring 的`DefaultResourceLoader`类，我们可以使用诸如`file:`或`classpath:`之类的前缀来指定我们的资源可以被找到的位置。

这相当于创建一个`FileSystemResource`类或`ClassPathResource`类。

这种方法还有一个优点，就是可以对代码进行文档化。我们可以很容易地看到图片目录将在应用程序根目录中找到，而匿名图片将在类路径中找到。

就是这样。我们现在可以在我们的控制器中使用我们的属性。以下是`PictureUploadController`类的相关部分：

```java
package masterSpringMvc.profile;

import masterSpringMvc.config.PictureUploadProperties;
import org.apache.tomcat.util.http.fileupload.IOUtils;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.core.io.Resource;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.multipart.MultipartFile;
import org.springframework.web.servlet.mvc.support.RedirectAttributes;

import javax.servlet.http.HttpServletResponse;
import java.io.*;
import java.net.URLConnection;

@Controller
public class PictureUploadController {
    private final Resource picturesDir;
 private final Resource anonymousPicture;

 @Autowired
 public PictureUploadController(PictureUploadProperties uploadProperties) {
 picturesDir = uploadProperties.getUploadPath();
 anonymousPicture = uploadProperties.getAnonymousPicture();
 }

    @RequestMapping(value = "/uploadedPicture")
    public void getUploadedPicture(HttpServletResponse response) throws IOException {
        response.setHeader("Content-Type", URLConnection.guessContentTypeFromName(anonymousPicture.getFilename()));
 IOUtils.copy(anonymousPicture.getInputStream(), response.getOutputStream());
    }

  private Resource copyFileToPictures(MultipartFile file) throws IOException {
       String fileExtension = getFileExtension(file.getOriginalFilename());
       File tempFile = File.createTempFile("pic", fileExtension, picturesDir.getFile());
       try (InputStream in = file.getInputStream();
            OutputStream out = new FileOutputStream(tempFile)) {

           IOUtils.copy(in, out);
       }
       return new FileSystemResource(tempFile);
   }    
// The rest of the code remains the same
}
```

此时，如果您再次启动应用程序，您会发现结果并没有改变。匿名图片仍然显示，用户上传的图片仍然会出现在项目根目录的`pictures`目录中。

## 显示上传的图片

现在，我们需要向我们的`PictureUploadController`类添加一个模型属性来显示用户的图片：

```java
@ModelAttribute("picturePath")
public Resource picturePath() {
  return anonymousPicture;
}
```

现在我们可以注入它以在提供上传的图片时检索其值：

```java
@RequestMapping(value = "/uploadedPicture")
public void getUploadedPicture(HttpServletResponse response, @ModelAttribute("picturePath") Path picturePath) throws IOException {
    response.setHeader("Content-Type", URLConnection.guessContentTypeFromName(picturePath.toString()));
    Files.copy(picturePath, response.getOutputStream());
}
```

`@ModelAttribute`注解是一种方便的方法，可以使用带注解的方法创建模型属性。然后可以使用相同的注解将它们注入到控制器方法中。使用此代码，只要我们没有重定向到另一个页面，模型中就会有一个`picturePath`参数。它的默认值是我们在属性中定义的匿名图片。

当文件上传时，我们需要更新此值。更新`onUpload`方法：

```java
@RequestMapping(value = "/upload", method = RequestMethod.POST)
public String onUpload(MultipartFile file, RedirectAttributes redirectAttrs, Model model) throws IOException {

    if (file.isEmpty() || !isImage(file)) {
        redirectAttrs.addFlashAttribute("error", "Incorrect file. Please upload a picture.");
        return "redirect:/upload";
    }

    Resource picturePath = copyFileToPictures(file);
 model.addAttribute("picturePath", picturePath);

    return "profile/uploadPage";
}
```

通过注入模型，我们可以在上传完成后更新`picturePath`参数。

现在，问题是我们的两个方法`onUpload`和`getUploadedPicture`将出现在不同的请求中。不幸的是，模型属性将在每次之间重置。

这就是为什么我们将`picturePath`参数定义为会话属性。我们可以通过向我们的控制器类添加另一个注解来实现这一点：

```java
@Controller
@SessionAttributes("picturePath")
public class PictureUploadController {
}
```

哎呀！这么多注解只是为了处理一个简单的会话属性。您将获得以下输出：

![显示上传的图片](img/image00955.jpeg)

这种方法使代码组合变得非常容易。此外，我们没有直接使用`HttpServletRequest`或`HttpSession`。此外，我们的对象可以很容易地进行类型化。

## 处理文件上传错误

我的细心读者一定会想到我们的代码可能会抛出两种异常：

+   `IOException`: 如果在将文件写入磁盘时发生了不好的情况，就会抛出此错误。

+   `MultipartException`: 如果上传文件时发生错误，则会抛出此错误。例如，当超过最大文件大小时。

这将为我们提供一个很好的机会来看一下在 Spring 中处理异常的两种方式：

+   在控制器方法中使用`@ExceptionHandler`注解

+   使用在 Servlet 容器级别定义的全局异常处理程序

让我们通过在我们的`PictureUploadController`类中使用`@ExceptionHandler`注解来处理`IOException`，添加以下方法：

```java
@ExceptionHandler(IOException.class)
public ModelAndView handleIOException(IOException exception) {
    ModelAndView modelAndView = new ModelAndView("profile/uploadPage");
    modelAndView.addObject("error", exception.getMessage());
    return modelAndView;
}
```

这是一种简单而强大的方法。每当我们的控制器中抛出`IOException`时，将调用此方法。

为了测试异常处理程序，由于使 Java IO 代码抛出异常可能会很棘手，只需在测试期间替换`onUpload`方法体：

```java
@RequestMapping(value = "/upload", method = RequestMethod.POST)
public String onUpload(MultipartFile file, RedirectAttributes redirectAttrs, Model model) throws IOException {
    throw new IOException("Some message");
}
```

更改后，如果我们尝试上传图片，将在上传页面上看到此异常的错误消息显示：

![处理文件上传错误](img/image00956.jpeg)

现在，我们将处理`MultipartException`。这需要在 Servlet 容器级别（即在 Tomcat 级别）进行，因为此异常不是直接由我们的控制器抛出的。

我们需要向我们的配置中添加一个新的`EmbeddedServletContainerCustomizer` bean。将此方法添加到`WebConfiguration`类中：

```java
@Bean
public EmbeddedServletContainerCustomizer containerCustomizer() {
    EmbeddedServletContainerCustomizer 
embeddedServletContainerCustomizer = new EmbeddedServletContainerCustomizer() {
        @Override
        public void customize(ConfigurableEmbeddedServletContainer container) {
            container.addErrorPages(new ErrorPage(MultipartException.class, "/uploadError"));
        }
    };
    return embeddedServletContainerCustomizer;
}
```

这有点啰嗦。请注意，`EmbeddedServletContainerCustomizer`是一个包含单个方法的接口；因此，它可以被 lambda 表达式替换：

```java
@Bean
public EmbeddedServletContainerCustomizer containerCustomizer() {
    EmbeddedServletContainerCustomizer embeddedServletContainerCustomizer
            = container -> container.addErrorPages(new ErrorPage(MultipartException.class, "/uploadError"));
    return embeddedServletContainerCustomizer;
}
```

因此，我们只需编写以下内容：

```java
@Bean
public EmbeddedServletContainerCustomizer containerCustomizer() {
    return container -> container.addErrorPages(new ErrorPage(MultipartException.class, "/uploadError"));
}
```

此代码创建了一个新的错误页面，当发生`MultipartException`时将调用该页面。它还可以映射到 HTTP 状态。`EmbeddedServletContainerCustomizer`接口还具有许多其他功能，将允许自定义我们的应用程序运行的 Servlet 容器。有关更多信息，请访问[`docs.spring.io/spring-boot/docs/current/reference/html/boot-features-developing-web-applications.html#boot-features-customizing-embedded-containers`](http://docs.spring.io/spring-boot/docs/current/reference/html/boot-features-developing-web-applications.html#boot-features-customizing-embedded-containers)。

现在，我们需要在我们的`PictureUploadController`类中处理这个`uploadError` URL：

```java
@RequestMapping("uploadError")
public ModelAndView onUploadError(HttpServletRequest request) {
    ModelAndView modelAndView = new ModelAndView("uploadPage");
    modelAndView.addObject("error", request.getAttribute(WebUtils.ERROR_MESSAGE_ATTRIBUTE));
    return modelAndView;
}
```

在 Servlet 环境中定义的错误页面包含许多有助于调试错误的有趣属性：

| 属性 | 描述 |
| --- | --- |
| `javax.servlet.error.status_code` | 这是错误的 HTTP 状态码。 |
| `javax.servlet.error.exception_type` | 这是异常类。 |
| `javax.servlet.error.message` | 这是抛出的异常的消息。 |
| `javax.servlet.error.request_uri` | 这是发生异常的 URI。 |
| `javax.servlet.error.exception` | 这是实际的异常。 |
| `javax.servlet.error.servlet_name` | 这是捕获异常的 Servlet 的名称。 |

所有这些属性都可以方便地在 Spring Web 的`WebUtils`类上访问。

如果有人试图上传太大的文件，他们将收到非常明确的错误消息。

您现在可以通过上传一个非常大的文件（> 1Mb）或将`multipart.maxFileSize`属性设置为较低的值（例如 1kb）来测试错误是否被正确处理：

![处理文件上传错误](img/image00957.jpeg)

# 翻译错误消息

对于开发人员来说，看到应用程序抛出的异常是非常好的。然而，对于我们的用户来说，它们的价值很小。因此，我们将对它们进行翻译。为了做到这一点，我们必须将我们应用程序的`MessageSource`类注入到我们控制器的构造函数中：

```java

private final MessageSource messageSource;

@Autowired
public PictureUploadController(PictureUploadProperties uploadProperties, MessageSource messageSource) {
    picturesDir = uploadProperties.getUploadPath();
    anonymousPicture = uploadProperties.getAnonymousPicture();
    this.messageSource = messageSource;
}
```

现在，我们可以从消息包中检索消息：

```java
@ExceptionHandler(IOException.class)
public ModelAndView handleIOException(Locale locale) {
    ModelAndView modelAndView = new ModelAndView("profile/uploadPage");
    modelAndView.addObject("error", messageSource.getMessage("upload.io.exception", null, locale));
    return modelAndView;
}

@RequestMapping("uploadError")
public ModelAndView onUploadError(Locale locale) {
    ModelAndView modelAndView = new ModelAndView("profile/uploadPage");
    modelAndView.addObject("error", messageSource.getMessage("upload.file.too.big", null, locale));
    return modelAndView;
}
```

以下是英文消息：

```java
upload.io.exception=An error occurred while uploading the file. Please try again.
upload.file.too.big=Your file is too big.
```

现在，法语消息：

```java
upload.io.exception=Une erreur est survenue lors de l'envoi du fichier. Veuillez réessayer.
upload.file.too.big=Votre fichier est trop gros.
```

# 将配置文件放入会话中

我们希望的下一步是将配置文件存储在会话中，以便每次进入配置文件页面时都不会被重置。这对一些用户来说可能会很烦人，我们必须解决这个问题。

### 提示

**HTTP 会话**是在请求之间存储信息的一种方式。HTTP 是一种无状态协议，这意味着没有办法将来自同一用户的两个请求联系起来。大多数 Servlet 容器所做的是将名为`JSESSIONID`的 cookie 与每个用户关联起来。该 cookie 将在请求头中传输，并允许您在一个称为`HttpSession`的抽象中存储任意对象。这样的会话通常会在用户关闭或切换 Web 浏览器或预定义的不活动期之后结束。

我们刚刚看到了一种使用`@SessionAttributes`注解将对象放入会话中的方法。这在控制器内部效果很好，但在多个控制器之间共享数据时会变得困难。我们必须依赖字符串来从其名称解析属性，这很难重构。出于同样的原因，我们不希望直接操作`HttpSession`。另一个阻止直接使用会话的论点是，依赖于它的控制器很难进行单元测试。

在使用 Spring 保存会话中的内容时，还有另一种流行的方法：使用`@Scope("session")`为 bean 添加注释。

然后，您将能够在控制器和其他 Spring 组件中注入会话 bean，以设置或检索其中的值。

让我们在`profile`包中创建一个`UserProfileSession`类：

```java
package masterSpringMvc.profile;

import org.springframework.context.annotation.Scope;
import org.springframework.context.annotation.ScopedProxyMode;
import org.springframework.stereotype.Component;
import java.io.Serializable;
import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

@Component
@Scope(value = "session", proxyMode = ScopedProxyMode.TARGET_CLASS)
public class UserProfileSession implements Serializable {
    private String twitterHandle;
    private String email;
    private LocalDate birthDate;
    private List<String> tastes = new ArrayList<>();

    public void saveForm(ProfileForm profileForm) {
        this.twitterHandle = profileForm.getTwitterHandle();
        this.email = profileForm.getEmail();
        this.birthDate = profileForm.getBirthDate();
        this.tastes = profileForm.getTastes();
    }

    public ProfileForm toForm() {
        ProfileForm profileForm = new ProfileForm();
        profileForm.setTwitterHandle(twitterHandle);
        profileForm.setEmail(email);
        profileForm.setBirthDate(birthDate);
        profileForm.setTastes(tastes);
        return profileForm;
    }
}
```

我们已经方便地提供了一种从`ProfileForm`对象转换的方法。这将帮助我们从`ProfileController`构造函数中存储和检索表单数据。我们需要在控制器的构造函数中注入我们的`UserProfileSession`变量并将其存储为字段。我们还需要将`ProfileForm`公开为模型属性，这将消除在`displayProfile`方法中注入它的需要。最后，一旦验证通过，我们就可以保存配置文件：

```java
@Controller
public class ProfileController {

    private UserProfileSession userProfileSession;
    @Autowired
    public ProfileController(UserProfileSession userProfileSession) {
        this.userProfileSession = userProfileSession;
    }

    @ModelAttribute
    public ProfileForm getProfileForm() {
        return userProfileSession.toForm();
    }

    @RequestMapping(value = "/profile", params = {"save"}, method = RequestMethod.POST)
    public String saveProfile(@Valid ProfileForm profileForm, BindingResult bindingResult) {
        if (bindingResult.hasErrors()) {
            return "profile/profilePage";
        }
        userProfileSession.saveForm(profileForm);
        return "redirect:/profile";
    }

    // the rest of the code is unchanged
}
```

这就是使用 Spring MVC 在会话中保存数据所需的全部内容。

现在，如果您完成了配置文件表单并刷新页面，数据将在请求之间持久保存。

在进入下一章之前，我想详细介绍一些我们刚刚使用的概念。

首先是通过构造函数进行注入。`ProfileController`构造函数使用`@Autowired`进行注释，这意味着 Spring 将在实例化 bean 之前从应用程序上下文中解析构造函数参数。另一种稍微不那么冗长的替代方法是使用字段注入：

```java
@Controller
public class ProfileController {

    @Autowired
    private UserProfileSession userProfileSession;
}
```

构造函数注入可能更好，因为如果我们要远离`spring-test`框架，它会使我们的控制器的单元测试更容易，并且它会使我们的 bean 的依赖关系更加明确。

有关字段注入和构造函数注入的详细讨论，请参阅 Oliver Gierke 在[`olivergierke.de/2013/11/why-field-injection-is-evil/`](http://olivergierke.de/2013/11/why-field-injection-is-evil/)上的出色博客文章。

可能需要澄清的另一件事是`Scope`注解上的`proxyMode`参数：

```java
@Scope(value = "session", proxyMode = ScopedProxyMode.TARGET_CLASS)
```

Spring 有三个`proxyMode`参数可用，如果不计算默认值：

+   `TARGET_CLASS`：这使用 CGI 代理

+   `INTERFACES`：这将创建一个 JDK 代理

+   `NO`：这不会创建任何代理

代理的优势通常在将某些东西注入到长期存在的组件中（如单例）时发挥作用。因为注入只发生一次，当 bean 被创建时，对注入的 bean 的后续调用可能不会反映其实际状态。

在我们的情况下，会话 bean 的实际状态存储在会话中，而不是直接存储在 bean 中。这解释了为什么 Spring 必须创建代理：它需要拦截对我们 bean 方法的调用，并监听其变化。这样，bean 的状态可以透明地存储和检索到底层的 HTTP 会话中。

对于会话 bean，我们被迫使用代理模式。CGI 代理将对您的字节码进行检测，并在任何类上工作，而 JDK 方法可能会更轻量级一些，但需要您实现一个接口。

最后，我们使`UserProfileSession` bean 实现了`Serializable`接口。这并不是严格要求的，因为 HTTP 会话可以在内存中存储任意对象，但是使最终存储在会话中的对象可序列化确实是一个好习惯。

实际上，我们可能会更改会话的持久化方式。事实上，我们将在第七章中将会话存储在 Redis 数据库中，*优化您的请求*，在那里 Redis 必须使用`Serializable`对象。最好始终将会话视为通用数据存储。我们必须提供一种从该存储系统中写入和读取对象的方法。

为了使我们的 bean 上的序列化正常工作，我们还需要使其每个字段都可序列化。在我们的情况下，字符串和日期是可序列化的，所以我们可以继续。

# 自定义错误页面

Spring Boot 允许您定义自己的错误视图，而不是我们之前看到的 Whitelabel 错误页面。它必须具有名称`error`，其目的是处理所有异常。默认的`BasicErrorController`类将公开许多有用的模型属性，您可以在此页面上显示这些属性。

让我们在`src/main/resources/templates`中创建一个自定义错误页面。让我们称之为`error.html`：

```java
<!DOCTYPE html>
<html >
<head lang="en">
    <meta charset="UTF-8"/>
    <title th:text="${status}">404</title>

    <link href="/webjars/materializecss/0.96.0/css/materialize.css" type="text/css" rel="stylesheet"
          media="screen,projection"/>
</head>
<body>
<div class="row">
    <h1 class="indigo-text center" th:text="${error}">Not found</h1>

    <p class="col s12 center" th:text="${message}">
        This page is not available
    </p>
</div>
</body>
</html>
```

现在，如果我们导航到我们的应用程序未处理的 URL，我们会看到我们的自定义错误页面：

![自定义错误页面](img/image00958.jpeg)

处理错误的更高级选项是定义自己的`ErrorController`类的实现，这是负责全局处理所有异常的控制器。查看`ErrorMvcAutoConfiguration`类和`BasicErrorController`类，它是默认实现。

# 使用矩阵变量的 URL 映射

我们现在知道我们的用户对什么感兴趣。改进我们的 Tweet 控制器，以便它允许从关键字列表中进行搜索，这是一个好主意。

在 URL 中传递键值对的一个有趣方式是使用矩阵变量。这与请求参数非常相似。考虑以下代码：

```java
someUrl/param?var1=value1&var2=value2
```

矩阵变量理解前面的参数：

```java
someUrl/param;var1=value1;var2=value2
```

它们还允许每个参数都是一个列表：

```java
someUrl/param;var1=value1,value2;var2=value3,value4
```

矩阵变量可以映射到控制器内的不同对象类型：

+   `Map<String, List<?>>`：这处理多个变量和多个值

+   `Map<String, ?>`：这处理每个变量只有一个值的情况

+   `List<?>`：如果我们对一个可以配置名称的单个变量感兴趣，就会使用这个

在我们的情况下，我们想要处理这样的情况：

```java
http://localhost:8080/search/popular;keywords=scala,java
```

第一个参数`popular`是 Twitter 搜索 API 已知的结果类型。它可以取以下值：`mixed`、`recent`或`popular`。

我们 URL 的其余部分是关键字列表。因此，我们将它们映射到一个简单的`List<String>`对象。

默认情况下，Spring MVC 会删除 URL 中分号后面的每个字符。我们需要做的第一件事是关闭这种行为，以启用我们应用程序中的矩阵变量。

让我们在`WebConfiguration`类中添加以下代码：

```java
@Override
public void configurePathMatch(PathMatchConfigurer configurer) {
    UrlPathHelper urlPathHelper = new UrlPathHelper();
    urlPathHelper.setRemoveSemicolonContent(false);
    configurer.setUrlPathHelper(urlPathHelper);
}
```

让我们在`search`包中创建一个新的控制器，我们将其称为`SearchController`。它的作用是处理以下请求：

```java
package masterSpringMvc.search;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.twitter.api.Tweet;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.MatrixVariable;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.servlet.ModelAndView;

import java.util.List;

@Controller
public class SearchController {
    private SearchService searchService;
    @Autowired
    public SearchController(SearchService searchService) {
        this.searchService = searchService;
    }

    @RequestMapping("/search/{searchType}")
    public ModelAndView search(@PathVariable String searchType, @MatrixVariable List<String> keywords) {
        List<Tweet> tweets = searchService.search(searchType, keywords);
        ModelAndView modelAndView = new ModelAndView("resultPage");
        modelAndView.addObject("tweets", tweets);
        modelAndView.addObject("search", String.join(",", keywords));
        return modelAndView;
    }
}
```

正如你所看到的，我们能够重用现有的结果页面来显示推文。我们还希望将搜索委托给另一个名为`SearchService`的类。我们将在与`SearchController`相同的包中创建这个服务：

```java
package masterSpringMvc.search;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.twitter.api.Tweet;
import org.springframework.social.twitter.api.Twitter;
import org.springframework.stereotype.Service;
import java.util.List;

@Service
public class SearchService {
    private Twitter twitter;

    @Autowired
    public SearchService(Twitter twitter) {
        this.twitter = twitter;
    }

    public List<Tweet> search(String searchType, List<String> keywords) {
        return null;
    }
}
```

现在，我们需要实现`search()`方法。

`twitter.searchOperations().search(params)`上可访问的搜索操作以`searchParameters`作为高级搜索的参数。这个对象允许我们根据十几个标准进行搜索。我们对`query`、`resultType`和`count`属性感兴趣。

首先，我们需要创建一个`ResultType`构造函数，其中包含`searchType`路径变量。`ResultType`是一个枚举，所以我们可以迭代它的不同值，并找到与输入匹配的值，忽略大小写：

```java
private SearchParameters.ResultType getResultType(String searchType) {
    for (SearchParameters.ResultType knownType : SearchParameters.ResultType.values()) {
        if (knownType.name().equalsIgnoreCase(searchType)) {
            return knownType;
        }
    }
    return SearchParameters.ResultType.RECENT;
}
```

现在我们可以创建一个带有以下方法的`SearchParameters`构造函数：

```java
private SearchParameters createSearchParam(String searchType, String taste) {

    SearchParameters.ResultType resultType = getResultType(searchType);
    SearchParameters searchParameters = new SearchParameters(taste);
    searchParameters.resultType(resultType);
    searchParameters.count(3);
    return searchParameters;
}
```

现在，创建`SearchParameters`构造函数的列表就像进行映射操作一样简单（获取关键字列表并为每个关键字返回一个`SearchParameters`构造函数）：

```java
List<SearchParameters> searches = keywords.stream()
        .map(taste -> createSearchParam(searchType, taste))
        .collect(Collectors.toList());
```

现在，我们想要为每个`SearchParameters`构造函数获取推文。你可能会想到这样的东西：

```java
List<Tweet> tweets = searches.stream()
        .map(params -> twitter.searchOperations().search(params))
        .map(searchResults -> searchResults.getTweets())
        .collect(Collectors.toList());
```

然而，如果你仔细想想，这将返回一个推文列表。我们想要的是将所有推文展平，以便得到一个简单的列表。原来调用`map`然后展平结果的操作称为`flatMap`。所以我们可以写：

```java
List<Tweet> tweets = searches.stream()
        .map(params -> twitter.searchOperations().search(params))
        .flatMap(searchResults -> searchResults.getTweets().stream())
        .collect(Collectors.toList());
```

`flatMap`函数的语法，它以流作为参数，一开始有点难以理解。让我向你展示`SearchService`类的整个代码，这样我们就可以退一步看看：

```java
package masterSpringMvc.search;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.twitter.api.SearchParameters;
import org.springframework.social.twitter.api.Tweet;
import org.springframework.social.twitter.api.Twitter;
import org.springframework.stereotype.Service;

import java.util.List;
import java.util.stream.Collectors;

@Service
public class SearchService {
    private Twitter twitter;

    @Autowired
    public SearchService(Twitter twitter) {
        this.twitter = twitter;
    }

    public List<Tweet> search(String searchType, List<String> keywords) {
        List<SearchParameters> searches = keywords.stream()
                .map(taste -> createSearchParam(searchType, taste))
                .collect(Collectors.toList());

        List<Tweet> results = searches.stream()
                .map(params -> twitter.searchOperations().search(params))
                .flatMap(searchResults -> searchResults.getTweets().stream())
                .collect(Collectors.toList());

        return results;
    }

    private SearchParameters.ResultType getResultType(String searchType) {
        for (SearchParameters.ResultType knownType : SearchParameters.ResultType.values()) {
            if (knownType.name().equalsIgnoreCase(searchType)) {
                return knownType;
            }
        }
        return SearchParameters.ResultType.RECENT;
    }

    private SearchParameters createSearchParam(String searchType, String taste) {
        SearchParameters.ResultType resultType = getResultType(searchType);
        SearchParameters searchParameters = new SearchParameters(taste);
        searchParameters.resultType(resultType);
        searchParameters.count(3);
        return searchParameters;
    }
}
```

现在，如果我们导航到`http://localhost:8080/search/mixed;keywords=scala,java`，我们会得到预期的结果。首先搜索 Scala 关键字，然后搜索 Java：

![带矩阵变量的 URL 映射](img/image00959.jpeg)

# 把它放在一起

现在，一切都可以单独工作，是时候将一切组合起来了。我们将分三步完成这个过程：

1.  将上传表单移动到个人资料页面，并删除旧的上传页面。

1.  将个人资料页面上的提交按钮更改为直接触发口味搜索。

1.  更改我们应用程序的主页。它应该立即显示与我们用户口味匹配的搜索结果。如果不可用，转到个人资料页面。

我鼓励你尝试自己做。你会在途中遇到一些很容易解决的问题，但你应该知道足够的知识来自己解决它们。我相信你。

好了，现在你已经完成了工作（你已经完成了，对吧？），让我们来看看我的解决方案。

第一步是删除旧的`uploadPage`标题。不要回头，就这么做。

接下来，将这些行放在`profilePage`标题的下方：

```java
<div class="row">

    <div class="col m8 s12 offset-m2">
        <img th:src="img/uploadedPicture}" width="100" height="100"/>
    </div>

    <div class="col s12 center red-text" th:text="${error}" th:if="${error}">
        Error during upload
    </div>

    <form th:action="@{/profile}" method="post" enctype="multipart/form-data" class="col m8 s12 offset-m2">

        <div class="input-field col s6">
            <input type="file" id="file" name="file"/>
        </div>

        <div class="col s6 center">
            <button class="btn indigo waves-effect waves-light" type="submit" name="upload" th:text="#{upload}">Upload
                <i class="mdi-content-send right"></i>
            </button>
        </div>
    </form>
</div>
```

这与以前的`uploadPage`的内容非常相似。我们只是删除了标题，并更改了提交按钮的标签。将相应的翻译添加到包中。

在英语中：

```java
upload=Upload
```

用法语：

```java
Upload=Envoyer
```

我们还将提交按钮的名称更改为`upload`。这将帮助我们在控制器端识别这个操作。

现在，如果我们尝试上传我们的图片，它会将我们重定向到旧的上传页面。我们需要在`PictureUploadController`类的`onUpload`方法中修复这个问题：

```java
@RequestMapping(value = "/profile", params = {"upload"}, method = RequestMethod.POST)
public String onUpload(@RequestParam MultipartFile file, RedirectAttributes redirectAttrs) throws IOException {

    if (file.isEmpty() || !isImage(file)) {
        redirectAttrs.addFlashAttribute("error", "Incorrect file. Please upload a picture.");
        return "redirect:/profile";
    }

    Resource picturePath = copyFileToPictures(file);
    userProfileSession.setPicturePath(picturePath);

    return "redirect:profile";
}
```

请注意，我们更改了处理 POST 的 URL。现在是`/profile`而不是`/upload`。当`GET`和`POST`请求具有相同的 URL 时，表单处理会更简单，并且在处理异常时会节省我们很多麻烦。这样，我们就不必在错误发生后重定向用户。

我们还删除了模型属性`picturePath`。因为我们现在在会话中有一个代表用户的 bean，`UserProfileSession`，我们决定将其添加在那里。我们在`UserProfileSession`类中添加了一个`picturePath`属性以及相关的 getter 和 setter。

不要忘记在我们的`PictureUploadController`类中注入`UserProfileSession`类，并将其作为字段可用。

请记住，我们会话 bean 的所有属性都必须是可序列化的，与资源不同。因此我们需要以不同的方式存储它。URL 类似乎是一个很好的选择。它是可序列化的，而且很容易使用`UrlResource`类从 URL 创建资源：

```java
@Component
@Scope(value = "session", proxyMode = ScopedProxyMode.TARGET_CLASS)
public class UserProfileSession implements Serializable {
    private URL picturePath;

    public void setPicturePath(Resource picturePath) throws IOException {
        this.picturePath = picturePath.getURL();
    }

    public Resource getPicturePath() {
        return picturePath == null ? null : new UrlResource(picturePath);
    }
}
```

我需要做的最后一件事是在错误后将`profileForm`作为模型属性可用。这是因为在呈现`profilePage`时需要它。

总之，这是`PictureUploadController`类的最终版本：

```java
package masterSpringMvc.profile;

import masterSpringMvc.config.PictureUploadProperties;
import org.apache.tomcat.util.http.fileupload.IOUtils;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.MessageSource;
import org.springframework.core.io.FileSystemResource;
import org.springframework.core.io.Resource;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.*;
import org.springframework.web.multipart.MultipartFile;
import org.springframework.web.servlet.ModelAndView;
import org.springframework.web.servlet.mvc.support.RedirectAttributes;

import javax.servlet.http.HttpServletResponse;
import java.io.*;
import java.net.URLConnection;
import java.util.Locale;

@Controller
public class PictureUploadController {
    private final Resource picturesDir;
    private final Resource anonymousPicture;
    private final MessageSource messageSource;
    private final UserProfileSession userProfileSession;

    @Autowired
    public PictureUploadController(PictureUploadProperties uploadProperties,
                                   MessageSource messageSource,
                                   UserProfileSession userProfileSession) {
        picturesDir = uploadProperties.getUploadPath();
        anonymousPicture = uploadProperties.getAnonymousPicture();
        this.messageSource = messageSource;
        this.userProfileSession = userProfileSession;
    }

    @RequestMapping(value = "/uploadedPicture")
    public void getUploadedPicture(HttpServletResponse response) throws IOException {
        Resource picturePath = userProfileSession.getPicturePath();
        if (picturePath == null) {
            picturePath = anonymousPicture;
        }
        response.setHeader("Content-Type", URLConnection.guessContentTypeFromName(picturePath.getFilename()));
        IOUtils.copy(picturePath.getInputStream(), response.getOutputStream());
    }

    @RequestMapping(value = "/profile", params = {"upload"}, method = RequestMethod.POST)
    public String onUpload(@RequestParam MultipartFile file, RedirectAttributes redirectAttrs) throws IOException {

        if (file.isEmpty() || !isImage(file)) {
            redirectAttrs.addFlashAttribute("error", "Incorrect file. Please upload a picture.");
            return "redirect:/profile";
        }

        Resource picturePath = copyFileToPictures(file);
        userProfileSession.setPicturePath(picturePath);

        return "redirect:profile";
    }

    private Resource copyFileToPictures(MultipartFile file) throws IOException {
        String fileExtension = getFileExtension(file.getOriginalFilename());
        File tempFile = File.createTempFile("pic", fileExtension, picturesDir.getFile());
        try (InputStream in = file.getInputStream();
             OutputStream out = new FileOutputStream(tempFile)) {

            IOUtils.copy(in, out);
        }
        return new FileSystemResource(tempFile);
    }

    @ExceptionHandler(IOException.class)
    public ModelAndView handleIOException(Locale locale) {
        ModelAndView modelAndView = new ModelAndView("profile/profilePage");
        modelAndView.addObject("error", messageSource.getMessage("upload.io.exception", null, locale));
        modelAndView.addObject("profileForm", userProfileSession.toForm());
        return modelAndView;
    }

    @RequestMapping("uploadError")
    public ModelAndView onUploadError(Locale locale) {
        ModelAndView modelAndView = new ModelAndView("profile/profilePage");
        modelAndView.addObject("error", messageSource.getMessage("upload.file.too.big", null, locale));
        modelAndView.addObject("profileForm", userProfileSession.toForm());
        return modelAndView;
    }

    private boolean isImage(MultipartFile file) {
        return file.getContentType().startsWith("image");
    }

    private static String getFileExtension(String name) {
        return name.substring(name.lastIndexOf("."));
    }
}
```

因此，现在我们可以转到个人资料页面，上传我们的图片，并提供个人信息，如下截图所示：

![将其放在一起](img/image00960.jpeg)

现在，让我们在个人资料完成后将用户重定向到搜索页面。为此，我们需要修改`ProfileController`类中的`saveProfile`方法：

```java
@RequestMapping(value = "/profile", params = {"save"}, method = RequestMethod.POST)
public String saveProfile(@Valid ProfileForm profileForm, BindingResult bindingResult) {
    if (bindingResult.hasErrors()) {
        return "profile/profilePage";
    }
    userProfileSession.saveForm(profileForm);
    return "redirect:/search/mixed;keywords=" + String.join(",", profileForm.getTastes());
}
```

现在我们能够从我们的个人资料搜索推文，我们不再需要之前创建的`searchPage`或`TweetController`。只需删除`searchPage.html`页面和`TweetController`。

最后，我们可以修改我们的主页，这样如果我们已经完成了我们的个人资料，它就会重定向我们到一个符合我们口味的搜索页面。

让我们在控制器包中创建一个新的控制器。它负责将访问我们网站根目录的用户重定向到他们的个人资料（如果资料不完整）或`resultPage`（如果他们的口味可用）：

```java
package masterSpringMvc.controller;

import masterSpringMvc.profile.UserProfileSession;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

import java.util.List;

@Controller
public class HomeController {
    private UserProfileSession userProfileSession;

    @Autowired
    public HomeController(UserProfileSession userProfileSession) {
        this.userProfileSession = userProfileSession;
    }

    @RequestMapping("/")
    public String home() {
        List<String> tastes = userProfileSession.getTastes();
        if (tastes.isEmpty()) {
            return "redirect:/profile";
        }
        return "redirect:/search/mixed;keywords=" + String.join(",", tastes);
    }
}
```

# 检查点

在本章中，我们添加了两个控制器，`PictureUploadController`负责将上传的文件写入磁盘并处理上传错误，`SearchController`可以使用矩阵参数从关键字列表中搜索推文。

然后，该控制器将搜索委托给一个新的服务，`SearchService`。

我们删除了旧的`TweetController`。

我们创建了一个会话 bean，`UserProfileSession`，来存储关于用户的信息。

最后，我们在`WebConfiguration`中添加了两个内容。我们为 Servlet 容器添加了错误页面，并支持矩阵变量。

![检查点](img/image00961.jpeg)

在资源方面，我们添加了一个代表匿名用户的图片和一个处理错误的静态页面。我们将文件上传到`profilePage`，并且删除了旧的`searchPage`。

![检查点](img/image00962.jpeg)

# 总结

在本章中，我们讨论了文件上传和错误处理。上传文件并不是很复杂。然而，一个重要的设计决定是如何处理上传的文件。我们本可以将图片存储在数据库中，但我们选择将其写入磁盘，并将每个用户的图片位置保存在他们的会话中。

我们看到了在控制器级别和 Servlet 容器级别处理异常的典型方法。有关 Spring MVC 错误处理的其他资源，您可以参考[`spring.io/blog/2013/11/01/exception-handling-in-spring-mvc`](https://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc)上的博客文章。

我们的应用程序已经看起来相当不错，但我们需要编写的代码量非常合理。

敬请关注下一章，我们将看到 Spring MVC 也是构建 REST 应用程序的强大框架。

# 第四章。打造 RESTful 应用程序

在本章中，我们将介绍 RESTful 架构的主要原则。然后，借助非常方便的工具，我们将设计一个友好的 API，利用 Jackson 的能力将我们的模型序列化为 JSON。

我们将使用适当的错误代码和 HTTP 动词记录我们的应用程序，并使用 Swagger UI 自动生成我们应用程序的整洁前端。

最后，我们将研究其他形式的序列化，并了解更多关于 Spring MVC 的内容协商机制。

# 什么是 REST？

**REST**（表述状态转移）是一种定义创建可扩展 Web 服务的最佳实践的架构风格，利用了 HTTP 协议的能力。

一个 RESTful 的 Web 服务应该自然地表现出以下特性：

+   **客户端-服务器**: UI 与数据存储分离

+   **无状态**: 每个请求都包含足够的信息，以便服务器在不维护任何状态的情况下运行

+   **可缓存**: 服务器的响应包含足够的信息，允许客户端对数据存储做出明智的决定

+   **统一接口**: URI 唯一标识资源，超链接允许发现 API

+   **分层**: API 的每个资源提供了合理的细节水平

这种架构的优势在于它易于维护和发现。它还具有良好的可扩展性，因为无需在服务器和客户端之间维护持久连接，这消除了负载平衡或粘性会话的需要。最后，服务更有效，因为信息布局整齐，易于缓存。

让我们看看如何通过使用 Richardson 的成熟度模型逐步设计更好的 API。

# Richardson 的成熟度模型

Leonard Richardson 因定义了从 0 到 3 的四个级别而闻名，描述了 Web API 的“RESTfulness”级别。每个级别都需要额外的工作和投资在 API 中，但也提供了额外的好处。

## 级别 0 – HTTP

级别 0 真的很容易达到；你只需要通过 HTTP 协议在网络上提供你的资源。你可以使用你认为最适合你的用例的任何数据表示（XML、JSON 等）。

## 级别 1 – 资源

大多数人在听到 REST 这个词时会想到资源。资源是我们模型中元素的唯一标识符，例如用户或推文。使用 HTTP，资源显然与统一资源标识符 URI 相关联，如下例所示：

+   `/users` 包含我们所有用户的列表

+   `/user/42` 包含特定用户

+   `/user/42/tweets` 包含与特定用户关联的所有推文的列表

也许你的 API 可以允许访问与用户相关的特定推文，使用`/user/42/tweet/3`，或者每条推文都有唯一标识，这种情况下你可能更喜欢`/tweet/3`。

这个级别的目标是通过公开多个专门的资源来处理应用程序的复杂性。

关于服务器可以返回的响应类型没有规则。当你列出所有资源时，你可能只想包含稀缺信息，并在请求特定资源时提供更多细节。一些 API 甚至允许你在提供给你之前列出你感兴趣的字段。

真的取决于你来定义 API 的形式，记住一个简单的规则：最少惊讶原则。给你的用户他们期望的东西，你的 API 就已经很好了。

## 级别 2 – HTTP 动词

这个级别是关于使用 HTTP 动词来识别资源上可能的操作。这是描述 API 可以做什么的一个非常好的方式，因为 HTTP 动词是开发人员之间的一个众所周知的标准。

主要动词列在这里：

+   `GET`: 这读取特定 URI 上的数据。

+   `HEAD`：这与`GET`相同，但没有响应主体。这对于获取资源的元数据（缓存信息等）很有用。

+   `DELETE`：这会删除一个资源。

+   `PUT`：这会更新或创建一个资源。

+   `POST`：这会更新或创建一个资源。

+   `PATCH`：这会部分更新一个资源。

+   `OPTIONS`：这会返回服务器在特定资源上支持的方法列表。

大多数允许**创建读取更新删除**（**CRUD**）操作的应用只需要三个动词：`GET`、`DELETE`和`POST`。你实现的动词越多，你的 API 就会变得越丰富和更有语义。它帮助第三方通过允许他们输入一些命令并查看发生了什么来与你的服务交互。

`OPTIONS`和`HEAD`动词很少见，因为它们在元数据级别上工作，通常对任何应用程序都不是至关重要的。

乍一看，`PUT`和`POST`动词似乎做着相同的事情。主要区别在于`PUT`动词被认为是幂等的，这意味着多次发送相同的请求应该导致相同的服务器状态。这条规则的含义基本上是，`PUT`动词应该在给定的 URI 上操作，并包含足够的信息使请求成功。

例如，客户端可以在`/user/42`上使用`PUT`数据，结果将是更新或创建，取决于请求之前实体是否存在。

另一方面，当你不确定应该写入什么 URI 时，应该使用`POST`。你可以发送`POST`到`/users`而不在请求中指定 ID，并期望用户被创建。你也可以发送`POST`到相同的`/users`资源，这次在请求实体中指定一个用户 ID，并期望服务器更新相应的用户。

正如你所看到的，这两个选项都有效。一个常见的用例是使用`POST`进行创建（因为大多数情况下，服务器应该负责 ID），并使用`PUT`来更新已知 ID 的资源。

服务器也可能允许部分修改资源（而不需要客户端发送完整的资源内容）。在这种情况下，它应该响应`PATCH`方法。

在这个级别上，我也鼓励你在提供响应时使用有意义的 HTTP 代码。我们马上会看到最常见的代码。

## Level 3 - 超媒体控制

超媒体控制也被称为**超文本作为应用状态的引擎**（**HATEOAS**）。在这个生僻的首字母缩略词背后，隐藏着 RESTful 服务最重要的特性：通过超文本链接使其可发现。这本质上是服务器告诉客户端它的选项是什么，使用响应头或响应实体。

例如，在使用`PUT`创建资源后，服务器应该返回一个带有`201 CREATED`代码的响应，并发送一个包含创建的资源 URI 的`Location`头。

没有一个标准定义了 API 其他部分的链接应该是什么样子。Spring Data REST，一个允许你使用最少的配置创建 RESTful 后端的 Spring 项目，通常会输出这样：

```java

{
 "_links" : {
 "people" : {
 "href" : "http://localhost:8080/users{?page,size,sort}",
 "templated" : true
 }
 }
}

```

然后，去`/users`：

```java

{
 "_links" : {
 "self" : {
 "href" : "http://localhost:8080/users{?page,size,sort}",
 "templated" : true
 },
 "search" : {
 "href" : "http://localhost:8080/users/search"
 }
 },
 "page" : {
 "size" : 20,
 "totalElements" : 0,
 "totalPages" : 0,
 "number" : 0
 }
}

```

这给了你一个关于你可以用 API 做什么的好主意，不是吗？

# API 版本控制

如果第三方客户端使用你的 API，你可以考虑对 API 进行版本控制，以避免在更新应用程序时出现破坏性变化。

对 API 进行版本控制通常是提供一组稳定资源在子域下可用的问题。例如，GitLab 维护其 API 的三个版本。它们可以在`https://example/api/v3`下访问，等等。像软件中的许多架构决策一样，版本控制是一种权衡。

设计这样的 API 并识别 API 中的破坏性变化将需要更多的工作。通常情况下，添加新字段不会像移除或转换 API 实体结果或请求那样成为问题。

大多数情况下，您将负责 API 和客户端，因此不需要这样的复杂性。

### 注意

有关 API 版本控制的更深入讨论，请参阅此博客文章：

[`www.troyhunt.com/2014/02/your-api-versioning-is-wrong-which-is.html`](http://www.troyhunt.com/2014/02/your-api-versioning-is-wrong-which-is.html)

# 有用的 HTTP 代码

良好的 RESTful API 的另一个重要方面是以明智的方式使用 HTTP 代码。HTTP 规范定义了许多标准代码。它们应该涵盖良好 API 需要向其用户传达的 99%内容。以下列表包含最重要的代码，每个 API 都应该使用并且每个开发人员都应该知道：

| 代码 | 意义 | 用法 |
| --- | --- | --- |
| **2xx - 成功** | **当一切顺利时使用这些代码。** |   |
| `200` | 一切正常。 | 请求成功。 |
| `201` | 已创建资源 | 资源已成功创建。响应应包括与创建相关联的位置列表。 |
| `204` | 没有内容可返回。 | 服务器已成功处理请求，但没有内容可返回。 |
| **3xx - 重定向** | **当客户端需要进一步操作以满足请求时使用这些代码**。 |   |
| `301` | 永久移动 | 资源的 URI 已更改，并且其新位置在`Location`标头中指示。 |
| `304` | 资源未被修改。 | 资源自上次以来未发生更改。此响应必须包括日期、ETag 和缓存信息。 |
| **4xx - 客户端错误** | **由于客户端的错误而导致请求未成功执行**。 |   |
| `400` | 错误的请求 | 服务器无法理解客户端发送的数据。 |
| `403` | 禁止 | 请求已理解但不允许。这可以丰富错误描述信息。 |
| `404` | 未找到 | 没有与此 URI 匹配的内容。这可以用来替代 403，如果不应该透露有关安全性的信息。 |
| `409` | 冲突 | 请求与另一个修改冲突。响应应包括有关如何解决冲突的信息。 |
| **5xx - 服务器错误** | **服务器端发生错误**。 |   |
| `500` | 内部服务器错误 | 服务器意外地未能处理请求。 |

### 注意

有关更详细的列表，请参阅[`www.restapitutorial.com/httpstatuscodes.html`](http://www.restapitutorial.com/httpstatuscodes.html)。

# 客户是王者

我们将允许第三方客户端通过 REST API 检索搜索结果。这些结果将以 JSON 或 XML 的形式提供。

我们希望处理`/api/search/mixed;keywords=springFramework`形式的请求。这与我们已经创建的搜索表单非常相似，只是请求路径以`api`开头。在此命名空间中找到的每个 URI 都应返回二进制结果。

让我们在`search.api`包中创建一个新的`SearchApiController`类：

```java
package masterSpringMvc.search.api;

import masterSpringMvc.search.SearchService;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.twitter.api.Tweet;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api/search")
public class SearchApiController {
    private SearchService searchService;

    @Autowired
    public SearchApiController(SearchService searchService) {
        this.searchService = searchService;
    }

    @RequestMapping(value = "/{searchType}", method = RequestMethod.GET)
    public List<Tweet> search(@PathVariable String searchType, @MatrixVariable List<String> keywords) {
        return searchService.search(searchType, keywords);
    }
}
```

这与我们以前的控制器非常相似，有三个细微的差异：

+   控制器类使用`@RequestMapping`注解。这将是我们的基本地址，并将前缀在此控制器中声明的每个其他映射。

+   我们不再重定向到视图，而是在搜索方法中返回一个普通对象。

+   控制器使用`@RestController`而不是`@Controller`进行注释。

`RestController`是一种快捷方式，用于声明将每个响应返回为如果使用`@ResponseBody`注解进行注释的控制器。它告诉 Spring 将返回类型序列化为适当的格式，默认为 JSON。

在使用 REST API 时，一个良好的实践是始终指定您将响应的方法。对于`GET`或`POST`方法，请求能够以相同的方式处理的可能性非常小。

如果您访问`http://localhost:8080/api/search/mixed;keywords=springFramework`，您应该会得到一个非常大的结果，如下所示：

![客户端是王者](img/image00963.jpeg)

确实，Spring 自动处理了整个`Tweet`类的属性的序列化，使用了 Jackson。

# 调试 RESTful API

使用浏览器，您只能对特定 API 执行`GET`请求。好的工具将使您的开发变得更简单。有很多工具可以测试 RESTful API。我只会列出我使用和喜爱的工具。

## JSON 格式化扩展

通常，您只会测试`GET`方法，您的第一反应将是将地址复制到浏览器中检查结果。在这种情况下，您有可能获得更多的内容，而不仅仅是纯文本，例如 Chrome 的 JSON Formatter 或 Firefox 的 JSONView 等扩展。

## 浏览器中的 RESTful 客户端

浏览器是处理 HTTP 请求的自然工具。然而，使用地址栏很少能够详细测试您的 API。

Postman 是 Chrome 的一个扩展，RESTClient 是其 Firefox 的对应物。它们都具有类似的功能，例如创建和共享查询集合、修改标头以及处理身份验证（基本、摘要和 OAuth）。在撰写本文时，只有 RESTClient 处理 OAuth2。

## httpie

**httpie**是一个类似 curl 但面向 REST 查询的命令行实用程序。它允许您输入诸如此类的命令：

```java

http PUT httpbin.org/put hello=world

```

这比这个丑陋的版本要友好得多：

```java

curl -i -X PUT httpbin.org/put -H Content-Type:application/json -d '{"hello": "world"}'

```

# 自定义 JSON 输出

使用我们的工具，我们能够轻松地查看服务器生成的请求。它很大。默认情况下，Spring Boot 使用的 JSON 序列化库 Jackson 将序列化所有可以通过 getter 方法访问的内容。

我们希望有一些更轻量级的东西，比如这样：

```java
{
 "text": "original text",
 "user": "some_dude",
 "profileImageUrl": "url",
 "lang": "en",
 "date": 2015-04-15T20:18:55,
 "retweetCount": 42
}

```

自定义将被序列化的字段的最简单方法是向我们的 bean 添加注释。您可以在类级别使用`@JsonIgnoreProperties`注释来忽略一组属性，或者在希望忽略的属性的 getter 上添加`@JsonIgnore`。

在我们的情况下，`Tweet`类不是我们自己的类。它是 Spring Social Twitter 的一部分，我们无法对其进行注释。

直接使用模型类进行序列化很少是一个好选择。这将使您的模型与您的序列化库绑定在一起，而这应该保持为一个实现细节。

在处理不可修改的代码时，Jackson 提供了两个选项：

+   创建一个专门用于序列化的新类。

+   使用 mixins，这些是简单的类，将与您的模型关联起来。这些将在您的代码中声明，并且可以用任何 Jackson 注释进行注释。

由于我们只需要对模型的字段进行一些简单的转换（大量隐藏和少量重命名），我们可以选择使用 mixins。

这是一种良好的、非侵入式的方式，可以通过一个简单的类或接口在运行时重命名和排除字段。

另一种指定应用程序不同部分中使用的字段子集的选项是使用`@JsonView`注解对其进行注释。这不会在本章中涵盖，但我鼓励您查看这篇优秀的博客文章[`spring.io/blog/2014/12/02/latest-jackson-integration-improvements-in-spring`](https://spring.io/blog/2014/12/02/latest-jackson-integration-improvements-in-spring)。

我们希望能够控制我们 API 的输出，所以让我们创建一个名为`LightTweet`的新类，可以从一条推文中构建出来：

```java
package masterSpringMvc.search;

import org.springframework.social.twitter.api.Tweet;
import org.springframework.social.twitter.api.TwitterProfile;

import java.time.LocalDateTime;
import java.time.ZoneId;
import java.util.Date;

public class LightTweet {
    private String profileImageUrl;
    private String user;
    private String text;
    private LocalDateTime date;
    private String lang;
    private Integer retweetCount;

    public LightTweet(String text) {
        this.text = text;
    }

    public static LightTweet ofTweet(Tweet tweet) {
        LightTweet lightTweet = new LightTweet(tweet.getText());
        Date createdAt = tweet.getCreatedAt();
        if (createdAt != null) {
            lightTweet.date = LocalDateTime.ofInstant(createdAt.toInstant(), ZoneId.systemDefault());
        }
        TwitterProfile tweetUser = tweet.getUser();
        if (tweetUser != null) {
            lightTweet.user = tweetUser.getName();
            lightTweet.profileImageUrl = tweetUser.getProfileImageUrl();
        }
        lightTweet.lang = tweet.getLanguageCode();
        lightTweet.retweetCount = tweet.getRetweetCount();
        return lightTweet;
    }

  // don't forget to generate getters
  // They are used by Jackson to serialize objects
}
```

现在我们需要让我们的`SearchService`类返回`LightTweets`类而不是 tweets：

```java
    public List<LightTweet> search(String searchType, List<String> keywords) {
        List<SearchParameters> searches = keywords.stream()
                .map(taste -> createSearchParam(searchType, taste))
                .collect(Collectors.toList());

        List<LightTweet> results = searches.stream()
                .map(params -> twitter.searchOperations().search(params))
                .flatMap(searchResults -> searchResults.getTweets().stream())
                .map(LightTweet::ofTweet)
                .collect(Collectors.toList());

        return results;
    }
```

这将影响`SearchApiController`类的返回类型，以及`SearchController`类中的 tweets 模型属性。在这两个类中进行必要的修改。

我们还需要更改`resultPage.html`文件的代码，因为一些属性已更改（我们不再有嵌套的`user`属性）：

```java
<ul class="collection">
    <li class="collection-item avatar" th:each="tweet : ${tweets}">
        <img th:src="img/strong>}" alt="" class="circle"/>
        <span class="title" th:text="${tweet.user}">Username</span>

        <p th:text="${tweet.text}">Tweet message</p>
    </li>
</ul>
```

我们快要完成了。如果重新启动应用程序并转到`http://localhost:8080/api/search/mixed;keywords=springFramework`，您会发现日期格式不是我们期望的那个：

![自定义 JSON 输出](img/image00964.jpeg)

这是因为 Jackson 没有内置对 JSR-310 日期的支持。幸运的是，这很容易解决。只需将以下库添加到 build.gradle 文件中的依赖项中：

```java
compile 'com.fasterxml.jackson.datatype:jackson-datatype-jsr310'
```

这确实改变了日期格式，但现在它输出的是一个数组而不是格式化的日期。

要更改这一点，我们需要了解库做了什么。它包括一个名为 JSR-310 Module 的新 Jackson 模块。Jackson 模块是一个扩展点，用于自定义序列化和反序列化。这个模块将由 Spring Boot 在启动时自动注册到 JacksonAutoConfiguration 类中，该类将创建一个默认的 Jackson ObjectMapper 方法，并支持众所周知的模块。

我们可以看到前一个模块为 JSR-310 中定义的所有新类添加了一堆序列化器和反序列化器。这将尝试将每个日期转换为 ISO 格式，如果可能的话。请参阅[`github.com/FasterXML/jackson-datatype-jsr310`](https://github.com/FasterXML/jackson-datatype-jsr310)。

例如，如果我们仔细看 LocalDateTimeSerializer，我们会发现它实际上有两种模式，并且可以使用称为 WRITE_DATES_AS_TIMESTAMPS 的序列化特性在两种模式之间切换。

要定义此属性，我们需要自定义 Spring 的默认对象映射器。从自动配置中可以看出，Spring MVC 提供了一个实用类来创建我们可以使用的 ObjectMapper 方法。将以下 bean 添加到您的 WebConfiguration 类中：

```java
@Bean
@Primary
public ObjectMapper objectMapper(Jackson2ObjectMapperBuilder builder) {
   ObjectMapper objectMapper = builder.createXmlMapper(false).build();
   objectMapper.configure(SerializationFeature.WRITE_DATES_AS_TIMESTAMPS, false);
   return objectMapper;
}
```

这次，我们完成了，日期已经格式化正确，如您在这里所见：

![自定义 JSON 输出](img/image00965.jpeg)

# 用户管理 API

我们的搜索 API 非常好，但让我们做一些更有趣的事情。像许多 Web 应用程序一样，我们将需要一个用户管理模块来识别我们的用户。为此，我们将创建一个新的 user 包。在此包中，我们将添加一个模型类，如下所示：

```java
package masterSpringMvc.user;

import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

public class User {
    private String twitterHandle;
    private String email;
    private LocalDate birthDate;
    private List<String> tastes = new ArrayList<>();

    // Getters and setters for all fields
}
```

由于我们暂时不想使用数据库，我们将在同一个包中创建一个 UserRepository 类，由一个简单的 Map 支持：

```java
package masterSpringMvc.user;

import org.springframework.stereotype.Repository;

import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.concurrent.ConcurrentHashMap;

@Repository
public class UserRepository {
    private final Map<String, User> userMap = new ConcurrentHashMap<>();

    public User save(String email, User user) {
        user.setEmail(email);
        return userMap.put(email, user);
    }

    public User save(User user) {
        return save(user.getEmail(), user);
    }

    public User findOne(String email) {
        return userMap.get(email);
    }

    public List<User> findAll() {
        return new ArrayList<>(userMap.values());
    }

    public void delete(String email) {
        userMap.remove(email);
    }

    public boolean exists(String email) {
        return userMap.containsKey(email);
    }
}
```

最后，在 user.api 包中，我们将创建一个非常天真的控制器实现：

```java
package masterSpringMvc.user.api;

import masterSpringMvc.user.User;
import masterSpringMvc.user.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api")
public class UserApiController {

    private UserRepository userRepository;

    @Autowired
    public UserApiController(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    @RequestMapping(value = "/users", method = RequestMethod.GET)
    public List<User> findAll() {
        return userRepository.findAll();
    }

    @RequestMapping(value = "/users", method = RequestMethod.POST)
    public User createUser(@RequestBody User user) {
        return userRepository.save(user);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.PUT)
    public User updateUser(@PathVariable String email, @RequestBody User user) {
        return userRepository.save(email, user);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.DELETE)
    public void deleteUser(@PathVariable String email) {
        userRepository.delete(email);
    }
}
```

我们使用 RESTful 存储库实现了所有经典的 CRUD 操作，使用用户的电子邮件地址作为唯一标识符。

在这种情况下，您将很快面临问题，因为 Spring 会删除点后面找到的内容。解决方案与我们在 URL 映射中使用的支持 URL 中的分号的解决方案非常相似，该解决方案在第三章中有所介绍，*文件上传和错误处理*。

在我们已经在 WebConfiguration 类中定义的 configurePathMatch（）方法中添加 useRegisteredSuffixPatternMatch 属性，该属性设置为 false：

```java
@Override
public void configurePathMatch(PathMatchConfigurer configurer) {
    UrlPathHelper urlPathHelper = new UrlPathHelper();
    urlPathHelper.setRemoveSemicolonContent(false);
    configurer.setUrlPathHelper(urlPathHelper);
    configurer.setUseRegisteredSuffixPatternMatch(true);
}
```

现在我们已经有了 API，可以开始与之交互了。

以下是一些使用 httpie 的示例命令：

```java

~ $ http get http://localhost:8080/api/users
HTTP/1.1 200 OK
Content-Type: application/json;charset=UTF-8
Date: Mon, 20 Apr 2015 00:01:08 GMT
Server: Apache-Coyote/1.1
Transfer-Encoding: chunked

[]

~ $ http post http://localhost:8080/api/users email=geo@springmvc.com birthDate=2011-12-12 tastes:='["spring"]'
HTTP/1.1 200 OK
Content-Length: 0
Date: Mon, 20 Apr 2015 00:02:07 GMT
Server: Apache-Coyote/1.1

~ $ http get http://localhost:8080/api/users
HTTP/1.1 200 OK
Content-Type: application/json;charset=UTF-8
Date: Mon, 20 Apr 2015 00:02:13 GMT
Server: Apache-Coyote/1.1
Transfer-Encoding: chunked

[
 {
 "birthDate": "2011-12-12",
 "email": "geo@springmvc.com",
 "tastes": [
 "spring"
 ],
 "twitterHandle": null
 }
]

~ $ http delete http://localhost:8080/api/user/geo@springmvc.com
HTTP/1.1 200 OK
Content-Length: 0
Date: Mon, 20 Apr 2015 00:02:42 GMT
Server: Apache-Coyote/1.1

~ $ http get http://localhost:8080/api/users
HTTP/1.1 200 OK
Content-Type: application/json;charset=UTF-8
Date: Mon, 20 Apr 2015 00:02:46 GMT
Server: Apache-Coyote/1.1
Transfer-Encoding: chunked

[]

```

这很好，但不够好。状态码还没有处理。我们需要更多的 RESTfulness 来爬上 Richardson 阶梯。

# 状态码和异常处理

我们要做的第一件事是正确处理响应状态。默认情况下，Spring 会自动处理一些状态：

+   `500 Server Error`：表示处理请求时发生异常。

+   `405 Method not Supported`：当在现有处理程序上使用不正确的方法时出现。

+   `404 Not Found`：当处理程序不存在时出现。

+   `400 Bad Request`：表示请求体或参数与服务器的期望不匹配。

+   `200 OK`：对于任何没有错误处理的请求抛出。

使用 Spring MVC，有两种返回状态码的方式：

+   从 REST 控制器返回 ResponseEntity 类

+   抛出一个异常，将在专用处理程序中捕获

## 使用 ResponseEntity 的状态码

HTTP 协议规定我们在创建新用户时应返回`201 Created`状态。在我们的 API 中，可以使用`POST`方法实现这一点。在处理不存在的实体时，我们还需要抛出一些 404 错误。

Spring MVC 有一个将 HTTP 状态与响应实体关联起来的类，称为`ResponseEntity`。让我们更新我们的`UserApiController`类来处理错误代码：

```java
package masterSpringMvc.user.api;

import masterSpringMvc.user.User;
import masterSpringMvc.user.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api")
public class UserApiController {

    private UserRepository userRepository;

    @Autowired
    public UserApiController(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    @RequestMapping(value = "/users", method = RequestMethod.GET)
    public List<User> findAll() {
        return userRepository.findAll();
    }

    @RequestMapping(value = "/users", method = RequestMethod.POST)
    public ResponseEntity<User> createUser(@RequestBody User user) {
        HttpStatus status = HttpStatus.OK;
        if (!userRepository.exists(user.getEmail())) {
            status = HttpStatus.CREATED;
        }
        User saved = userRepository.save(user);
        return new ResponseEntity<>(saved, status);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.PUT)
    public ResponseEntity<User> updateUser(@PathVariable String email, @RequestBody User user) {
        if (!userRepository.exists(user.getEmail())) {
            return new ResponseEntity<>(HttpStatus.NOT_FOUND);
        }
        User saved = userRepository.save(email, user);
        return new ResponseEntity<>(saved, HttpStatus.CREATED);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.DELETE)
    public ResponseEntity<User> deleteUser(@PathVariable String email) {
        if (!userRepository.exists(email)) {
            return new ResponseEntity<>(HttpStatus.NOT_FOUND);
        }
        userRepository.delete(email);
        return new ResponseEntity<>(HttpStatus.OK);
    }
}
```

您可以看到我们朝着第一级 RESTful 发展，但涉及了大量样板代码。

## 异常状态代码

在我们的 API 中处理错误的另一种方法是抛出异常。有两种方法可以将异常映射到 Spring MVC 中：

+   在类级别使用`@ExceptionHandler`，就像我们在第三章中的上传控制器中对`IOException`所做的那样，*文件上传和错误处理*

+   使用`@ControllerAdvice`来捕获所有控制器抛出的全局异常或一部分控制器抛出的异常

这两个选项可以帮助您做出一些面向业务的决策，并在应用程序中定义一套实践。

要将这些处理程序与 HTTP 状态代码关联起来，我们可以在注释方法中注入响应，并使用`HttpServletResponse.sendError()`方法，或者只需在方法上注释`@ResponseStatus`注解。

我们将定义自己的异常，`EntityNotFoundException`。当用户正在处理的实体找不到时，我们的业务存储库将抛出此异常。这将有助于简化 API 代码。

这是异常的代码。我们可以将其放在一个名为`error`的新包中：

```java
package masterSpringMvc.error;

public class EntityNotFoundException extends Exception {
    public EntityNotFoundException(String message) {
        super(message);
    }

    public EntityNotFoundException(String message, Throwable cause) {
        super(message, cause);
    }
}
```

我们的存储库现在将在各个位置抛出异常。我们还将区分保存和更新用户：

```java
package masterSpringMvc.user;

import masterSpringMvc.error.EntityNotFoundException;
import org.springframework.stereotype.Repository;

import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.concurrent.ConcurrentHashMap;

@Repository
public class UserRepository {
    private final Map<String, User> userMap = new ConcurrentHashMap<>();

    public User update(String email, User user) throws EntityNotFoundException {
        if (!exists(email)) {
            throw new EntityNotFoundException("User " + email + " cannot be found");
        }
        user.setEmail(email);
        return userMap.put(email, user);
    }

    public User save(User user) {
        return userMap.put(user.getEmail(), user);
    }

    public User findOne(String email) throws EntityNotFoundException {
        if (!exists(email)) {
            throw new EntityNotFoundException("User " + email + " cannot be found");
        }
        return userMap.get(email);
    }

    public List<User> findAll() {
        return new ArrayList<>(userMap.values());
    }

    public void delete(String email) throws EntityNotFoundException {
        if (!exists(email)) {
            throw new EntityNotFoundException("User " + email + " cannot be found");
        }
        userMap.remove(email);
    }

    public boolean exists(String email) {
        return userMap.containsKey(email);
    }
}
```

我们的控制器变得更简单，因为它不必处理 404 状态。我们现在从我们的控制器方法中抛出`EntityNotFound`异常：

```java
package masterSpringMvc.user.api;

import masterSpringMvc.error.EntityNotFoundException;
import masterSpringMvc.user.User;
import masterSpringMvc.user.UserRepository;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.http.HttpStatus;
import org.springframework.http.ResponseEntity;
import org.springframework.web.bind.annotation.*;

import java.util.List;

@RestController
@RequestMapping("/api")
public class UserApiController {

    private UserRepository userRepository;

    @Autowired
    public UserApiController(UserRepository userRepository) {
        this.userRepository = userRepository;
    }

    @RequestMapping(value = "/users", method = RequestMethod.GET)
    public List<User> findAll() {
        return userRepository.findAll();
    }

    @RequestMapping(value = "/users", method = RequestMethod.POST)
    public ResponseEntity<User> createUser(@RequestBody User user) {
        HttpStatus status = HttpStatus.OK;
        if (!userRepository.exists(user.getEmail())) {
            status = HttpStatus.CREATED;
        }
        User saved = userRepository.save(user);
        return new ResponseEntity<>(saved, status);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.PUT)
    public ResponseEntity<User> updateUser(@PathVariable String email, @RequestBody User user) throws EntityNotFoundException {
        User saved = userRepository.update(email, user);
        return new ResponseEntity<>(saved, HttpStatus.CREATED);
    }

    @RequestMapping(value = "/user/{email}", method = RequestMethod.DELETE)
    public ResponseEntity<User> deleteUser(@PathVariable String email) throws EntityNotFoundException {
        userRepository.delete(email);
        return new ResponseEntity<>(HttpStatus.OK);
    }
}
```

如果我们不处理此异常，Spring 将默认抛出 500 错误。为了处理它，我们将在错误包中创建一个小类，就在我们的`EntityNotFoundException`类旁边。它将被称为`EntityNotFoundMapper`类，并负责处理异常：

```java
package masterSpringMvc.error;

import org.springframework.http.HttpStatus;
import org.springframework.web.bind.annotation.ControllerAdvice;
import org.springframework.web.bind.annotation.ExceptionHandler;
import org.springframework.web.bind.annotation.ResponseStatus;

@ControllerAdvice
public class EntityNotFoundMapper {

    @ExceptionHandler(EntityNotFoundException.class)
    @ResponseStatus(value = HttpStatus.NOT_FOUND, reason = "Entity could not be found")
    public void handleNotFound() {
    }
}
```

@ControllerAdvice`注解允许我们通过对 bean 进行注解来为一组控制器添加一些行为。这些控制器建议可以处理异常，还可以使用`@ModelAttribute`声明模型属性或使用`@InitBinder`声明验证器策略。

通过我们刚刚编写的代码，我们可以在一个地方处理我们的控制器抛出的所有`EntityNotFoundException`类，并将其与 404 状态关联起来。这样，我们可以抽象这个概念，并确保我们的应用程序在所有控制器中一致地处理它。

我们不打算在我们的 API 中处理超链接。相反，我鼓励您查看 Spring HATEOAS 和 Spring Data REST，它们提供了非常优雅的解决方案，使您的资源更易发现。

# Swagger 文档

Swagger 是一个非常棒的项目，它可以让您在 HTML5 网页中记录和与 API 进行交互。以下截图展示了 API 文档：

![Swagger 文档](img/image00966.jpeg)

Swagger 以前很庞大（用 Scala 编写）并且在 Spring 设置中有些复杂。自 2.0 版本以来，该库已经被重写，一个名为`spring-fox`的非常整洁的项目将允许轻松集成。

### 注意

`spring-fox`，以前称为`swagger-springmvc`，已经存在三年多了，仍然是一个非常活跃的项目。

将以下依赖项添加到构建文件中：

```java
compile 'io.springfox:springfox-swagger2:2.1.2'
compile 'io.springfox:springfox-swagger-ui:2.1.2'
```

第一个将提供一个注解，以在您的应用程序中启用 Swagger，并使用注解描述您的资源。Swagger 然后将生成您的 API 的 JSON 表示。

第二个是一个 WebJar，其中包含通过 Web 客户端使用生成的 JSON 的静态资源。

现在您唯一需要做的就是将`@EnableSwagger2`注解添加到您的`WebConfiguration`类中：

```java
@Configuration
@EnableSwagger2
public class WebConfiguration extends WebMvcConfigurerAdapter {
 }
```

我们刚刚添加的`swagger-ui.jar`文件中包含了`META-INF/resources`中的 HTML 文件。

当您访问`http://localhost:8080/swagger-ui.html`时，Spring Boot 会自动提供它。

默认情况下，Springfox 将扫描整个类路径，并显示应用程序中声明的所有请求映射。

在我们的情况下，我们只想公开 API：

```java
@Bean
public Docket userApi() {
    return new Docket(DocumentationType.SWAGGER_2)
        .select()
        .paths(path -> path.startsWith("/api/"))
        .build();
}
```

Springfox 与`Docket`组合一起工作，您必须在配置类中定义它们作为 bean。它们是 RESTful 资源的逻辑分组。一个应用程序可以有很多。

查看文档（[`springfox.github.io/springfox`](http://springfox.github.io/springfox)）以查看所有可用的不同设置。

# 生成 XML

RESTful API 有时会以不同的媒体类型（JSON、XML 等）返回响应。负责选择正确媒体类型的机制在 Spring 中称为内容协商。

在 Spring MVC 中，默认情况下，`ContentNegotiatingViewResolver` bean 将负责根据应用程序中定义的内容协商策略来解析正确的内容。

您可以查看`ContentNegotiationManagerFactoryBean`，了解这些策略在 Spring MVC 中是如何应用的。

内容类型可以通过以下策略解析：

+   根据客户端发送的`Accept`头部

+   使用参数，如`?format=json`

+   使用路径扩展，如`/myResource.json`或`/myResource.xml`

您可以通过覆盖`WebMvcConfigurerAdapter`类的`configureContentNegotiation()`方法来自定义这些策略在 Spring 配置中的使用。

默认情况下，Spring 将使用`Accept`头部和路径扩展。

要在 Spring Boot 中启用 XML 序列化，您可以将以下依赖项添加到类路径中：

```java
compile 'com.fasterxml.jackson.dataformat:jackson-dataformat-xml'
```

如果您使用浏览器浏览您的 API 并转到`http://localhost:8080/api/users`，您将看到以下结果为 XML：

![生成 XML](img/image00967.jpeg)

这是因为您的浏览器通常不会请求 JSON，但 XML 在 HTML 之后。如下截图所示：

![生成 XML](img/image00968.jpeg)

要获取 JSON，您可以转到`http://localhost:8080/api/users.json`，或者使用 Postman 或 httpie 发送适当的`Accept`头部。

# 检查点

在本章中，我们添加了一个搜索`ApiController`类。因为 Twitter API 返回的推文不适合我们的使用，我们引入了一个`LightTweet`类来将它们转换为更友好的格式。

我们还开发了一个用户 API。`User`类是模型。用户通过`UserRepository`类存储和检索，`UserApiController`类公开 HTTP 端点以执行用户的 CRUD 操作。我们还添加了一个通用异常和一个将异常与 HTTP 状态关联的映射器。

在配置中，我们添加了一个文档化我们的 API 的 bean，感谢 Swagger，并且我们自定义了 JSR-310 日期的序列化。我们的代码库应该如下所示：

![检查点](img/image00969.jpeg)

# 总结

在本章中，我们已经看到如何使用 Spring MVC 创建 RESTful API。这种后端在性能和维护方面都有很大的好处，当与 JavaScript MVC 框架（如 Backbone、Angular JS 或 React.js）配合使用时，效果更佳。

我们看到了如何正确处理错误和异常，并学会了如何利用 HTTP 状态来创建更好的 API。

最后，我们使用 Swagger 添加了自动文档，并增加了生成 XML 和 JSON 的能力。

在下一章中，我们将学习如何保护我们的应用程序，并使用 Twitter API 注册我们的用户。

# 第五章。保护您的应用程序

在本章中，我们将学习如何保护我们的 Web 应用程序，以及如何应对现代分布式 Web 应用程序的安全挑战。

本章将分为五个部分：

+   首先，我们将在几分钟内设置基本的 HTTP 认证

+   然后，我们将为网页设计基于表单的认证，保留 RESTful API 的基本认证

+   我们将允许用户通过 Twitter OAuth API 进行注册

+   然后，我们将利用 Spring Session 来确保我们的应用程序可以使用分布式会话机制进行扩展

+   最后，我们将配置 Tomcat 使用 SSL 进行安全连接

# 基本认证

最简单的身份验证机制是基本认证（[`en.wikipedia.org/wiki/Basic_access_authentication`](http://en.wikipedia.org/wiki/Basic_access_authentication)）。简而言之，如果没有用户名和密码，我们的页面将无法访问。

我们的服务器将通过发送“401 未经授权”的 HTTP 状态码并生成`WWW-Authenticate`头来指示我们的资源受到保护。

为了成功通过安全检查，客户端必须发送一个包含`Basic`值后面跟着`user:password`字符串的 base 64 编码的`Authorization`头。浏览器窗口将提示用户输入用户名和密码，如果认证成功，用户将获得对受保护页面的访问权限。

让我们将 Spring Security 添加到我们的依赖项中：

```java
compile 'org.springframework.boot:spring-boot-starter-security'
```

重新启动应用程序并导航到应用程序中的任何 URL。系统将提示您输入用户名和密码：

![基本认证](img/image00970.jpeg)

如果您未能进行身份验证，您将看到抛出`401`错误。默认用户名是`user`。身份验证的正确密码将在每次应用程序启动时随机生成，并显示在服务器日志中：

```java

Using default security password: 13212bb6-8583-4080-b790-103408c93115

```

默认情况下，Spring Security 保护除`/css/`、`/js/`、`/images/`和`**/favicon.ico`等少数经典路由之外的所有资源。

如果您希望配置默认凭据，可以将以下属性添加到`application.properties`文件中：

```java
security.user.name=admin
security.user.password=secret
```

## 授权用户

在我们的应用程序中只有一个用户不允许进行细粒度的安全控制。如果我们想要更多地控制用户凭据，我们可以在`config`包中添加以下`SecurityConfiguration`类：

```java
package masterSpringMvc.config;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.authentication.builders.AuthenticationManagerBuilder;
import org.springframework.security.config.annotation.method.configuration.EnableGlobalMethodSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;

@Configuration
@EnableGlobalMethodSecurity(securedEnabled = true)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Autowired
    public void configureAuth(AuthenticationManagerBuilder auth)
            throws Exception {
        auth.inMemoryAuthentication()
                .withUser("user").password("user").roles("USER").and()
                .withUser("admin").password("admin").roles("USER", "ADMIN");
    }
}
```

这段代码将设置一个包含我们应用程序用户及其角色的内存系统。它将覆盖先前在应用程序属性中定义的安全名称和密码。

`@EnableGlobalMethodSecurity`注释将允许我们对应用程序的方法和类进行注释，以定义它们的安全级别。

例如，假设我们的应用程序只有管理员才能访问用户 API。在这种情况下，我们只需在资源中添加`@Secured`注释，以允许仅对 ADMIN 角色进行访问：

```java
@RestController
@RequestMapping("/api")
@Secured("ROLE_ADMIN")
public class UserApiController {
  // ... code omitted
}
```

我们可以使用 httpie 轻松测试，通过使用`-a`开关使用基本认证和`-p=h`开关，只显示响应头。

让我们尝试一下没有管理员配置文件的用户：

```java

> http GET 'http://localhost:8080/api/users' -a user:user -p=h
HTTP/1.1 403 Forbidden
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Content-Type: application/json;charset=UTF-8
Date: Sat, 23 May 2015 17:40:09 GMT
Expires: 0
Pragma: no-cache
Server: Apache-Coyote/1.1
Set-Cookie: JSESSIONID=2D4761C092EDE9A4DB91FA1CAA16C59B; Path=/; HttpOnly
Transfer-Encoding: chunked
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

```

现在，使用管理员：

```java

> http GET 'http://localhost:8080/api/users' -a admin:admin -p=h
HTTP/1.1 200 OK
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Content-Type: application/json;charset=UTF-8
Date: Sat, 23 May 2015 17:42:58 GMT
Expires: 0
Pragma: no-cache
Server: Apache-Coyote/1.1
Set-Cookie: JSESSIONID=CE7A9BF903A25A7A8BAD7D4C30E59360; Path=/; HttpOnly
Transfer-Encoding: chunked
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

```

您还会注意到 Spring Security 自动添加了一些常见的安全头：

+   `Cache Control`：这可以防止用户缓存受保护的资源

+   `X-XSS-Protection`：这告诉浏览器阻止看起来像 CSS 的东西

+   `X-Frame-Options`：这将禁止我们的网站嵌入到 IFrame 中

+   `X-Content-Type-Options`：这可以防止浏览器猜测用于伪造 XSS 攻击的恶意资源的 MIME 类型

### 注意

这些头的全面列表可在[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#headers`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#headers)上找到。

## 授权的 URL

注释我们的控制器非常容易，但并不总是最可行的选择。有时，我们只想完全控制我们的授权。

删除`@Secured`注释；我们将想出更好的办法。

让我们看看通过修改`SecurityConfiguration`类，Spring Security 允许我们做什么：

```java
@Configuration
@EnableGlobalMethodSecurity(securedEnabled = true)
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Autowired
    public void configureAuth(AuthenticationManagerBuilder auth)
        throws Exception {
        auth.inMemoryAuthentication()
            .withUser("user").password("user").roles("USER").and()
            .withUser("admin").password("admin").roles("USER", "ADMIN");
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .httpBasic()
            .and()
            .csrf().disable()
            .authorizeRequests()
            .antMatchers("/login", "/logout").permitAll()
            .antMatchers(HttpMethod.GET, "/api/**").hasRole("USER")
            .antMatchers(HttpMethod.POST, "/api/**").hasRole("ADMIN")
            .antMatchers(HttpMethod.PUT, "/api/**").hasRole("ADMIN")
            .antMatchers(HttpMethod.DELETE, "/api/**").hasRole("ADMIN")
            .anyRequest().authenticated();
    }
}
```

在前面的代码示例中，我们使用 Spring Security 的流畅 API 配置了应用程序的安全策略。

通过调用与不同安全问题相关的方法并与`and()`方法链接，此 API 允许我们全局配置 Spring Security。

我们刚刚定义的是基本身份验证，没有 CSRF 保护。所有用户将允许在`/login`和`/logout`上的请求。对 API 的`GET`请求只允许具有`USER`角色的用户，而对 API 的`POST`、`PUT`和`DELETE`请求只对具有 ADMIN 角色的用户可访问。最后，每个其他请求将需要任何角色的身份验证。

CSRF 代表**跨站点请求伪造**，指的是一种攻击，恶意网站会在其网站上显示一个表单，并在您的网站上发布表单数据。如果您网站的用户没有注销，`POST`请求将保留用户的 cookie，因此将被授权。

CSRF 保护将生成短暂的令牌，这些令牌将与表单数据一起发布。我们将在下一节中看到如何正确启用它；现在，让我们先禁用它。有关更多详细信息，请参见[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#csrf`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#csrf)。

### 注意

要了解有关授权请求 API 的更多信息，请查看[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#authorize-requests`](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#authorize-requests)。

## Thymeleaf 安全标签

有时，您需要显示来自身份验证层的数据，例如用户的名称和角色，或根据用户的权限隐藏和显示网页的一部分。`thymeleaf-extras-springsecurity`模块将允许我们这样做。

将以下依赖项添加到您的`build.gradle`文件中：

```java
compile 'org.thymeleaf.extras:thymeleaf-extras-springsecurity3'
```

使用此库，我们可以在`layout/default.html`的导航栏下添加一个小块，以显示已登录的用户：

```java
<!DOCTYPE html>
<html 

      >
<head>
  <!-- content trimmed -->
</head>
<body>

<!-- content trimmed -->
<nav>
    <div class="nav-wrapper indigo">
        <ul class="right">
        <!-- content trimmed -->
        </ul>
    </div>
</nav>
<div>
 You are logged as <b sec:authentication="name" /> with roles <span sec:authentication="authorities" />
 -
 <form th:action="@{/logout}" method="post" style="display: inline-block">
 <input type="submit" value="Sign Out" />
 </form>
 <hr/>
</div>

<section layout:fragment="content">
    <p>Page content goes here</p>
</section>

<!-- content trimmed -->
</body>
</html>
```

请注意 HTML 声明中的新命名空间和`sec:authentication`属性。它允许访问`org.springframework.security.core.Authentication`对象的属性，该对象表示当前登录的用户，如下截图所示：

![Thymeleaf 安全标签](img/image00971.jpeg)

暂时不要点击注销链接，因为它与基本身份验证不兼容。我们将在下一部分使其工作。

`lib`标签还有一些其他标签，例如用于检查用户授权的标签：

```java
<div sec:authorize="hasRole('ROLE_ADMIN')">
    You are an administrator
</div>
```

### 注意

请参阅[`github.com/thymeleaf/thymeleaf-extras-springsecurity`](https://github.com/thymeleaf/thymeleaf-extras-springsecurity)上可用的文档，以了解有关该库的更多信息。

# 登录表单

基本身份验证对于我们的 RESTful API 很好，但我们更希望有一个由我们团队精心设计的登录页面，以改善网页体验。

Spring Security 允许我们定义尽可能多的`WebSecurityConfigurerAdapter`类。我们将把我们的`SecurityConfiguration`类分成两部分：

+   `ApiSecurityConfiguration`：这将首先进行配置。这将使用基本身份验证保护 RESTful 端点。

+   `WebSecurityConfiguration`：然后将为我们应用程序的其余部分配置登录表单。

您可以删除或重命名`SecurityConfiguration`，并创建`ApiSecurityConfiguration`代替：

```java
@Configuration
@Order(1)
public class ApiSecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Autowired
    public void configureAuth(AuthenticationManagerBuilder auth)
        throws Exception {
        auth.inMemoryAuthentication()
            .withUser("user").password("user").roles("USER").and()
            .withUser("admin").password("admin").roles("USER", "ADMIN");
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .antMatcher("/api/**")
            .httpBasic().and()
            .csrf().disable()
            .authorizeRequests()
            .antMatchers(HttpMethod.GET).hasRole("USER")
            .antMatchers(HttpMethod.POST).hasRole("ADMIN")
            .antMatchers(HttpMethod.PUT).hasRole("ADMIN")
            .antMatchers(HttpMethod.DELETE).hasRole("ADMIN")
            .anyRequest().authenticated();
    }
}
```

请注意`@Order(1)`注解，这将确保在执行其他配置之前执行此配置。然后，创建第二个用于 Web 的配置，称为`WebSecurityConfiguration`：

```java
package masterSpringMvc.config;

import org.springframework.context.annotation.Configuration;
import org.springframework.security.config.annotation.web.builders.HttpSecurity;
import org.springframework.security.config.annotation.web.configuration.WebSecurityConfigurerAdapter;

@Configuration
public class WebSecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
                .formLogin()
                .defaultSuccessUrl("/profile")
                .and()
                .logout().logoutSuccessUrl("/login")
                .and()
                .authorizeRequests()
                .antMatchers("/webjars/**", "/login").permitAll()
                .anyRequest().authenticated();
    }
}
```

此代码的结果是，与`/api/**`匹配的任何内容都将受到基本身份验证的保护，而不受 CSRF 保护。然后，将加载第二个配置。它将保护其他所有内容。应用程序的这一部分中的所有内容都需要客户端进行身份验证，除了 WebJars 上的请求和登录页面上的请求（这将避免重定向循环）。

如果未经身份验证的用户尝试访问受保护的资源，他们将自动重定向到登录页面。

默认情况下，登录 URL 是`GET /login`。默认登录将通过`POST /login`请求发布，其中将包含三个值：用户名（`username`）、密码（`password`）和 CSRF 令牌（`_csrf`）。如果登录不成功，用户将被重定向到`/login?error`。默认注销页面是一个带有 CSRF 令牌的`POST /logout`请求。

现在，如果您尝试在应用程序上导航，此表单将自动生成！

如果您已经从以前的尝试中登录，请关闭浏览器；这将清除会话。

![登录表单](img/image00972.jpeg)

我们现在可以登录和退出应用程序了！

这很可爱，但我们可以用很少的努力做得更好。首先，我们将在`WebSecurityConfiguration`类中定义一个`/login`登录页面：

```java
@Override
protected void configure(HttpSecurity http) throws Exception {
    http
        .formLogin()
        .loginPage("/login") // <= custom login page
        .defaultSuccessUrl("/profile")
        // the rest of the configuration stays the same
}
```

这将让我们创建自己的登录页面。为此，我们需要一个非常简单的控制器来处理`GET login`请求。您可以在`authentication`包中创建一个：

```java
package masterSpringMvc.authentication;

import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;

@Controller
public class LoginController {

    @RequestMapping("/login")
    public String authenticate() {
        return "login";
    }
}
```

这将触发位于模板目录中的`login.html`页面的显示。让我们创建它：

```java
<!DOCTYPE HTML>
<html 

      layout:decorator="layout/default">
<head>
    <title>Login</title>
</head>
<body>
<div class="section no-pad-bot" layout:fragment="content">
    <div class="container">

        <h2 class="header center orange-text">Login</h2>

        <div class="row">
            <div id="errorMessage" class="card-panel red lighten-2" th:if="${param.error}">
                <span class="card-title">Invalid user name or password</span>
            </div>

            <form class="col s12" action="/login" method="post">
                <div class="row">
                    <div class="input-field col s12">
                        <input id="username" name="username" type="text" class="validate"/>
                        <label for="username">Username</label>
                    </div>
                </div>
                <div class="row">
                    <div class="input-field col s12">
                        <input id="password" name="password" type="password" class="validate"/>
                        <label for="password">Password</label>
                    </div>
                </div>
                <div class="row center">
                    <button class="btn waves-effect waves-light" type="submit" name="action">Submit
                        <i class="mdi-content-send right"></i>
                    </button>
                </div>
                <input type="hidden" th:name="${_csrf.parameterName}" th:value="${_csrf.token}"/>
            </form>
        </div>
    </div>
</div>
</body>
</html>
```

请注意，我们处理错误消息，并发布 CSRF 令牌。我们还使用默认的用户名和密码输入名称，但如果需要，这些是可配置的。结果看起来已经好多了！

![登录表单](img/image00973.jpeg)

您可以立即看到，Spring Security 默认为所有非经过身份验证的用户分配匿名凭据。

我们不应该向匿名用户显示登出按钮，因此我们可以将相应的 HTML 部分包装在`sec:authorize="isAuthenticated()"`中，只显示给经过身份验证的用户，如下所示：

```java
<div sec:authorize="isAuthenticated()">
    You are logged as <b sec:authentication="name"/> with roles <span sec:authentication="authorities"/>
    -
    <form th:action="@{/logout}" method="post" style="display: inline-block">
        <input type="submit" value="Sign Out"/>
    </form>
    <hr/>
</div>
```

# Twitter 身份验证

我们的应用程序与 Twitter 强烈集成，因此允许我们通过 Twitter 进行身份验证似乎是合乎逻辑的。

在继续之前，请确保您已在 Twitter 应用程序上启用了 Twitter 登录（[`apps.twitter.com`](https://apps.twitter.com)）：

![Twitter 身份验证](img/image00974.jpeg)

## 设置社交身份验证

Spring social 通过 OAuth 提供程序（如 Twitter）实现身份验证，通过登录/注册场景。它将拦截`/signin/twitter`上的`POST`请求。如果用户未知于`UsersConnectionRepository`接口，则将调用`signup`端点。这将允许我们采取必要措施在我们的系统上注册用户，也许要求他们提供额外的细节。

让我们开始工作。我们需要做的第一件事是将`signin/**`和`/signup` URL 添加为公开可用的资源。让我们修改我们的`WebSecurityConfiguration`类，更改`permitAll`行：

```java
.antMatchers("/webjars/**", "/login", "/signin/**", "/signup").permitAll()
```

为了启用登录/注册场景，我们还需要一个`SignInAdapter`接口，一个简单的监听器，当已知用户再次登录时将被调用。

我们可以在我们的`LoginController`旁边创建一个`AuthenticatingSignInAdapter`类。

```java
package masterSpringMvc.authentication;

import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.social.connect.Connection;
import org.springframework.social.connect.UserProfile;
import org.springframework.social.connect.web.SignInAdapter;
import org.springframework.stereotype.Component;
import org.springframework.web.context.request.NativeWebRequest;

@Component
public class AuthenticatingSignInAdapter implements SignInAdapter {

    public static void authenticate(Connection<?> connection) {
        UserProfile userProfile = connection.fetchUserProfile();
        String username = userProfile.getUsername();
        UsernamePasswordAuthenticationToken authentication = new UsernamePasswordAuthenticationToken(username, null, null);
        SecurityContextHolder.getContext().setAuthentication(authentication);
        System.out.println(String.format("User %s %s connected.", userProfile.getFirstName(), userProfile.getLastName()));
    }

    @Override
    public String signIn(String userId, Connection<?> connection, NativeWebRequest request) {
        authenticate(connection);
        return null;
    }
}
```

正如您所看到的，此处理程序在完美的时间调用，允许用户使用 Spring Security 进行身份验证。我们马上就会回到这一点。现在，我们需要在同一个包中定义我们的`SignupController`类，负责首次访问用户：

```java
package masterSpringMvc.authentication;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.social.connect.Connection;
import org.springframework.social.connect.ConnectionFactoryLocator;
import org.springframework.social.connect.UsersConnectionRepository;
import org.springframework.social.connect.web.ProviderSignInUtils;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.context.request.WebRequest;

@Controller
public class SignupController {
    private final ProviderSignInUtils signInUtils;

    @Autowired
    public SignupController(ConnectionFactoryLocator connectionFactoryLocator, UsersConnectionRepository connectionRepository) {
        signInUtils = new ProviderSignInUtils(connectionFactoryLocator, connectionRepository);
    }

    @RequestMapping(value = "/signup")
    public String signup(WebRequest request) {
        Connection<?> connection = signInUtils.getConnectionFromSession(request);
        if (connection != null) {
            AuthenticatingSignInAdapter.authenticate(connection);
            signInUtils.doPostSignUp(connection.getDisplayName(), request);
        }
        return "redirect:/profile";
    }
}
```

首先，此控制器从会话中检索当前连接。然后，它通过与之前相同的方法对用户进行身份验证。最后，它将触发`doPostSignUp`事件，这将允许 Spring Social 在我们之前提到的`UsersConnectionRepository`接口中存储与我们的用户相关的信息。

我们需要做的最后一件事是在我们的登录页面下方的前一个表单下面添加一个成功的“使用 Twitter 登录”按钮：

```java
<form th:action="@{/signin/twitter}" method="POST" class="center">
    <div class="row">
        <button class="btn indigo" name="twitterSignin" type="submit">Connect with Twitter
            <i class="mdi-social-group-add left"></i>
        </button>
    </div>
</form>
```

![设置社交身份验证](img/image00975.jpeg)

当用户点击**使用 Twitter 连接**按钮时，他们将被重定向到 Twitter 登录页面：

![设置社交身份验证](img/image00976.jpeg)

## 解释

代码不多，但要理解所有部分有点棘手。理解正在发生的事情的第一步是查看 Spring Boot 的`SocialWebAutoConfiguration`类。

在这个类中声明的`SocialAutoConfigurationAdapter`类包含以下 bean：

```java
@Bean
@ConditionalOnBean(SignInAdapter.class)
@ConditionalOnMissingBean(ProviderSignInController.class)
public ProviderSignInController signInController(
        ConnectionFactoryLocator factoryLocator,
        UsersConnectionRepository usersRepository, SignInAdapter signInAdapter) {
    ProviderSignInController controller = new ProviderSignInController(
            factoryLocator, usersRepository, signInAdapter);
    if (!CollectionUtils.isEmpty(this.signInInterceptors)) {
 controller.setSignInInterceptors(this.signInInterceptors);
    }
    return controller;
}
```

如果在我们的配置中检测到一个`ProviderSignInController`类，那么`ProviderSignInController`类将自动设置。这个控制器是登录过程的基石。看一下它的功能（我只会总结重要的部分）：

+   它将处理我们的连接按钮的`POST /signin/{providerId}`

+   它将重定向用户到我们身份提供者的适当登录 URL

+   它将通过`GET /signin/{providerId}`从身份提供者接收到 OAuth 令牌

+   然后它将处理登录

+   如果在`UsersConnectionRepository`接口中找不到用户，它将使用`SessionStrategy`接口来存储待处理的登录请求，然后重定向到`signupUrl`页面

+   如果找到用户，则会调用`SignInAdapter`接口，并将用户重定向到`postSignupUrl`页面。

这个身份验证的两个重要组件是`UsersConnectionRepository`接口，负责从某种存储中存储和检索用户，以及`SessionStrategy`接口，它将临时存储用户连接，以便可以从`SignupController`类中检索到。

默认情况下，Spring Boot 为每个身份验证提供程序创建一个`InMemoryUsersConnectionRepository`接口，这意味着我们的用户连接数据将存储在内存中。如果重新启动服务器，用户将变为未知用户，并且将再次通过注册流程。

`ProviderSignInController`类默认使用`HttpSessionSessionStrategy`，它会将连接存储在 HTTP 会话中。我们在`SignupController`类中使用的`ProviderSignInUtils`类也默认使用这个策略。如果我们在多个服务器上分发我们的应用程序，这可能会有问题，因为会话可能不会在每台服务器上都可用。

通过为`ProviderSignInController`和`ProviderSignInUtils`类提供自定义的`SessionStrategy`接口，可以轻松地覆盖这些默认设置，以将数据存储在 HTTP 会话之外的其他位置。

同样，我们可以通过提供`UsersConnectionRepository`接口的另一个实现来为我们的用户连接数据使用另一种存储方式。

Spring Social 提供了一个`JdbcUsersConnectionRepository`接口，它会自动将经过身份验证的用户保存在数据库中的`UserConnection`表中。这本书不会对此进行详细介绍，但您应该可以通过将以下 bean 添加到配置中来轻松配置它：

```java
@Bean
@Primary
public UsersConnectionRepository getUsersConnectionRepository(
  DataSource dataSource, ConnectionFactoryLocator connectionFactoryLocator) {
    return new JdbcUsersConnectionRepository(
      dataSource, connectionFactoryLocator, Encryptors.noOpText());
}
```

### 注意

查看我的博客上的这篇文章[`geowarin.github.io/spring/2015/08/02/social-login-with-spring.html`](http://geowarin.github.io/spring/2015/08/02/social-login-with-spring.html)以获取更多详细信息。

# 分布式会话

正如我们在前面的部分中看到的，Spring Social 在几个时刻将东西存储在 HTTP 会话中。我们的用户配置文件也存储在会话中。这是一个经典的方法，可以在用户浏览网站时将东西保存在内存中。

然而，如果我们想要扩展我们的应用程序并将负载分布到多个后端服务器，这可能会带来麻烦。我们现在已经进入了云时代，第七章，“优化您的请求”将讨论将我们的应用程序部署到云端。

为了使我们的会话在分布式环境中工作，我们有几种选择：

+   我们可以使用粘性会话。这将确保特定用户始终被重定向到同一台服务器并保持其会话。这需要额外的部署配置，并不是特别优雅的方法。

+   重构我们的代码，将数据放入数据库而不是会话中。然后，如果我们将其与客户端发送的每个请求一起使用的 cookie 或令牌相关联，我们可以从数据库中加载用户的数据。

+   使用 Spring Session 项目透明地使用分布式数据库，如 Redis 作为底层会话提供程序。

在本章中，我们将看到如何设置第三种方法。设置起来非常容易，并且提供了惊人的好处，即可以在不影响应用程序功能的情况下关闭它。

我们需要做的第一件事是安装 Redis。在 Mac 上安装它，使用`brew`命令：

```java

brew install redis

```

对于其他平台，请按照[`redis.io/download`](http://redis.io/download)上的说明进行操作。

然后，您可以使用以下命令启动服务器：

```java

redis-server

```

将以下依赖项添加到您的`build.gradle`文件中：

```java
compile 'org.springframework.boot:spring-boot-starter-redis'
compile 'org.springframework.session:spring-session:1.0.1.RELEASE'
```

在`application.properties`旁边创建一个名为`application-redis.properties`的新配置文件：

```java
spring.redis.host=localhost
spring.redis.port=6379
```

Spring Boot 提供了一种方便的方式来将配置文件与配置文件关联。在这种情况下，只有在 Redis 配置文件处于活动状态时，才会加载`application-redis.properties`文件。

然后，在`config`包中创建一个`RedisConfig`类：

```java
package masterSpringMvc.config;

import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Profile;
import org.springframework.session.data.redis.config.annotation.web.http.EnableRedisHttpSession;

@Configuration
@Profile("redis")
@EnableRedisHttpSession
public class RedisConfig {
}
```

正如您所看到的，此配置仅在`redis`配置文件处于活动状态时才会生效。

我们完成了！现在我们可以使用以下标志启动我们的应用程序：

```java

-Dspring.profiles.active=redis

```

您还可以使用`gradlew build`生成 JAR 文件，并使用以下命令启动它：

```java

java -Dserver.port=$PORT -Dspring.profiles.active=redis -jar app.jar

```

或者，您可以在 Bash 中使用 Gradle 启动它，如下所示：

```java

SPRING_PROFILES_ACTIVE=redis ./gradlew bootRun

```

您还可以简单地将其设置为 IDE 运行配置中的 JVM 选项。

就是这样！现在您有一个服务器存储着您已登录用户的详细信息。这意味着我们可以扩展并为我们的 Web 资源拥有多个服务器，而我们的用户不会注意到。而且我们不必在我们这边编写任何代码。

这也意味着即使重新启动服务器，您也将保留会话。

为了验证它是否有效，请使用`redis-cli`命令连接到 Redis。一开始，它将不包含任何键：

```java

> redis-cli
127.0.0.1:6379> KEYS *
(empty list or set)

```

转到您的应用程序并开始将内容放入会话中：

```java

127.0.0.1:6379> KEYS *
1) "spring:session:expirations:1432487760000"
2) "spring:session:sessions:1768a55b-081a-4673-8535-7449e5729af5"
127.0.0.1:6379> HKEYS spring:session:sessions:1768a55b-081a-4673-8535-7449e5729af5
1) "sessionAttr:SPRING_SECURITY_CONTEXT"
2) "sessionAttr:org.springframework.security.web.csrf.HttpSessionCsrfTokenRepository.CSRF_TOKEN"
3) "lastAccessedTime"
4) "maxInactiveInterval"
5) "creationTime"

```

### 注意

您可以在[`redis.io/commands`](http://redis.io/commands)上查看可用命令的列表。

# SSL

**安全套接字层**（**SSL**）是一种安全协议，其中数据经过加密并通过证书发送给受信任的一方。在本部分中，我将向您展示使用 Spring Boot 创建安全连接的不同方法。完成这些步骤对于开始下一章并不是强制性的。它们包含在内是为了完整起见，因此如果您急于将应用程序部署到云端，可以随意跳过它们。

在第八章，“将您的 Web 应用程序部署到云端”中，我们将看到大多数云平台已经处理 SSL，因此我们不必在我们这边进行配置。

## 生成自签名证书

通常，X.509 证书由证书颁发机构提供。他们通常会向您收费，因此，为了测试目的，我们可以创建自己的自签名密钥库文件。

JDK 自带一个名为 keytool 的二进制文件，用于管理证书。使用它，您可以创建一个密钥库并将证书导入现有的密钥库中。您可以在项目根目录内发出以下命令来创建一个：

```java

$ keytool -genkey -alias masterspringmvc -keyalg RSA -keystore src/main/resources/tomcat.keystore
Enter keystore password: password
Re-enter new password: password
What is your first and last name?
 [Unknown]:  Master Spring MVC
What is the name of your organizational unit?
 [Unknown]:  Packt
What is the name of your organization?
 [Unknown]:  Packt
What is the name of your City or Locality?
 [Unknown]:  Paris
What is the name of your State or Province?
 [Unknown]:  France
What is the two-letter country code for this unit?
 [Unknown]:  FR
Is CN=Master Spring MVC, OU=Packt, O=Packt, L=Paris, ST=France, C=FR correct?
 [no]:  yes

Enter key password for <masterspringmvc>
 (RETURN if same as keystore password): password2
Re-enter new password: password2

```

这将生成一个名为`masterspringmvc`的密钥库，使用 RSA 算法，并将其存储在`src/main/resources`中的密钥库中。

### 提示

不要将密钥库推送到您的存储库中。它可能会被暴力破解，这将使您的网站的安全性失效。您还应该使用强大的、随机生成的密码生成密钥库。

## 简单的方法

如果你只关心有一个安全的 https 通道而没有 http 通道，那就很容易了：

```java

server.port = 8443
server.ssl.key-store = classpath:tomcat.keystore
 server.ssl.key-store-password = password
server.ssl.key-password = password2

```

### 提示

不要将密码推送到您的存储库中。使用`${}`符号导入环境变量。

## 双重方式

如果您希望在应用程序中同时使用 http 和 https 通道，您应该向应用程序添加这种配置：

```java
@Configuration
public class SslConfig {

    @Bean
    public EmbeddedServletContainerFactory servletContainer() throws IOException {
        TomcatEmbeddedServletContainerFactory tomcat = new TomcatEmbeddedServletContainerFactory();
        tomcat.addAdditionalTomcatConnectors(createSslConnector());
        return tomcat;
    }

    private Connector createSslConnector() throws IOException {
        Connector connector = new Connector(Http11NioProtocol.class.getName());
        Http11NioProtocol protocol =
                (Http11NioProtocol) connector.getProtocolHandler();
        connector.setPort(8443);
        connector.setSecure(true);
        connector.setScheme("https");
        protocol.setSSLEnabled(true);
        protocol.setKeyAlias("masterspringmvc");
        protocol.setKeystorePass("password");
        protocol.setKeyPass("password2");
        protocol.setKeystoreFile(new ClassPathResource("tomcat.keystore").getFile().getAbsolutePath());
        protocol.setSslProtocol("TLS");
        return connector;
    }
}
```

这将加载先前生成的密钥库，以在 8080 端口之外创建一个额外的 8443 端口的通道。

您可以使用 Spring Security 自动将连接从`http`重定向到`https`，配置如下：

```java
@Configuration
public class WebSecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        http
            .requiresChannel().anyRequest().requiresSecure()
            .and()
            /* rest of the configuration */;
    }
}
```

## 在一个安全的服务器后面

通常，使用 SSL 保护应用程序的最便捷方式是将其放在一个启用了 SSL 的 Web 服务器后面，如 Apache 或 CloudFlare。这些通常会使用事实上的标头来指示连接先前是使用 SSL 发起的。

如果您告诉 Spring Boot 您的`application.properties`文件中正确的标头是什么，它就可以理解这个协议：

```java

server.tomcat.remote_ip_header=x-forwarded-for
server.tomcat.protocol_header=x-forwarded-proto

```

### 注意

有关更多详细信息，请参阅此处的文档[`docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html#howto-use-tomcat-behind-a-proxy-server`](http://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html#howto-use-tomcat-behind-a-proxy-server)。

# 检查点

在本章中，我们添加了三个配置项：`ApiSecurityConfiguration`，用于配置我们的 REST API 使用基本的 HTTP 身份验证；`WebSecurityConfiguration`，为我们的 Web 用户设置一个登录表单，以便使用帐户或 Twitter 登录；以及`RedisConfig`，允许我们的会话存储和从 Redis 服务器检索。

在认证包中，我们添加了一个`LoginController`类，用于重定向到我们的登录页面，一个`SignupController`类，第一次用户使用 Twitter 注册时将调用它，以及一个`AuthenticatingSignInAdapater`类，每次使用 Twitter 登录时都会调用它：

![检查点](img/image00977.jpeg)

# 总结

使用 Spring 来保护我们的 Web 应用程序非常简单。可能性是无限的，高级配置如社交登录也近在咫尺。分发会话和扩展也只需要几分钟。

在下一章中，我们将看到如何测试我们的应用程序，并确保它永远不会退化。

# 第六章。不留任何机会——单元测试和验收测试

在本章中，我们将看到为什么以及如何测试我们的应用程序。我们将看到单元测试和验收测试之间的区别，并学习如何进行两者。

本章分为两部分。在第一部分中，我们将使用 Java 编写测试，同时学习不同的测试方法。在第二部分中，我们将使用 Groovy 编写完全相同的测试，并看看如何使用这种令人敬畏的语言来提高我们的代码可读性。

如果您在本章中做了所有的事情，您将有双重测试，所以请随意保留对您最易读的测试。

# 为什么我要测试我的代码？

在 Java 世界工作使许多开发人员意识到测试的重要性。一系列良好的测试可以及早发现回归，并在我们发布产品时让我们更有信心。

现在很多人都熟悉持续集成的概念（[`www.thoughtworks.com/continuous-integration`](http://www.thoughtworks.com/continuous-integration)）。这是一种实践，其中服务器负责在源代码控制系统上进行更改时构建应用程序。

构建应该尽可能快，并且能够自我测试。这种实践的主要思想是获得快速的反馈循环；一旦系统中的某些东西出现问题，你应该尽快了解出了什么问题。

你为什么要在意？毕竟，测试你的应用程序是额外的成本；花在设计和维护测试上的时间必然会占用一些开发时间。

实际上，bug 被发现得越晚，成本就越高。如果你仔细想想，甚至由你的 QA 团队发现的 bug 的成本也比你自己发现的 bug 更高。它迫使你回到编写代码时的上下文：我为什么写这一行？那个函数的基础业务规则是什么？

如果你早早地编写测试，并且能够在几秒钟内启动它们，那么在你的代码中解决潜在 bug 肯定会花费更少的时间。

测试的另一个好处是它们作为代码的活文档。写大量的文档，甚至是代码注释，可能会变得无效，因为它们很容易过时，养成为极限情况或意外行为编写良好测试的习惯将成为未来的安全网。

这行代码是干什么用的？你有没有发现自己问过这种问题？如果你有一套良好的单元测试，你可以删除它并查看结果！测试给了我们对代码和重构能力前所未有的信心。软件非常脆弱。如果你不在乎它，它会慢慢腐烂和死亡。

要负责任——不要让你的代码死掉！

# 我应该如何测试我的代码？

我们可以对软件进行不同类型的测试，比如安全测试、性能测试等。作为开发人员，我们将专注于我们可以自动化的测试，并且将有助于改进我们的代码。

测试分为两类：单元测试和验收测试。测试金字塔（[`martinfowler.com/bliki/TestPyramid.html`](http://martinfowler.com/bliki/TestPyramid.html)）显示了这些测试应该以什么比例编写：

![我应该如何测试我的代码？](img/image00978.jpeg)

在金字塔的底部，你有单元测试（启动快，相对容易维护），在顶部是 UI 测试（成本更高，执行速度更慢）。集成测试位于中间：它们可以被视为具有单元之间复杂交互的大型单元测试。

金字塔的理念是提醒你把焦点放在你影响最大并且获得最佳反馈循环的地方。

# 测试驱动开发

许多开发人员养成了良好的测试驱动开发（TTD）的习惯。这种实践是从极限编程（XP）继承而来的，它将每个开发阶段分成小步骤，然后为每个步骤编写一个失败的测试。你进行必要的修改，使测试再次通过（测试变绿）。然后你可以重构你的代码，只要测试仍然是绿色的。以下图示了 TDD 的循环：

![测试驱动开发](img/image00979.jpeg)

你可以通过非常短的反馈循环迭代，直到功能完成，保证没有回归，并且保证你从一开始就测试了所有的代码。

TDD 受到了批评。最有趣的批评是这些：

+   编写测试比实际实现需要更多的时间

+   它可能导致设计不良的应用程序

事实上，成为一个优秀的 TDD 实践者需要时间。一旦你知道应该测试什么，并且足够了解你的工具，你将不会浪费太多时间。

使用 TDD（或任何其他方法）来设计一个具有良好设计的应用程序也需要有经验的开发人员。如果你陷入了 baby steps 的咒语并忘记了看大局，那么糟糕的设计可能是 TDD 的副作用。TDD 不会奇迹般地导致出色的应用程序设计，所以要小心，并记得在完成每个功能后退一步。

从书的开头，我们的代码中只有一个自动生成的单元测试。这很糟糕！我们没有遵循良好的实践。这一章是为了解决这个问题而存在的。

# 单元测试

我们可以编写的较低级别的测试称为单元测试。它们应该测试代码的一小部分，因此称为单元。如何定义一个单元取决于你；它可以是一个类或一组密切相关的类。定义这个概念将决定什么将被模拟（用虚拟对象替换）。你要用轻量级替代品替换数据库吗？你要替换与外部服务的交互吗？你要模拟行为与被测试的上下文无关的密切相关的对象吗？

我的建议是保持平衡的态度。保持你的测试干净和快速，其他一切都会随之而来。

我很少完全模拟数据层。我倾向于在测试中使用嵌入式数据库。它们提供了一种在测试时加载数据的简单方法。

作为一个规则，我总是模拟与外部服务的协作，原因有两个，如下：

+   测试的速度和在不连接到网络的情况下运行测试的可能性

+   为了能够在与这些服务通信时测试错误情况

此外，模拟和存根之间存在微妙的区别。我们将尝试使用这两种方法来看它们之间的关系。

## 适合工作的正确工具

测试新手的第一个障碍是缺乏编写相关和可维护测试的好工具和库的知识。

我将在这里列出一些。这个列表绝不是详尽无遗的，但它包含了我们将要使用的工具，并且与 Spring 轻松兼容：

| JUnit | 最广泛采用的 Java 测试运行器。默认由所有构建工具启动。 |
| --- | --- |
| AssertJ | 一种流畅的断言库。比 Hamcrest 更容易使用。 |
| Mockito | 一个简单的模拟框架。 |
| DbUnit | 用于使用 XML 数据集模拟和断言数据库内容。 |
| Spock | 一种优雅的 Groovy DSL，用于以行为驱动开发（BDD）风格（Given/When/Then）编写测试。 |

Groovy 在我的测试工具集中占据了重要位置。即使你还没有准备好将一些 Groovy 代码投入生产，你仍然可以在测试中轻松使用这种语言的便利性。使用 Gradle 非常容易实现，但我们将在几分钟内看到。

# 验收测试

在 Web 应用程序的背景下，“验收测试”通常指的是在浏览器中的端到端测试。在 Java 世界中，Selenium 显然是最可靠和成熟的库之一。

在 JavaScript 世界中，我们可以找到其他替代方案，如 PhantomJS 或 Protractor。PhantomJS 在我们的案例中非常相关，因为这里有一个 Web 驱动程序可用于在这个无头浏览器中运行 Selenium 测试，这将提高启动时间，而且不需要模拟 X 服务器或启动单独的 Selenium 服务器：

| Selenium 2 | 提供 Web 驱动程序以操纵浏览器进行自动化测试。 |
| --- | --- |
| PhantomJS | 一个无头浏览器（没有 GUI）。可能是最快的浏览器。 |
| FluentLenium | 用于操纵 Selenium 测试的流畅库。 |
| Geb | 用于操纵 Selenium 测试的 Groovy 库。 |

# 我们的第一个单元测试

现在是时候编写我们的第一个单元测试了。

我们将专注于在控制器级别编写测试，因为我们几乎没有业务代码或服务。编写 Spring MVC 测试的关键是我们类路径中的`org.springframework.boot:spring-boot-starter-test`依赖项。它将添加一些非常有用的库，比如这些：

+   `hamcrest`：这是 JUnit 的断言库

+   `mockito`：这是一个模拟库

+   `spring-test`：这是 Spring 测试库

我们将测试当用户尚未创建其个人资料时，重定向到个人资料页面的情况。

我们已经有一个名为`MasterSpringMvc4ApplicationTests`的自动生成测试。这是使用 Spring 测试框架编写的最基本的测试：如果上下文无法加载，它将什么也不做，只会失败。

```java
@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = MasterSpringMvc4Application.class)
@WebAppConfiguration
public class MasterSpringMvc4ApplicationTests {

    @Test
    public void contextLoads() {
    }
}
```

我们可以删除这个测试，并创建一个新的测试，确保没有个人资料的用户将默认重定向到个人资料页面。它实际上测试了`HomeController`类的代码，所以让我们称之为`HomeControllerTest`类，并将其放在与`HomeController`相同的包中，即`src/test/java`。所有的 IDE 都有从类创建 JUnit 测试用例的快捷方式。现在找出如何使用您的 IDE 来完成这个操作！

这是测试：

```java
package masterSpringMvc.controller;

import masterSpringMvc.MasterSpringMvcApplication;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.context.WebApplicationContext;

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultHandlers.print;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = MasterSpringMvcApplication.class)
@WebAppConfiguration
public class HomeControllerTest {
    @Autowired
    private WebApplicationContext wac;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        this.mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).build();
    }

    @Test
    public void should_redirect_to_profile() throws Exception {
        this.mockMvc.perform(get("/"))
                .andDo(print())
                .andExpect(status().isFound())
                .andExpect(redirectedUrl("/profile"));
    }
}
```

我们使用`MockMvc`来模拟与 Spring 控制器的交互，而不会产生 Servlet 容器的实际开销。

我们还使用了 Spring 提供的一些匹配器来断言我们的结果。它们实际上实现了 Hamcrest 匹配器。

`.andDo(print())`语句将为测试场景的请求和响应生成整洁的调试输出。如果您觉得太啰嗦，可以将其注释掉。

就是这样！语法在开始时有点棘手，但一个具有良好代码补全功能的 IDE 将能够帮助您。

现在我们想测试的是，如果用户填写了其个人资料的测试部分，我们是否可以将其重定向到正确的搜索。为此，我们需要使用`MockHttpSession`类对会话进行存根。

```java
import org.springframework.mock.web.MockHttpSession;
import masterSpringMvc.profile.UserProfileSession;

// put this test below the other one
@Test
public void should_redirect_to_tastes() throws Exception {
    MockHttpSession session = new MockHttpSession();
    UserProfileSession sessionBean = new UserProfileSession();
    sessionBean.setTastes(Arrays.asList("spring", "groovy"));
    session.setAttribute("scopedTarget.userProfileSession", sessionBean);

    this.mockMvc.perform(get("/").session(session))
        .andExpect(status().isFound())
        .andExpect(redirectedUrl("/search/mixed;keywords=spring,groovy"));
}
```

您将不得不为测试添加`setTastes()` setter 到`UserProfileSession` bean 中。

在`org.springframework.mock.web`包中有很多用于 Servlet 环境的模拟工具。

请注意，表示我们会话中的 bean 的属性以`scopedTarget`为前缀。这是因为 Spring 会对会话 bean 进行代理。因此，在 Spring 上下文中实际上有两个对象，我们定义的实际 bean 和最终会出现在会话中的代理。

模拟会话是一个很好的类，但我们可以使用一个构建器来重构测试，该构建器将隐藏实现细节，并且以后可以重复使用：

```java
@Test
public void should_redirect_to_tastes() throws Exception {

    MockHttpSession session = new SessionBuilder().userTastes("spring", "groovy").build();
    this.mockMvc.perform(get("/")
        .session(session))
        .andExpect(status().isFound())
        .andExpect(redirectedUrl("/search/mixed;keywords=spring,groovy"));
}
```

构建器的代码如下：

```java
public class SessionBuilder {
    private final MockHttpSession session;
    UserProfileSession sessionBean;

    public SessionBuilder() {
        session = new MockHttpSession();
        sessionBean = new UserProfileSession();
        session.setAttribute("scopedTarget.userProfileSession", sessionBean);
    }

    public SessionBuilder userTastes(String... tastes) {
        sessionBean.setTastes(Arrays.asList(tastes));
        return this;
    }

    public MockHttpSession build() {
        return session;
    }
}
```

在这次重构之后，您的测试应该始终通过，当然。

# 模拟和存根

如果我们想测试`SearchController`类处理的搜索请求，我们肯定会想要模拟`SearchService`。

有两种方法可以做到这一点：使用模拟对象或存根。

## 使用 Mockito 进行模拟

首先，我们可以使用 Mockito 创建一个模拟对象：

```java
package masterSpringMvc.search;

import masterSpringMvc.MasterSpringMvcApplication;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.mockito.InjectMocks;
import org.mockito.Mock;
import org.mockito.MockitoAnnotations;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;

import java.util.Arrays;

import static org.hamcrest.Matchers.*;
import static org.mockito.Matchers.*;
import static org.mockito.Mockito.*;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = MasterSpringMvcApplication.class)
@WebAppConfiguration
public class SearchControllerMockTest {
    @Mock
    private SearchService searchService;

    @InjectMocks
    private SearchController searchController;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        MockitoAnnotations.initMocks(this);
        this.mockMvc = MockMvcBuilders
                .standaloneSetup(searchController)
                .setRemoveSemicolonContent(false)
                .build();
    }

    @Test
    public void should_search() throws Exception {

        when(searchService.search(anyString(), anyListOf(String.class)))
                .thenReturn(Arrays.asList(
                        new LightTweet("tweetText")
                ));

        this.mockMvc.perform(get("/search/mixed;keywords=spring"))
                .andExpect(status().isOk())
                .andExpect(view().name("resultPage"))
                .andExpect(model().attribute("tweets", everyItem(
                        hasProperty("text", is("tweetText"))
                )));

        verify(searchService, times(1)).search(anyString(), anyListOf(String.class));
    }
}
```

您可以看到，我们创建了一个独立的上下文，而不是使用 web 应用程序上下文来设置`MockMvc`。这个上下文只包含我们的控制器。这意味着我们可以完全控制控制器及其依赖项的实例化和初始化。这将使我们能够轻松地在我们的控制器中注入一个模拟对象。

缺点是我们必须重新声明我们的配置的一部分，比如说我们不想在分号后删除 URL 字符的配置。

我们使用了一些 Hamcrest 匹配器来断言最终会出现在视图模型中的属性。

模拟的方法有其好处，比如能够验证与模拟对象的交互并在运行时创建期望。

这也会使您的测试与对象的实际实现耦合。例如，如果您更改了控制器中获取推文的方式，您很可能会破坏与该控制器相关的测试，因为它们仍然尝试模拟我们不再依赖的服务。

## 在测试时存根我们的 bean

另一种方法是在我们的测试中用另一个实现类替换`SearchService`类的实现。

我们早些时候有点懒，没有为`SearchService`定义一个接口。*始终根据接口而不是实现进行编程*。在这句谚语背后的智慧中，隐藏着*四人帮*最重要的教训。

控制反转的好处之一是允许在测试或实际系统中轻松替换我们的实现。为了使其工作，我们将不得不修改所有使用`SearchService`的地方，使用新的接口。有了一个好的 IDE，有一个叫做`提取接口`的重构，它会做到这一点。这应该创建一个包含我们的`SearchService`类的`search()`公共方法的接口：

```java
public interface TwitterSearch {
    List<LightTweet> search(String searchType, List<String> keywords);
}
```

当然，我们的两个控制器，`SearchController`和`SearchApiController`，现在必须使用接口而不是实现。

现在我们有能力为`TwitterSearch`类创建一个测试替身，专门用于我们的测试用例。为了使其工作，我们将需要声明一个名为`StubTwitterSearchConfig`的新 Spring 配置，其中将包含`TwitterSearch`的另一个实现。我将其放在 search 包中，紧邻`SearchControllerMockTest`：

```java
package masterSpringMvc.search;

import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Primary;

import java.util.Arrays;

@Configuration
public class StubTwitterSearchConfig {
    @Primary @Bean
    public TwitterSearch twitterSearch() {
        return (searchType, keywords) -> Arrays.asList(
                new LightTweet("tweetText"),
                new LightTweet("secondTweet")
        );
    }
}
```

在这个配置类中，我们使用`@Primary`注解重新声明了`TwitterSearch` bean，这将告诉 Spring 优先使用这个实现，如果在类路径中找到其他实现。

由于`TwitterSearch`接口只包含一个方法，我们可以使用 lambda 表达式来实现它。

这是使用我们的`StubConfiguration`类以及带有`SpringApplicationConfiguration`注解的主配置的完整测试：

```java
package masterSpringMvc.search;

import masterSpringMvc.MasterSpringMvcApplication;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.context.WebApplicationContext;

import static org.hamcrest.Matchers.*;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = {
        MasterSpringMvcApplication.class,
        StubTwitterSearchConfig.class
})
@WebAppConfiguration
public class SearchControllerTest {
    @Autowired
    private WebApplicationContext wac;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        this.mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).build();
    }

    @Test
    public void should_search() throws Exception {

        this.mockMvc.perform(get("/search/mixed;keywords=spring"))
                .andExpect(status().isOk())
                .andExpect(view().name("resultPage"))
                .andExpect(model().attribute("tweets", hasSize(2)))
                .andExpect(model().attribute("tweets",
                                hasItems(
                                        hasProperty("text", is("tweetText")),
                                        hasProperty("text", is("secondTweet"))
                                ))
                );
    }
}
```

## 我应该使用模拟对象还是存根对象？

这两种方法都有各自的优点。有关详细解释，请查看 Martin Fowler 的这篇伟大的文章：[`martinfowler.com/articles/mocksArentStubs.html`](http://martinfowler.com/articles/mocksArentStubs.html)。

我的测试例程更多地是关于编写存根，因为我喜欢测试对象的输出而不是它们的内部工作原理。但这取决于你。Spring 作为一个依赖注入框架，意味着你可以轻松选择你喜欢的方法。

# 单元测试 REST 控制器

我们刚刚测试了一个传统的控制器重定向到视图。原则上，测试 REST 控制器非常类似，但有一些微妙之处。

由于我们将测试控制器的 JSON 输出，我们需要一个 JSON 断言库。将以下依赖项添加到您的`build.gradle`文件中：

```java
testCompile 'com.jayway.jsonpath:json-path'
```

让我们为`SearchApiController`类编写一个测试，该控制器允许搜索推文并以 JSON 或 XML 格式返回结果：

```java
package masterSpringMvc.search.api;

import masterSpringMvc.MasterSpringMvcApplication;
import masterSpringMvc.search.StubTwitterSearchConfig;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.http.MediaType;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.context.WebApplicationContext;

import static org.hamcrest.Matchers.*;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultHandlers.print;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = {
        MasterSpringMvcApplication.class,
        StubTwitterSearchConfig.class
})
@WebAppConfiguration
public class SearchApiControllerTest {
    @Autowired
    private WebApplicationContext wac;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        this.mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).build();
    }

    @Test
    public void should_search() throws Exception {

        this.mockMvc.perform(
                get("/api/search/mixed;keywords=spring")
                        .accept(MediaType.APPLICATION_JSON))
                .andDo(print())
                .andExpect(status().isOk())
                .andExpect(content().contentTypeCompatibleWith(MediaType.APPLICATION_JSON))
                .andExpect(jsonPath("$", hasSize(2)))
                .andExpect(jsonPath("$[0].text", is("tweetText")))
                .andExpect(jsonPath("$[1].text", is("secondTweet")));
    }
}
```

注意 JSON 输出上的简单而优雅的断言。测试我们的用户控制器将需要更多的工作。

首先，让我们将`assertj`添加到类路径中；它将帮助我们编写更清晰的测试：

```java
testCompile 'org.assertj:assertj-core:3.0.0'
```

然后，为了简化测试，在我们的`UserRepository`类中添加一个`reset()`方法，这将帮助我们进行测试：

```java
void reset(User... users) {
        userMap.clear();
        for (User user : users) {
                save(user);
        }
}
```

在现实生活中，我们可能应该提取一个接口并创建一个存根进行测试。我会把这留给你作为练习。

这是第一个获取用户列表的测试：

```java
package masterSpringMvc.user.api;

import masterSpringMvc.MasterSpringMvcApplication;
import masterSpringMvc.user.User;
import masterSpringMvc.user.UserRepository;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.http.MediaType;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.context.WebApplicationContext;

import static org.hamcrest.Matchers.*;
   import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = MasterSpringMvcApplication.class)
@WebAppConfiguration
public class UserApiControllerTest {

    @Autowired
    private WebApplicationContext wac;

    @Autowired
    private UserRepository userRepository;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        this.mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).build();
        userRepository.reset(new User("bob@spring.io"));
    }

    @Test
    public void should_list_users() throws Exception {
        this.mockMvc.perform(
                get("/api/users")
                        .accept(MediaType.APPLICATION_JSON)
        )
                .andExpect(status().isOk())
                .andExpect(content().contentTypeCompatibleWith(MediaType.APPLICATION_JSON))
                .andExpect(jsonPath("$", hasSize(1)))
                .andExpect(jsonPath("$[0].email", is("bob@spring.io")));
    }
}
```

为了使其工作，为`User`类添加一个构造函数，以电子邮件属性作为参数。注意：您还需要为 Jackson 添加一个默认构造函数。

该测试与之前的测试非常相似，另外设置了`UserRepository`。

现在让我们测试创建用户的`POST`方法：

```java
import static org.assertj.core.api.Assertions.assertThat;

// Insert this test below the previous one
@Test
public void should_create_new_user() throws Exception {
        User user = new User("john@spring.io");
        this.mockMvc.perform(
                post("/api/users")
                        .contentType(MediaType.APPLICATION_JSON)
                        .content(JsonUtil.toJson(user))
        )
                .andExpect(status().isCreated());

        assertThat(userRepository.findAll())
                .extracting(User::getEmail)
                .containsOnly("bob@spring.io", "john@spring.io");
}
```

有两件事需要注意。第一件事是使用 AssertJ 来断言测试后存储库的内容。您需要以下静态导入才能使其工作：

```java
import static org.assertj.core.api.Assertions.assertThat;
```

第二个是我们使用一个实用方法，在将对象发送到控制器之前将其转换为 JSON。为此，我在`utils`包中创建了一个简单的实用程序类，如下所示：

```java
package masterSpringMvc.utils;

import com.fasterxml.jackson.annotation.JsonInclude;
import com.fasterxml.jackson.databind.ObjectMapper;

import java.io.IOException;

public class JsonUtil {
    public static byte[] toJson(Object object) throws IOException {
        ObjectMapper mapper = new ObjectMapper();
        mapper.setSerializationInclusion(JsonInclude.Include.NON_NULL);
        return mapper.writeValueAsBytes(object);
    }
}
```

`DELETE`方法的测试如下：

```java
@Test
public void should_delete_user() throws Exception {
        this.mockMvc.perform(
                delete("/api/user/bob@spring.io")
                        .accept(MediaType.APPLICATION_JSON)
        )
                .andExpect(status().isOk());

        assertThat(userRepository.findAll()).hasSize(0);
}

@Test
public void should_return_not_found_when_deleting_unknown_user() throws Exception {
        this.mockMvc.perform(
                delete("/api/user/non-existing@mail.com")
                        .accept(MediaType.APPLICATION_JSON)
        )
                .andExpect(status().isNotFound());
}
```

最后，这是用于更新用户的`PUT`方法的测试：

```java
@Test
public void put_should_update_existing_user() throws Exception {
        User user = new User("ignored@spring.io");
        this.mockMvc.perform(
                put("/api/user/bob@spring.io")
                        .content(JsonUtil.toJson(user))
                        .contentType(MediaType.APPLICATION_JSON)
        )
                .andExpect(status().isOk());

        assertThat(userRepository.findAll())
                .extracting(User::getEmail)
                .containsOnly("bob@spring.io");
}
```

糟糕！最后一个测试没有通过！通过检查`UserApiController`的实现，我们很容易看出原因：

```java
   @RequestMapping(value = "/user/{email}", method = RequestMethod.PUT)
    public ResponseEntity<User> updateUser(@PathVariable String email, @RequestBody User user) throws EntityNotFoundException {
        User saved = userRepository.update(email, user);
        return new ResponseEntity<>(saved, HttpStatus.CREATED);
    }
```

我们在控制器中返回了错误的状态！将其更改为`HttpStatus.OK`，测试应该再次变为绿色。

使用 Spring，可以轻松地使用应用程序的相同配置编写控制器测试，但我们也可以有效地覆盖或更改测试设置中的一些元素。

在运行所有测试时，您将注意到的另一件有趣的事情是应用程序上下文只加载一次，这意味着开销实际上非常小。

我们的应用程序也很小，因此我们没有努力将配置拆分为可重用的部分。不在每个测试中加载完整的应用程序上下文可能是一个非常好的做法。您实际上可以使用`@ComponentScan`注释将组件扫描拆分为不同的单元。

此注释有几个属性，允许您使用`includeFilter`和`excludeFilter`定义过滤器（例如仅加载控制器）并使用`basePackageClasses`和`basePackages`注释扫描特定包。

您还可以将配置拆分为多个`@Configuration`类。一个很好的例子是将我们应用程序的用户和推文部分的代码拆分为两个独立的部分。

现在我们将看一下验收测试，这是一种非常不同的测试。

# 测试身份验证

如果您希望在 MockMvc 测试中设置 Spring Security，可以在我们之前的测试旁边编写此测试：

```java
package masterSpringMvc.user.api;

import masterSpringMvc.MasterSpringMvcApplication;
import masterSpringMvc.user.User;
import masterSpringMvc.user.UserRepository;
import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.http.MediaType;
import org.springframework.security.web.FilterChainProxy;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;
import org.springframework.test.context.web.WebAppConfiguration;
import org.springframework.test.web.servlet.MockMvc;
import org.springframework.test.web.servlet.setup.MockMvcBuilders;
import org.springframework.web.context.WebApplicationContext;

import java.util.Base64;

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.status;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = MasterSpringMvcApplication.class)
@WebAppConfiguration
public class UserApiControllerAuthTest {

    @Autowired
    private FilterChainProxy springSecurityFilter;

    @Autowired
    private WebApplicationContext wac;

    @Autowired
    private UserRepository userRepository;

    private MockMvc mockMvc;

    @Before
    public void setup() {
        this.mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).addFilter(springSecurityFilter).build();
        userRepository.reset(new User("bob@spring.io"));
    }

    @Test
    public void unauthenticated_cannot_list_users() throws Exception {
        this.mockMvc.perform(
                get("/api/users")
                        .accept(MediaType.APPLICATION_JSON)
        )
                .andExpect(status().isUnauthorized());
    }

    @Test
    public void admin_can_list_users() throws Exception {
        this.mockMvc.perform(
                get("/api/users")
                        .accept(MediaType.APPLICATION_JSON)
                        .header("Authorization", basicAuth("admin", "admin"))
        )
                .andExpect(status().isOk());
    }

    private String basicAuth(String login, String password) {
        byte[] auth = (login + ":" + password).getBytes();
        return "Basic " + Base64.getEncoder().encodeToString(auth);
    }
}
```

在前面的示例中，我们将`SpringSecurityFilter`添加到了我们的配置中。这将激活 Spring 安全检查。要测试身份验证是否有效，我们只需在请求中发送正确的标头。

基本身份验证的优势在于它非常容易模拟。对于更复杂的设置，您将不得不在身份验证端点上执行模拟请求。

在撰写本文时，Spring Boot 的版本为 1.2.3，并依赖于 Spring Security 3。

几周后，Spring Boot 1.3.0 将可用，它将更新 Spring Security 并使用版本 4。

这是一个好消息，因为 Spring Security 4 包括使用简单注释轻松设置经过身份验证的用户。有关更多详细信息，请参见[`docs.spring.io/spring-security/site/docs/4.0.x/reference/htmlsingle/#test`](http://docs.spring.io/spring-security/site/docs/4.0.x/reference/htmlsingle/#test)。

# 编写验收测试

单元测试只能覆盖应用程序组件之间的不同交互的子集。为了再进一步，我们需要设置验收测试，这些测试将实际启动完整的应用程序，并允许我们与其界面进行交互。

## Gradle 配置

在将集成测试添加到项目中时，我们想要做的第一件事是将它们放在与单元测试不同的位置。

其原因实质上是，验收测试比单元测试慢。它们可以成为不同集成作业的一部分，例如每晚构建，我们希望开发人员能够轻松地从他们的 IDE 启动不同类型的测试。要使用 Gradle 实现这一点，我们将不得不添加一个名为`integrationTest`的新配置。对于 Gradle 来说，配置是一组工件及其依赖项。我们的项目中已经有几个配置：`compile`，`testCompile`等。

您可以通过在项目的根目录键入`./gradlew properties`来查看项目的配置等更多信息。

在`build.gradle`文件的末尾添加新的配置：

```java
configurations {
    integrationTestCompile.extendsFrom testCompile
    integrationTestRuntime.extendsFrom testRuntime
}
```

这将允许您为`integrationTestCompile`和`integrationTestRuntime`声明依赖项。更重要的是，通过继承测试配置，我们可以访问它们的依赖项。

### 提示

我不建议将集成测试依赖项声明为`integrationTestCompile`。就 Gradle 而言，这样做是可以的，但 IDE 内的支持是不存在的。我通常会将我的集成测试依赖项声明为`testCompile`依赖项。这只是一个小不便。

现在我们有了新的配置，我们必须创建一个与它们关联的`sourceSet`类。`sourceSet`类表示 Java 源代码和资源的逻辑组。当然，它们也必须继承自测试和主类；请参阅以下代码：

```java
sourceSets {
    integrationTest {
        compileClasspath += main.output + test.output
        runtimeClasspath += main.output + test.output
    }
}
```

最后，我们需要添加一个任务来从我们的构建中运行它们，如下所示：

```java
task integrationTest(type: Test) {
    testClassesDir = sourceSets.integrationTest.output.classesDir
    classpath = sourceSets.integrationTest.runtimeClasspath
    reports.html.destination = file("${reporting.baseDir}/integrationTests")
}
```

要运行我们的测试，我们可以输入`./gradlew integrationTest`。除了配置我们的类路径和查找测试类的位置之外，我们还定义了一个目录，用于生成测试报告。

这个配置允许我们在`src/integrationTest/java`或`src/integrationTest/groovy`中编写我们的测试，这将使我们更容易识别它们并单独运行它们，而不是与我们的单元测试一起运行。

默认情况下，它们将生成在`build/reports/tests`中。如果我们不覆盖它们，如果我们使用`gradle clean test integrationTest`同时运行测试和集成测试，它们将互相覆盖。

值得一提的是，Gradle 生态系统中的一个新插件旨在简化声明新的测试配置，详细信息请访问[`plugins.gradle.org/plugin/org.unbroken-dome.test-sets`](https://plugins.gradle.org/plugin/org.unbroken-dome.test-sets)。

## 我们的第一个 FluentLenium 测试

FluentLenium 是一个用于操纵 Selenium 测试的惊人库。让我们向我们的构建脚本添加一些依赖项：

```java
testCompile 'org.fluentlenium:fluentlenium-assertj:0.10.3'
testCompile 'com.codeborne:phantomjsdriver:1.2.1'
testCompile 'org.seleniumhq.selenium:selenium-java:2.45.0'
```

默认情况下，`fluentlenium`带有`selenium-java`。我们重新声明它，只是为了明确要求使用最新版本。我们还添加了对`PhantomJS`驱动程序的依赖，这不是 Selenium 官方支持的。`selenium-java`库的问题在于它捆绑了所有支持的 web 驱动程序。

您可以通过输入`gradle dependencies`来查看我们项目的依赖树。在底部，您将看到类似于以下内容：

```java
+--- org.fluentlenium:fluentlenium-assertj:0.10.3
|    +--- org.fluentlenium:fluentlenium-core:0.10.3
|    |    \--- org.seleniumhq.selenium:selenium-java:2.44.0 -> 2.45.0
|    |         +--- org.seleniumhq.selenium:selenium-chrome-driver:2.45.0

|    |         +--- org.seleniumhq.selenium:selenium-htmlunit-driver:2.45.0

|    |         +--- org.seleniumhq.selenium:selenium-firefox-driver:2.45.0

|    |         +--- org.seleniumhq.selenium:selenium-ie-driver:2.45.0

|    |         +--- org.seleniumhq.selenium:selenium-safari-driver:2.45.0

|    |         +--- org.webbitserver:webbit:0.4.14 (*)
|    |         \--- org.seleniumhq.selenium:selenium-leg-rc:2.45.0
|    |              \--- org.seleniumhq.selenium:selenium-remote-driver:2.45.0 (*)
|    \--- org.assertj:assertj-core:1.6.1 -> 3.0.0
```

由于我们只会使用`PhantomJS`驱动程序，将所有这些依赖项放在类路径中是非常不必要的。为了排除我们不需要的依赖项，我们可以在依赖项声明之前的构建脚本中添加以下部分：

```java
configurations {
    testCompile {
        exclude module: 'selenium-safari-driver'
        exclude module: 'selenium-ie-driver'
        //exclude module: 'selenium-firefox-driver'
        exclude module: 'selenium-htmlunit-driver'
        exclude module: 'selenium-chrome-driver'
    }
}
```

我们只需将`firefox`驱动程序准备好。`PhantomJS`驱动程序是一个无头浏览器，因此理解没有 GUI 发生的事情可能会很棘手。切换到 Firefox 来调试复杂的测试可能会很好。

有了正确配置的类路径，我们现在可以编写我们的第一个集成测试。Spring Boot 有一个非常方便的注解来支持这个测试：

```java
import masterSpringMvc.MasterSpringMvcApplication;
import masterSpringMvc.search.StubTwitterSearchConfig;
import org.fluentlenium.adapter.FluentTest;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.phantomjs.PhantomJSDriver;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.boot.test.WebIntegrationTest;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;

import static org.assertj.core.api.Assertions.assertThat;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = {
        MasterSpringMvcApplication.class,
        StubTwitterSearchConfig.class
})
@WebIntegrationTest(randomPort = true)
public class FluentIntegrationTest extends FluentTest {

    @Value("${local.server.port}")
    private int serverPort;

    @Override
    public WebDriver getDefaultDriver() {
        return new PhantomJSDriver();
    }

    public String getDefaultBaseUrl() {
        return "http://localhost:" + serverPort;
    }

    @Test
    public void hasPageTitle() {
        goTo("/");
        assertThat(findFirst("h2").getText()).isEqualTo("Login");
    }
}
```

请注意，FluentLenium 具有一个用于请求 DOM 元素的简洁 API。使用 AssertJ，我们可以在页面内容上编写易于阅读的断言。

### 注意

请查看[`github.com/FluentLenium/FluentLenium`](https://github.com/FluentLenium/FluentLenium)上的文档以获取更多信息。

使用`@WebIntegrationTest`注解，Spring 实际上会创建嵌入式 Servlet 容器（Tomcat）并在随机端口上启动我们的 Web 应用程序！我们需要在运行时检索此端口号。这将允许我们为我们的测试提供一个基本 URL，这个 URL 将成为我们在测试中进行的所有导航的前缀。

如果您尝试在这个阶段运行测试，您将看到以下错误消息：

```java

java.lang.IllegalStateException: The path to the driver executable must be set by the phantomjs.binary.path capability/system property/PATH variable; for more information, see https://github.com/ariya/phantomjs/wiki. The latest version can be downloaded from http://phantomjs.org/download.html

```

实际上，PhantomJS 需要安装在您的机器上才能正常工作。在 Mac 上，只需使用`brew install phantomjs`。对于其他平台，请参阅[`phantomjs.org/download.html`](http://phantomjs.org/download.html)上的文档。

如果您不想在您的机器上安装新的二进制文件，请用`new FirefoxDriver()`替换`new PhantomJSDriver()`。您的测试会慢一点，但您会有一个 GUI。

我们的第一个测试是着陆在个人资料页面，对吧？现在我们需要找到一种登录的方法。

使用存根进行伪登录怎么样？

将这个类放在测试源代码中（`src/test/java`）：

```java
package masterSpringMvc.auth;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Primary;
import org.springframework.security.authentication.UsernamePasswordAuthenticationToken;
import org.springframework.security.core.context.SecurityContextHolder;
import org.springframework.social.connect.ConnectionFactoryLocator;
import org.springframework.social.connect.UsersConnectionRepository;
import org.springframework.social.connect.web.ProviderSignInController;
import org.springframework.social.connect.web.SignInAdapter;
import org.springframework.web.context.request.NativeWebRequest;
import org.springframework.web.servlet.view.RedirectView;

@Configuration
public class StubSocialSigninConfig {

    @Bean
    @Primary
    @Autowired
    public ProviderSignInController signInController(ConnectionFactoryLocator factoryLocator,
                                                     UsersConnectionRepository usersRepository,
                                                     SignInAdapter signInAdapter) {
        return new FakeSigninController(factoryLocator, usersRepository, signInAdapter);
    }

    public class FakeSigninController extends ProviderSignInController {
        public FakeSigninController(ConnectionFactoryLocator connectionFactoryLocator,
                                    UsersConnectionRepository usersConnectionRepository,
                                    SignInAdapter signInAdapter) {
            super(connectionFactoryLocator, usersConnectionRepository, signInAdapter);
        }

        @Override
        public RedirectView signIn(String providerId, NativeWebRequest request) {
            UsernamePasswordAuthenticationToken authentication =
                    new UsernamePasswordAuthenticationToken("geowarin", null, null);
            SecurityContextHolder.getContext().setAuthentication(authentication);
            return new RedirectView("/");
        }
    }
}
```

这将认证任何点击 Twitter 登录按钮的用户为 geowarin。

我们将编写第二个测试，填写个人资料表单并断言搜索结果是否显示：

```java
import masterSpringMvc.MasterSpringMvcApplication;
import masterSpringMvc.auth.StubSocialSigninConfig;
import masterSpringMvc.search.StubTwitterSearchConfig;
import org.fluentlenium.adapter.FluentTest;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.phantomjs.PhantomJSDriver;
import org.springframework.beans.factory.annotation.Value;
import org.springframework.boot.test.SpringApplicationConfiguration;
import org.springframework.boot.test.WebIntegrationTest;
import org.springframework.test.context.junit4.SpringJUnit4ClassRunner;

import static org.assertj.core.api.Assertions.assertThat;
import static org.fluentlenium.core.filter.FilterConstructor.withName;

@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = {
        MasterSpringMvcApplication.class,
        StubTwitterSearchConfig.class,
        StubSocialSigninConfig.class
})
@WebIntegrationTest(randomPort = true)
public class FluentIntegrationTest extends FluentTest {

    @Value("${local.server.port}")
    private int serverPort;

    @Override
    public WebDriver getDefaultDriver() {
        return new PhantomJSDriver();
    }

    public String getDefaultBaseUrl() {
        return "http://localhost:" + serverPort;
    }

    @Test
    public void hasPageTitle() {
        goTo("/");
        assertThat(findFirst("h2").getText()).isEqualTo("Login");
    }

    @Test
    public void should_be_redirected_after_filling_form() {
        goTo("/");
        assertThat(findFirst("h2").getText()).isEqualTo("Login");

        find("button", withName("twitterSignin")).click();
 assertThat(findFirst("h2").getText()).isEqualTo("Your profile");

        fill("#twitterHandle").with("geowarin");
        fill("#email").with("geowarin@mymail.com");
        fill("#birthDate").with("03/19/1987");

        find("button", withName("addTaste")).click();
        fill("#tastes0").with("spring");

        find("button", withName("save")).click();

        takeScreenShot();
        assertThat(findFirst("h2").getText()).isEqualTo("Tweet results for spring");
        assertThat(findFirst("ul.collection").find("li")).hasSize(2);
    }
}
```

请注意，我们可以轻松地要求我们的网络驱动程序对当前用于测试的浏览器进行截图。这将产生以下输出：

![我们的第一个 FluentLenium 测试](img/image00980.jpeg)

## 使用 FluentLenium 的页面对象

以前的测试有点混乱。我们在测试中硬编码了所有选择器。当我们使用相同的元素编写大量测试时，这可能变得非常危险，因为每当我们更改页面布局时，所有测试都会失败。此外，测试有点难以阅读。

为了解决这个问题，一个常见的做法是使用一个页面对象来表示我们应用程序中的特定网页。使用 FluentLenium，页面对象必须继承`FluentPage`类。

我们将创建三个页面，分别对应我们 GUI 的每个元素。第一个将是具有单击`twitterSignin`按钮选项的登录页面，第二个将是具有填写个人资料表单的便利方法的个人资料页面，最后一个将是我们可以断言显示结果的结果页面。

让我们立即创建登录页面。我把所有三个页面都放在了`pages`包中：

```java
package pages;

import org.fluentlenium.core.FluentPage;
import org.fluentlenium.core.domain.FluentWebElement;
import org.openqa.selenium.support.FindBy;

import static org.assertj.core.api.Assertions.assertThat;

public class LoginPage extends FluentPage {
    @FindBy(name = "twitterSignin")
    FluentWebElement signinButton;

    public String getUrl() {
        return "/login";
    }

    public void isAt() {
        assertThat(findFirst("h2").getText()).isEqualTo("Login");
    }

    public void login() {
        signinButton.click();
    }
}
```

让我们为我们的个人资料页面创建一个页面：

```java
package pages;

import org.fluentlenium.core.FluentPage;
import org.fluentlenium.core.domain.FluentWebElement;
import org.openqa.selenium.support.FindBy;

import static org.assertj.core.api.Assertions.assertThat;

public class ProfilePage extends FluentPage {
    @FindBy(name = "addTaste")
    FluentWebElement addTasteButton;
    @FindBy(name = "save")
    FluentWebElement saveButton;

    public String getUrl() {
        return "/profile";
    }

    public void isAt() {
        assertThat(findFirst("h2").getText()).isEqualTo("Your profile");
    }

    public void fillInfos(String twitterHandle, String email, String birthDate) {
        fill("#twitterHandle").with(twitterHandle);
        fill("#email").with(email);
        fill("#birthDate").with(birthDate);
    }

    public void addTaste(String taste) {
        addTasteButton.click();
        fill("#tastes0").with(taste);
    }

    public void saveProfile() {
        saveButton.click();
    }
}
```

让我们也为搜索结果页面创建另一个：

```java
package pages;

import com.google.common.base.Joiner;
import org.fluentlenium.core.FluentPage;
import org.fluentlenium.core.domain.FluentWebElement;
import org.openqa.selenium.support.FindBy;

import static org.assertj.core.api.Assertions.assertThat;

public class SearchResultPage extends FluentPage {
    @FindBy(css = "ul.collection")
    FluentWebElement resultList;

    public void isAt(String... keywords) {
        assertThat(findFirst("h2").getText())
                .isEqualTo("Tweet results for " + Joiner.on(",").join(keywords));
    }

    public int getNumberOfResults() {
        return resultList.find("li").size();
    }
}
```

现在我们可以使用这些页面对象重构测试：

```java
@Page
private LoginPage loginPage;
@Page
private ProfilePage profilePage;
@Page
private SearchResultPage searchResultPage;

@Test
public void should_be_redirected_after_filling_form() {
    goTo("/");
    loginPage.isAt();

    loginPage.login();
    profilePage.isAt();

    profilePage.fillInfos("geowarin", "geowarin@mymail.com", "03/19/1987");
    profilePage.addTaste("spring");

    profilePage.saveProfile();

    takeScreenShot();
    searchResultPage.isAt();
    assertThat(searchResultPage.getNumberOfResults()).isEqualTo(2);
}
```

更易读了，不是吗？

## 使我们的测试更加 Groovy

如果你不了解 Groovy，可以将其视为 Java 的近亲，但没有冗长。Groovy 是一种具有可选类型的动态语言。这意味着当需要时，您可以获得类型系统的保证，并且在知道自己在做什么时，可以使用鸭子类型的多功能性。

使用这种语言，您可以编写没有 getter、setter、`equals`和`hashcode`方法的 POJOs。一切都为您处理。

写`==`实际上会调用`equals`方法。操作符可以被重载，这允许使用小箭头（例如`<<`）向文件中写入文本。这也意味着您可以将整数添加到`BigIntegers`并获得正确的结果。

**Groovy 开发工具包**（**GDK**）还为经典的 Java 对象添加了几种非常有趣的方法。它还将正则表达式和闭包视为一等公民。

### 注意

如果您想对 Groovy 有一个扎实的介绍，请查看[`www.groovy-lang.org/style-guide.html`](http://www.groovy-lang.org/style-guide.html)上的 Groovy 风格指南。

您还可以观看 Peter Ledbrook 在[`www.infoq.com/presentations/groovy-for-java`](http://www.infoq.com/presentations/groovy-for-java)上的精彩演示。

就我个人而言，我总是试图在我工作的应用程序的测试方面推动 Groovy。这确实提高了代码的可读性和开发人员的生产力。

## 使用 Spock 进行单元测试

为了能够在我们的项目中编写 Groovy 测试，我们需要使用 Groovy 插件而不是 Java 插件。

以下是您构建脚本中的内容：

```java
apply plugin: 'java'
```

将其更改为以下内容：

```java
apply plugin: 'groovy'
```

这种修改是完全无害的。Groovy 插件扩展了 Java 插件，因此它唯一的区别是它可以在`src/main/groovy`、`src/test/groovy`和`src/integrationTest/groovy`中添加 Groovy 源。

显然，我们还需要将 Groovy 添加到类路径中。我们还将通过`spock-spring`依赖项添加 Spock，这将使其与 Spring 兼容，这是最受欢迎的 Groovy 测试库：

```java
testCompile 'org.codehaus.groovy:groovy-all:2.4.4:indy'
testCompile 'org.spockframework:spock-spring'
```

现在我们可以用不同的方法重写`HomeControllerTest`。让我们在`src/test/groovy`中创建一个`HomeControllerSpec`类。我将其添加到`masterSpringMvc.controller`包中，就像我们的第一个`HomeControllerTest`实例一样：

```java
package masterSpringMvc.controller

import masterSpringMvc.MasterSpringMvcApplication
import masterSpringMvc.search.StubTwitterSearchConfig
import org.springframework.beans.factory.annotation.Autowired
import org.springframework.boot.test.SpringApplicationContextLoader
import org.springframework.test.context.ContextConfiguration
import org.springframework.test.context.web.WebAppConfiguration
import org.springframework.test.web.servlet.MockMvc
import org.springframework.test.web.servlet.setup.MockMvcBuilders
import org.springframework.web.context.WebApplicationContext
import spock.lang.Specification

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@ContextConfiguration(loader = SpringApplicationContextLoader,
        classes = [MasterSpringMvcApplication, StubTwitterSearchConfig])
@WebAppConfiguration
class HomeControllerSpec extends Specification {
    @Autowired
    WebApplicationContext wac;

    MockMvc mockMvc;

    def setup() {
        mockMvc = MockMvcBuilders.webAppContextSetup(this.wac).build();
    }

    def "User is redirected to its profile on his first visit"() {
        when: "I navigate to the home page"
        def response = this.mockMvc.perform(get("/"))

        then: "I am redirected to the profile page"
        response
                .andExpect(status().isFound())
                .andExpect(redirectedUrl("/profile"))
    }
}
```

我们的测试立即变得更易读，因为我们可以使用字符串作为方法名，并且 Spock 提供了小的 BDD DSL（领域特定语言）。这在这里并不直接可见，但`then`块内的每个语句都将隐式地成为一个断言。

在撰写本文时，由于 Spock 不读取元注解，因此无法使用`@SpringApplicationConfiguration`注解，因此我们只是用`@ContextConfiguration(loader = SpringApplicationContextLoader)`替换了它，这本质上是一样的。

现在我们有了相同测试的两个版本，一个是 Java，另一个是 Groovy。由您来选择最适合您编码风格的版本，并删除另一个版本。如果您决定坚持使用 Groovy，您将不得不用 Groovy 重写`should_redirect_to_tastes()`测试。这应该很容易。

Spock 还对模拟有强大的支持。我们可以稍微不同地重写之前的`SearchControllerMockTest`类：

```java
package masterSpringMvc.search

import masterSpringMvc.MasterSpringMvcApplication
import org.springframework.boot.test.SpringApplicationContextLoader
import org.springframework.test.context.ContextConfiguration
import org.springframework.test.context.web.WebAppConfiguration
import org.springframework.test.web.servlet.setup.MockMvcBuilders
import spock.lang.Specification

import static org.hamcrest.Matchers.*;
import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.*;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.*;

@ContextConfiguration(loader = SpringApplicationContextLoader,
        classes = [MasterSpringMvcApplication])
@WebAppConfiguration
class SearchControllerMockSpec extends Specification {
    def twitterSearch = Mock(TwitterSearch)
    def searchController = new SearchController(twitterSearch)

    def mockMvc = MockMvcBuilders.standaloneSetup(searchController)
            .setRemoveSemicolonContent(false)
            .build()

    def "searching for the spring keyword should display the search page"() {
        when: "I search for spring"
        def response = mockMvc.perform(get("/search/mixed;keywords=spring"))

        then: "The search service is called once"
        1 * twitterSearch.search(_, _) >> [new LightTweet('tweetText')]

        and: "The result page is shown"
        response
                .andExpect(status().isOk())
                .andExpect(view().name("resultPage"))

        and: "The model contains the result tweets"
        response
                .andExpect(model().attribute("tweets", everyItem(
                hasProperty("text", is("tweetText"))
        )))
    }
}
```

Mockito 的所有冗长都已经消失。`then`块实际上断言了`twitterSearch`方法被调用一次(`1 *`)，并且带有任何参数(`_, _`)。与 mockito 一样，我们也可以期望特定的参数。

双箭头`>>`语法用于从模拟方法返回对象。在我们的情况下，它是包含一个元素的列表。

只需在我们的类路径中添加少量依赖，我们就已经编写了更易读的测试，但我们还没有完成。我们还将重构我们的验收测试以使用 Geb，这是一个可以驱动 Selenium 测试的 Groovy 库。

## 使用 Geb 进行集成测试

Geb 是在 Grails 框架中编写测试的事实上的库。尽管它的版本是 0.12.0，但它非常稳定，非常舒适。

它提供了类似 jQuery 的选择器 API，使得即使对于前端开发人员来说，编写测试也变得很容易。Groovy 也是一种具有一些 JavaScript 影响的语言，这也会吸引他们。

让我们在类路径中添加支持 Spock 规范的 Geb：

```java
testCompile 'org.gebish:geb-spock:0.12.0'
```

可以通过在`src/integrationTest/groovy`的根目录下找到的 Groovy 脚本`GebConfig.groovy`来配置 Geb：

```java
import org.openqa.selenium.Dimension
import org.openqa.selenium.firefox.FirefoxDriver
import org.openqa.selenium.phantomjs.PhantomJSDriver

reportsDir = new File('./build/geb-reports')
driver = {
        def driver = new FirefoxDriver()
    // def driver = new PhantomJSDriver()
    driver.manage().window().setSize(new Dimension(1024, 768))
    return driver
}
```

在这个配置中，我们指示 Geb 将生成其报告的位置以及要使用的驱动程序。Geb 中的报告是增强版的屏幕截图，还包含当前页面的 HTML。可以通过在 Geb 测试中调用`report`函数来随时触发它们的生成。

让我们用 Geb 重写我们的第一个集成测试：

```java
import geb.Configuration
import geb.spock.GebSpec
import masterSpringMvc.MasterSpringMvcApplication
import masterSpringMvc.search.StubTwitterSearchConfig
import org.springframework.beans.factory.annotation.Value
import org.springframework.boot.test.SpringApplicationContextLoader
import org.springframework.boot.test.WebIntegrationTest
import org.springframework.test.context.ContextConfiguration

@ContextConfiguration(loader = SpringApplicationContextLoader,
        classes = [MasterSpringMvcApplication, StubTwitterSearchConfig])
@WebIntegrationTest(randomPort = true)
class IntegrationSpec extends GebSpec {

    @Value('${local.server.port}')
    int port

    Configuration createConf() {
        def configuration = super.createConf()
        configuration.baseUrl = "http://localhost:$port"
        configuration
    }

    def "User is redirected to the login page when not logged"() {
        when: "I navigate to the home page"
        go '/'
//        report 'navigation-redirection'

        then: "I am redirected to the profile page"
        $('h2', 0).text() == 'Login'
    }
}
```

目前，它与 FluentLenium 非常相似。我们已经可以看到`$`函数，它将允许我们通过其选择器抓取 DOM 元素。在这里，我们还声明了我们要通过给定的`0`索引在页面中找到第一个`h2`。

## 使用 Geb 的页面对象

使用 Geb 的页面对象真是一种真正的乐趣。我们将创建与之前相同的页面对象，以便您可以欣赏到其中的区别。

使用 Geb，页面对象必须继承自`geb.Page`类。首先，让我们创建`LoginPage`。我建议避免将其放在与之前相同的包中。我创建了一个名为`geb.pages`的包：

```java
package geb.pages

import geb.Page

class LoginPage extends Page {

    static url = '/login'
    static at = { $('h2', 0).text() == 'Login' }
    static content = {
        twitterSignin { $('button', name: 'twitterSignin') }
    }

    void loginWithTwitter() {
        twitterSignin.click()
    }
}
```

然后我们可以创建`ProfilePage`：

```java
package geb.pages

import geb.Page

class ProfilePage extends Page {

    static url = '/profile'
    static at = { $('h2', 0).text() == 'Your profile' }
    static content = {
        addTasteButton { $('button', name: 'addTaste') }
        saveButton { $('button', name: 'save') }
    }

    void fillInfos(String twitterHandle, String email, String birthDate) {
        $("#twitterHandle") << twitterHandle
        $("#email") << email
        $("#birthDate") << birthDate
    }

    void addTaste(String taste) {
        addTasteButton.click()
        $("#tastes0") << taste
    }

    void saveProfile() {
        saveButton.click();
    }
}
```

这基本上与以前的页面相同。请注意小的`<<`用于为输入元素分配值。您也可以在它们上调用`setText`。

`at`方法完全属于框架的一部分，当您导航到相应的页面时，Geb 将自动断言这些方法。

让我们创建`SearchResultPage`：

```java
package geb.pages

import geb.Page

class SearchResultPage extends Page {
    static url = '/search'
    static at = { $('h2', 0).text().startsWith('Tweet results for') }
    static content = {
        resultList { $('ul.collection') }
        results { resultList.find('li') }
    }
}
```

由于能够重用先前定义的内容，它会变得更短。

在没有设置页面对象的情况下，我们可以编写以下测试：

```java
import geb.Configuration
import geb.pages.LoginPage
import geb.pages.ProfilePage
import geb.pages.SearchResultPage
import geb.spock.GebSpec
import masterSpringMvc.MasterSpringMvcApplication
import masterSpringMvc.auth.StubSocialSigninConfig
import masterSpringMvc.search.StubTwitterSearchConfig
import org.springframework.beans.factory.annotation.Value
import org.springframework.boot.test.SpringApplicationContextLoader
import org.springframework.boot.test.WebIntegrationTest
import org.springframework.test.context.ContextConfiguration

@ContextConfiguration(loader = SpringApplicationContextLoader,
        classes = [MasterSpringMvcApplication, StubTwitterSearchConfig, StubSocialSigninConfig])
@WebIntegrationTest(randomPort = true)
class IntegrationSpec extends GebSpec {

    @Value('${local.server.port}')
    int port

    Configuration createConf() {
        def configuration = super.createConf()
        configuration.baseUrl = "http://localhost:$port"
        configuration
    }

    def "User is redirected to the login page when not logged"() {
        when: "I navigate to the home page"
        go '/'

        then: "I am redirected to the login page"
        $('h2').text() == 'Login'
    }

    def "User is redirected to its profile on his first visit"() {
        when: 'I am connected'
        to LoginPage
        loginWithTwitter()

        and: "I navigate to the home page"
        go '/'

        then: "I am redirected to the profile page"
        $('h2').text() == 'Your profile'
    }

    def "After filling his profile, the user is taken to result matching his tastes"() {
        given: 'I am connected'
        to LoginPage
        loginWithTwitter()

        and: 'I am on my profile'
        to ProfilePage

        when: 'I fill my profile'
        fillInfos("geowarin", "geowarin@mymail.com", "03/19/1987");
        addTaste("spring")

        and: 'I save it'
        saveProfile()

        then: 'I am taken to the search result page'
        at SearchResultPage
        page.results.size() == 2
    }
}
```

哇，多么美丽！您肯定可以直接使用 Geb 编写用户故事！

通过我们简单的测试，我们只是触及了 Geb 的表面。还有更多功能可用，我鼓励您阅读*Geb 之书*，这是一份非常好的文档，可在[`www.gebish.org/manual/current/`](http://www.gebish.org/manual/current/)上找到。

# 检查点

在本章中，我们在 `src/test/java` 中添加了一堆测试。我选择使用 Groovy，所以我删除了重复的测试：

![检查点](img/image00981.jpeg)

在 `src/test/groovy` 目录中，我已经重构了两个测试如下：

![检查点](img/image00982.jpeg)

在 `src/integrationTest/groovy` 中，我们有一个使用 Geb 编写的集成测试：

![检查点](img/image00983.jpeg)

最后，我们在 Gradle 构建中添加了一个 `integrationTest` 任务。运行 `gradle clean test` 和 `gradle clean integrationTest` 来确保所有测试都通过。

如果构建成功，我们准备进入下一章。

# 总结

在本章中，我们研究了单元测试和集成测试之间的区别。

我们看到测试是一个健康的习惯，将使我们对我们构建和发布的内容充满信心。这将在长远来看为我们节省金钱并减少一些头痛。

Spring 与经典的使用 Java 编写的 JUnit 测试很好配合，并且对集成测试有一流的支持。但我们也可以轻松地使用其他语言，比如 Groovy，使测试更易读和更易写。

测试无疑是 Spring 框架的最大优势之一，也是首次使用依赖注入的主要原因之一。

敬请关注下一章，我们将优化我们的应用程序，使其准备好在云中部署！

# 第七章。优化您的请求

在本章中，我们将研究不同的技术来提高我们应用程序的性能。

我们将实现优化 Web 应用程序的经典方法：缓存控制头、Gzipping、应用程序缓存和 ETags，以及更具反应性的内容，如异步方法调用和 WebSockets。

# 生产配置文件

在上一章中，我们看到了如何定义一个应用程序属性文件，该文件只在使用特定配置文件启动应用程序时才会被读取。我们将使用相同的方法，在 `src/main/resources` 目录中创建一个 `application-prod.properties` 文件，就在现有的 `application.properties` 文件旁边。这样，我们将能够使用优化设置配置生产环境。

我们将在这个文件中放入一些属性以开始。在第二章中，*处理表单和复杂的 URL 映射*，我们停用了 Thymeleaf 缓存，并强制翻译捆绑包在每次访问时重新加载。

这对开发很有用，但在生产中是无用且耗时的。所以让我们来解决这个问题：

```java
spring.thymeleaf.cache=true
spring.messages.cache-seconds=-1
```

缓存期限为 `-1` 表示永久缓存捆绑包。

现在，如果我们使用 "prod" 配置文件启动应用程序，模板和捆绑包应该永久缓存。

来自 "prod" 配置文件的属性确实会覆盖我们 `application.properties` 文件中声明的属性。

# Gzipping

**Gzipping** 是一种被浏览器广泛理解的压缩算法。您的服务器将提供压缩响应，这将消耗更多的 CPU 周期，但将节省带宽。

然后客户端浏览器将为解压资源和向用户显示资源而付费。

要利用 Tomcat 的 Gzipping 能力，只需将以下行添加到 `application-prod.properties` 文件中：

```java
server.tomcat.compression=on
server.tomcat.compressableMimeTypes=text/html,text/xml,text/css,text/plain,\
  application/json,application/xml,application/javascript
```

这将在提供与列表中指定的 MIME 类型匹配且长度大于 2048 字节的任何文件时启用 Tomcat 的 Gzipping 压缩。您可以将 `server.tomcat.compression` 设置为 `force` 以强制压缩，或者将其设置为数字值，如果您想更改 Gzipped 资产的最小长度值。

如果您想更多地控制压缩，比如压缩级别，或者想排除用户代理不进行压缩，您可以通过将 `org.eclipse.jetty:jetty-servlets` 依赖项添加到您的项目中，使用 Jetty 中的 `GzipFilter` 类。

这将自动触发`GzipFilterAutoConfiguration`类，可以通过以`spring.http.gzip`为前缀的一些属性进行配置。查看`GzipFilterProperties`以了解其自定义级别。

### 注意

有关更多信息，请参阅[`docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html#how-to-enable-http-response-compression`](http://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html#how-to-enable-http-response-compression)上的文档。

# 缓存控制

缓存控制是由服务器发送的一组 HTTP 头，用于控制用户的浏览器允许缓存资源的方式。

在上一章中，我们已经看到 Spring Security 自动禁用了受保护资源的缓存。

如果我们想要从缓存控制中受益，我们必须首先禁用该功能：

```java
security.headers.cache=false

# Cache resources for 3 days
spring.resources.cache-period=259200
```

现在，启动应用程序，转到主页，并检查 Chrome 开发者控制台。您会看到我们的 JavaScript 文件已经被 Gzip 压缩和缓存，如下截图所示：

![缓存控制](img/image00984.jpeg)

如果您想对缓存有更多控制，可以在配置中为自己的资源添加处理程序：

```java
@Override
public void addResourceHandlers(ResourceHandlerRegistry registry) {
    // This is just an example
    registry.addResourceHandler("/img/**")
            .addResourceLocations("classpath:/static/images/")
            .setCachePeriod(12);
}
```

我们还可以覆盖 Spring Security 的默认设置。如果我们想要为我们的 API 停用“无缓存控制”策略，我们可以像这样更改`ApiSecurityConfiguration`类：

```java
@Override
protected void configure(HttpSecurity http) throws Exception {
    http
        .antMatcher("/api/**")
// This is just an example – not required in our case
        .headers().cacheControl().disable()
        .httpBasic().and()
        .csrf().disable()
        .authorizeRequests()
        .antMatchers(HttpMethod.GET).hasRole("USER")
        .antMatchers(HttpMethod.POST).hasRole("ADMIN")
        .antMatchers(HttpMethod.PUT).hasRole("ADMIN")
        .antMatchers(HttpMethod.DELETE).hasRole("ADMIN")
        .anyRequest().authenticated();
}
```

# 应用程序缓存

现在我们的网络请求已经被压缩和缓存，我们可以采取的下一步措施是将昂贵操作的结果放入缓存以减少服务器负载。Twitter 搜索需要一些时间，并且会消耗我们在 Twitter API 上的应用程序请求比例。使用 Spring，我们可以轻松地缓存搜索并在每次使用相同参数调用搜索时返回相同的结果。

我们需要做的第一件事是使用`@EnableCache`注解激活 Spring 缓存。我们还需要创建一个`CacheManager`来解析我们的缓存。让我们在`config`包中创建一个`CacheConfiguration`类：

```java
package masterSpringMvc.config;

import org.springframework.cache.CacheManager;
import org.springframework.cache.annotation.EnableCaching;
import org.springframework.cache.concurrent.ConcurrentMapCache;
import org.springframework.cache.support.SimpleCacheManager;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import java.util.Arrays;

@Configuration
@EnableCaching
public class CacheConfiguration {

    @Bean
    public CacheManager cacheManager() {
        SimpleCacheManager simpleCacheManager = new SimpleCacheManager();
        simpleCacheManager.setCaches(Arrays.asList(
                new ConcurrentMapCache("searches")
        ));
        return simpleCacheManager;
    }
}
```

在上一个例子中，我们使用了最简单的缓存抽象。还有其他可用的实现，比如`EhCacheCacheManager`或`GuavaCacheManager`，我们一会儿会用到。

现在我们已经配置了缓存，我们可以在我们的方法上使用`@Cacheable`注解。这样做时，Spring 将自动缓存方法的结果，并将其与当前参数关联以进行检索。

Spring 需要在缓存方法的 bean 周围创建代理。这通常意味着在同一个 bean 内调用缓存方法不会失败地使用 Spring 的缓存。

在我们的情况下，在`SearchService`类中，我们调用搜索操作的部分将受益于缓存。

作为预备步骤，最好将负责创建`SearchParameters`类的代码放在一个名为`SearchParamsBuilder`的专用对象中：

```java
package masterSpringMvc.search;

import org.springframework.social.twitter.api.SearchParameters;

import java.util.List;
import java.util.stream.Collectors;

public class SearchParamsBuilder {

    public static SearchParameters createSearchParam(String searchType, String taste) {
        SearchParameters.ResultType resultType = getResultType(searchType);
        SearchParameters searchParameters = new SearchParameters(taste);
        searchParameters.resultType(resultType);
        searchParameters.count(3);
        return searchParameters;
    }

    private static SearchParameters.ResultType getResultType(String searchType) {
        for (SearchParameters.ResultType knownType : SearchParameters.ResultType.values()) {
            if (knownType.name().equalsIgnoreCase(searchType)) {
                return knownType;
            }
        }
        return SearchParameters.ResultType.RECENT;
    }
}
```

这将帮助我们在我们的服务中创建搜索参数。

现在我们想为我们的搜索结果创建一个缓存。我们希望每次调用 Twitter API 时都会缓存。Spring 缓存注解依赖于代理来对`@Cacheable`方法进行检测。因此，我们需要一个新的类，其中的方法带有`@Cacheable`注解。

当您使用 Spring 抽象 API 时，您不知道缓存的底层实现。许多都要求缓存方法的返回类型和参数类型都是可序列化的。

`SearchParameters`不是可序列化的，这就是为什么我们将搜索类型和关键字（都是字符串）传递给缓存方法的原因。

由于我们想要将`LightTweets`对象放入缓存，我们希望使它们可序列化；这将确保它们始终可以从任何缓存抽象中写入和读取：

```java
public class LightTweet implements Serializable {
    // the rest of the code remains unchanged
}
```

让我们创建一个`SearchCache`类，并将其放在`search.cache`包中：

```java
package masterSpringMvc.search.cache;

import masterSpringMvc.search.LightTweet;
import masterSpringMvc.search.SearchParamsBuilder;
import org.apache.commons.logging.Log;
import org.apache.commons.logging.LogFactory;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.autoconfigure.social.TwitterProperties;
import org.springframework.cache.annotation.Cacheable;
import org.springframework.social.twitter.api.SearchParameters;
import org.springframework.social.twitter.api.Twitter;
import org.springframework.social.twitter.api.impl.TwitterTemplate;
import org.springframework.stereotype.Service;

import java.util.List;
import java.util.stream.Collectors;

@Service
public class SearchCache {
    protected final Log logger = LogFactory.getLog(getClass());
    private Twitter twitter;

    @Autowired
    public SearchCache(TwitterProperties twitterProperties) {
        this.twitter = new TwitterTemplate(twitterProperties.getAppId(), twitterProperties.getAppSecret());
    }

    @Cacheable("searches")
    public List<LightTweet> fetch(String searchType, String keyword) {
        logger.info("Cache miss for " + keyword);
        SearchParameters searchParam = SearchParamsBuilder.createSearchParam(searchType, keyword);
        return twitter.searchOperations()
                .search(searchParam)
                .getTweets().stream()
                .map(LightTweet::ofTweet)
                .collect(Collectors.toList());
    }
}
```

它真的不能再简单了。我们使用`@Cacheable`注释来指定将使用的缓存的名称。不同的缓存可能有不同的策略。

请注意，我们手动创建了一个新的`TwitterTemplate`方法，而不是像以前那样注入它。这是因为稍后我们将不得不从其他线程访问缓存。在 Spring Boot 的`TwitterAutoConfiguration`类中，`Twitter` bean 绑定到请求范围，因此在 Servlet 线程之外不可用。

有了这两个新对象，我们的`SearchService`类的代码就变成了这样：

```java
package masterSpringMvc.search;

import masterSpringMvc.search.cache.SearchCache;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Profile;
import org.springframework.stereotype.Service;

import java.util.List;
import java.util.stream.Collectors;

@Service
@Profile("!async")
public class SearchService implements TwitterSearch {
    private SearchCache searchCache;

    @Autowired
    public SearchService(SearchCache searchCache) {
        this.searchCache = searchCache;
    }

    @Override
    public List<LightTweet> search(String searchType, List<String> keywords) {
        return keywords.stream()
                .flatMap(keyword -> searchCache.fetch(searchType, keyword).stream())
                .collect(Collectors.toList());
    }
}
```

请注意，我们使用`@Profile("!async")`对服务进行了注释。这意味着只有在未激活`async`配置文件时，我们才会创建这个 bean。

稍后，我们将创建`TwitterSearch`类的另一个实现，以便能够在两者之间切换。

不错！假设我们重新启动应用程序并尝试一个大请求，比如以下内容：

`http://localhost:8080/search/mixed;keywords=docker,spring,spring%20boot,spring%20mvc,groovy,grails`

一开始可能需要一点时间，但然后我们的控制台将显示以下日志：

```java
2015-08-03 16:04:01.958  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for docker
2015-08-03 16:04:02.437  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for spring
2015-08-03 16:04:02.728  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for spring boot
2015-08-03 16:04:03.098  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for spring mvc
2015-08-03 16:04:03.383  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for groovy
2015-08-03 16:04:03.967  INFO 38259 --- [nio-8080-exec-8] m.search.cache.SearchCache               : Cache miss for grails

```

之后，如果我们点击刷新，结果将立即显示，并且控制台中不会出现缓存未命中。

就我们的缓存而言，就缓存 API 而言还有很多内容。您可以使用以下方法对方法进行注释：

+   `@CachEvict`：这将从缓存中删除条目

+   `@CachePut`：这将把方法的结果放入缓存，而不会干扰方法本身

+   `@Caching`：这将重新组合缓存注释

+   `@CacheConfig`：这指向不同的缓存配置

`@Cacheable`注释也可以配置为根据某些条件缓存结果。

### 注意

有关 Spring 缓存的更多信息，请参阅以下文档：

[`docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/cache.html)

## 缓存失效

目前，搜索结果将被永久缓存。使用默认的简单缓存管理器并不能给我们很多选项。我们可以做的另一件事是改进我们的应用程序缓存。由于我们的类路径中有 Guava，我们可以用以下代码替换缓存配置中的现有缓存管理器：

```java
package masterSpringMvc.config;

import com.google.common.cache.CacheBuilder;
import org.springframework.cache.CacheManager;
import org.springframework.cache.annotation.EnableCaching;
import org.springframework.cache.guava.GuavaCacheManager;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

import java.util.concurrent.TimeUnit;

@Configuration
@EnableCaching
public class CacheConfiguration {

    @Bean
    public CacheManager cacheManager() {
        GuavaCacheManager cacheManager = new GuavaCacheManager("searches");
        cacheManager
                .setCacheBuilder(
                        CacheBuilder.newBuilder()
                                .softValues()
                                .expireAfterWrite(10, TimeUnit.MINUTES)
                );
        return cacheManager;
    }
}
```

这将构建一个在 10 分钟后过期并使用软值的缓存，这意味着如果 JVM 内存不足，条目将被清理。

尝试玩弄 Guava 的缓存构建器。您可以为测试指定更小的时间单位，甚至指定不同的缓存策略。

### 注意

请参阅[`code.google.com/p/guava-libraries/wiki/CachesExplained`](https://code.google.com/p/guava-libraries/wiki/CachesExplained)上的文档。

## 分布式缓存

我们已经有了一个 Redis 配置文件。如果 Redis 可用，我们还可以将其用作缓存提供程序。这将允许我们在多个服务器上分发缓存。让我们更改`RedisConfig`类：

```java
package masterSpringMvc.config;

import org.springframework.beans.factory.annotation.Qualifier;
import org.springframework.cache.CacheManager;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;
import org.springframework.context.annotation.Primary;
import org.springframework.context.annotation.Profile;
import org.springframework.data.redis.cache.RedisCacheManager;
import org.springframework.data.redis.connection.RedisConnectionFactory;
import org.springframework.data.redis.core.RedisTemplate;
import org.springframework.session.data.redis.config.annotation.web.http.EnableRedisHttpSession;

import java.util.Arrays;

@Configuration
@Profile("redis")
@EnableRedisHttpSession
public class RedisConfig {

    @Bean(name = "objectRedisTemplate")
    public RedisTemplate objectRedisTemplate(RedisConnectionFactory redisConnectionFactory) {
        RedisTemplate<Object, Object> template = new RedisTemplate<>();
        template.setConnectionFactory(redisConnectionFactory);
        return template;
    }

    @Primary @Bean
    public CacheManager cacheManager(@Qualifier("objectRedisTemplate") RedisTemplate template) {
        RedisCacheManager cacheManager = new RedisCacheManager(template);
        cacheManager.setCacheNames(Arrays.asList("searches"));
        cacheManager.setDefaultExpiration(36_000);
        return cacheManager;
    }
}
```

有了这个配置，如果我们使用"Redis"配置文件运行我们的应用程序，那么 Redis 缓存管理器将被用来代替`CacheConfig`类中定义的缓存管理器，因为它被`@Primary`注释。

这将允许缓存在需要在多个服务器上进行扩展时进行分布。Redis 模板用于序列化缓存返回值和参数，并且需要对象是`Serializable`。

# 异步方法

我们的应用程序仍然存在瓶颈；当用户搜索十个关键字时，每次搜索都会按顺序执行。我们可以通过使用不同的线程并同时启动所有搜索来轻松提高应用程序的速度。

要启用 Spring 的异步功能，必须使用`@EnableAsync`注释。这将透明地执行任何使用`@Async`注释的方法，使用`java.util.concurrent.Executor`。

可以通过实现`AsyncConfigurer`接口来自定义默认的执行程序。让我们在`config`包中创建一个名为`AsyncConfig`的新配置类：

```java
package masterSpringMvc.config;

import org.apache.commons.logging.Log;
import org.apache.commons.logging.LogFactory;
import org.springframework.aop.interceptor.AsyncUncaughtExceptionHandler;
import org.springframework.context.annotation.Configuration;
import org.springframework.scheduling.annotation.AsyncConfigurer;
import org.springframework.scheduling.annotation.EnableAsync;

import java.util.concurrent.Executor;
import java.util.concurrent.Executors;

@Configuration
@EnableAsync
public class AsyncConfiguration implements AsyncConfigurer {

    protected final Log logger = LogFactory.getLog(getClass());

    @Override
    public Executor getAsyncExecutor() {
        return Executors.newFixedThreadPool(10);
    }

    @Override
    public AsyncUncaughtExceptionHandler getAsyncUncaughtExceptionHandler() {
        return (ex, method, params) -> logger.error("Uncaught async error", ex);
    }
}
```

通过这种配置，我们确保在整个应用程序中不会分配超过 10 个线程来处理我们的异步任务。这在 Web 应用程序中非常重要，因为每个客户端都有一个专用的线程。您使用的线程越多，它们阻塞的时间越长，您可以处理的客户端请求就越少。

让我们注释我们的搜索方法并使其异步化。我们需要使其返回`Future`的子类型，这是一个表示异步结果的 Java 并发类。

我们将创建`TwitterSearch`类的新实现，该实现将在不同的线程中查询搜索 API。该实现有点棘手，所以我会将其分解成小部分。

首先，我们需要使用`@Async`注解对将查询 API 的方法进行注释，以告诉 Spring 使用我们的执行程序安排任务。同样，Spring 将使用代理来完成其工作，因此这个方法必须在调用它的服务的不同类中。如果这个组件也能使用我们的缓存，那就太好了。这将导致我们创建这个组件：

```java
@Component
private static class AsyncSearch {
    protected final Log logger = LogFactory.getLog(getClass());
    private SearchCache searchCache;

    @Autowired
    public AsyncSearch(SearchCache searchCache) {
        this.searchCache = searchCache;
    }

    @Async
    public ListenableFuture<List<LightTweet>> asyncFetch(String searchType, String keyword) {
        logger.info(Thread.currentThread().getName() + " - Searching for " + keyword);
        return new AsyncResult<>(searchCache.fetch(searchType, keyword));
    }
}
```

现在不要创建这个类。让我们先看看我们的服务需要什么。

`ListenableFuture`抽象允许我们在未来完成后添加回调，无论是在正确结果的情况下还是在发生异常时。

等待一堆异步任务的算法看起来像这样：

```java
@Override
public List<LightTweet> search(String searchType, List<String> keywords) {
    CountDownLatch latch = new CountDownLatch(keywords.size());
    List<LightTweet> allTweets = Collections.synchronizedList(new ArrayList<>());
    keywords
            .stream()
            .forEach(keyword -> asyncFetch(latch, allTweets, searchType, keyword));

    await(latch);
    return allTweets;
}
```

如果您不了解`CountDownLatch`方法，它只是一个简单的阻塞计数器。

`await()`方法将等待，直到锁存器达到 0 才解锁线程。

在前面的代码中显示的`asyncFetch`方法将为我们的`asynFetch`方法附加一个回调。回调将结果添加到`allTweets`列表中，并递减锁存器。一旦每个回调都被调用，该方法将返回所有推文。

明白了吗？这是最终代码：

```java
package masterSpringMvc.search;

import masterSpringMvc.search.cache.SearchCache;
import org.apache.commons.logging.Log;
import org.apache.commons.logging.LogFactory;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.annotation.Profile;
import org.springframework.scheduling.annotation.Async;
import org.springframework.scheduling.annotation.AsyncResult;
import org.springframework.social.twitter.api.SearchParameters;
import org.springframework.stereotype.Component;
import org.springframework.stereotype.Service;
import org.springframework.util.concurrent.ListenableFuture;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.concurrent.CountDownLatch;

@Service
@Profile("async")
public class ParallelSearchService implements TwitterSearch {
    private final AsyncSearch asyncSearch;

    @Autowired
    public ParallelSearchService(AsyncSearch asyncSearch) {
        this.asyncSearch = asyncSearch;
    }

    @Override
    public List<LightTweet> search(String searchType, List<String> keywords) {
        CountDownLatch latch = new CountDownLatch(keywords.size());
        List<LightTweet> allTweets = Collections.synchronizedList(new ArrayList<>());

        keywords
                .stream()
                .forEach(keyword -> asyncFetch(latch, allTweets, searchType, keyword));

        await(latch);
        return allTweets;
    }

    private void asyncFetch(CountDownLatch latch, List<LightTweet> allTweets, String searchType, String keyword) {
        asyncSearch.asyncFetch(searchType, keyword)
                .addCallback(
                        tweets -> onSuccess(allTweets, latch, tweets),
                        ex -> onError(latch, ex));
    }

    private void await(CountDownLatch latch) {
        try {
            latch.await();
        } catch (InterruptedException e) {
            throw new IllegalStateException(e);
        }
    }

    private static void onSuccess(List<LightTweet> results, CountDownLatch latch, List<LightTweet> tweets) {
        results.addAll(tweets);
        latch.countDown();
    }

    private static void onError(CountDownLatch latch, Throwable ex) {
        ex.printStackTrace();
        latch.countDown();
    }

    @Component
    private static class AsyncSearch {
        protected final Log logger = LogFactory.getLog(getClass());
        private SearchCache searchCache;

        @Autowired
        public AsyncSearch(SearchCache searchCache) {
            this.searchCache = searchCache;
        }

        @Async
        public ListenableFuture<List<LightTweet>> asyncFetch(String searchType, String keyword) {
            logger.info(Thread.currentThread().getName() + " - Searching for " + keyword);
            return new AsyncResult<>(searchCache.fetch(searchType, keyword));
        }
    }
}
```

现在，要使用这个实现，我们需要使用`async`配置文件运行应用程序。

我们可以通过用逗号分隔它们来同时运行多个活动配置文件，如下所示：

`--spring.profiles.active=redis,async`

如果我们对多个术语进行搜索，我们可以看到类似这样的东西：

```java
pool-1-thread-3 - Searching groovy
pool-1-thread-1 - Searching spring
pool-1-thread-2 - Searching java
```

这表明不同的搜索是并行进行的。

Java 8 实际上引入了一种称为`CompletableFuture`的新类型，这是一个更好的 API 来操作 futures。可完成的未来的主要问题是没有执行程序可以在没有一点代码的情况下与它们一起工作。这超出了本文的范围，但您可以查看我的博客了解有关该主题的文章：[`geowarin.github.io/spring/2015/06/12/completable-futures-with-spring-async.html`](http://geowarin.github.io/spring/2015/06/12/completable-futures-with-spring-async.html)。

### 注意

**免责声明**

以下部分包含大量的 JavaScript。显然，我认为你应该看一下代码，特别是如果 JavaScript 不是你最喜欢的语言的话。现在是学习它的时候了。话虽如此，即使 WebSocket 非常酷，也不是必需的。您可以放心地跳到最后一章并立即部署您的应用程序。

# ETags

我们的 Twitter 结果被整洁地缓存，因此刷新结果页面的用户不会触发对 Twitter API 的额外搜索。但是，即使结果没有改变，响应也会多次发送给这个用户，这将浪费带宽。

ETag 是 Web 响应数据的哈希值，并作为标头发送。客户端可以记住资源的 ETag，并使用`If-None-Match`标头将最后已知版本发送到服务器。这使得服务器可以在请求在此期间不发生变化时回答`304 Not Modified`。

Spring 有一个特殊的 Servlet 过滤器，称为`ShallowEtagHeaderFilter`，用于处理 ETags。只需将其添加为`MasterSpringMvc4Application`配置类中的一个 bean：

```java
@Bean
public Filter etagFilter() {
    return new ShallowEtagHeaderFilter();
}
```

只要响应没有缓存控制标头，这将自动生成响应的 ETags。

现在，如果我们查询我们的 RESTful API，我们可以看到 ETag 随服务器响应一起发送：

```java
> http GET 'http://localhost:8080/api/search/mixed;keywords=spring' -a admin:admin
HTTP/1.1 200 OK
Content-Length: 1276
Content-Type: application/json;charset=UTF-8
Date: Mon, 01 Jun 2015 11:29:51 GMT
ETag: "00a66d6dd835b6c7c60638eab976c4dd7"
Server: Apache-Coyote/1.1
Set-Cookie: JSESSIONID=662848E4F927EE9A1BA2006686ECFE4C; Path=/; HttpOnly

```

现在，如果我们再次请求相同的资源，在`If-None-Match`标头中指定我们知道的最后一个 ETag，服务器将自动以`304 Not Modified`状态响应：

```java
> http GET 'http://localhost:8080/api/search/mixed;keywords=spring' If-None-Match:'"00a66d6dd835b6c7c60638eab976c4dd7"' -a admin:admin
HTTP/1.1 304 Not Modified
Date: Mon, 01 Jun 2015 11:34:21 GMT
ETag: "00a66d6dd835b6c7c60638eab976c4dd7"
Server: Apache-Coyote/1.1
Set-Cookie: JSESSIONID=CA956010CF268056C241B0674C6C5AB2; Path=/; HttpOnly

```

### 提示

由于我们搜索的并行性质，不同关键字获取的推文可能以不同的顺序到达，这将导致 ETag 发生变化。如果您希望这种技术适用于多个搜索，请在将搜索结果发送到客户端之前考虑对搜索结果进行排序。

如果我们想利用它，显然需要重写我们的客户端代码来处理它们。我们将看到一个简单的解决方案，使用 jQuery 来做到这一点，使用浏览器的本地存储来保存用户的最新查询。

首先，从我们的模型中删除`tweets`变量；我们将不再从服务器进行搜索。您将需要修改一个或两个测试以反映这一变化。

在继续之前，让我们将 lodash 添加到我们的 JavaScript 库中。如果您不了解 lodash，可以将其添加到项目依赖项中，如下所示：

```java
compile 'org.webjars.bower:lodash:3.9.3'
```

将其添加到`default.html`布局中，就在 materialize 的 JavaScript 下面：

```java
<script src="img/lodash.js"></script>
```

我们将修改`resultPage.html`文件，并将推文应该出现的部分留空：

```java
<!DOCTYPE html>
<html 

      layout:decorator="layout/default">
<head lang="en">
    <title>Hello twitter</title>
</head>
<body>
<div class="row" layout:fragment="content">

    <h2 class="indigo-text center" th:text="|Tweet results for ${search}|">Tweets</h2>

    <ul id="tweets" class="collection">
 </ul>
</div>
</body>
</html>
```

然后，我们将在页面底部添加一个脚本元素，就在关闭 body 之前：

```java
<script layout:fragment="script" th:inline="javascript">
    /*<![CDATA[*/
    var baseUrl = /*[[@{/api/search}]]*/ "/";
    var currentLocation = window.location.href;
    var search = currentLocation.substr(currentLocation.lastIndexOf('/'));
    var url = baseUrl + search;
    /*]]>*/
</script>
```

上述脚本将负责构建我们请求的 URL。我们将通过发出简单的 jQuery AJAX 调用来使用它：

```java
$.ajax({
    url: url,
    type: "GET",
    beforeSend: setEtag,
    success: onResponse
});
```

我们将使用`beforeSend`回调在发出调用之前有机会修改请求标头：

```java
function getLastQuery() {
    return JSON.parse(localStorage.getItem('lastQuery')) || {};
}

function storeQuery(query) {
    localStorage.setItem('lastQuery', JSON.stringify(query));
}

function setEtag(xhr) {
    xhr.setRequestHeader('If-None-Match', getLastQuery().etag)
}
```

如您所见，我们可以轻松地从本地存储中读取和写入。这里的问题是本地存储只能处理字符串，因此我们必须将查询对象解析和序列化为 JSON。

如果 HTTP 状态是`304 Not Modified`，我们可以通过从本地存储中检索内容来处理响应：

```java
function onResponse(tweets, status, xhr) {
  if (xhr.status == 304) {
      console.log('Response has not changed');
      tweets = getLastQuery().tweets
  }

  var etag = xhr.getResponseHeader('Etag');
  storeQuery({tweets: tweets, etag: etag});

  displayTweets(tweets);
}

function displayTweets(tweets) {
  $('#tweets').empty();
  $.each(tweets, function (index, tweet) {
      addTweet(tweet);
  })
}
```

对于接下来将看到的`addTweet`函数，我使用了 lodash，这是一个非常有用的 JavaScript 实用程序库，用于生成模板。将推文添加到页面的函数可以编写如下：

```java
function addTweet(tweet) {
    var template = _.template('<li class="collection-item avatar">' +
        '<img class="circle" src="img/${tweet.profileImageUrl}" />' +
        '<span class="title">${tweet.user}</span>' +
        '<p>${tweet.text}</p>' +
        '</li>');

    $('#tweets').append(template({tweet: tweet}));
}
```

这是很多 JavaScript！使用 Backbone.js 等库将这种模式概括为单页面应用程序可能更有意义。尽管如此，这将作为一个简单的示例，展示如何在应用程序中实现 ETags。

如果您尝试多次刷新搜索页面，您会发现内容不会改变，并且会立即显示：

![ETags](img/image00985.jpeg)

ETags 还有其他用途，例如用于事务的乐观锁定（它让您知道客户端应该在任何时间上使用对象的哪个版本）。在服务器端在发送数据之前对数据进行哈希处理也是额外的工作，但它将节省带宽。

# WebSockets

我们可以考虑的另一种优化是在数据可用时将数据发送到客户端。由于我们在多个线程中获取搜索结果，数据将以多个块的形式到达。我们可以逐步发送它们，而不是等待所有结果。

Spring 对 WebSockets 有很好的支持，这是一种允许客户端与服务器保持长时间连接的协议。数据可以在连接的两端推送到 WebSockets，消费者将实时获取数据。

我们将使用一个名为 SockJS 的 JavaScript 库，以确保与所有浏览器兼容。如果我们的用户使用过时的浏览器，Sockjs 将自动切换到另一种策略。

我们还将使用 StompJS 连接到我们的消息代理。

将以下库添加到您的构建中：

```java
compile 'org.springframework.boot:spring-boot-starter-websocket'
compile 'org.springframework:spring-messaging'

compile 'org.webjars:sockjs-client:1.0.0'
compile 'org.webjars:stomp-websocket:2.3.3'
```

将 WebJars 添加到我们的默认 Thymeleaf 模板中：

```java
<script src="img/sockjs.js"></script>
<script src="img/stomp.js"></script>
```

要在我们的应用程序中配置 WebSockets，我们还需要添加一些配置：

```java
@Configuration
@EnableWebSocketMessageBroker
public class WebSocketConfiguration extends AbstractWebSocketMessageBrokerConfigurer {

    @Override
    public void configureMessageBroker(MessageBrokerRegistry config) {
        config.enableSimpleBroker("/topic");
        config.setApplicationDestinationPrefixes("/ws");
    }

    @Override
    public void registerStompEndpoints(StompEndpointRegistry registry) {
        registry.addEndpoint("/twitterSearch").withSockJS();
    }

}
```

这将配置我们应用程序中可用的不同频道。SockJS 客户端将连接到`twitterSearch`端点，并将数据推送到服务器上的`/ws/ channel`，并能够监听`/topic/`以进行更改。

这将允许我们在新的控制器中注入`SimpMessagingTemplate`，以便通过`/topic/searchResult`频道向客户端推送数据，如下所示：

```java
@Controller
public class SearchSocketController {
    private CachedSearchService searchService;
    private SimpMessagingTemplate webSocket;

    @Autowired
    public SearchSocketController(CachedSearchService searchService, SimpMessagingTemplate webSocket) {
        this.searchService = searchService;
        this.webSocket = webSocket;
    }

    @MessageMapping("/search")
    public void search(@RequestParam List<String> keywords) throws Exception {
        Consumer<List<LightTweet>> callback = tweet -> webSocket.convertAndSend("/topic/searchResults", tweet);
        twitterSearch(SearchParameters.ResultType.POPULAR, keywords, callback);
    }

    public void twitterSearch(SearchParameters.ResultType resultType, List<String> keywords, Consumer<List<LightTweet>> callback) {
        keywords.stream()
            .forEach(keyword -> {
                searchService.search(resultType, keyword)
                    .addCallback(callback::accept, Throwable::printStackTrace);
            });
    }
}
```

在我们的`resultPage`中，JavaScript 代码非常简单：

```java
var currentLocation = window.location.href;
var search = currentLocation.substr(currentLocation.lastIndexOf('=') + 1);

function connect() {
  var socket = new SockJS('/hello');
  stompClient = Stomp.over(socket);
  // stompClient.debug = null;
  stompClient.connect({}, function (frame) {
      console.log('Connected: ' + frame);

      stompClient.subscribe('/topic/searchResults', function (result) {
          displayTweets(JSON.parse(result.body));
      });

      stompClient.send("/app/search", {}, JSON.stringify(search.split(',')));
  });
}
```

`displayTweets`函数基本上与以前相同：

```java
function displayTweets(tweets) {
    $.each(tweets, function (index, tweet) {
        addTweet(tweet);
    })
}

function addTweet(tweet) {
    var template = _.template('<li class="collection-item avatar">' +
        '<img class="circle" src="img/${tweet.profileImageUrl}" />' +
        '<span class="title">${tweet.userName}</span>' +
        '<p>${tweet.text}</p>' +
        '</li>');

    $('#tweets').append(template({tweet: tweet}));
}
```

就是这样！客户端现在将实时接收应用程序中所有搜索的结果！

在将其推向生产之前，这将需要更多的工作。以下是一些想法：

+   为客户端创建子频道，以便私下监听更改

+   当客户端使用完毕时关闭频道

+   为新推文添加 CSS 过渡，以便用户感觉到它是实时的

+   使用真正的代理，如 RabbitMQ，允许后端与连接一起扩展

WebSocket 还有比这个简单示例更多的内容。不要忘记查看[`docs.spring.io/spring/docs/current/spring-framework-reference/html/websocket.html`](http://docs.spring.io/spring/docs/current/spring-framework-reference/html/websocket.html)上的文档以获取更多信息。

# 检查点

在本章中，我们创建了两个新的配置：`AsyncConfiguration`，它将允许我们使用`@Async`注解将任务提交给执行器，并且`CacheConfiguration`，它将创建一个`CacheManager`接口，并允许我们使用`@Cacheable`注解。由于我们可以使用 Redis 作为缓存管理器，我们还修改了`RedisConfig`类。

我们创建了一个`SearchCache`类，其中包含了推文的缓存，现在我们有两个`TwitterSearch`实现可供选择：老旧的`SearchService`，它将同步获取每个结果，以及`ParallelSearchService`，它将在不同的线程中发出每个查询：

![检查点](img/image00986.jpeg)

# 总结

在本章中，我们看到了与性能改进相关的两种不同哲学。一开始，我们试图通过缓存数据并尽可能少地使用与服务器的连接来减少客户端使用的带宽。

然而，在第二部分，我们开始做一些更高级的事情，允许搜索并行运行，并且每个客户端通过 Web 套接字与服务器保持同步的持久连接。这将允许客户端实时接收更新，我们的应用程序将感觉更具反应性，但会消耗更多的线程。

我强烈建议您在我们进入下一章并永久部署我们的应用程序之前，对结果进行完善！

# 第八章。将您的 Web 应用部署到云端

在本章中，我们将参观不同的云提供商，了解分布式架构的挑战和好处，并了解如何将您的 Web 应用程序部署到 Pivotal Web Services 和 Heroku。

# 选择您的主机

云托管有许多形式。对于开发人员来说，选择主要将在平台即服务（PaaS）和基础设施即服务（IaaS）之间进行。

使用最新的技术，您通常会有一台裸机，您可以管理并在其中安装应用程序所需的所有服务。

如果我们不考虑 Docker 等技术（这绝对是令人惊叹的，您绝对应该尝试一下），这与传统托管非常相似，其中您的运营团队将不得不设置和维护应用程序可以运行的环境。

另一方面，PaaS 使得在开发应用程序时轻松部署应用程序，只需简单的推送即可部署工作流程。

最知名的提供商有：

+   由 Pivotal 支持的 Cloud Foundry

+   由红帽提供的 OpenShift

+   Heroku 于 2010 年被 Salesforce 收购

这三个提供商各有优缺点。我将尝试为您概述这些。

## Cloud Foundry

由 Pivotal 支持，Pivotal Web 服务是由 Spring 背后的公司 Pivotal 维护的开源 PaaS Cloud Foundry 运行，并提供有趣的套餐。

他们提供 60 天的免费试用，其定价是您为实例分配的内存和您拥有的实例数量的函数。

他们的价格范围从每月 2.70 美元的最小（128 Mb）实例到每月 43.20 美元的 2 GB 实例。

如果您想尝试一下，免费试用不需要信用卡。他们有一个市场，可以轻松安装服务，如 Redis 或 Postgre SQL，但免费选项相对有限。他们有一个很好的命令行实用程序，可以从控制台管理您的应用程序。您可以使用构建包，也可以直接推送 JAR 文件进行部署。

### 提示

构建包将尝试猜测您正在使用的堆栈，并以最标准的方式构建您的应用程序（Maven 的`mvn package`，Gradle 的`./gradlew stage`等）。

### 注意

请参考以下网址提供的教程，将您的应用程序部署到 Cloud Foundry：

[`docs.cloudfoundry.org/buildpacks/java/gsg-spring.html`](http://docs.cloudfoundry.org/buildpacks/java/gsg-spring.html)

## OpenShift

**OpenShift**由 Red Hat 维护，并由 OpenShift Origin 提供支持，这是一个在 Google 的 Kubernetes 之上运行 Docker 容器的开源设施。

它的定价合理，并提供了很多自由度，因为它既是 PaaS 又是 IaaS。其定价是基于齿轮、运行应用程序的容器或服务（如 Jenkins 或数据库）。

OpenShift 有一个免费计划，提供三个小齿轮。您的应用程序每月必须闲置 24 小时，除非您输入您的计费信息。

额外或更大的齿轮按月收费，最小的约为 15 美元，最大的为 72 美元。

要在 OpenShift 上部署 Spring Boot 应用程序，您将需要使用自定义的 Do It Yourself cartridge。这比其他基于构建包的 PaaS 需要更多的工作，但也更容易配置。

查看博客文章，了解有关在 OpenShift 上使用 Spring Boot 的教程，网址为[`blog.codeleak.pl/2015/02/openshift-diy-build-spring-boot.html`](http://blog.codeleak.pl/2015/02/openshift-diy-build-spring-boot.html)。

## Heroku

Heroku 是一个知名的 PaaS，拥有广泛的文档和基于构建包的代码中心方法。它可以连接到许多称为附加组件的服务，但使用它们需要您的计费信息。

对于一个免费项目来说真的很有趣，而且很快就可以开始。不足之处是，如果您想扩展规模，它的直接成本将超过每月 25 美元。免费实例在 30 分钟的不活动后将进入睡眠模式，这意味着免费的 Heroku 应用程序加载时间总是需要 30 秒。

Heroku 拥有出色的管理仪表板和命令行工具。在本章中，我选择了 Heroku，因为它非常直接。您在这里掌握的概念适用于大多数 PaaS。

只要您不使用 Redis 附加组件，您可以遵循本章的大部分内容并部署您的应用程序，而无需提供信用卡信息。如果选择免费计划，您将不会被收费。

# 将您的 Web 应用程序部署到 Pivotal Web 服务

如果您想将您的应用程序部署到 Pivotal Web 服务（PWS），请参考本节。

## 安装 Cloud Foundry CLI 工具

创建 Cloud Foundry 应用程序的第一步是在 PWS 上设置一个帐户。这在[`docs.run.pivotal.io/starting/`](http://docs.run.pivotal.io/starting/)中有记录。

您将被要求创建一个组织，每个新组织都将在组织内创建一个默认空间（开发）。如下图所示：

![安装 Cloud Foundry CLI 工具](img/image00987.jpeg)

在左侧导航栏中，您将看到一个指向**工具**的链接，您可以从中下载 CLI。它也可以从开发者控制台中获得。选择适合您操作系统的适当软件包：

![安装 Cloud Foundry CLI 工具](img/image00988.jpeg)

## 组装应用程序

我们的应用程序只需要组装以进行部署。

PWS 的好处是您无需推送源代码即可部署。您可以生成 JAR，推送它，一切都将被自动检测。

我们可以使用以下命令将其打包以进行部署：

```java
./gradlew assemble

```

这将在`build/libs`目录中创建一个 jar 文件。此时，您可以执行以下命令。以下命令将将您的部署目标定位到 PWS（`run.pivotal.io`）中的空间：

```java
$ cf login -a api.run.pivotal.io -u <account email> -p <password> -o <organization> -s development

API endpoint: api.run.pivotal.io
Authenticating...
OK

Targeted org <account org>

Targeted space development

API endpoint:   https://api.run.pivotal.io (API version: 2.33.0) 
User:           <account email> 
Org:            <account organization> 
Space:          <account space>

```

成功登录后，您可以使用以下命令推送您的 jar 文件。您需要想出一个可用的名称：

```java
$ cf push your-app-name -p build/libs/masterSpringMvc-0.0.1-SNAPSHOT.jar

Creating app msmvc4 in org Northwest / space development as wlund@pivotal.io...
OK
Creating route msmvc4.cfapps.io...
OK
Binding msmvc4.cfapps.io to msmvc4...
OK
Uploading msmvc4...
Uploading app files from: build/libs/masterSpringMvc-0.0.1-SNAPSHOT.jar
Uploading 690.8K, 108 files
Done uploading 
OK
Starting app msmvc4 in org <Organization> / space development as <account email>
-----> Downloaded app package (15M)
-----> Java Buildpack Version: v3.1 | https://github.com/cloudfoundry/java-buildpack.git#7a538fb
-----> Downloading Open Jdk JRE 1.8.0_51 from https://download.run.pivotal.io/openjdk/trusty/x86_64/openjdk-1.8.0_51.tar.gz (1.5s)
 Expanding Open Jdk JRE to .java-buildpack/open_jdk_jre (1.4s)
-----> Downloading Open JDK Like Memory Calculator 1.1.1_RELEASE from https://download.run.pivotal.io/memory-calculator/trusty/x86_64/memory-calculator-1.1.1_RELEASE (0.1s)
 Memory Settings: -Xmx768M -Xms768M -XX:MaxMetaspaceSize=104857K -XX:MetaspaceSize=104857K -Xss1M
-----> Downloading Spring Auto Reconfiguration 1.7.0_RELEASE from https://download.run.pivotal.io/auto-reconfiguration/auto-reconfiguration-1.7.0_RELEASE.jar (0.0s)
-----> Uploading droplet (59M)
0 of 1 instances running, 1 starting
1 of 1 instances running

App started
OK
App msmvc4 was started using this command `CALCULATED_MEMORY=$($PWD/.java-buildpack/open_jdk_jre/bin/java-buildpack-memory-calculator-1.1.1_RELEASE -memorySizes=metaspace:64m.. -memoryWeights=heap:75,metaspace:10,stack:5,native:10 -totMemory=$MEMORY_LIMIT) && SERVER_PORT=$PORT $PWD/.java-buildpack/open_jdk_jre/bin/java -cp $PWD/.:$PWD/.java-buildpack/spring_auto_reconfiguration/spring_auto_reconfiguration-1.7.0_RELEASE.jar -Djava.io.tmpdir=$TMPDIR -XX:OnOutOfMemoryError=$PWD/.java-buildpack/open_jdk_jre/bin/killjava.sh $CALCULATED_MEMORY org.springframework.boot.loader.JarLauncher`

Showing health and status for app msmvc4 in org <Organization> / space development as <Account Email>
OK

requested state: started
instances: 1/1
usage: 1G x 1 instances
urls: msmvc4.cfapps.io
last uploaded: Tue Jul 28 22:04:08 UTC 2015
stack: cflinuxfs2
buildpack: java-buildpack=v3.1-https://github.com/cloudfoundry/java-buildpack.git#7a538fb java-main open-jdk-like-jre=1.8.0_51 open-jdk-like-memory-calculator=1.1.1_RELEASE spring-auto-reconfiguration=1.7.0_RELEASE

 state     since                    cpu    memory         disk         details 
#0   running   2015-07-28 03:05:04 PM   0.0%   450.9M of 1G   137M of 1G

```

平台正在为您执行很多工作。它提供了一个容器，并检测所需的构建包，本例中为 Java。

然后安装所需的 JDK 并上传我们指向的应用程序。它创建了一个应用程序的路由，并向我们报告，然后为我们启动了应用程序。

现在您可以在开发者控制台上查看应用程序：

![组装应用程序](img/image00989.jpeg)

选择突出显示的路由后，应用程序将可供使用。访问[`msmvc4.cfapps.io`](http://msmvc4.cfapps.io)，然后您将看到以下截图：

![组装应用程序](img/image00990.jpeg)

太棒了！

唯一还不能工作的是文件上传。但是，我们将在一分钟内解决这个问题。

## 激活 Redis

在您的应用程序服务中，您可以在许多服务之间进行选择。其中之一是 Redis Cloud，它具有 30MB 免费存储空间的免费计划。继续选择此计划。

在表格中，选择你喜欢的任何名称，并将服务绑定到你的应用程序。默认情况下，Cloud Foundry 将在你的环境中注入与服务相关的一些属性：

+   `cloud.services.redis.connection.host`

+   `cloud.services.redis.connection.port`

+   `cloud.services.redis.connection.password`

+   `cloud.services.redis.connection.uri`

这些属性将始终遵循相同的约定，因此在添加更多服务时很容易跟踪您的服务。

默认情况下，Cloud Foundry 启动 Spring 应用程序并激活 Cloud 配置文件。

我们可以利用这一点，在`src/main/resources`中创建一个`application-cloud.properties`文件，当我们的应用程序在 PWS 上运行时将使用该文件：

```java
spring.profiles.active=prod,redis

spring.redis.host=${cloud.services.redis.connection.host}
spring.redis.port=${cloud.services.redis.connection.port}
spring.redis.password=${cloud.services.redis.connection.password}

upload.pictures.uploadPath=file:/tmp
```

这将绑定我们的 Redis 实例到我们的应用程序，并激活两个额外的配置文件：`prod`和`redis`。

我们还更改了上传图片的路径。请注意，在云上使用文件系统遵守不同的规则。请参考以下链接获取更多详细信息：

[`docs.run.pivotal.io/devguide/deploy-apps/prepare-to-deploy.html#filesystem`](http://docs.run.pivotal.io/devguide/deploy-apps/prepare-to-deploy.html#filesystem)

我们需要做的最后一件事是停用一个 Spring Session 功能，在我们托管的实例上将不可用：

```java
@Bean
@Profile({"cloud", "heroku"})
public static ConfigureRedisAction configureRedisAction() {
    return ConfigureRedisAction.NO_OP;
}
```

### 注意

有关更多信息，请访问[`docs.spring.io/spring-session/docs/current/reference/html5/#api-redisoperationssessionrepository-sessiondestroyedevent`](http://docs.spring.io/spring-session/docs/current/reference/html5/#api-redisoperationssessionrepository-sessiondestroyedevent)。

您将看到此配置也将应用于 Heroku。

就是这样。您可以重新组装您的 Web 应用程序并再次推送它。现在，您的会话和应用程序缓存将存储在 Redis 中！

您可能希望探索市场，寻找其他可用功能，例如绑定到数据或消息服务，扩展应用程序以及管理超出本介绍范围的应用程序的健康状况。

玩得开心，享受平台提供的生产力！

# 在 Heroku 上部署您的 Web 应用程序

在本节中，我们将免费在 Heroku 上部署您的应用程序。我们甚至将使用免费的 Redis 实例来存储我们的会话和缓存。

## 安装工具

创建 Heroku 应用程序的第一件事是下载[`toolbelt.heroku.com`](https://toolbelt.heroku.com)上可用的命令行工具。

在 Mac 上，您还可以使用`brew`命令进行安装：

```java
> brew install heroku-toolbelt

```

在 Heroku 上创建一个帐户，并使用`heroku login`将工具包链接到您的帐户：

```java
> heroku login
Enter your Heroku credentials.
Email: geowarin@mail.com
Password (typing will be hidden):
Authentication successful.

```

然后，转到您的应用程序根目录，输入`heroku create appName --region eu`。将`appName`替换为您选择的名称。如果您不提供名称，它将自动生成：

```java
> heroku create appname --region eu
Creating appname... done, region is eu
https://appname.herokuapp.com/ | https://git.heroku.com/appname.git
Git remote heroku added

```

如果您已经使用 UI 创建了一个应用程序，那么转到您的应用程序根目录，然后简单地添加远程`heroku git:remote -a yourapp`。

这些命令的作用是向我们的 Git 存储库添加一个名为`heroku`的 Git 远程。在 Heroku 上部署的过程只是将您的分支之一推送到 Heroku。远程安装的 Git 挂钩将负责其余的工作。

如果您输入`git remote -v`命令，您应该会看到`heroku`版本：

```java
> git remote -v
heroku    https://git.heroku.com/appname.git (fetch)
heroku    https://git.heroku.com/appname.git (push)
origin    https://github.com/Mastering-Spring-MVC-4/mastering-spring-mvc4-code.git (fetch)
origin    https://github.com/Mastering-Spring-MVC-4/mastering-spring-mvc4-code.git (push)

```

## 设置应用程序

我们需要两个要素来在 Heroku 上运行 Gradle 应用程序：构建文件中的一个名为`stage`的任务，以及一个包含用于运行我们的应用程序的命令的小文件，名为`ProcFile`。

### Gradle

Gradle 构建包将自动尝试在您的应用程序根目录上运行`./gradlew stage`命令。

### 注意

您可以在[`github.com/heroku/heroku-buildpack-gradle`](https://github.com/heroku/heroku-buildpack-gradle)上获取有关 Gradle 构建包的更多信息。

我们还没有"stage"任务。将以下代码添加到您的`build.gradle`文件中：

```java
task stage(type: Copy, dependsOn: [clean, build]) {
    from jar.archivePath
    into project.rootDir
    rename {
        'app.jar'
    }
}
stage.mustRunAfter(clean)

clean << {
    project.file('app.jar').delete()
}
```

这将定义一个名为`stage`的任务，它将复制 Spring Boot 在应用程序根目录生成的 jar 文件，并将其命名为`app.jar`。

这样查找 jar 文件会容易得多。`stage`任务依赖于`clean`任务和`build`任务，这意味着在开始`stage`任务之前，两者都将被执行。

默认情况下，Gradle 将尝试优化任务依赖图。因此，我们必须提供一个提示，并强制运行`stage`之前运行`clean`任务。

最后，我们向已经存在的`clean`任务添加了一个新的指令，即删除生成的`app.jar`文件。

现在，如果您运行`./gradlew stage`，它应该运行测试并将打包的应用程序放在项目的根目录。

### Procfile

当 Heroku 检测到一个 Gradle 应用程序时，它将自动运行一个安装了 Java 8 的容器。因此，我们需要非常少的配置。

我们需要一个包含用于运行我们的应用程序的 shell 命令的文件。在您的应用程序根目录创建一个名为`Procfile`的文件：

```java
web: java -Dserver.port=$PORT -Dspring.profiles.active=heroku,prod -jar app.jar
```

这里有几件事情需要注意。首先，我们将我们的应用程序声明为 Web 应用程序。我们还重新定义了应用程序将在其上运行的端口，使用环境变量。这非常重要，因为您的应用程序将与许多其他应用程序共存，每个应用程序只分配一个端口。

最后，您可以看到我们的应用程序将使用两个配置文件运行。第一个是我们在上一章中创建的`prod`配置文件，用于优化性能，还有一个新的`heroku`配置文件，我们将在稍后创建。

## 一个 Heroku 配置文件

我们不希望将诸如我们的 Twitter 应用程序密钥之类的敏感信息放入源代码控制中。因此，我们必须创建一些属性，以从应用程序环境中读取这些属性：

```java
spring.social.twitter.appId=${twitterAppId}
spring.social.twitter.appSecret=${twitterAppSecret}
```

为了使这个工作，您必须在 Heroku 上配置我们之前讨论过的两个环境变量。您可以使用工具包来完成这个任务：

```java
> heroku config:set twitterAppId=appId
```

或者，您可以转到您的仪表板，并在设置选项卡中配置环境：

![一个 Heroku 配置文件](img/image00991.jpeg)

### 注意

访问[`devcenter.heroku.com/articles/config-vars`](https://devcenter.heroku.com/articles/config-vars)获取更多信息。

## 运行您的应用程序

现在是时候在 Heroku 上运行我们的应用程序了！

如果您还没有这样做，请将所有更改提交到主分支。现在，只需将主分支推送到`heroku`远程，使用`git push heroku master`。这将下载所有依赖项并从头构建您的应用程序，因此可能需要一些时间：

```java
> git push heroku master
Counting objects: 1176, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (513/513), done.
Writing objects: 100% (1176/1176), 645.63 KiB | 0 bytes/s, done.
Total 1176 (delta 485), reused 1176 (delta 485)
remote: Compressing source files... done.
remote: Building source:
remote:
remote: -----> Gradle app detected
remote: -----> Installing OpenJDK 1.8... done
remote: -----> Building Gradle app...
remote:        WARNING: The Gradle buildpack is currently in Beta.
remote: -----> executing ./gradlew stage
remote:        Downloading https://services.gradle.org/distributions/gradle-2.3-all.zip

...

remote:        :check
remote:        :build
remote:        :stage
remote:
remote:        BUILD SUCCESSFUL
remote:
remote:        Total time: 2 mins 36.215 secs
remote: -----> Discovering process types
remote:        Procfile declares types -> web
remote:
remote: -----> Compressing... done, 130.1MB
remote: -----> Launching... done, v4
remote:        https://appname.herokuapp.com/ deployed to Heroku
remote:
remote: Verifying deploy.... done.
To https://git.heroku.com/appname.git
* [new branch]      master -> master

```

应用程序构建完成后，它将自动运行。输入`heroku logs`以查看最新日志，或者输入`heroku logs -t`以跟踪它们。

您可以在控制台上看到您的应用程序正在运行，如果一切按计划进行，您将能够连接到[`yourapp.herokuapp.com`](http://yourapp.herokuapp.com)。如下面的截图所示：

![运行您的应用程序](img/image00992.jpeg)

我们在线了！是时候告诉您的朋友了！

## 激活 Redis

要在我们的应用程序中激活 Redis，我们可以在几种选择之间进行选择。Heroku Redis 附加组件是测试版。它完全免费，带有 20MB 的存储空间，分析和日志记录。

### 注意

访问[`elements.heroku.com/addons/heroku-redis`](https://elements.heroku.com/addons/heroku-redis)以获取更多详细信息。

在这个阶段，您将需要提供您的信用卡详细信息以继续。

要为您的应用程序安装 Redis 附加组件，请输入以下内容：

```java
heroku addons:create heroku-redis:test

```

现在，我们已经激活了附加组件，当我们的应用程序在 Heroku 上运行时，将会有一个名为`REDIS_URL`的环境变量可用。

您可以使用`heroku config`命令检查该变量是否已定义：

```java
> heroku config
=== masterspringmvc Config Vars
JAVA_OPTS:        -Xmx384m -Xss512k -XX:+UseCompressedOops
REDIS_URL:        redis://x:xxx@ec2-xxx-xx-xxx-xxx.eu-west-1.compute.amazonaws.com:6439

```

由于`RedisConnectionFactory`类不理解 URI，我们需要稍微调整一下：

```java
@Configuration
@Profile("redis")
@EnableRedisHttpSession
public class RedisConfig {

    @Bean
    @Profile("heroku")
    public RedisConnectionFactory redisConnectionFactory() throws URISyntaxException {
        JedisConnectionFactory redis = new JedisConnectionFactory();

        String redisUrl = System.getenv("REDIS_URL");
        URI redisUri = new URI(redisUrl);
        redis.setHostName(redisUri.getHost());
        redis.setPort(redisUri.getPort());
        redis.setPassword(redisUri.getUserInfo().split(":", 2)[1]);

        return redis;
    }

    @Bean
         @Profile({"cloud", "heroku"})
    public static ConfigureRedisAction configureRedisAction() {
        return ConfigureRedisAction.NO_OP;
    }
}
```

我们现在在`RedisConfig`类中有两个 Heroku 特定的 bean。这些 bean 只有在`redis`和`heroku`配置文件都激活时才会生效。

请注意，我们还停用了一些 Spring Session 配置。

Spring Session 通常会通过 Redis Pub/Sub 接口监听与销毁会话密钥相关的事件。

它将自动尝试配置 Redis 环境以在启动时激活监听器。在我们这样的安全环境中，除非您拥有管理员访问权限，否则不允许添加监听器。

在我们的情况下，这些 redis 监听器并不是非常重要，所以我们可以安全地禁用这种行为。欲了解更多信息，请访问[`docs.spring.io/spring-session/docs/current/reference/html5/#api-redisoperationssessionrepository-sessiondestroyedevent`](http://docs.spring.io/spring-session/docs/current/reference/html5/#api-redisoperationssessionrepository-sessiondestroyedevent)。

我们需要修改我们的`Procfile`文件，以便 Heroku 使用`redis`配置运行我们的应用程序：

```java
web: java -Dserver.port=$PORT -Dspring.profiles.active=heroku,redis,prod -jar app.jar
```

提交您的更改并将代码推送到 Heroku。

# 改进您的应用程序

我们已经在线部署了一个相当不错的应用程序，但在您进行改进之前，它既不是非常有用，也不是非常原创。

尝试使其更好，更个性化。一旦您为自己的成就感到自豪，请在 Twitter 上使用`#masterspringmvc`标签推文您的应用程序 URL。

尝试推出尽可能最好的应用程序。我们还有很多事情没有做。以下是一些想法：

+   删除用户的旧图片以避免保留未使用的图片

+   使用 Twitter 身份验证信息填充用户配置文件

+   与用户帐户进行交互

+   使用 Web 套接字频道查看应用程序上正在进行的实时搜索

让您的想象力飞翔！

我的版本的应用程序部署在[`masterspringmvc.herokuapp.com`](http://masterspringmvc.herokuapp.com)。我将改进一些细节，使应用程序更具反应性。试着找出不同之处！

# 摘要

在云提供商上部署我们的应用程序非常简单，因为它是一个可运行的 jar 包，这要归功于 Spring Boot。云部署现在非常实惠，部署 Java 应用程序几乎变得太容易了。

通过 Redis 支持的会话，我们奠定了可扩展应用程序的基础。事实上，我们可以轻松地在负载均衡器后面添加多个服务器，并根据需求吸收高流量。

唯一不可扩展的是我们的 WebSocket，它需要额外的工作才能在消息代理（如 Rabbit MQ）之上运行。

我肯定还记得以前很难找到运行 Tomcat 的主机，并且价格昂贵。那些日子已经一去不复返，未来属于 Web 开发人员，所以让它发生吧！

在下一章中，我们将看看如何使我们的应用程序变得更好，讨论我们尚未涵盖的技术，谈论 Spring 生态系统的一般情况以及现代 Web 应用程序的挑战。

# 第九章。超越 Spring Web

在本章中，我们将看到我们已经走了多远，我们解决了哪些问题，还有哪些问题有待解决。

我们将讨论 Spring 生态系统的一般情况，以及持久性、部署和单页应用程序。

# Spring 生态系统

从 Web 到数据，Spring 是一个全面的生态系统，旨在以模块化的方式解决各种问题：

![Spring 生态系统](img/image00993.jpeg)

请查看 Spring IO 平台[`spring.io/platform`](https://spring.io/platform)。

## 核心

在 Spring 框架的核心，显然有一个依赖注入机制。

我们只是浅尝了安全功能和框架与 Groovy 的出色集成。

## 执行

我们详细了解了 Spring Boot 的内容——将简单性和内聚性带入庞大的子项目网络。

它使您能够专注于真正重要的事情，即您的业务代码。

Spring XD 项目也非常有趣。其目标是提供处理、分析、转换或导出数据的工具，并且明确关注大数据。有关更多信息，请访问[`projects.spring.io/spring-xd`](http://projects.spring.io/spring-xd)。

## 数据

在开发我们的应用程序时，我们还没有考虑如何在数据库中存储数据。在 Pivotal 的参考架构中，有一个专门用于关系数据和非关系（NoSQL）数据的层。

Spring 生态系统在`spring-data`标签下提供了许多有趣的解决方案，可以在[`projects.spring.io/spring-data/`](http://projects.spring.io/spring-data/)找到。

在构建缓存时，我们瞥见了 Spring Data Redis，但 Spring Data 还有更多内容。

所有 Spring Data 项目都共享基本概念，例如模板 API，这是一个从持久性系统中检索和存储对象的抽象。

Spring Data JPA（[`projects.spring.io/spring-data-jpa/`](http://projects.spring.io/spring-data-jpa/)）和 Spring Data Mongo（[`projects.spring.io/spring-data-mongodb/`](http://projects.spring.io/spring-data-mongodb/)）是一些最著名的 Spring Data 项目。它们让您通过存储库操作实体，这些存储库是提供创建查询、持久化对象等功能的简单接口。

Petri Kainulainen（[`www.petrikainulainen.net/spring-data-jpa-tutorial/`](http://www.petrikainulainen.net/spring-data-jpa-tutorial/)）在 Spring Data 上有很多深入的例子。它没有使用 Spring Boot 提供的设施，但您应该能够很容易地开始使用指南，例如[`spring.io/guides/gs/accessing-data-jpa/`](https://spring.io/guides/gs/accessing-data-jpa/)。

Spring Data REST 也是一个神奇的项目，它将通过 RESTful API 半自动地公开您的实体。请访问[`spring.io/guides/gs/accessing-data-rest/`](https://spring.io/guides/gs/accessing-data-rest/)获取详细教程。

## 其他值得注意的项目

Spring Integration（[`projects.spring.io/spring-integration`](http://projects.spring.io/spring-integration)）和 Spring Reactor（[`projectreactor.io`](http://projectreactor.io)）也是我最喜欢的 Spring 项目之一。

Spring Reactor 是 Pivotal 实现的反应流。其想法是在服务器端提供完全非阻塞的 IO。

另一方面，Spring Integration 专注于企业集成模式，并允许你设计通道来加载和转换来自异构系统的数据。

关于你可以通过通道实现的一个很好而简单的例子可以在这里看到：[`ilopmar.github.io/contest/#_spring_boot_application`](http://ilopmar.github.io/contest/#_spring_boot_application)。

如果你的应用需要与异构和/或复杂的子系统进行通信，那么一定值得一看。

在 Spring 生态系统中，我们还没有提到的最后一个项目是 Spring Batch，它是一个非常有用的抽象，用于处理企业系统的日常运营中的大量数据。

# 部署

Spring Boot 提供了将你的 Spring 应用程序作为简单的 JAR 运行和分发的能力，在这方面取得了很大的成功。

这无疑是朝着正确方向迈出的一步，但有时你不只是想部署你的 Web 应用。

当处理具有多个服务器和数据源的复杂系统时，运维团队的工作可能会变得非常头疼。

## Docker

谁没有听说过 Docker 呢？它是容器世界中的新宠儿，并且由于其充满活力的社区而取得了相当大的成功。

Docker 的理念并不新颖，它利用了 Linux 容器（LXC）和 cgroups 来为应用程序提供完全隔离的环境。

你可以在 Spring 网站上找到一个关于 Docker 的教程，它会指导你进行第一步：[`spring.io/guides/gs/spring-boot-docker`](https://spring.io/guides/gs/spring-boot-docker)。

Pivotal Cloud Foundry 多年来一直在使用容器技术，他们的容器管理器叫做 Warden。他们最近转向了 Garden，这是一个支持不仅仅是 Linux 容器，还有 Windows 容器的抽象。

Garden 是 Cloud Foundry 的最新版本（称为 Diego）的一部分，它还允许 Docker 镜像作为部署单元。

Cloud Foundry 的开发人员版本也以 Lattice 的名字发布了，可以在[`spring.io/blog/2015/04/06/lattice-and-spring-cloud-resilient-sub-structure-for-your-cloud-native-spring-applications`](https://spring.io/blog/2015/04/06/lattice-and-spring-cloud-resilient-sub-structure-for-your-cloud-native-spring-applications)找到。

如果你想在不使用命令行的情况下测试容器，我建议你看看 Kitematic。通过这个工具，你可以在不在系统上安装二进制文件的情况下运行 Jenkins 容器或 MongoDB。访问[`kitematic.com/`](https://kitematic.com/)了解更多关于 Kitematic 的信息。

Docker 生态系统中另一个值得一提的工具是 Docker Compose。它允许你通过一个配置文件运行和链接多个容器。

请参考[`java.dzone.com/articles/spring-session-demonstration`](http://java.dzone.com/articles/spring-session-demonstration)，这是一个由两个 Web 服务器、一个用于存储用户会话的 Redis 和一个用于负载均衡的 Nginx 实例组成的 Spring Boot 应用的很好的例子。当然，关于 Docker Swarm 还有很多值得学习的地方，它可以让你通过简单的命令来扩展你的应用，还有 Docker Machine，它可以在任何机器上为你创建 Docker 主机，包括云提供商。

Google 的 Kubernetes 和 Apache Mesos 也是 Docker 容器大大受益的分布式系统的很好的例子。

# 单页应用

今天大多数的 Web 应用都是用 JavaScript 编写的。Java 被放在后端，并且在处理数据和业务规则方面起着重要作用。然而，现在很多 GUI 的工作都是在客户端进行的。

这在响应性和用户体验方面有很好的原因，但这些应用增加了额外的复杂性。

开发人员现在必须精通 Java 和 JavaScript，而且一开始可能会对各种框架感到有些不知所措。

## 参与者

如果你想深入了解 JavaScript，我强烈推荐 Dave Syer 的 Spring 和 AngularJS 教程，可在[`spring.io/guides/tutorials/spring-security-and-angular-js`](https://spring.io/guides/tutorials/spring-security-and-angular-js)上找到。

选择 JavaScript MVC 框架也可能有些困难。多年来，AngularJS 一直受到 Java 社区的青睐，但人们似乎正在远离它。欲了解更多信息，请访问[`gist.github.com/tdd/5ba48ba5a2a179f2d0fa`](https://gist.github.com/tdd/5ba48ba5a2a179f2d0fa)。

其他选择包括以下内容：

+   **BackboneJS**：这是一个非常简单的 MVC 框架，建立在 Underscore 和 jQuery 之上。

+   **Ember**：这是一个全面的系统，提供了更多与数据交互的便利设施。

+   **React**：这是 Facebook 的最新项目。它有一种处理视图的新而非常有趣的哲学。它的学习曲线相当陡峭，但在设计 GUI 框架方面，它是一个非常有趣的系统。

React 是我目前最喜欢的项目。它让你专注于视图，其单向数据流使得应用程序的状态易于理解。然而，它仍处于 0.13 版本。这使得它非常有趣，因为充满活力的社区总是提出新的解决方案和想法，但也有些令人不安，因为即使经过两年多的开源开发，前方的道路似乎仍然很长。请访问[`facebook.github.io/react/blog/2014/03/28/the-road-to-1.0.html`](https://facebook.github.io/react/blog/2014/03/28/the-road-to-1.0.html)了解有关“通往 1.0 版本的道路”的信息。

## 未来

我看到很多 Java 开发人员抱怨 JavaScript 的宽松性，并且很难处理它不是一种强类型语言的事实。

还有其他选择，比如**Typescript**（[`www.typescriptlang.org/`](http://www.typescriptlang.org/)），非常有趣并提供了我们 Java 开发人员一直用来简化生活的东西：接口、类、IDE 中的有用支持和自动完成。

很多人押注下一个版本（2.0）的 Angular 将会彻底改变一切。我认为这是最好的。他们与微软的 Typescript 团队的合作真的很独特。

大多数 JEE 开发人员听到 ECMAScript 的一个重大新功能是装饰器时会微笑，这允许开发这个新框架的装饰器是一种注解机制：

### 注意

要了解注解和装饰器之间的区别，请访问[`blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html`](http://blog.thoughtram.io/angular/2015/05/03/the-difference-between-annotations-and-decorators.html)。

JavaScript 正在迅速发展，ECMAScript 6 具有许多有趣的功能，使其成为一种非常先进和复杂的语言。不要错过机会，在为时已晚之前查看[`github.com/lukehoban/es6features`](https://github.com/lukehoban/es6features)！

Web 组件规范也是一个改变游戏规则的因素。其目标是提供可重用的 UI 组件，React 团队和 Angular 2 团队都计划与其进行接口交互。谷歌已经在 Web 组件之上开发了一个名为 Polymer 的有趣项目，现在已经是 1.0 版本。

### 注意

请参阅[`ng-learn.org/2014/12/Polymer/`](http://ng-learn.org/2014/12/Polymer/)的文章，以了解更多关于这些项目的情况。

## 无状态

在处理 JavaScript 客户端时，依赖会话 cookie 并不是最佳选择。大多数应用程序选择完全无状态，并使用令牌识别客户端。

如果您想坚持使用 Spring Session，请查看`HeaderHttpSessionStrategy`类。它具有通过 HTTP 标头发送和检索会话的实现。可以在[`drissamri.be/blog/2015/05/21/spr`](https://drissamri.be/blog/2015/05/21/spr)找到示例。

# 总结

Spring 生态系统广泛，为现代 Web 应用程序开发人员提供了很多选择。

很难找到一个 Spring 项目没有解决的问题。

是时候说再见了！我希望您喜欢我们与 Spring MVC 的小旅程，并且它将帮助您愉快地开发并创建令人惊叹的项目，无论是在工作中还是在业余时间。

# 附录 A. 参考文献

这个学习路径已经为您准备好，使用 Spring MVC 框架创建企业级应用程序。它包括以下 Packt 产品：

+   *Spring Essentials, Shameer Kunjumohamed and Hamidreza Sattari*

+   *Spring MVC Cookbook, Alex Bretet*

+   *Mastering Spring MVC 4, Geoffroy Warins*

# 索引

## A

+   @After 注释 / @Before 和@After 注释

+   @AfterClass 注释 / @BeforeClass 和@AfterClass 注释

+   @AspectJ 注释

+   声明 / 声明@Aspect 注释

+   切入点 / 切入点

+   建议 / 建议

+   基于@AspectJ 注释的 AOP

+   关于 / 基于@AspectJ 注释的 AOP

+   验收测试

+   关于 / 我应该如何测试我的代码？, 验收测试, 编写验收测试

+   Gradle，配置 / Gradle 配置

+   使用 FluentLenium / 我们的第一个 FluentLenium 测试

+   使用 Groovy / 使我们的测试更加 Groovy

+   ACID（原子性，一致性，隔离性，持久性）

+   关于 / Spring 事务支持

+   ACID 属性

+   关于 / ACID 属性

+   参考链接 / ACID 属性

+   高级消息队列协议（AMQP）

+   任务，与之堆叠 / 准备就绪

+   任务，与之消耗 / 准备就绪

+   关于 / AMQP 还是 JMS？

+   由 pivotal 提供的 URL / pivotal 提供的 AMQP 简介

+   应用程序事件，发布 / 发布应用程序事件的更好方法

+   建议，@AspectJ 注释

+   关于 / 建议

+   注释 / 建议

+   @Around 建议 / @Around 建议

+   访问建议参数 / 访问建议参数

+   贫血领域模型

+   URL / 贫血领域模型

+   关于 / 贫血领域模型

+   angular-translate.js

+   用于客户端翻译 / 使用 angular-translate.js 进行客户端翻译

+   URL / 使用 angular-translate.js 进行客户端翻译

+   AngularJS

+   关于 / SPA 框架

+   用于设计客户端 MVC 模式 / Designing a client-side MVC pattern with AngularJS

+   URL / There's more...

+   URL，用于表单文档 / See also

+   AngularJS Controllers

+   关于 / AngularJS Controllers

+   双向 DOM-scope 绑定 / Bidirectional DOM-scope binding

+   AngularJS Directives

+   关于 / AngularJS directives

+   ng-repeat / ng-repeat

+   ng-if / ng-if

+   AngularJS factories

+   关于 / AngularJS factories

+   依赖注入 / Dependency injection

+   AngularJS JavaScript library

+   URL / Setting up the DOM and creating modules

+   angular 路由

+   关于 / Angular routes

+   Angular UI

+   使用 Bootstrap 分页 / Bootstrap pagination with the Angular UI

+   注解定义的控制器

+   @Controller annotation / @Controller

+   @RequestMapping annotation / @RequestMapping

+   注解

+   定义 / Auditing with Spring Data

+   @CreatedBy / Auditing with Spring Data

+   @CreatedDate / Auditing with Spring Data

+   @LastModifiedBy / Auditing with Spring Data

+   @LastModifiedDate / Auditing with Spring Data

+   AssertFalse / On-field constraint annotations

+   AssertFalse.List / On-field constraint annotations

+   AssertTrue / On-field constraint annotations

+   AssertTrue.List / On-field constraint annotations

+   DecimalMax / On-field constraint annotations

+   DecimalMax.List / On-field constraint annotations

+   DecimalMin / On-field constraint annotations

+   DecimalMin.List / On-field constraint annotations

+   Digits / On-field constraint annotations

+   Digits.List / On-field constraint annotations

+   Future / On-field constraint annotations

+   Future.List / On-field constraint annotations

+   Max / On-field constraint annotations

+   Max.List / On-field constraint annotations

+   Min / On-field constraint annotations

+   Min.List / On-field constraint annotations

+   NotNull / On-field constraint annotations

+   NotNull.列表/ 现场约束注释

+   过去/ 现场约束注释

+   过去.列表/ 现场约束注释

+   模式/ 现场约束注释

+   模式.列表/ 现场约束注释

+   大小/ 现场约束注释

+   大小.列表/ 现场约束注释

+   Apache Commons 日志桥接/ Apache Commons 日志桥接

+   Apache HTTP

+   URL/ 还有更多...

+   替代方案/ 替代方案 Apache HTTP

+   Apache HTTP 配置

+   代理 Tomcat/ 配置 Apache HTTP 代理您的 Tomcat, 如何做..., 它是如何工作的...

+   关于/ Apache HTTP 配置

+   虚拟主机/ 虚拟主机

+   mod_proxy 模块/ mod_proxy 模块

+   ProxyPassReverse/ ProxyPassReverse

+   mod_alias 模块/ mod_alias 模块

+   Tomcat 连接器/ Tomcat 连接器

+   Apache HTTP 文档

+   URL/ 可扩展模型

+   Apache HTTP 服务器

+   在 MS Windows 上安装，URL/ 如何做...

+   在 Linux/Mac OS 上安装，URL/ 如何做...

+   Apache JServ 协议（AJP）连接器/ AJP 连接器

+   API

+   使用 Swagger 记录/ 使用 Swagger 记录和公开 API, 如何做...

+   使用 Swagger 公开/ 使用 Swagger 记录和公开 API, 如何做...

+   公开的元数据/ 公开的元数据

+   API 端点

+   为 Taskify 应用程序构建/ 为 Taskify 应用程序构建 API 端点

+   UserController.java/ UserController.java

+   TaskController.java/ TaskController.java

+   API 服务器应用

+   构建/ 构建 API 服务器应用

+   项目，设置/ 设置和配置项目

+   定义用户和任务/ 定义模型定义-用户和任务

+   API 版本控制

+   关于/ API 版本控制

+   参考链接/ API 版本控制

+   应用程序

+   日志记录，使用 Log4j2/ 使用 Log4j2 进行现代应用程序日志记录, 如何做...

+   应用程序缓存

+   创建/ 应用程序缓存

+   参考链接/ 应用程序缓存

+   失效/ 缓存失效

+   分布式缓存/ 分布式缓存

+   参数解析器

+   JPA2 标准 API / JPA2 标准 API 和 Spring Data JPA 规范

+   Spring Data JPA 规范 / JPA2 标准 API 和 Spring Data JPA 规范

+   SpecificationArgumentResolver/ SpecificationArgumentResolver

+   面向方面的编程（AOP）

+   关于/ 面向方面的编程

+   静态 AOP/ 静态和动态 AOP

+   动态 AOP / 静态和动态 AOP

+   概念/ AOP 概念和术语

+   术语/ AOP 概念和术语

+   Spring AOP / Spring AOP-定义和配置样式

+   基于 XML 模式的 AOP/ 基于 XML 模式的 AOP

+   @AspectJ 基于注释的 AOP/ @AspectJ 基于注释的 AOP

+   异步请求处理

+   在 Spring MVC 中/ Spring MVC 中的异步请求处理

+   异步方法

+   使用/ 异步方法

+   参考链接/ 异步方法

+   Atomikos

+   URL/ 全局与本地事务

+   认证

+   关于/ 认证

+   测试/ 测试认证

+   AuthenticationManager 接口/ AuthenticationManager 接口

+   授权

+   关于/ 授权

+   授权的 URL

+   认证/ 授权的 URL

+   授权用户

+   认证/ 授权用户

## B

+   @Before 注释 / @Before 和@After 注释

+   @BeforeClass 注释 / @BeforeClass 和@AfterClass 注释

+   BackboneJS

+   关于/ 玩家

+   基本身份验证

+   URL/ 基本身份验证

+   关于/ 基本身份验证

+   配置/ 基本身份验证

+   用于授权用户/ 授权用户

+   用于授权的 URL/ 授权的 URL

+   使用 thymeleaf 安全标签/ Thymeleaf 安全标签

+   BasicAuthenticationFilter

+   关于/ BasicAuthenticationFilter

+   使用 authenticationEntryPoint/ 使用 authenticationEntryPoint

+   基本方案

+   认证/ 通过基本方案进行认证, 如何做...

+   Spring 安全命名空间/ Spring 安全命名空间

+   AuthenticationManager 接口/ AuthenticationManager 接口

+   Spring 安全参考/ 在 Spring 安全参考中

+   记住我 cookie/功能/ 记住我 cookie/功能

+   bean 定义配置文件

+   使用/ 使用 bean 定义配置文件

+   bean 依赖项

+   注入/ 注入 bean 依赖项

+   基于构造函数的依赖注入/ 基于构造函数的依赖注入

+   基于 setter 的依赖注入/ 基于 setter 的依赖注入

+   BeanFactory 接口

+   关于/ Spring IoC 容器

+   bean 生命周期

+   连接/ 连接到 bean 生命周期

+   InitializingBean，实现/ 实现 InitializingBean 和 DisposableBean

+   DisposableBean，实现/ 实现 InitializingBean 和 DisposableBean

+   @PostConstruct，对@Components 进行注释/ 在@Components 上注释@PostConstruct 和@PreDestroy

+   @PreDestroy，对@Components 进行注释/ 在@Components 上注释@PostConstruct 和@PreDestroy

+   init-method 和 destroy-method 属性/ <bean/>的 init-method 和 destroy-method 属性

+   beans

+   关于/ Spring IoC 容器, 详细介绍 Beans

+   定义/ Bean 定义

+   实例化/ 实例化 beans

+   实例化，使用构造函数/ 使用构造函数

+   实例化，使用静态工厂方法/ 使用静态工厂方法

+   实例化，使用实例工厂方法/ 使用实例工厂方法

+   使用命名空间快捷方式进行更清晰的 bean 定义/ 使用命名空间快捷方式进行更清晰的 bean 定义

+   列表，作为依赖项进行连线/ 将列表作为依赖项进行连线

+   映射，作为依赖项进行连线/ 将映射作为依赖项进行连线

+   依赖项，自动装配/ 自动装配依赖项

+   作用域/ Bean 作用域

+   bean 验证

+   用于验证资源/ 准备工作, 如何做…

+   使用 Spring 验证器/ 使用 Spring 验证器

+   JSR-303/JSR-349 bean 验证 / 使用 JSR-303/JSR-349 Bean 验证

+   ValidationUnits 实用程序/ ValidationUtils

+   创建自定义验证器 / 创建自定义验证器

+   参考链接 / Spring 关于验证的参考

+   绑定请求

+   关于 / 绑定请求和编组响应, 准备就绪, 如何做..., 它是如何工作的...

+   Bitronix

+   URL / 全局与本地事务

+   样板逻辑

+   抽象 / 样板逻辑的抽象

+   自动生成的 ID，提取 / 提取自动生成的 ID

+   bookapp-rest 应用程序

+   URL / 我们的 MessageSource bean 定义

+   Bootstrap

+   响应式单页 Web 设计，设置 / 使用 Bootstrap 设置和自定义响应式单页 Web 设计, 如何做..., 安装 Bootstrap 主题

+   亮点 / Bootstrap 亮点

+   URL / 还有更多...

+   Bootstrap 组件

+   导航栏 / 导航栏

+   英雄单元 / 英雄单元

+   警报 / 警报

+   徽章和标签 / 徽章和标签

+   Bootstrap CSS 实用程序

+   统一按钮 / 统一按钮

+   图标 / 图标

+   表格 / 表格

+   Bootstrap 分页

+   使用 Angular UI / 使用 Angular UI 的 Bootstrap 分页

+   URL / 使用 Angular UI 的 Bootstrap 分页

+   Bootstrap 脚手架

+   关于 / Bootstrap 脚手架

+   网格系统和响应式设计 / 网格系统和响应式设计

+   定义列 / 定义列

+   列，偏移 / 偏移和嵌套

+   嵌套 / 偏移和嵌套

+   流体网格 / 流体网格

+   Bootstrap 主题

+   自定义 / 自定义 Bootstrap 主题

+   安装 / 主题安装

+   经纪人通道 / Spring 4 中 STOMP over WebSocket 和回退选项

+   BSON（二进制 JSON）格式

+   关于 / Spring Data MongoDB

+   Maven 构建生命周期

+   关于 / Maven 的构建生命周期

+   清洁生命周期 / 清洁生命周期

+   默认生命周期 / 默认生命周期

+   插件 / 插件目标

+   内置生命周期 / 内置生命周期绑定

+   Maven 命令 / 关于 Maven 命令

## C

+   @ComponentScan 注释 / 创建一个简单的 WebSocket 应用程序

+   @Configuration 注释 / 创建一个简单的 WebSocket 应用程序

+   @ContextConfiguration 注释 / @ContextConfiguration 注释, 还有更多…

+   @ControllerAdvice

+   使用@ControllerAdvice 进行全局异常处理 / 使用@ControllerAdvice 进行全局异常处理

+   支持 ResponseEntityExceptionHandler 类 / 支持 ResponseEntityExceptionHandler 类

+   统一的错误响应对象 / 统一的错误响应对象

+   @Controller 注释 / @Controller

+   缓存控制

+   关于 / 另请参阅

+   缓存控制

+   关于 / 缓存控制

+   配置 / 缓存控制

+   货物

+   与集成测试 / 使用 Cargo，Rest-assured 和 Maven failsafe 进行集成测试, 如何做…, 它是如何工作的…

+   Codehaus Cargo / Code Cargo

+   Maven 插件 / Cargo Maven 插件

+   关于 / 关于 Cargo

+   URL / 关于 Cargo

+   Cargo Maven 插件

+   关于 / Cargo Maven 插件

+   Maven 阶段，绑定到 / 绑定到 Maven 阶段

+   现有的 Tomcat 实例，使用 / 使用现有的 Tomcat 实例

+   级联属性

+   关于 / 级联属性

+   证书签名请求（CSR）

+   URL / 关于 SSL 和 TLS

+   检查点

+   关于 / 检查点

+   清理命令 / 清理

+   清理生命周期

+   预清理阶段 / 清理生命周期

+   清理阶段 / 清理生命周期

+   后清理阶段 / 清理生命周期

+   客户端表单

+   使用 HTML5/AngularJS 进行验证 / 使用 HTML5 AngularJS 验证客户端表单, 如何做…, 它是如何工作的…

+   控制变量 / 表单中的控制变量

+   状态转换 / 表单状态转换和样式

+   样式 / 表单状态转换和样式

+   客户端表单，验证约束

+   必需的 / 必需的

+   最小/最大长度 / 最小/最大长度

+   正则表达式模式 / 正则表达式模式

+   客户端 MVC 模式

+   设计，使用 AngularJS / 使用 AngularJS 设计客户端 MVC 模式

+   客户端验证，配置文件页面

+   启用 / 客户端验证

+   参考链接 / 客户端验证

+   Cloud Foundry

+   关于 / Cloud Foundry

+   URL / Cloud Foundry

+   Cloud Foundry CLI 工具

+   安装 / 安装 Cloud Foundry CLI 工具

+   URL / 安装 Cloud Foundry CLI 工具

+   cloudstreetmarket-parent

+   关于 / 准备就绪

+   代码测试

+   好处 / 为什么我应该测试我的代码？

+   单元测试 / 我应该如何测试我的代码？

+   验收测试 / 我应该如何测试我的代码？

+   组件类型注释

+   @Component / 组件类型注释

+   @Service / 组件类型注释

+   @Repository / 组件类型注释

+   @Controller / 组件类型注释

+   @RestController / 组件类型注释

+   配置元数据，依赖注入

+   关于 / 配置元数据

+   基于 XML 的配置元数据 / 基于 XML 的配置元数据

+   基于注释的配置元数据 / 基于注释的配置元数据

+   基于 XML 的与基于注释的配置 / 基于 XML 与基于注释的配置

+   组件类型注释 / 组件类型注释

+   基于 Java 的配置元数据 / 基于 Java 的配置元数据

+   JSR 330 标准注释 / JSR 330 标准注释

+   基于构造函数的依赖注入

+   关于 / 基于构造函数还是基于 setter 的依赖注入 - 哪个更好？

+   构造函数注入

+   关于 / 将配置文件放入会话中

+   URL / 将配置文件放入会话中

+   容器级默认初始化和销毁方法

+   关于 / 容器级默认初始化方法和默认销毁方法

+   容器管理的事务（CMT）

+   关于 / Spring 事务的相关性

+   内容协商

+   配置 / 如何做..., 它是如何工作的...

+   XML 编组，支持 / 支持 XML 编组

+   ContentNegotiationManager

+   与 ContentNegotiationManager 的协商策略

+   接受头 / 接受头

+   URL 路径中的文件扩展名后缀 / URL 路径中的文件扩展名后缀

+   请求参数 / 请求参数

+   Java 激活框架 / Java 激活框架

+   ContentNegotiationManagerFactoryBean JavaDoc

+   关于 / ContentNegotiationManagerFactoryBean JavaDoc

+   内容

+   为 REST 国际化 / 为 REST 国际化消息和内容

+   动态翻译，后端实现 / 后端

+   动态翻译，前端实现 / 前端, 它是如何工作的...

+   持续集成

+   参考链接 / 为什么我应该测试我的代码？

+   控制器

+   使用简单 URL 映射进行配置 / 使用简单 URL 映射配置控制器, 如何做...

+   控制器方法处理程序签名

+   关于 / 控制器方法处理程序签名

+   支持的方法参数类型 / 支持的方法参数类型

+   方法参数的支持注解 / 方法参数的支持注解

+   支持的返回类型 / 支持的返回类型

+   控制器

+   关于 / 详细的控制器

+   使用@RequestMapping 映射请求 URL / 使用@RequestMapping 映射请求 URL

+   使用@PathVariable 注解的 URI 模板模式 / 使用@PathVariable 注解的 URI 模板模式

+   使用@RequestParam 注解绑定参数 / 使用@RequestParam 注解绑定参数

+   请求处理程序方法参数 / 请求处理程序方法参数

+   请求处理程序方法返回类型 / 请求处理程序方法返回类型

+   模型属性，设置 / 设置模型属性

+   为 JSON 和 XML 媒体构建 RESTful 服务 / 为 JSON 和 XML 媒体构建 RESTful 服务

+   使用 RestController 构建 RESTful 服务 / 使用 RestController 构建 RESTful 服务

+   授权 / 在服务和控制器上进行授权, 如何做...

+   控制变量，客户端表单

+   修改/未修改状态 / 修改/未修改状态

+   $error 属性 / 错误

+   ConversionService API / ConversionService API

+   CookieHttpSessionStrategy / CookieHttpSessionStrategy

+   核心模块

+   创建/ 为什么我们创建核心模块？

+   创建读取更新删除（CRUD）

+   关于/ Level 2-HTTP 动词

+   跨站点请求伪造（csrf）/ 我们的<http>配置

+   跨站点请求伪造（CSRF）攻击

+   关于/ 认证

+   跨站点请求伪造（CSRF）

+   关于/ 授权的 URL

+   URL/ 授权的 URL

+   自定义约束

+   参考链接/ 特定实现约束

+   自定义错误页面

+   创建/ 自定义错误页面

+   自定义范围

+   创建/ 创建自定义范围

+   自定义验证器

+   URL/ 创建自定义验证器

## D

+   DAO 支持

+   关于/ DAO 支持和@Repository 注释

+   数据

+   使用 OAuth 从第三方 API 检索/ 使用 OAuth 从第三方 API 检索数据, 如何做..., 它是如何工作的...

+   Yahoo!，财务数据/ Yahoo!财务数据介绍

+   图形，生成/显示/ 图形生成/显示

+   财务数据，拉取/ 财务数据是如何拉取/刷新的？

+   财务数据，刷新/ 财务数据是如何拉取/刷新的？

+   调用第三方服务/ 调用第三方服务

+   现有的 API 提供商/ Spring Social-现有的 API 提供商

+   数据供应实现

+   通过接口注入服务/ 通过接口注入服务

+   虚拟实现，选择/ Spring 如何选择虚拟实现？

+   在视图层中使用的 DTO/ 在视图层中使用的 DTO

+   虚拟服务实现/ 虚拟服务实现

+   数据访问对象（DAO）/ 基于 XML 的配置元数据

+   数据库迁移

+   自动化，使用 FlyWay/ 使用 FlyWay 自动化数据库迁移, 如何做...

+   数据源

+   配置/ 配置数据源

+   参考/ 配置数据源

+   数据源

+   关于/ Spring 管理的数据源 bean

+   数据传输对象（DTO）

+   关于/ 个人资料页面-表单

+   声明式事务管理

+   关于/ 声明式事务管理

+   代理模式/ 事务模式-代理和 AspectJ

+   AspectJ 模式 / 事务模式-代理和 AspectJ

+   定义事务行为 / 定义事务行为

+   回滚规则，设置 / 设置回滚规则

+   默认生命周期

+   验证 / 默认生命周期

+   初始化 / 默认生命周期

+   generate-sources / 默认生命周期

+   process-sources / 默认生命周期

+   generate-resources / 默认生命周期

+   process-resources / 默认生命周期

+   编译 / 默认生命周期

+   process-classes / 默认生命周期

+   generate-test-sources / 默认生命周期

+   process-test-sources / 默认生命周期

+   generate-test-resources / 默认生命周期

+   process-test-resources / 默认生命周期

+   test-compile / 默认生命周期

+   process-test-classes / 默认生命周期

+   测试 / 默认生命周期

+   准备包 / 默认生命周期

+   打包 / 默认生命周期

+   pre-integration-test / 默认生命周期

+   integration-test / 默认生命周期

+   post-integration-test / 默认生命周期

+   验证 / 默认生命周期

+   install / 默认生命周期

+   部署 / 默认生命周期

+   依赖注入 / 依赖注入

+   依赖注入（DI） / Spring 框架模块

+   关于 / 依赖注入, Spring 框架带来了什么？

+   Spring IoC 容器 / Spring IoC 容器

+   配置元数据 / 配置元数据

+   依赖注入，带有作用域的 bean

+   关于 / 带有作用域的 bean 的依赖注入

+   可部署模块

+   名称，选择 / 我们如何选择可部署模块的名称？

+   部署

+   关于 / 部署

+   Docker / Docker

+   开发环境

+   设置 / 设置开发环境

+   Dispatcher Servlet

+   架构 / DispatcherServlet

+   DispatcherServlet

+   关于 / DispatcherServlet 解释

+   使用 WebApplicationContext/ WebApplicationContext-Web 的 ApplicationContext

+   支持豆/ 支持 DispatcherServlet 的豆和它们的角色

+   支持的豆/ 支持 DispatcherServlet 的豆和它们的角色/ DispatcherServlet-Spring MVC 入口点

+   分布式缓存

+   配置/ 分布式缓存

+   分布式会话

+   关于/ 分布式会话

+   设置/ 分布式会话

+   DNS

+   URL/ 还有更多...

+   DNS 配置/ DNS 配置或主机别名

+   DNS 记录

+   版本/ 在生产中-编辑 DNS 记录

+   Docker

+   关于/ Docker

+   URL/ Docker

+   参考链接/ Docker

+   文档

+   使用 Swagger/ 使用 Swagger 进行文档编制

+   文档对象模型（DOM）/ 每个 HTML 文档一个应用程序

+   DOM

+   设置/ 设置 DOM 和创建模块

+   DOM 范围绑定

+   双向/ 双向 DOM 范围绑定

+   领域驱动设计（DDD）

+   关于/ 贫血领域模型

+   领域对象和实体

+   关于/ 领域对象和实体

+   查询解析方法/ 查询解析方法

+   @Query 注释，使用/ 使用@Query 注释

+   Spring Data web 支持扩展/ Spring Data web 支持扩展

+   审计，使用 Spring Data/ 使用 Spring Data 进行审计

+   领域对象安全（ACLs）

+   URL/ 领域对象安全（ACLs）

+   DTO

+   转换为 Spring HATEOAS 资源/ 将 DTO 转换为 Spring HATEOAS 资源, 如何做..., 它是如何工作的...

## E

+   @EnableAutoConfiguration 注释/ 创建一个简单的 WebSocket 应用程序

+   Eclipse

+   为 Java 8 配置/ 为 Java 8，Maven 3 和 Tomcat 8 配置 Eclipse, 如何做...

+   为 Maven 3 配置/ 为 Java 8，Maven 3 和 Tomcat 8 配置 Eclipse, 如何做...

+   为 Tomcat 8 配置/ 为 Java 8，Maven 3 和 Tomcat 8 配置 Eclipse, 如何做...

+   eclipse.ini 文件/ eclipse.ini 文件

+   -vm 选项，设置/ 设置-vm 选项

+   JVM 参数，自定义/ 自定义 JVM 参数

+   JDK 兼容级别，修改/ 更改 JDK 兼容级别

+   Maven，配置/ 配置 Maven

+   存储库管理器/ 存储库管理器

+   Tomcat 8，集成/ Eclipse 中的 Tomcat 8

+   URL/ 还有更多...

+   GIT，配置/ 在 Eclipse 中配置 GIT, 它是如何工作的...

+   Eclipse.ini 文件

+   URL/ 还有更多...

+   eclipse.ini 文件

+   关于/ eclipse.ini 文件

+   URL/ eclipse.ini 文件

+   Eclipse IDE

+   需要/ 为什么要使用 Eclipse IDE？

+   下载，适用于 Java EE 开发人员/ 如何做...

+   安装，适用于 Java EE 开发人员/ 如何做..., Eclipse for Java EE developers

+   URL/ 如何做...

+   JVM，选择/ 选择 JVM

+   Java SE 8/ Java SE 8

+   EJB3 实体

+   定义/ 准备就绪, 如何做..., 它是如何工作的...

+   要求/ 实体要求

+   模式，映射/ 映射模式

+   继承，定义/ 定义继承

+   关系，定义/ 定义关系

+   嵌入式数据库

+   使用/ 使用嵌入式数据库

+   EmbeddedServletContainerCustomizer 接口

+   关于/ 处理文件上传错误

+   URL/ 处理文件上传错误

+   Ember

+   关于/ 玩家

+   Ember.js

+   关于/ SPA 框架, 介绍 Ember.js

+   Ember 应用程序

+   解剖学/ Ember 应用程序的解剖学

+   路由器/ 路由器

+   路由或路由处理程序/ 路由或路由处理程序

+   模板/ 模板

+   组件/ 组件

+   模型/ 模型

+   控制器/ 控制器

+   输入助手/ 输入助手

+   自定义助手/ 自定义助手

+   初始化程序/ 初始化程序

+   服务/ 服务

+   Ember CLI

+   关于/ 介绍 Ember.js, 使用 Ember CLI

+   使用/ 使用 Ember CLI

+   features / 使用 Ember CLI

+   setting up / 设置 Ember CLI

+   commands / 使用 Ember CLI 命令入门

+   project structure / Ember 项目结构

+   POD structure / 使用 POD 结构

+   Ember CLI 命令

+   about / 使用 Ember CLI 命令入门

+   ember / 使用 Ember CLI 命令入门

+   ember new <appname> / 使用 Ember CLI 命令入门

+   ember init / 使用 Ember CLI 命令入门

+   ember build / 使用 Ember CLI 命令入门

+   ember server (or serve) / 使用 Ember CLI 命令入门

+   ember generate <generatortype> <name> <options> / 使用 Ember CLI 命令入门

+   ember destroy <generatortype> <name> <options> / 使用 Ember CLI 命令入门

+   ember test / 使用 Ember CLI 命令入门

+   ember install <addon-name> / 使用 Ember CLI 命令入门

+   Ember Data

+   about / 介绍 Ember.js

+   data, persisting with / 使用 Ember Data 持久化数据

+   DS.Model / 使用 Ember Data 持久化数据

+   DS.Store / 使用 Ember Data 持久化数据

+   DS.Adapter / 使用 Ember Data 持久化数据

+   DS.Serializer / 使用 Ember Data 持久化数据

+   architecture / Ember Data 架构

+   models, building / 定义模型

+   model relationships, defining / 定义模型关系

+   Ember 开发堆栈

+   about / 介绍 Ember.js

+   Ember Inspector

+   about / 介绍 Ember.js

+   Ember object model

+   about / 理解 Ember 对象模型

+   types (classes), declaring / 声明类型（类）和实例

+   instances, declaring / 声明类型（类）和实例

+   properties, accessing / 访问和修改属性

+   properties, mutating / 访问和修改属性

+   computed properties / 计算属性

+   property observers / 属性观察者

+   collections, working with / 处理集合

+   Ember.Array / 使用集合

+   Ember.ArrayProxy / 使用集合

+   Ember.MutableArray / 使用集合

+   Ember.Enumerable / 使用集合

+   Ember.NativeArray / 使用集合

+   企业版（EE）/ AMQP 还是 JMS？

+   企业集成（EAI）

+   关于 / Spring 子项目

+   企业 JavaBean（EJB）

+   关于 / 介绍

+   企业 JavaBean（EJB）

+   关于 / Spring 事务的相关性

+   实体

+   关于 / 实体的好处

+   好处 / 实体的好处

+   实体，OAuth2

+   资源所有者 / OAuth2 授权框架

+   客户端或第三方应用程序 / OAuth2 授权框架

+   授权服务器 / OAuth2 授权框架

+   资源服务器 / OAuth2 授权框架

+   实体管理器

+   关于 / 实体管理器及其持久性上下文

+   持久性上下文 / 实体管理器及其持久性上下文

+   EntityManagerFactory bean

+   关于 / EntityManagerFactory bean 及其持久性单元

+   厄尔朗

+   URL / 如何做...

+   错误消息

+   翻译 / 翻译错误消息

+   ETag

+   关于 / 另请参阅

+   ETags

+   关于 / ETags

+   生成 / ETags

+   使用 / ETags

+   异常处理

+   关于 / 状态码和异常处理

+   异常

+   在 Spring 数据层处理 / 在 Spring 数据层处理异常

+   全局处理 / 准备工作, 如何做..., 工作原理...

## F

+   备用控制器

+   配置，使用 ViewResolver / 使用 ViewResolver 配置备用控制器, 如何做...

+   URI 模板模式 / URI 模板模式

+   ViewResolvers / ViewResolvers

+   备用选项

+   使用 / Spring 4 中 STOMP over WebSocket 和备用选项

+   Fastboot

+   关于 / 介绍 Ember.js

+   feedEk jQuery 插件

+   URL / 创建响应式内容

+   FetchType 属性

+   关于 / FetchType 属性

+   文件上传

+   关于 / 上传文件

+   个人资料图片，上传/ 上传文件

+   上传的图片，在网页上显示/ 将图像写入响应

+   上传属性，管理/ 管理上传属性

+   上传的图片，显示/ 显示上传的图片

+   错误，处理/ 处理文件上传错误

+   实现/ 将其放在一起

+   检查点/ 检查点

+   文件上传

+   处理/ 处理文件上传

+   过滤

+   关于/ 如何做..., 它是如何工作的...

+   FluentLenium

+   用于验收测试/ 我们的第一个 FluentLenium 测试

+   关于/ 我们的第一个 FluentLenium 测试

+   URL/ 我们的第一个 FluentLenium 测试

+   页面对象/ 使用 FluentLenium 的页面对象

+   FlyWay

+   用于自动化数据库迁移/ 使用 FlyWay 自动化数据库迁移, 如何做...

+   命令/ 有限的命令数量

+   maven 插件/ 关于 Flyway Maven 插件

+   配置参数，URL/ 关于 Flyway Maven 插件

+   官方文档/ 官方文档

+   GitHub 仓库，URL/ 官方文档

+   FlyWay，命令

+   关于/ 有限的命令数量

+   迁移/ 迁移

+   清洁/ 清洁

+   信息/ 信息

+   验证/ 验证

+   基线/ 基线

## G

+   垃圾收集

+   参考链接/ 还有更多...

+   GDAXI 指数代码

+   URL/ 如何做...

+   Geb

+   用于集成测试/ 使用 Geb 进行集成测试

+   关于/ 使用 Geb 进行集成测试

+   页面对象/ 使用 Geb 的页面对象

+   参考链接/ 使用 Geb 的页面对象

+   Git

+   关于/ 上传文件

+   空目录/ 上传文件

+   GIT

+   安装/ 下载和安装 GIT

+   下载/ 下载和安装 GIT

+   URL/ 下载和安装 GIT

+   在 Eclipse 中配置/ 在 Eclipse 中配置 GIT

+   全局事务

+   全局与本地事务/ 全局与本地事务

+   参考链接/ 全局与本地事务

+   Google 协议缓冲区

+   URL / 提供的 HttpMessageConverters

+   Gradle

+   配置 / Gradle 配置

+   运行 / Gradle

+   URL / Gradle

+   GrantedAuthority 接口

+   关于 / GrantedAuthority 接口

+   Groovy

+   接受测试/ 使我们的测试更加灵活

+   关于 / 使我们的测试更加灵活

+   URL / 使我们的测试更加灵活

+   Groovy 开发工具包（GDK）

+   关于 / 使我们的测试更加灵活

+   Gzipping

+   关于 / Gzipping

+   参考链接 / Gzipping

## H

+   HandlerMapping

+   关于 / DispatcherServlet

+   HAProxy

+   URL / 替代 Apache HTTP 的选择

+   标题

+   参考链接 / 另请参阅

+   堆内存

+   年轻一代 / 自定义 JVM 参数

+   旧一代 / 自定义 JVM 参数

+   Heroku

+   关于 / Heroku

+   Web 应用程序，部署 / 在 Heroku 上部署您的 Web 应用程序

+   命令行工具，安装 / 安装工具

+   URL / 安装工具

+   Web 应用程序，设置 / 设置应用程序

+   运行 Gradle / Gradle

+   运行 Procfile / Procfile

+   配置文件，创建 / 一个 Heroku 配置文件

+   Web 应用程序，执行 / 运行您的应用程序

+   激活 Redis / 激活 Redis

+   Heroku Redis 附加组件

+   URL / 激活 Redis

+   Hibernate 查询语言（HQL）

+   关于 / 使用 JPQL

+   HikariCP 数据源

+   关于 / 另请参阅

+   URL / 另请参阅

+   主机

+   别名 / 主机的别名

+   选择 / 选择您的主机

+   Cloud Foundry / Cloud Foundry

+   OpenShift / OpenShift

+   Heroku / Heroku

+   主机别名 / DNS 配置或主机别名

+   HTML5/AngularJS

+   客户端表单，验证 / 使用 HTML5 AngularJS 验证客户端表单, 如何做..., 它是如何工作的...

+   HTML 文档

+   模块自动引导 / 模块自动引导

+   模块自动引导，手动 / 手动模块引导

+   HTTP/1.1 规范

+   参考链接 / HTTP/1.1 规范-RFC 7231 语义和内容

+   必要条件/【基本要求】

+   安全方法/【安全和幂等方法】

+   幂等方法/【安全和幂等方法】

+   特定于方法的约束/【其他特定于方法的约束】

+   HTTP 代码

+   关于/【有用的 HTTP 代码】

+   URL/【有用的 HTTP 代码】

+   HTTP 连接器/【HTTP 连接器】

+   URL/【另请参阅】

+   httpie

+   关于/【httpie】

+   HttpMessageConverters

+   使用/【HttpMessageConverters】

+   本机 HttpMessageConverters/【提供的 HttpMessageConverters】

+   MappingJackson2HttpMessageConverter，使用/【使用 MappingJackson2HttpMessageConverter】

+   HTTP 方法

+   REST 处理程序，扩展到/【将 REST 处理程序扩展到所有 HTTP 方法】，【如何做…】，【它是如何工作的…】

+   HTTP 会话

+   配置文件，存储/【将配置文件放入会话中】

+   关于/【将配置文件放入会话中】

+   HTTP 状态码/【HTTP 状态码】

+   HTTP 动词

+   获取/【级别 2 - HTTP 动词】

+   头/【级别 2 - HTTP 动词】

+   删除/【级别 2 - HTTP 动词】

+   放置/【级别 2 - HTTP 动词】

+   发布/【级别 2 - HTTP 动词】

+   PATCH/【级别 2 - HTTP 动词】

+   选项/【级别 2 - HTTP 动词】

+   超媒体驱动的 API

+   链接，构建/【为超媒体驱动的 API 构建链接】，【如何做…】，【它是如何工作的…】，【构建链接】

+   资源装配器/【资源装配器】

+   PagedResourcesAssembler/【PagedResourcesAssembler】

+   EntityLinks/【EntityLinks】

+   ControllerLinkBuilder/【ControllerLinkBuilder】

+   @RequestMapping 中的正则表达式/【在@RequestMapping 中使用正则表达式】

+   超媒体作为应用程序状态的引擎（HATEOAS）

+   关于/【介绍】

+   超文本应用语言（HAL）

+   URL/【另请参阅】

+   应用程序状态的超文本作为引擎（HATEOAS）

+   关于/【级别 3 - 超媒体控件】

## 我

+   iconmonstr

+   URL/【将图像写入响应】

+   IDE（集成开发环境）

+   关于/【Spring 工具套件（STS）】

+   标识符

+   关于/【实体要求】

+   ID 暴露

+   URL/【另请参阅】

+   信息命令/ 信息

+   继承，EJB3 实体

+   定义/ 定义继承

+   单表策略/ 单表策略

+   按类策略/ 按类策略

+   继承，Maven 依赖

+   关于/ Maven 依赖的继承

+   基本继承/ 基本继承

+   管理继承/ 管理继承

+   集成测试

+   Spring Beans，注入/ 将 Spring Beans 注入集成测试, 如何做...

+   使用 Geb/ 使用 Geb 进行集成测试

+   拦截器

+   关于/ 更改区域设置

+   国际化（i18n）

+   关于/ 国际化

+   区域设置，修改/ 更改区域设置

+   应用文本，翻译/ 翻译应用文本

+   数据列表，在表单中处理/ 表单中的列表

+   物联网（IoT）/ 微服务架构

+   互联网服务提供商（ISP）/ DNS 配置或主机别名

+   控制反转（IOC）

+   关于/ Spring 框架带来了什么？

+   控制反转（IoC）容器/ Spring 框架模块

## J

+   Jackson 2.x 扩展组件

+   URL/ 提供的 HttpMessageConverters

+   JaCoCo

+   URL/ 另请参阅

+   jar

+   关于/ 准备就绪

+   jar 依赖

+   关于/ 准备就绪

+   jar 模块

+   选择名称/ 我们如何选择 jar 模块的名称？

+   Java 8

+   Eclipse，配置/ 准备就绪, 如何做...

+   流/ Java 8 流和 lambda 表达式

+   lambda 表达式/ Java 8 流和 lambda 表达式

+   Java 8 日期时间 API

+   参考链接/ 个人资料页面-表单

+   Java 激活框架（JAF）

+   关于/ 提供的 HttpMessageConverters

+   JavaBeans 组件/ 使用 JSP EL 呈现变量

+   JavaBeans 标准

+   URL/ 关于 JavaBeans 标准的更多信息

+   JavaDoc

+   URL/ WebContentGenerator 提供的更多功能, 使用 JAXB2 实现作为 XML 解析器

+   Java EE 教程

+   URL/ 使用 JSTL 呈现变量

+   Java 持久化 API（JPA）

+   关于/ 介绍

+   在 Spring 中配置 / 在 Spring 中配置 Java 持久化 API, 如何做..., 它是如何工作的...

+   Spring 管理的 DataSource bean / Spring 管理的 DataSource bean

+   EntityManagerFactory bean，配置 / EntityManagerFactory bean 及其持久化单元

+   持久化单元，配置 / EntityManagerFactory bean 及其持久化单元

+   Spring Data JPA，配置 / Spring Data JPA 配置

+   使用 / 利用 JPA 和 Spring Data JPA, 如何做..., 它是如何工作的...

+   Java 持久化查询语言（JPQL）

+   使用 / 使用 JPQL

+   参考链接 / 使用 JPQL

+   Java SE 8

+   使用 / Java SE 8

+   Java 服务器页面（JSP）

+   关于 / 解析 JSP 视图

+   Java 服务器页面标签库（JSTL）

+   关于 / 解析 JSP 视图

+   Java 服务器标签库（JSTL）

+   用于在视图中显示模型 / 在视图中显示模型，使用 JSTL, 如何做..., 它是如何工作的...

+   URL / 更多关于 JSTL

+   Java Util 日志适配器 / Java Util 日志适配器

+   JAXB2 实现

+   作为 XML 解析器使用 / 将 JAXB2 实现作为 XML 解析器使用

+   JDBC 操作

+   使用 Sql*类 / 使用 Sql*类进行 JDBC 操作

+   组件 / 使用 Sql*类进行 JDBC 操作

+   JdbcTemplate

+   方法 / JdbcTemplate

+   回调接口 / JdbcTemplate

+   NamedParameterJdbcTemplate / NamedParameterJdbcTemplate/ JdbcTemplate

+   JDK 8

+   安装 / 如何做...

+   JDK 兼容级别

+   修改 / 更改 JDK 兼容级别

+   JMS

+   关于 / AMQP 还是 JMS？

+   联接表继承策略

+   关于 / 另请参阅

+   JOTM

+   URL / 全局与本地事务

+   JPA（Java 持久化架构）

+   关于 / Spring Data JPA

+   JPA 实体

+   选择公开的策略 / 选择公开 JPA 实体的策略, 如何做..., 它是如何工作的...

+   REST CRUD 原则 / REST CRUD 原则

+   最小信息，暴露/ 暴露最小信息, 如果实体拥有关系

+   资源分离/ 资源分离

+   JSON 输出

+   自定义/ 自定义 JSON 输出

+   JSP EL

+   URL / 更多关于 JSP EL

+   JSP 表达式语言（JSP EL）/ 准备就绪

+   关于/ 准备就绪

+   JSP

+   Taglib 指令/ JSP 中的 Taglib 指令

+   JSP 标准标签库（JSTL）

+   关于/ 使用 JSTL 呈现变量

+   JSR-250

+   关于/ JSR-250 和遗留方法安全

+   JSR-303/JSR-349 bean 验证

+   使用/ 使用 JSR-303/JSR-349 Bean 验证

+   字段约束注释/ 字段约束注释

+   特定于实现的约束/ 特定于实现的约束

+   LocalValidator（可重用）/ LocalValidator（可重用）

+   JSR-310

+   URL / 自定义 JSON 输出

+   JSR-356

+   URL / 另请参阅

+   JTA（Java 事务 API）

+   关于/ Spring 事务的相关性

+   JUnit 规则

+   URL / JUnit 规则

+   JVM

+   选择/ 选择 JVM

+   JVM 参数

+   自定义/ 自定义 JVM 参数

## L

+   lambda，Java 8

+   关于/ Java 8 流和 lambda

+   布局

+   使用/ 使用布局

+   链接

+   为超媒体驱动的 API 构建/ 为超媒体驱动的 API 构建链接, 如何做…

+   链接！/ ResourceSupport 类

+   Liquibase

+   URL / 另请参阅

+   液体火

+   关于/ 介绍 Ember.js

+   负载均衡 WebSockets

+   URL / 另请参阅

+   LocaleResolver

+   用于国际化消息/ 使用 LocaleResolver

+   AcceptHeaderLocaleResolver / AcceptHeaderLocaleResolver

+   FixedLocaleResolver / FixedLocaleResolver

+   SessionLocaleResolver / SessionLocaleResolver

+   CookieLocaleResolver / CookieLocaleResolver

+   本地存储

+   URL / localStorage 的浏览器支持

+   Log4j 1.x API 桥接/ Log4j 1.x API 桥接

+   Log4j2

+   用于应用程序日志记录/ Log4j2 的现代应用程序日志记录, 如何做…

+   和其他日志框架/ Apache Log4j2 等其他日志框架

+   SLF4j, 案例 / SLF4j 的案例

+   迁移到 / 迁移到 log4j 2

+   API 和核心 / Log4j 2 API 和核心

+   适配器 / Log4j 2 适配器

+   配置文件 / 配置文件

+   自动配置 / 自动配置

+   自动配置, URL / 自动配置

+   官方文档 / 官方文档

+   官方文档, URL / 官方文档

+   Redis Appender, 实现 / 有趣的 Redis Appender 实现

+   Redis, URL / 有趣的 Redis Appender 实现

+   Log4j2, 适配器

+   关于 / Log4j 2 适配器

+   Log4j 1.x API 桥接器 / Log4j 1.x API 桥接器

+   Apache Commons Logging 桥接器 / Apache Commons Logging 桥接器

+   SLF4J 桥接器 / SLF4J 桥接器

+   Java Util Logging 适配器 / Java Util Logging 适配器

+   Web Servlet 支持 / Web Servlet 支持

+   登录表单

+   设计 / 登录表单

+   Luna 分发

+   URL / 如何做...

## M

+   @MessageMapping

+   用于定义消息处理程序 / 通过@MessageMapping 定义消息处理程序

+   m2eclipse 插件

+   URL / 更多信息...

+   编组响应

+   关于 / 绑定请求和编组响应, 如何做..., 它是如何工作的...

+   Material Design

+   使用 WebJars / 使用 WebJars 进行 Material Design

+   Materialize

+   URL / 使用 WebJars 进行 Material Design

+   矩阵变量

+   URL 映射 / 使用矩阵变量进行 URL 映射

+   Maven

+   需要 / 为什么要使用 Maven?

+   配置 / 配置 Maven

+   项目结构, 定义 / 使用 Maven 定义项目结构, 准备工作, 如何做...

+   构建生命周期 / Maven 的构建生命周期

+   参考资料 / 更多信息...

+   Maven 3

+   Eclipse, 配置 / 准备工作, 如何做...

+   Maven checkstyle 插件

+   关于 / Maven 的 checkstyle 插件

+   URL / Maven 的 checkstyle 插件

+   Maven Failsafe

+   与 Maven Surefire 相比 / Maven Failsafe 与 Maven Surefire

+   Maven 模型

+   参考链接 / 使用 Maven 属性

+   Maven 插件

+   URL / 还有更多...

+   Maven Surefire

+   关于 / 使用 Mockito 和 Maven Surefire 进行单元测试, 如何做…

+   内存优化

+   参考链接 / 还有更多...

+   面向消息的中间件（MoM） / 使用 RabbitMQ 和 AMQP 堆叠和消费任务

+   消息代理

+   使用全功能消息代理 / 使用全功能消息代理

+   集群能力 / 集群能力 - RabbitMQ

+   STOMP 消息类型 / 更多 STOMP 消息类型

+   StompMessageBrokerRelay / StompMessageBrokerRelay

+   消息驱动的 Bean（MDB）

+   关于 / Spring 事务的相关性

+   消息

+   用于 REST 的国际化 / 为 REST 国际化消息和内容

+   使用 MessageSource beans 进行国际化 / MessageSource beans

+   使用 LocaleResolver / 使用 LocaleResolver

+   发送，分发 / 发送消息以分发

+   SimpMessagingTemplate / SimpMessagingTemplate

+   @SendTo 注释 / The @SendTo 注释

+   使用 Spring Session 进行安全保护 / 使用 Spring Session 和 Redis 保护消息

+   使用 Redis 进行安全保护 / 使用 Spring Session 和 Redis 保护消息

+   Apache HTTP 代理配置 / Apache HTTP 代理配置

+   Redis 服务器安装 / Redis 服务器安装

+   MySQL 服务器安装 / MySQL 服务器安装

+   应用级别的更改 / 应用级别的更改

+   RabbitMQ 配置 / RabbitMQ 配置

+   结果 / 结果

+   Redis 服务器 / Redis 服务器

+   Spring 会话 / Spring 会话

+   SessionRepositoryFilter / SessionRepositoryFilter

+   RedisConnectionFactory / RedisConnectionFactory

+   CookieHttpSessionStrategy / CookieHttpSessionStrategy

+   Tomcat 的 Redis 会话管理器 / Tomcat 的 Redis 会话管理器

+   在 Redis 中查看会话 / 查看/刷新 Redis 中的会话

+   在 Redis 中查看/刷新会话 / 查看/刷新 Redis 中的会话

+   securityContextPersistenceFilter / securityContextPersistenceFilter

+   AbstractSessionWebSocketMessageBrokerConfigurer / AbstractSessionWebSocketMessageBrokerConfigurer

+   AbstractSecurityWebSocketMessageBrokerConfigurer / AbstractSecurityWebSocketMessageBrokerConfigurer

+   Spring 会话，URL / Spring 会话

+   Apache HTTP 代理，额外配置 / Apache HTTP 代理额外配置

+   Spring Data Redis / Spring Data Redis

+   MessageSource beans

+   用于国际化消息 / MessageSource beans

+   ResourceBundleMessageSource / ResourceBundleMessageSource

+   ReloadableResourceBundleMessageSource / ReloadableResourceBundleMessageSource

+   StaticMessageSource / StaticMessageSource

+   定义 / 我们的 MessageSource bean 定义

+   面向消息的中间件（MOM）

+   关于 / 介绍

+   迁移命令 / 迁移

+   Mockito

+   单元测试 / 使用 Mockito 和 Maven Surefire 进行单元测试, 如何做...

+   @Test 注释 / @Test 注释

+   使用 / 使用 Mockito

+   JUnitRunner / MockitoJUnitRunner

+   transferCriticalData 示例 / transferCriticalData 示例

+   registerUser 示例 / registerUser 示例

+   URL / 关于 Mockito

+   JUnit 规则 / JUnit 规则

+   用于创建模拟 / 使用 Mockito 进行模拟

+   MockitoJUnitRunner / MockitoJUnitRunner

+   模拟

+   关于 / Mocks 和 stubs

+   和存根，选择 / 我应该使用模拟还是存根？

+   参考链接 / 我应该使用模拟还是存根？

+   模型

+   在视图中显示，使用 JSTL / 在视图中显示模型，使用 JSTL, 如何做..., 它是如何工作的...

+   在控制器中填充 / 在控制器中填充模型

+   使用 JSP EL 渲染变量 / 使用 JSP EL 渲染变量

+   隐式对象 / 隐式对象

+   模型-视图-控制器（MVC）架构模式

+   关于 / 介绍 Ember.js

+   模型-视图-控制器模式

+   关于 / 模型-视图-控制器模式

+   模型 / 模型-视图-控制器模式

+   视图 / 模型-视图-控制器模式

+   控制器 / 模型-视图-控制器模式

+   模块

+   创建/ 设置 DOM 和创建模块

+   组件，定义/ 定义模块的组件, 工作原理…

+   URL/ 还有更多…

+   mod_alias 模块/ mod_alias 模块

+   mod_proxy 模块/ mod_proxy 模块

+   morris.js 库

+   URL/ 创建响应式内容

+   多用途互联网邮件扩展（MIME）

+   关于/ 上传文件

+   MVC 架构

+   关于/ MVC 架构

+   模型/ MVC 架构

+   视图/ MVC 架构

+   控制器/ MVC 架构

+   最佳实践/ MVC 评论家和最佳实践

+   评论家/ MVC 评论家和最佳实践

+   贫血领域模型/ 贫血领域模型

+   sagan 项目/ 从源代码中学习

+   sagan 项目，URL/ 从源代码中学习

+   MVC 设计模式/ MVC 设计模式

+   MVC 异常

+   URL/ 另请参阅

## N

+   本机 SQL 查询

+   使用/ 使用本机 SQL 查询

+   URL/ 使用本机 SQL 查询

+   导航

+   使用/ 导航

+   重定向选项/ 导航

+   前向选项/ 导航

+   无级联操作

+   关于/ 级联属性

+   Node.js

+   URL/ 设置 Ember CLI

## O

+   OAuth

+   数据，从第三方 API 检索/ 使用 OAuth 从第三方 API 检索数据, 操作方法…

+   OAuth2 认证服务器（AS）

+   关于/ 准备工作

+   OAuth2 授权框架

+   关于/ OAuth2 授权框架

+   实体/ OAuth2 授权框架

+   OAuth 开发

+   别名定义 / OAuth 开发的别名定义

+   面向对象编程（OOP）

+   关于/ 面向方面的编程

+   每个 HTTP 连接策略一个线程 / Spring MVC 中的异步请求处理

+   OpenShift

+   关于/ OpenShift

+   URL/ OpenShift

+   Oracle Hotspot JDK

+   URL/ 操作方法…

## P

+   页面对象

+   使用 FluentLenium/ 使用 FluentLenium 的页面对象

+   使用 Geb/ 使用 Geb 的页面对象

+   分页

+   添加/ 添加分页、过滤和排序功能, 如何做..., 它是如何工作的...

+   Spring 数据分页支持/ Spring 数据分页支持（您会喜欢它！）

+   和存储库中的排序/ 存储库中的分页和排序

+   PagingAndSortingRepository<T,ID>/ PagingAndSortingRepository<T,ID>

+   PageableHandlerMethodArgumentResolver/ web 部分-PageableHandlerMethodArgumentResolver

+   负载映射

+   使用@RequestBody 请求/ 使用@RequestBody 映射请求负载

+   永久代（PermGen）

+   关于/ 自定义 JVM 参数

+   持久化单元

+   关于/ EntityManagerFactory bean 及其持久化单元

+   PhantomJS

+   URL/ 我们的第一个 FluentLenium 测试

+   Pivotal Web Services（PWS）

+   Web 应用程序，部署/ 将您的 Web 应用程序部署到 Pivotal Web Services

+   普通的 Java 对象（POJOs）

+   关于/ 介绍

+   普通的旧 Java 对象（POJO）

+   关于/ 个人资料页面-表单

+   普通的旧 Java 对象（POJOs）

+   关于/ 贫血领域模型

+   普通的旧 Java 对象（POJOs）

+   关于/ 领域对象和实体

+   插件

+   关于/ 插件

+   Maven 编译器插件/ Maven 编译器插件

+   Maven surefire 插件/ Maven surefire 插件

+   Maven enforcer 插件/ Maven enforcer 插件

+   Maven war 插件/ Maven war 插件

+   Maven checkstyle 插件/ Maven checkstyle 插件

+   POD 结构

+   与之一起工作/ 与 POD 结构一起工作

+   切入点设计者（PCDs）

+   关于/ 切入点设计者

+   切入点，@AspectJ 注解

+   关于/ 切入点

+   设计者/ 切入点设计者

+   示例/ 切入点示例

+   POJO（普通的旧 Java 对象）/ Spring 框架背后的设计概念

+   Procfile

+   运行/ Procfile

+   生产配置文件

+   配置/ 生产配置文件

+   个人资料

+   存储，在会话中/ 将个人资料放入会话中

+   个人资料页面

+   关于/ 个人资料页面-表单

+   创建/ 个人资料页面-表单

+   添加验证/ 验证

+   启用客户端验证/ 客户端验证

+   检查点/ 检查点

+   项目对象模型（POM）

+   关于/ 为什么要使用 Maven？

+   项目结构

+   使用 Maven 定义/ 使用 Maven 定义项目结构, 准备就绪, 如何做...

+   创建 Maven 项目/ 新的 Maven 项目，新的 Maven 模块

+   创建 Maven 模块/ 新的 Maven 项目，新的 Maven 模块

+   标准项目层次结构/ 标准项目层次结构

+   在 IDE 中/ IDE 中的项目结构

+   属性

+   注入到 Spring 环境中/ 将属性注入到 Spring 环境中

+   PropertyEditor/ConversionService/ 在 PropertyEditors 或转换器之间进行选择

+   PropertyEditor 实现

+   关于/ 内置的 PropertyEditor 实现

+   PropertyPlaceholderConfigurer

+   关于/ 使用 PropertyPlaceholderConfigurer 外部化属性

+   属性，外部化/ 使用 PropertyPlaceholderConfigurer 外部化属性

+   特定于提供程序的配置，第三方 OAuth2 方案

+   关于/ 特定于提供程序的配置

+   connectionFactoryLocator bean/ 一个入口点-connectionFactoryLocator

+   特定于提供程序的 ConnectionFactories/ 特定于提供程序的 ConnectionFactories

+   使用提供程序帐户登录/ 使用提供程序帐户登录

+   验证的 API 调用，执行/ 执行验证的 API 调用

+   Spring social ConnectController/ Spring social ConnectController

+   SocialAuthenticationFilter/ SocialAuthenticationFilter

+   Spring 社交连接器列表/ Spring 社交连接器列表

+   实现 OAuth2 认证服务器/ 实现 OAuth2 认证服务器

+   和谐发展博客/ 和谐发展博客

+   代理模式

+   URL/ 还有更多...

+   ProxyPassReverse

+   关于/ ProxyPassReverse

+   工作者/ 工作者

## Q

+   查询查找策略

+   定义/ 查询解析方法

+   查询参数

+   关于/ 使用请求参数获取数据

## R

+   @Repository 注释

+   关于/ DAO 支持和@Repository 注释

+   @RequestBody

+   请求负载映射/ 使用@RequestBody 映射请求负载

+   @RequestMapping

+   新的支持类/ 自 Spring MVC 3.1 以来@RequestMapping 的新支持类

+   @RequestMapping 注释/ @RequestMapping

+   @RequestMapping 注释

+   支持/ 广泛支持@RequestMapping 注释

+   setMessageConverters/ setMessageConverters

+   setCustomArgumentResolvers/ setCustomArgumentResolvers

+   setWebBindingInitializer / setWebBindingInitializer

+   作为终极过滤器使用/ @RequestMapping 注释作为终极过滤器

+   @RequestPart

+   用于上传图像/ 使用@RequestPart 上传图像

+   @RunWith 注释

+   关于/ @RunWith 注释

+   RabbitMQ

+   作为多协议消息代理使用/ 将 RabbitMQ 用作多协议消息代理, 如何做...

+   URL / 如何做...

+   指南和文档，URL/ 另请参阅

+   任务，使用 Spring Session 和 Redis 进行保护/ 准备工作

+   任务，使用 Spring Session 和 Redis 进行保护/ 准备工作

+   raphael.js 库

+   URL / 创建响应式内容

+   React

+   关于/ 玩家

+   ReactJS

+   关于/ SPA 框架

+   Redis

+   消息，使用 Spring Session 和 Redis 进行保护/ 使用 Spring Session 和 Redis 保护消息

+   URL / Redis 服务器安装, 分布式会话

+   激活/ 激活 Redis, 激活 Redis

+   关系，EJB3 实体

+   定义/ 定义关系

+   选择/ 实体之间的关系是如何选择的

+   远程

+   URL / setMessageConverters

+   修复命令/ 修复, 关于 Flyway Maven 插件

+   存储库管理器

+   关于/ 存储库管理器

+   URL / 还有更多...

+   REpresentational State Transfer (REST)

+   关于/ REST 的定义

+   Restful CloudStreetMarket/ RESTful CloudStreetMarket

+   REpresentational State Transfer (REST)

+   关于/ 为 JSON 和 XML 媒体构建 RESTful 服务

+   请求通道/ Spring 4 中 STOMP over WebSocket 和回退选项

+   RequestMappingHandlerAdapter

+   URL / 自 Spring MVC 3.1 以来@RequestMapping 的新支持类

+   RequestMappingHandlerAdapter bean

+   关于 / 一个超级 RequestMappingHandlerAdapter bean

+   资源

+   处理 / 处理资源

+   ResourceSupport 类 / ResourceSupport 类

+   响应通道 / Spring 4 中 STOMP over WebSocket 和回退选项

+   ResponseEntityExceptionHandler

+   URL / JavaDocs

+   响应式内容

+   创建 / 创建响应式内容

+   响应式单页 Web 设计

+   使用 Bootstrap 设置 / 使用 Bootstrap 设置和自定义响应式单页 Web 设计, 如何做...

+   自定义 Bootstrap 主题 / 自定义 Bootstrap 主题

+   响应式单页 Web 设计

+   安装 Bootstrap 主题 / 安装 Bootstrap 主题

+   自定义 Bootstrap 主题 / 自定义 Bootstrap 主题

+   REST

+   关于 / 什么是 REST？

+   Rest-assured

+   与之集成测试 / 使用 Cargo，Rest-assured 和 Maven failsafe 进行集成测试, 如何做..., 它是如何工作的...

+   关于 / Rest assured

+   静态导入 / 静态导入

+   用法 / 一种给定，当，然后的方法

+   REST-assured

+   示例 / 更多 REST-assured 示例

+   示例，URL / 更多 REST-assured 示例

+   REST 控制器

+   单元测试 / 单元测试 REST 控制器

+   REST 环境

+   凭据，存储 / 在 REST 环境中存储凭据

+   客户端（AngularJS） / 客户端（AngularJS）

+   服务器端 / 服务器端

+   微服务，用于身份验证 / 用于微服务的身份验证

+   使用 BASIC 身份验证 / 使用 BASIC 身份验证

+   使用 OAuth 进行登录 / 使用 OAuth2

+   HTML5 SessionStorage / HTML5 SessionStorage

+   BCryptPasswordEncoder / BCryptPasswordEncoder

+   HTTP 头，使用 AngularJS 设置 / 使用 AngularJS 设置 HTTP 头

+   浏览器支持，用于 localStorage / 用于 localStorage 的浏览器支持

+   SSL 和 TLS / 关于 SSL 和 TLS

+   RESTful API，调试

+   关于 / 调试 RESTful API

+   JSON 格式化扩展 / JSON 格式化扩展

+   浏览器中的 RESTful 客户端 / 浏览器中的 RESTful 客户端

+   httpie / httpie

+   RESTful web 服务，属性

+   客户端-服务器 / 什么是 REST？

+   无状态的 / 什么是 REST？

+   可缓存的 / 什么是 REST？

+   统一接口 / 什么是 REST？

+   分层的 / 什么是 REST？

+   REST 处理程序

+   扩展，到 HTTP 方法 / 将 REST 处理程序扩展到所有 HTTP 方法, 如何做…, 它是如何工作的...

+   HTTP/1.1 规范 / HTTP/1.1 规范 - RFC 7231 语义和内容

+   负载映射，使用@RequestBody 请求 / 使用@RequestBody 映射请求负载

+   HttpMessageConverters / HttpMessageConverters

+   @RequestPart，用于上传图像 / 使用@RequestPart 上传图像

+   事务管理 / 事务管理

+   Richardson 的成熟模型

+   关于 / Richardson 的成熟模型

+   级别 0 - HTTP / 级别 0 - HTTP

+   级别 1 - 资源 / 级别 1 - 资源

+   级别 2 - HTTP 动词 / 级别 2 - HTTP 动词

+   级别 3 - 超媒体控制 / 级别 3 - 超媒体控制

+   Richardson 成熟模型

+   关于 / Richardson 成熟模型

+   URL / Richardson 成熟模型

+   ROME 项目

+   URL / 提供的 HttpMessageConverters

+   根名称服务器 / DNS 配置或主机别名

+   路由

+   处理 / 处理路由

+   例行

+   需要 / 为什么需要这样的例行？

## S

+   @SendTo 注释 /  @SendTo 注释

+   Saas 提供商

+   URL / Spring 社交连接器列表

+   模式，EJB3 实体

+   映射 / 映射模式

+   表，映射 / 映射表

+   列，映射 / 映射列

+   字段，注释 / 注释字段或 getter

+   getter，注释 / 注释字段或 getter

+   主键，映射 / 映射主键

+   标识符生成 / 标识符生成

+   SearchApiController 类

+   在 search.api 包中创建 / 客户是王

+   securityContextPersistenceFilter / securityContextPersistenceFilter

+   安全头

+   关于 / 授权用户

+   URL / 授权用户

+   自签名证书

+   生成 / 生成自签名证书

+   序列化器

+   URL / Jackson 自定义序列化器

+   服务类 / 基于 XML 的配置元数据

+   服务提供商（SP）

+   关于 / 准备就绪

+   服务

+   授权 / 在服务和控制器上进行授权, 如何做...

+   SessionRepositoryFilter

+   关于 / SessionRepositoryFilter

+   RedisConnectionFactory / RedisConnectionFactory

+   基于 setter 的 DI

+   关于 / 基于构造函数还是基于 setter 的 DI - 哪个更好？

+   SimpleJdbc 类 / SimpleJdbc 类

+   简单文本导向消息协议（STOMP）

+   关于 / STOMP 协议

+   URL / STOMP 协议

+   简单 URL 映射

+   用于配置控制器 / 使用简单 URL 映射配置控制器, 如何做...

+   简单 WebSocket 应用程序

+   创建 / 创建一个简单的 WebSocket 应用程序

+   单页应用程序（SPA）

+   动机 / SPA 背后的动机

+   关于 / 解释 SPA

+   架构优势 / SPA 的架构优势

+   单页应用

+   关于 / 单页应用程序

+   建议 / 参与者

+   未来的增强 / 未来

+   无状态选项 / 无状态化

+   参考链接 / 无状态化

+   SLF4j

+   案例 / SLF4j 的案例

+   SLF4J 桥接器 / SLF4J 桥接器

+   社交事件

+   使用 STOMP 通过 SockJS 进行流式传输 / 使用 STOMP 通过 SockJS 进行流式传输社交事件 , 如何做...

+   Apache HTTP 代理配置 / Apache HTTP 代理配置

+   前端 / 前端

+   前端，URL / 前端

+   后端 / 后端, 它是如何工作的...

+   SockJS

+   关于 / SockJS

+   URL / SockJS

+   回退，选项 / 还有更多...

+   客户端查询，URL / 还有更多...

+   Sockjs

+   关于 / WebSockets

+   SPA 框架

+   关于 / SPA 框架

+   AngularJS / SPA 框架

+   ReactJS / SPA 框架

+   Ember.js / SPA 框架

+   SpEL（Spring 表达式语言）

+   关于 / 查询解析方法

+   SpEL API

+   关于 / SpEL API

+   接口和类 / SpEL API

+   Spock

+   用于单元测试 / 使用 Spock 进行单元测试

+   Spring

+   使用 / 使用 Spring 进行测试

+   安装 / 安装 Spring，Spring MVC 和 Web 结构, 如何做..., 它是如何工作的...

+   Maven 依赖项的继承 / Maven 依赖项的继承

+   包括第三方依赖项 / 包括第三方依赖项

+   Web 资源 / Web 资源

+   Java 持久性 API（JPA），配置 / 在 Spring 中配置 Java 持久性 API, 如何做..., 它是如何工作的...

+   生态系统 / Spring 生态系统

+   URL / Spring 生态系统

+   核心 / 核心

+   执行 / 执行

+   XD 项目，URL / 执行

+   数据 / 数据

+   值得注意的项目 / 其他值得注意的项目

+   Spring 的 JSF 集成

+   关于 / Spring 的 JSF 集成

+   Spring 的 Struts 集成

+   关于 / Spring 的 Struts 集成

+   Spring 管理的 DataSource bean

+   关于 / Spring 管理的 DataSource bean

+   spring-messaging 模块

+   关于 / Spring 4 中的 STOMP over WebSocket 和回退选项

+   spring-security-crypto

+   URL / 社交连接持久性

+   Spring-websocket-portfolio

+   URL / 另请参阅

+   Spring 4.2+

+   URL / 发布应用程序事件的更好方法

+   Spring AOP

+   定义 / Spring AOP - 定义和配置样式

+   配置样式 / Spring AOP - 定义和配置样式

+   Spring 应用程序

+   关于 / 你的第一个 Spring 应用程序

+   控制反转（IoC）/ 控制反转解释

+   Spring Beans

+   在集成测试中注入 / 将 Spring Beans 注入集成测试, 如何做...

+   SpringJUnit4ClassRunner / SpringJUnit4ClassRunner

+   @ContextConfiguration 注释 /  @ContextConfiguration 注释, 还有更多...

+   JdbcTemplate / JdbcTemplate

+   样板逻辑，抽象 / 抽象样板逻辑

+   自动生成的 ID，提取 / 提取自动生成的 ID

+   Spring Boot

+   登录 / 个人资料页面-表单

+   URL / 个人资料页面-表单

+   Spring Data

+   关于 / Spring Data, Spring Data

+   子项目，定义 / Spring Data

+   Commons / Spring Data Commons

+   存储库规范 / Spring Data 存储库规范

+   MongoDB / Spring Data MongoDB

+   领域对象和实体 / 领域对象和实体

+   Spring 事务支持 / Spring 事务支持

+   Spring Data Commons

+   定义 / Spring Data Commons

+   Spring Data JPA

+   配置 / Spring Data JPA 配置

+   使用 / 利用 JPA 和 Spring Data JPA, 如何做..., 它是如何工作的...

+   注入 EntityManager 实例 / 注入 EntityManager 实例

+   Java 持久性查询语言（JPQL），使用 / 使用 JPQL

+   代码，减少 / 使用 Spring Data JPA 减少样板代码

+   查询，创建 / 创建查询

+   实体，持久化 / 持久化实体

+   本地 SQL 查询，使用 / 使用本地 SQL 查询

+   配置事务 / 事务

+   URL / 数据

+   Spring Data 层

+   异常处理 / 在 Spring Data 层处理异常

+   Spring Data Mongo

+   URL / 数据

+   Spring Data MongoDB

+   关于 / Spring Data MongoDB

+   启用 / 启用 Spring Data MongoDB

+   MongoRepository / MongoRepository

+   Spring Data Redis（SDR）框架 / Spring Data Redis 和 Spring Session Data Redis

+   Spring Data 存储库

+   自定义实现 / 另请参阅

+   参考链接 / 另请参阅

+   Spring Data 存储库规范

+   关于 / Spring Data 存储库规范

+   Spring Data JPA / Spring Data JPA

+   Spring Data JPA，启用 / 启用 Spring Data JPA

+   JpaRepository / JpaRepository

+   Spring Data REST

+   URL / 另请参阅, 数据

+   Spring EL

+   URL / Spring EL

+   Spring 表达式语言

+   关于 / Spring 表达式语言

+   特性 / SpEL 特性

+   注解支持 / SpEL 注解支持

+   Spring 表达式语言（SpEL）

+   关于 / Spring 表达式语言

+   URL / Spring 表达式语言

+   使用请求参数获取数据 / 使用请求参数获取数据

+   Spring 表单

+   在 JSP 中组合 / 在 JSP 中组合表单

+   验证 / 验证表单

+   Spring 表单标签库

+   关于 / Spring 和 Spring 表单标签库

+   Springfox

+   URL / Swagger 文档

+   Spring 框架

+   URL / 内置的 PropertyEditor 实现

+   Spring 框架

+   设计概念 / Spring 框架背后的设计概念

+   关于 / Spring 框架带来了什么？

+   Spring 框架模块

+   关于 / Spring 框架模块

+   Spring HATEOAS 资源

+   DTO，转换成 / 将 DTO 转换为 Spring HATEOAS 资源, 如何做…

+   关于 / Spring HATEOAS 资源

+   ResourceSupport 类 / ResourceSupport 类

+   资源类 / 资源类

+   可识别的接口 / 可识别的接口

+   实体的@Id，抽象化 / 抽象化实体的@Id, 还有更多…

+   URL / 另请参阅, 另请参阅

+   Spring 集成

+   URL / 其他值得注意的项目

+   Spring IoC 容器

+   关于 / Spring IoC 容器

+   Spring IO 参考文档

+   URL / Spring IO 参考文档

+   Spring JDBC

+   方法 / Spring JDBC 抽象

+   Spring JDBC 抽象

+   关于 / Spring JDBC 抽象

+   JdbcTemplate / JdbcTemplate

+   SimpleJdbc 类 / SimpleJdbc 类

+   SpringJUnit4ClassRunner / SpringJUnit4ClassRunner

+   Spring 景观

+   关于 / Spring 景观

+   Spring 框架模块 / Spring 框架模块

+   Spring 工具套件（STS） / Spring 工具套件（STS）

+   Spring 子项目 / Spring 子项目

+   Spring MVC

+   Web 应用程序 / Spring MVC 架构

+   Spring MVC

+   特性 / Spring MVC 的特性

+   architecture / Spring MVC 的架构和组件, Spring MVC 架构

+   components / Spring MVC 的架构和组件

+   asynchronous request processing / Spring MVC 中的异步请求处理

+   installing / 安装 Spring，Spring MVC 和 web 结构, 如何做..., 它是如何工作的...

+   about / Spring MVC 概述

+   front controller / 前端控制器

+   MVC 设计模式 / MVC 设计模式

+   flow / Spring MVC 流程

+   DispatcherServlet / DispatcherServlet-Spring MVC 入口点

+   annotation-defined controllers / 注解定义的控制器

+   Spring MVC 1-0-1

+   about / Spring MVC 1-0-1

+   reference link / Spring MVC 1-0-1

+   Spring MVC 3.1 / 自 Spring MVC 3.1 以来的@RequestMapping 新支持类

+   Spring MVC 应用程序

+   creating / 你的第一个 Spring MVC 应用程序

+   setting up / 设置 Spring MVC 应用程序

+   project structure / Spring MVC 应用程序的项目结构

+   web.xml 文件 / 将 web.xml 文件 spring 化的 web 应用程序

+   web app, springifying / 将 web.xml 文件 spring 化的 web 应用程序

+   ApplicationContext 文件 / Spring MVC 应用程序中的 ApplicationContext 文件

+   HomeController / HomeController-主屏幕的@Controller

+   home.jsp 文件 / home.jsp 文件-登陆界面

+   incoming requests, handling / 处理传入请求

+   Spring Reactor

+   URL / 其他值得注意的项目

+   about / 其他值得注意的项目

+   Spring 安全

+   users, adapting / 将用户和角色适应 Spring 安全, 如何做..., 它是如何工作的...

+   roles, adapting / 将用户和角色适应 Spring 安全, 如何做..., 它是如何工作的...

+   about / Spring 安全简介

+   ThreadLocal context holders / ThreadLocal 上下文持有者

+   interfaces / Noticeable Spring Security interfaces

+   Authentication interface / The Authentication interface

+   UserDetails interface / The UserDetails interface

+   UserDetailsManager interface / The UserDetailsManager interface

+   GrantedAuthority interface / The GrantedAuthority interface

+   Spring security, reference

+   about / Spring Security reference

+   technical overview / Technical overview

+   URL / Technical overview, Sample applications

+   sample applications / Sample applications

+   core services / Core services

+   Spring Security 4

+   reference link / Testing the authentication

+   Spring security authorities

+   about / Spring Security authorities

+   configuration attributes / Configuration attributes

+   Security Interceptor protecting secure objects / Configuration attributes

+   Spring security filter-chain

+   URL / SocialAuthenticationFilter

+   Spring security namespace

+   <http> component / The <http> component

+   Spring security filter-chain / The Spring Security filter-chain

+   <http> configuration / Our <http> configuration

+   BasicAuthenticationFilter / BasicAuthenticationFilter

+   with authenticationEntryPoint / With an authenticationEntryPoint

+   URL / In the Spring Security reference

+   Spring security OAuth project

+   URL / Implementing an OAuth2 authentication server

+   Spring security reference

+   URL / In the Spring Security reference, The Spring Security reference

+   Spring session

+   messages, securing with / Securing messages with Spring Session and Redis

+   Spring Social

+   about / Setting up Spring Social Twitter

+   URL / Setting up Spring Social Twitter

+   Spring social reference

+   URL / The Spring social ConnectController

+   Spring Social Twitter project

+   creating / Enough Hello Worlds, let's fetch tweets!

+   application, registering / Registering your application

+   setting up / Setting up Spring Social Twitter

+   Twitter, accessing / Accessing Twitter

+   Spring subprojects

+   about / Spring subprojects

+   URL / Spring subprojects

+   Spring Tool Suite (STS)

+   关于

+   URL

+   Spring 事务

+   定义

+   声明式事务管理

+   使用@Transactional 注解

+   程序化事务管理

+   Spring 验证器

+   使用 Spring 验证器

+   ValodationUtils 实用程序

+   国际化验证错误

+   Spring WebSockets

+   URL，参见

+   Spring WebSocket 支持

+   关于 Spring WebSocket 支持

+   一体化配置

+   消息处理程序，通过@MessageMapping 定义

+   Sql*类

+   使用 Sql*类定义 JDBC 操作

+   SSL

+   参考链接

+   关于 SSL

+   生成自签名证书

+   创建

+   为 http 和 https 通道创建

+   在受保护的服务器后面创建

+   权威性（SOA）

+   状态码

+   500 服务器错误，状态码和异常处理

+   405 方法不受支持，状态码和异常处理

+   404 未找到，状态码和异常处理

+   400 错误请求

+   200 OK，状态码和异常处理

+   使用 ResponseEntity

+   带异常的状态码

+   状态码

+   关于状态码和异常处理

+   StompMessageBrokerRelay

+   STOMP over SockJS

+   社交事件，使用 STOMP 通过 SockJS 进行流式传输

+   STOMP over WebSocket

+   关于/ Spring 4 中的 STOMP over WebSocket 和回退选项

+   流，Java 8

+   关于/ Java 8 流和 lambda

+   存根

+   关于/ 模拟和存根

+   创建，用于测试 bean/ 在测试时存根化我们的 bean

+   和模拟，选择/ 我应该使用模拟还是存根？

+   支持的 bean，DispatcherServlet

+   HandlerMapping/ 支持 DispatcherServlet 的 Bean 及其角色

+   HandlerAdapter/ 支持 DispatcherServlet 的 Bean 及其角色

+   HandlerExceptionResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   ViewResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   LocaleResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   LocaleContextResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   ThemeResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   MultipartResolver/ 支持 DispatcherServlet 的 Bean 及其角色

+   FlashMapManager/ 支持 DispatcherServlet 的 Bean 及其角色

+   Swagger

+   API，文档/ 准备就绪, 如何做..., 它是如何工作的...

+   API，暴露/ 如何做..., 它是如何工作的...

+   不同的工具/ 不同的工具，不同的标准

+   关于/ Swagger 文档

+   Swagger.io

+   URL/ Swagger.io

+   Swagger UI

+   关于/ Swagger UI

## T

+   @Test 注释

+   关于/ @Test 注释

+   预期和超时参数/ 预期和超时参数

+   @Transactional 注释

+   使用/ 使用@Transactional 注释

+   事务管理，启用/ 启用@Transactional 的事务管理

+   Taskify 应用程序

+   构建/ 构建 Taskify 应用程序

+   Taskify Ember 应用

+   构建/ 构建 Taskify Ember 应用

+   Taskify，设置为 Ember CLI 项目/ 将 Taskify 设置为 Ember CLI 项目

+   Ember Data，设置/ 设置 Ember Data

+   应用程序路由，配置/ 配置应用程序路由

+   主屏幕，构建/ 构建主屏幕

+   构建用户屏幕 / 构建用户屏幕

+   自定义助手，构建 / 构建自定义助手

+   操作处理程序，添加 / 添加操作处理程序

+   自定义组件，构建 / 构建自定义组件-模态窗口

+   使用{{modal-window}}构建 userEditModal / 使用{{modal-window}}构建 userEditModal

+   构建任务屏幕 / 构建任务屏幕

+   任务

+   使用 RabbitMQ 堆叠 / 使用 RabbitMQ 和 AMQP 堆叠和消费任务, 如何做…

+   使用 RabbitMQ 消费 / 使用 RabbitMQ 和 AMQP 堆叠和消费任务, 如何做…

+   发送方 / 发送方

+   消费者端 / 消费者端

+   客户端 / 客户端

+   消息架构概述 / 消息架构概述

+   可扩展模型 / 可扩展模型

+   模板方法

+   关于 / JdbcTemplate

+   术语，面向方面的编程（AOP）

+   方面 / AOP 概念和术语

+   连接点 / AOP 概念和术语

+   建议 / AOP 概念和术语

+   切入点 / AOP 概念和术语

+   目标对象 / AOP 概念和术语

+   编织 / AOP 概念和术语

+   介绍 / AOP 概念和术语

+   测试驱动开发（TDD） / 使用 Spring 进行测试

+   测试驱动开发（TTD）

+   关于 / 测试驱动开发

+   测试框架

+   关于 / 介绍 Ember.js

+   测试支持，Spring

+   模拟对象 / 模拟对象

+   单元和集成测试工具 / 单元和集成测试工具

+   th*each 标签

+   关于 / 访问 Twitter

+   Spring 第三方依赖

+   Spring 框架依赖模型 / Spring 框架依赖模型

+   Spring MVC 依赖 / Spring MVC 依赖

+   使用 Maven 属性 / 使用 Maven 属性

+   第三方 OAuth2 方案

+   使用第三方 OAuth2 方案进行身份验证 / 使用第三方 OAuth2 方案进行身份验证, 如何做…, 它是如何工作的…

+   应用程序角度 / 从应用程序角度

+   Yahoo!观点 / 从 Yahoo!的观点

+   OAuth2 显式授权流程 / OAuth2 显式授权流程

+   刷新令牌和访问令牌 / 刷新令牌和访问令牌

+   Spring 社交 / Spring 社交-角色和关键功能

+   社交连接持久性 / 社交连接持久性

+   特定于提供程序的配置 / 特定于提供程序的配置

+   Thymeleaf

+   关于 / 解析 Thymeleaf 视图, 使用 Thymeleaf

+   视图，解析 / 解析 Thymeleaf 视图

+   使用 / 使用 Thymeleaf

+   参考链接 / 使用 Thymeleaf, Thymeleaf 安全标签

+   页面，添加 / 我们的第一个页面

+   thymeleaf 安全标签

+   使用 / Thymeleaf 安全标签

+   Tomcat（7+）

+   参考链接 / 全局与本地事务

+   Tomcat 8

+   Eclipse，配置 / 准备就绪, 如何做...

+   URL / 如何做...

+   Eclipse，集成 / Eclipse 中的 Tomcat 8

+   Tomcat 连接器

+   关于 / Tomcat 连接器

+   HTTP 连接器 / HTTP 连接器

+   AJP 连接器 / AJP 连接器

+   URL / 还有更多...

+   工具

+   关于 / 合适的工具

+   JUnit / 合适的工具

+   AssertJ / 合适的工具

+   Mockito / 合适的工具

+   DbUnit / 合适的工具

+   Spock / 合适的工具

+   交易

+   关于 / Spring 事务支持

+   事务属性

+   定义 / Spring 事务基础

+   事务管理

+   关于 / 事务管理

+   构建 / 简化的方法

+   ACID 属性 / ACID 属性

+   全局事务，本地事务 / 全局与本地事务

+   推特

+   URL / 注册您的应用程序, Twitter 身份验证

+   Twitter 身份验证

+   设置 / Twitter 身份验证

+   社交身份验证，设置 / 设置社交身份验证

+   编码 / 解释

+   Typescript

+   关于 / 未来

+   URL / 未来

## U

+   UI 行为

+   处理，使用的组件 / 使用组件处理 UI 行为

+   ToggleButton 组件，逐步构建 / 逐步构建 ToggleButton 组件

+   使用 Handlebars 构建 UI 模板

+   关于 / 使用 Handlebars 构建 UI 模板

+   Handlebars 助手 / Handlebars 助手

+   数据绑定，带输入助手 / 带输入助手的数据绑定

+   控制流助手，在 Handlebars 中使用 / 在 Handlebars 中使用控制流助手

+   事件助手，使用 / 使用事件助手

+   统一表达式语言（UEL） / Spring 表达式语言

+   单元测试

+   关于 / 我应该如何测试我的代码？, 单元测试

+   工具 / 工作的正确工具

+   编写 / 我们的第一个单元测试

+   REST 控制器 / 对 REST 控制器进行单元测试

+   使用 Spock / 使用 Spock 进行单元测试

+   URI 模板模式

+   关于 / URI 模板模式

+   Ant 样式路径模式 / Ant 样式路径模式

+   路径模式比较 / 路径模式比较

+   ViewResolvers / ViewResolvers

+   URL 映射

+   带矩阵变量 / 带矩阵变量的 URL 映射

+   UserDetails 接口

+   关于 / UserDetails 接口

+   认证提供者 / 认证提供者

+   UserDetailsManager 接口

+   关于 / UserDetailsManager 接口

+   用户体验范式

+   关于 / 用户体验范式

+   用户管理 API

+   关于 / 用户管理 API

+   用户

+   预调用处理 / 预调用处理

+   AccessDecisionManager 接口 / AccessDecisionManager

+   调用处理 / 调用处理后

+   基于表达式的访问控制 / 基于表达式的访问控制

+   Web 安全表达式 / Web 安全表达式

+   方法安全表达式 / 方法安全表达式

+   @PreAuthorize，用于访问控制 / 使用@PreAuthorize 和@PostAuthorize 进行访问控制

+   @PostAuthorize，用于访问控制 / 使用@PreAuthorize 和@PostAuthorize 进行访问控制

+   集合过滤，使用@PreFilter / 使用@PreFilter 和@PostFilter 过滤集合

+   使用@PostFilter 进行集合过滤 / 使用@PreFilter 和@PostFilter 进行集合过滤

+   JSR-250 / JSR-250 和传统方法安全

## V

+   验证命令 / 验证

+   验证，个人资料页面

+   添加 / 验证

+   参考链接 / 验证

+   自定义验证消息 / 自定义验证消息

+   定义自定义注释 / 自定义验证的自定义注释

+   ValidationUnits 实用程序

+   URL / ValidationUtils

+   验证器

+   参考链接 / 客户端验证

+   ViewResolver

+   用于配置回退控制器 / 使用 ViewResolver 配置回退控制器, 如何做..., 它是如何工作的...

+   视图解析器

+   AbstractCachingViewResolver / 解析视图

+   XmlViewResolver / 解析视图

+   ResourceBundleViewResolver / 解析视图

+   基于 URL 的视图解析器/ 解析视图

+   InternalResourceViewResolver / 解析视图

+   VelocityViewResolver / 解析视图

+   FreeMarkerViewResolver / 解析视图

+   JasperReportsViewResolver / 解析视图

+   TilesViewResolver / 解析视图

+   视图

+   使用 / 使用视图

+   解析 / 解析视图

+   JSP 视图，解析 / 解析 JSP 视图

+   在 JSP 页面中绑定模型属性 / 使用 JSTL 在 JSP 页面中绑定模型属性

+   视图技术，Spring MVC / 更多视图技术

## W

+   web.xml 文件

+   参考链接 / 还有更多...

+   Web 应用程序

+   Dispatcher Servlet / DispatcherServlet

+   显示数据 / 将数据传递给视图

+   部署到 Pivotal Web Services（PWS） / 将您的 Web 应用程序部署到 Pivotal Web Services

+   安装 Cloud Foundry CLI 工具 / 安装 Cloud Foundry CLI 工具

+   组装 / 组装应用程序

+   激活 Redis / 激活 Redis

+   在 Heroku 上部署 / 将您的 Web 应用程序部署到 Heroku

+   在 Heroku 上设置 / 设置应用程序

+   在 Heroku 上执行 / 运行您的应用程序

+   改进 / 改进您的应用程序

+   WebApplicationObjectSupport

+   URL/ WebContentGenerator 提供的更多功能

+   Web 存档（war）

+   关于/ 准备就绪

+   Web 缓存

+   URL/ Web 缓存

+   WebContentGenerator

+   关于/ WebContentGenerator 提供的更多功能

+   WebContentInterceptor

+   定义/ 定义通用的 WebContentInterceptor, 如何做..., 它是如何工作的...

+   控制器/ 控制器的常见行为

+   会话，需要/ 需要会话

+   会话，同步/ 同步会话

+   缓存头管理/ 缓存头管理

+   HTTP 方法支持/ HTTP 方法支持

+   高级拦截器/ 高级拦截器

+   请求生命周期/ 请求生命周期

+   WebJars

+   用于材料设计/ 使用 WebJars 进行材料设计

+   布局，使用/ 使用布局

+   使用导航/ 导航

+   TweetController，使用/ 检查点

+   Web 资源

+   关于/ Web 资源

+   目标运行环境/ 目标运行环境

+   Spring Web 应用程序上下文/ Spring Web 应用程序上下文

+   插件/ 插件

+   Web 服务

+   URL/ setMessageConverters

+   Web Servlet 支持/ Web Servlet 支持

+   WebSocket

+   关于/ WebSockets

+   使用/ WebSockets

+   参考链接/ WebSockets

+   WebSocket 应用程序

+   消息，广播给单个用户/ 在 WebSocket 应用程序中向单个用户广播消息

+   WebSockets

+   关于/ WebSockets 简介

+   URL/ WebSockets 简介

+   生命周期/ WebSocket 生命周期

+   URI 方案/ 两个专用 URI 方案

+   Web 结构

+   关于/ 安装 Spring，Spring MVC 和 Web 结构

+   创建/ 准备就绪, 如何做..., 它是如何工作的...

+   Web 工具平台（WTP）插件

+   关于/ Eclipse 中的 Tomcat 8

+   工作者/ 工作者

## X

+   XML

+   生成/ 生成 XML

+   XML 编组，支持

+   关于/ 支持 XML 编组

+   XStream 编组器/ XStream 编组器

+   XML 解析器

+   JAXB2 实现，使用为 / 使用 JAXB2 实现作为 XML 解析器

+   基于 XML 模式的 AOP

+   关于 / 基于 XML 模式的 AOP

+   XStream

+   URL / XStream 编组器

+   X Stream 转换器

+   URL / XStream 转换器

## Y

+   Yahoo! API

+   URL / 另请参阅

+   Yahoo!财务股票代码 / 另请参阅

## Z

+   zipcloud-core

+   关于 / 准备工作

+   zipcloud-parent

+   关于 / 准备工作
