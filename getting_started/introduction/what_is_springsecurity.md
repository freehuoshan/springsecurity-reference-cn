### 1.1 什么是Spring Security

Spring Security provides comprehensive security services for Java EE-based enterprise software applications. There is a particular emphasis on supporting projects built using The Spring Framework, which is the leading Java EE solution for enterprise software development. If you’re not using Spring for developing enterprise applications, we warmly encourage you to take a closer look at it. Some familiarity with Spring - and in particular dependency injection principles - will help you get up to speed with Spring Security more easily.

SpringSecurity为基于JAVAEE的企业应用提供了全面的安全服务。对于企业软件的开发，spring框架是领先的JAVAEE解决方案。如果你还没有使用Spring开发企业应用，那我们强烈建议你深入了解它。熟悉Spring,特别是依赖注入，将会使你使用SpringSecurity更快速容易。

People use Spring Security for many reasons, but most are drawn to the project after finding the security features of Java EE’s Servlet Specification or EJB Specification lack the depth required for typical enterprise application scenarios. Whilst mentioning these standards, it’s important to recognise that they are not portable at a WAR or EAR level. Therefore, if you switch server environments, it is typically a lot of work to reconfigure your application’s security in the new target environment. Using Spring Security overcomes these problems, and also brings you dozens of other useful, customisable security features.

人们使用Spring Security的原因有很多，但大部分都是在发现J2EE的Servlet规范亦或EJB规范缺少对典型企业级应用场景中更深层需求的支持后才转向Spring Security的。这里提到的Servlet及EJB标准都是不支持WAR或EAR级别的移植性的，因此，如果你更换服务器环境，那么你将需要在新的目标环境中重新配置你的应用安全方案，这将浪费你大量的时间。而使用Spring Security可以克服这些问题，同时，还能给你提供一系列有用的，可定制的安全特色。

As you probably know two major areas of application security are "authentication" and "authorization" (or "access-control"). These are the two main areas that Spring Security targets. "Authentication" is the process of establishing a principal is who they claim to be (a "principal" generally means a user, device or some other system which can perform an action in your application)."Authorization" refers to the process of deciding whether a principal is allowed to perform an action within your application. To arrive at the point where an authorization decision is needed, the identity of the principal has already been established by the authentication process. These concepts are common, and not at all specific to Spring Security.

你也许知道应用安全的两个主要领域是“认证”与“授权”。Spring Security的目标有两个领域：(1) "认证"是建立一个安全“主体”（principal，一个“主体”通常代表一个用户，设备或者是其它可以在你的应用中执行操作的相关系统）的过程；（2）“授权”是指决定是否允许一个“主体”在你的应用中执行某个操作的过程。首先需要通过“认证”过程为“主体”建立其标识，之后才能据此执行“授权”操作，这些概念并非Spring Security特有，而是安全领域中完全通用的。

At an authentication level, Spring Security supports a wide range of authentication models. Most of these authentication models are either provided by third parties, or are developed by relevant standards bodies such as the Internet Engineering Task Force. In addition, Spring Security provides its own set of authentication features. 

在认证层，Spring Security支持了大量的认证模型。这些模型大多由第三方组织提供，亦或是由相关的标准组织，如Internet Engineering Task Force开发，此外，Spring Security提供了它自己的认证特色。

Specifically, Spring Security currently supports authentication integration with all of these technologies:

目前，Spring Security的认证可以与以下技术集成:


HTTP BASIC authentication headers (an IETF RFC-based standard)

HTTP Digest authentication headers (an IETF RFC-based standard)

HTTP X.509 client certificate exchange (an IETF RFC-based standard)

LDAP (a very common approach to cross-platform authentication needs, especially in large environments)

Form-based authentication (for simple user interface needs)

OpenID authentication

Authentication based on pre-established request headers (such as Computer Associates Siteminder)

JA-SIG Central Authentication Service (otherwise known as CAS, which is a popular open source single sign-on system)

Transparent authentication context propagation for Remote Method Invocation (RMI) and HttpInvoker (a Spring remoting protocol)

Automatic "remember-me" authentication (so you can tick a box to avoid re-authentication for a predetermined period of time)

Anonymous authentication (allowing every unauthenticated call to automatically assume a particular security identity)

Run-as authentication (which is useful if one call should proceed with a different security identity)

Java Authentication and Authorization Service (JAAS)

JEE container autentication (so you can still use Container Managed Authentication if desired)

Kerberos

Java Open Source Single Sign On (JOSSO) *

OpenNMS Network Management Platform *

AppFuse *

AndroMDA *

Mule ESB *

Direct Web Request (DWR) *

Grails *

Tapestry *

JTrac *

Jasypt *

Roller *

Elastic Path *

Atlassian Crowd *

Your own authentication systems (see below)

(* Denotes provided by a third party

带有星号的是第三方提供的

Many independent software vendors (ISVs) adopt Spring Security because of this significant choice of flexible authentication models. Doing so allows them to quickly integrate their solutions with whatever their end clients need, without undertaking a lot of engineering or requiring the client to change their environment. If none of the above authentication mechanisms suit your needs, Spring Security is an open platform and it is quite simple to write your own authentication mechanism. Many corporate users of Spring Security need to integrate with "legacy" systems that don’t follow any particular security standards, and Spring Security is happy to "play nicely" with such systems.

许多独立软件厂商（ISVs）因其灵活的认证模型支持而采用Spring Security。使用Spring Security，不管他们的用户需要什么认证方法，他们都可以快速将它们的解决方案整合到其中，而无需承担太多的工程任务亦或要求用户更改他们的应用环境。如果上面提及的这么多认证机制都不符合你的需求，没关系！！Spring Security是一个开放的平台，你很容易就可以编写自己的认证机制。有许多Spring Security的企业用户需要与“遗留系统”进行整合，然而“遗留系统”并不遵循任何特定的安全标准，对于这种情况，Spring Security也乐于与这些系统一起工作。


Irrespective of the authentication mechanism, Spring Security provides a deep set of authorization capabilities. There are three main areas of interest - authorizing web requests, authorizing whether methods can be invoked, and authorizing access to individual domain object instances. To help you understand the differences, consider the authorization capabilities found in the Servlet Specification web pattern security, EJB Container Managed Security and file system security respectively. Spring Security provides deep capabilities in all of these important areas, which we’ll explore later in this reference guide.

除了认证机制外，Spring Security还提供了一系列的授权能力。主要包含三个领域：（1）授权web请求；（2）授权是否允许方法调用；（3）授权对某个领域对象实例的存取。为了帮助你更好的明白它们的不同，请考虑一下下面的授权能力：Servlet规范中的web模式安全，EJB容器管理安全及文件系统安全。Spring Security在所有这些重要的领域提供了相应的能力，我们将在本参考指南的后续部分进行讨论。








