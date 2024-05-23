# 第十五章：迁移到 Spring Security 4.2。

在本书的最后一章中，我们将回顾与从 Spring Security 3 迁移到 Spring Security 4.2 的常见迁移问题有关的信息。我们将花更多的时间讨论 Spring Security 3 和 Spring Security 4 之间的差异，因为这是大多数用户将遇到的难题。这是由于从 Spring Security 3 更新到 Spring Security 4.2 包含大量的非被动重构。

在本章末尾，我们还将突出显示 Spring Security 4.2 中可以找到的一些新功能。然而，我们并没有明确涵盖从 Spring Security 3 到 Spring Security 4.2 的变化。这是因为通过解释 Spring Security 3 和 Spring Security 4 之间的差异，用户应该能够轻松地更新到 Spring Security 4.2，因为 Spring Security 4.2 的变化是被动的。

在本章中，我们将涵盖以下主题：

+   回顾 Spring Security 4.2 中的重要增强功能。

+   了解您现有 Spring 版本中所需的配置更改。

+   当将它们迁移到 Spring Security 4.2 时，回顾 Spring Security 3 应用程序。

+   说明 Spring Security 4 中重要类和包的整体移动情况。

+   突出显示 Spring Security 4.2 中的一些新功能。一旦完成了本章的复习，你将处于一个很好的位置，可以将从 Spring Security 3 迁移到 Spring Security 4.2 的现有应用程序。

+   从 Spring Security 3 迁移。

你可能正在计划将一个现有应用程序迁移到 Spring Security 4.2，或者你可能正在尝试为 Spring Security 3 应用程序添加功能，并在这本书的页面中寻找指导。我们将在本章中尝试解决你们的两个问题。

首先，我们将概述 Spring Security 3 和 4.2 之间的关键差异，包括功能和配置。其次，我们将提供一些关于映射配置或类名更改的指导。这将使你更好地能够将书中的示例从 Spring Security 4.2 回退到 Spring Security 3（适用的）。

一个非常重要的迁移注意事项是，Spring Security 3+ 强制要求迁移到 Spring Framework 4 和 Java 5 (1.5) 或更高版本。请注意，在许多情况下，迁移这些其他组件可能对您的应用程序的影响比 Spring Security 的升级要大！

# 引言。

随着应用程序的利用方式不断发展，Spring Security 也必须做出相应的更新。在重大发布版本中，Spring Security 团队抓住了机会，进行了一些非被动的更改，主要关注以下几点：

+   通过默认设置确保 Spring Security 更加安全([`www.owasp.org/index.php/Establish_secure_defaults`](https://www.owasp.org/index.php/Establish_secure_defaults))。

+   最小化信息泄露([`www.owasp.org/index.php/Information_Leakage`](https://www.owasp.org/index.php/Information_Leakage))。

+   移除已弃用的 API。

在 JIRA 中可以找到 3.x 和 4.x 之间非被动更改的完整列表：[`jira.spring.io/browse/SEC-2916?jql=project%20%3D%20SEC%20AND%20fixVersion%20in%20(4.0.0%2C%204.0.0.M1%2C%204.0.0.M2%2C%204.0.0.RC1%2C%204.0.0.RC2)%20AND%20labels%20%3D%20passivity`](https://jira.spring.io/browse/SEC-2916?jql=project%20%3D%20SEC%20AND%20fixVersion%20in%20(4.0.0%2C%204.0.0.M1%2C%204.0.0.M2%2C%204.0.0.RC1%2C%204.0.0.RC2)%20AND%20labels%20%3D%20passivity).

# 示例迁移

Spring Security 团队创建了一个示例项目，展示了从 3.x 迁移到 4.x 时的所有更改，并将在 GitHub 上提供该项目。

示例包括 XML 和 JavaConfig 示例，可以在[`github.com/spring-projects/spring-security-migrate-3-to-4/`](https://github.com/spring-projects/spring-security-migrate-3-to-4/)找到。

# 在 Spring Security 4.2 中的增强功能

在 Spring Security 4.2 中有很多值得注意的更改，此版本还带来了对 Spring Framework 5 的早期支持。你可以找到 4.2.0.M1、4.2.0.RC1 和 4.2.0.RELEASE 的更改日志，涵盖了超过 80 个问题。社区贡献了绝大多数这些功能。

在 Spring Security 4.2 中进行了重大改进，自 Spring Security 3 以来，包括以下特性和它们的支持号码：

# 网络改进：

以下项目与 Spring Security 与基于 Web 的应用程序的交互相关：

+   **#3812**: Jackson 支持

+   **#4116**: 引用策略

+   **#3938**: 添加 HTTP 响应分割预防

+   **#3949**: 为`@AuthenticationPrincipal`添加了 bean 引用支持

+   **#3978**: 支持使用新添加的`RequestAttributeAuthenticationFilter`的 Standford WebAuth 和 Shibboleth。

+   **#4076**: 文档代理服务器配置

+   **#3795**: `ConcurrentSessionFilter`支持`InvalidSessionStrategy`

+   **#3904**: 添加`CompositeLogoutHandler`

# Spring Security 配置改进：

以下项目与 Spring Security 的配置相关：

+   **#3956**: 默认角色前缀的集中配置。详情请看问题

+   **#4102**: 在`WebSecurityConfigurerAdapter`中自定义默认配置

+   **#3899**: `concurrency-control@max-sessions`支持无限会话。

+   **#4097**: `intercept-url@request-matcher-ref`为 XML 命名空间添加了更强大的请求匹配支持

+   **#3990**: 支持从 Map（如 YML）构建`RoleHierarchy`。

+   **#4062**: 自定义`cookiePath`到`CookieCsrfTokenRepository`。

+   **#3794**: 允许在`SessionManagementConfigurer`上配置`InvalidSessionStrategy`

+   **#4020**: 修复`defaultMethodExpressionHandler`暴露的 beans 可以防止方法安全

# 在 Spring Security 4.x 中的其他更改

以下项目是一些值得注意的其他更改，其中许多可能会影响升级到 Spring Security 4.x：

+   **#4080**: Spring 5

+   #4095 - 添加`UserBuilder`

+   **#4018**：在`csrf()`被调用后进行修复，未来的`MockMvc`调用使用原始的`CsrfTokenRepository`

+   **常规依赖版本更新**

请注意，列出的数字指的是 GitHub 的 pull 请求或问题。

其他更微小的变化，包括代码库和框架配置的整体重构和清理，使整体结构和使用更具意义。Spring Security 的作者在登录和 URL 重定向等领域增加了可扩展性，尤其是之前不存在扩展性的地方。

如果你已经在 Spring Security 3 环境中工作，如果你没有推动框架的边界，可能不会找到升级的强烈理由。然而，如果你在 Spring Security 3 的可扩展点、代码结构或可配置性方面发现了局限性，那么你会欢迎我们在本章剩余部分详细讨论的许多小变化。

# **Spring Security 4 中的配置更改**

Spring Security 4 中的许多变化将在基于 XML 的配置的命名空间风格中可见。本章将主要覆盖基于 Java 的配置，但也会注意一些值得注意的基于 XML 的变化。尽管本章无法详细涵盖所有的小变化，但我们将尝试涵盖那些在您迁移到 Spring Security 4 时最可能影响您的变化。

# **废弃内容**

在 Spring Security 4 中移除了一大批废弃内容，以清理混乱。

以下是对 XML 和 JavaConfig 废弃内容的最终提交，其中包含 177 个更改文件，新增 537 处，删除 5023 处：[`github.com/spring-projects/spring-security/commit/6e204fff72b80196a83245cbc3bd0cd401feda00`](https://github.com/spring-projects/spring-security/commit/6e204fff72b80196a83245cbc3bd0cd401feda00)。

如果你使用 XML 命名空间或基于 Java 的配置，在许多情况下，你会避免废弃问题。如果你（或你使用的非 Spring 库）没有直接使用 API，那么你将不会受到影响。你可以很容易地在你的工作区中搜索这些列出的废弃内容。

# **Spring Security 核心模块的废弃内容**

本节描述了`spring-security-core`模块中所有的废弃 API。

# **org.springframework.security.access.SecurityConfig**

`SecurityConfig.createSingleAttributeList(String)`接口已被`SecurityConfig.createList(String¦ )`取代。这意味着如果你有这样的内容：

[PRE0]

它需要用以下代码替换：

[PRE1]

# **UserDetailsServiceWrapper**

`UserDetailsServiceWrapper`已被`RoleHierarchyAuthoritiesMapper`取代。例如，你可能有这样的内容：

[PRE2]

它需要被替换成类似这样的内容：

[PRE3]

# **UserDetailsWrapper**

`UserDetailsWrapper`因使用`RoleHierarchyAuthoritiesMapper`而被废弃。通常用户不会直接使用`UserDetailsWrapper`类。然而，如果他们这样做，他们可以使用`RoleHierarchyAuthoritiesMapper`，例如，下面代码可能存在：

[PRE4]

如果如此，则需要用以下代码片段替换：

[PRE5]

# 抽象访问决策管理器

`AbstractAccessDecisionManager`的默认构造函数以及`setDecisionVoters`方法已被废弃。自然而然，这影响了`AffirmativeBased`、`ConsensusBased`和`UnanimousBased`子类。例如，您可能使用以下代码片段：

[PRE6]

如果如此，它需要更改为以下代码片段：

[PRE7]

# 认证异常

在`AuthenticationException`中接受`extraInformation`的构造函数已被移除，以防止意外泄露`UserDetails`对象。具体来说，我们移除了以下代码：

[PRE8]

这影响了子类`AccountStatusException`、`AccountExpiredException`、`BadCredentialsException`、`CredentialsExpiredException`、`DisabledException`、`LockedException`和`UsernameNotFoundException`。如果您使用这些构造函数中的任何一个，只需移除附加参数。例如，以下代码片段更改了：

[PRE9]

上述代码片段应更改为以下代码片段：

[PRE10]

# 匿名认证提供者

`AnonymousAuthenticationProvider`的默认构造函数和`setKey`方法因使用构造器注入而被废弃。例如，您可能有以下代码片段：

[PRE11]

上述代码片段应更改为以下代码：

[PRE12]

# 认证详情源实现类

`AuthenticationDetailsSourceImpl`类因编写自定义`AuthenticationDetailsSource`而被废弃。例如，您可能有以下内容：

[PRE13]

您应该直接实现`AuthenticationDetailsSource`类以返回`CustomSource`对象：

[PRE14]

# 认证提供者管理器

`ProviderManager`类移除了废弃的默认构造函数和相应的设置器方法，改为使用构造器注入。它还移除了`clearExtraInformation`属性，因为`AuthenticationException`异常已经移除了额外信息属性。

例如，您可能像以下内容一样：

[PRE15]

如果如此，上述代码应更改为以下代码：

[PRE16]

由于`AuthenticationException`异常已经移除了额外信息属性，因此移除了`clearExtraInformation`属性。对此没有替代方案。

# 记住我认证提供者

`RememberMeAuthenticationProvider`类移除了默认构造函数和`setKey`方法，改为使用构造器注入。例如，查看以下代码：

[PRE17]

上述代码片段应迁移至以下内容：

[PRE18]

# 授权实体实现类

`GrantedAuthorityImpl`已被`SimpleGrantedAuthority`所取代，或者实现你自己的`GrantAuthority`对象。例如：

[PRE19]

这应该替换为以下内容：

[PRE20]

# `InMemoryDaoImpl`

`InMemoryDaoImpl`已被`InMemoryUserDetailsManager`所取代。例如：

[PRE21]

这应该被替换为：

[PRE22]

# `spring-security-web`模块中的弃用

本节描述了`spring-security-web`模块中所有弃用的 API。

# `FilterChainProxy`

`FilterChainProxy`移除了`setFilterChainMap`方法，改为使用构造注入。例如，你可能有以下内容：

[PRE23]

它应该被替换为：

[PRE24]

`FilterChainProxy`也移除了`getFilterChainMap`，改为使用`getFilterChains`，例如：

[PRE25]

这应该替换为以下代码：

[PRE26]

# `ExceptionTranslationFilter`

`ExceptionTranslationFilter`的默认构造函数和`setAuthenticationEntryPoint`方法已被移除，改为使用构造注入：

[PRE27]

这可以用以下代码替换：

[PRE28]

# `AbstractAuthenticationProcessingFilter`

`AbstractAuthenticationProcessingFilter`类的`successfulAuthentication(HttpServletRequest,HttpServletResponse,Authentication)`方法已被移除。所以，你的应用程序可能重写了以下方法：

[PRE29]

应替换为以下代码：

[PRE30]

# `AnonymousAuthenticationFilter`

`AnonymousAuthenticationFilter`类的默认构造函数和`setKey`、`setPrincipal`方法已被移除，改为使用构造注入。例如，看看以下代码片段：

[PRE31]

这应该替换为以下代码：

[PRE32]

# `LoginUrlAuthenticationEntryPoint`

`LoginUrlAuthenticationEntryPoint`的默认构造函数和`setLoginFormUrl`方法已被移除，改为使用构造注入。例如：

[PRE33]

这应该替换为以下代码：

[PRE34]

# `PreAuthenticatedGrantedAuthoritiesUserDetailsService`

`PreAuthenticatedGrantedAuthoritiesUserDetailsService`接口移除了`createuserDetails`，改为`createUserDetails`。

新方法在案例中进行了更正（`U`而不是`u`）。

这意味着如果你有一个`PreAuthenticatedGrantedAuthoritiesUserDetailsService`类的子类，它重写了`createuserDetails`，例如`SubclassPreAuthenticatedGrantedAuthoritiesUserDetailsService`扩展了`PreAuthenticatedGrantedAuthoritiesUserDetailsService`。

[PRE35]

它应该更改为重写`createUserDetails`：

[PRE36]

# `AbstractRememberMeServices`

`AbstractRememberMeServices`及其子类`PersistentTokenBasedRememberMeServices`和`TokenBasedRememberMeServices`移除了默认构造函数、`setKey`和`setUserDetailsService`方法，改为使用构造注入。

# `PersistentTokenBasedRememberMeServices`

对`AbstractRememberMeServices`及其子类`PreAuthenticatedGrantedAuthoritiesUserDetailsService`的更改使得用法类似于以下示例：

[PRE37]

但实现用法现在应替换为：

[PRE38]

# `RememberMeAuthenticationFilter`

`RememberMeAuthenticationFilter`的默认构造函数、`setAuthenticationManager`和`setRememberMeServices`方法已被移除，改为使用构造器注入，如下：

[PRE39]

这应该替换为：

[PRE40]

# TokenBasedRememberMeServices

`AbstractRememberMeServices`及其子类`PersistentTokenBasedRememberMeServices`和`TokenBasedRememberMeServices`移除了默认构造函数、`setKey`和`setUserDetailsService`方法，改为使用构造器注入。例如：

[PRE41]

这应该替换为：

[PRE42]

# ConcurrentSessionControlStrategy

`ConcurrentSessionControlStrategy`已被替换为`ConcurrentSessionControlAuthenticationStrategy`。以前，`ConcurrentSessionControlStrategy`无法与`SessionFixationProtectionStrategy`解耦。现在它完全解耦了。例如：

[PRE43]

这可以替换为：

[PRE44]

# SessionFixationProtectionStrategy

`SessionFixationProtectionStrategy`移除了`setRetainedAttributes`方法，改为让用户继承`SessionFixationProtectionStrategy`并重写`extractAttributes`方法。查看以下代码：

[PRE45]

它应该替换为：

[PRE46]

# BasicAuthenticationFilter

`BasicAuthenticationFilter`的默认构造函数、`setAuthenticationManager`和`setRememberMeServices`方法已被移除，改为使用构造器注入：

[PRE47]

这应该替换为：

[PRE48]

使用这个构造函数会自动将`ignoreFalure`设置为`true`。

# SecurityContextPersistenceFilter

`SecurityContextPersistenceFilter`移除了`setSecurityContextRepository`，改为使用构造器注入。例如：

[PRE49]

这应该替换为：

[PRE50]

# RequestCacheAwareFilter

`RequestCacheAwareFilter`移除了`setRequestCache`，改为使用构造器注入。例如：

[PRE51]

这应该替换为：

[PRE52]

# ConcurrentSessionFilter

`ConcurrentSessionFilter`移除了默认构造函数、`setExpiredUrl`和`setSessionRegistry`方法，改为使用构造器注入。例如：

[PRE53]

这应该替换为：

[PRE54]

# SessionManagementFilter

`SessionManagementFilter`移除了`setSessionAuthenticationStrategy`方法，改为使用构造器注入。例如：

[PRE55]

这应该替换为：

[PRE56]

# RequestMatcher

`RequestMatcher`及其实现已从`org.springframework.security.web.util`包移动到`org.springframework.security.web.util.matcher`。具体如下：

[PRE57]

# WebSecurityExpressionHandler

`WebSecurityExpressionHandler`已被移除，改为使用`SecurityExpressionHandler<FilterInvocation>`。

这意味着你可能有以下内容：

[PRE58]

这需要更新为：

[PRE59]

你可以这样实现`WebSecurityExpressionHandler`：

[PRE60]

然后它必须更新为：

[PRE61]

# @AuthenticationPrincipal

`org.springframework.security.web.bind.annotation.AuthenticationPrincipal`已被弃用，改为`org.springframework.security.core.annotation.AuthenticationPrincipal`。例如：

[PRE62]

这应该替换为：

[PRE63]

# 迁移默认过滤器 URL

许多 servlet 过滤器的默认 URL 被更改为帮助防止信息泄露。

有很多 URL 被更改，以下提交包含了 125 个更改的文件，共有 8,122 个增加和 395 个删除：[`github.com/spring-projects/spring-security/commit/c67ff42b8abe124b7956896c78e9aac896fd79d9`](https://github.com/spring-projects/spring-security/commit/c67ff42b8abe124b7956896c78e9aac896fd79d9)。

# JAAS

遗憾的是，我们没有篇幅讨论 Spring Security 的 JAAS 集成。然而，在 Spring Security 的示例中包含了一个 JAAS 样本应用程序，可以在[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#jaas-sample`](https://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#jaas-sample)找到。实际上，还有关于 JAAS 集成的优秀文档，可以在 Spring Security 的参考资料中找到，链接为[`docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#jaas`](https://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#jaas)。当查看 JAAS 参考文档时，你会注意到，从 Spring Security 4.2 开始，支持使用 JAAS 登录模块与任意的 JAAS 配置实现。Spring Security 4.2 还在`<http>`元素中添加了`jaas-api-provision`属性，确保了对于可能依赖于 JAAS 主题的应用程序，JAAS 主题被填充。

# 摘要

本章回顾了将现有 Spring Security 3 项目升级到 Spring Security 4.2 时您将发现的主要和小幅变化。在本章中，我们回顾了框架的主要增强功能，这些功能可能会促使进行升级。我们还检查了升级要求、依赖关系和常见的代码、配置更改，这些更改可能会在升级后阻止应用程序运行。我们还涵盖了 Spring Security 作者在代码库重构过程中进行的高级代码组织变化调查。

如果你是第一次阅读这一章节，我们希望你能回到书的其余部分，并使用这一章节作为指南，使你的 Spring Security 4.2 升级尽可能顺利地进行！
