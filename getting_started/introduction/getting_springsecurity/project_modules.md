##　 1.4.3　项目－模块


In Spring Security 3.0, the codebase has been sub-divided into separate jars which more clearly separate different functionaltiy areas and third-party dependencies. If you are using Maven to build your project, then these are the modules you will add to your pom.xml. Even if you’re not using Maven, we’d recommend that you consult the pom.xml files to get an idea of third-party dependencies and versions. Alternatively, a good idea is to examine the libraries that are included in the sample applications.

在　Spring Security3.0 版本，依据不同的功能模块和第三方依赖以jar包的方式分离开。如果你使用 maven 构建你的项目，可以在你的 pom.xml 文件中添加相应模块。即使你没有使用 maven 我们依然建议的参考 pom.xml 文件获取第三方依赖关系和版本信息。当然也可以参考示例应用中 lib 库。

### Core - spring-security-core.jar

Contains core authentication and access-contol classes and interfaces, remoting support and basic provisioning APIs. Required by any application which uses Spring Security. Supports standalone applications, remote clients, method (service layer) security and JDBC user provisioning. Contains the top-level packages:

包含心认证和访问控制的核心类和接口，远程支持和一些基本配置API.这个包是使用 Spring Security 必须要有的。 支持独立应用，远程客户端，方法（服务层）安全和使用JDBCD的配置。包含了一些顶层包:


* `org.springframework.security.core`
* `org.springframework.security.access`
* `org.springframework.security.authentication`
* `org.springframework.security.provisioning`

### Remoting - spring-security-remoting.jar

Provides intergration with Spring Remoting. You don’t need this unless you are writing a remote client which uses Spring Remoting. The main package is 

提供了与 Spring Remoting 的集成。除非你要使用 Spring Remoting 写远程客户端，一般你不需要这个 jar 包。主要包是:

`org.springframework.security.remoting.`

### Web - spring-security-web.jar

Contains filters and related web-security infrastructure code. Anything with a servlet API dependency. You’ll need it if you require Spring Security web authentication services and URL-based access-control. The main package is org.springframework.security.web.

包含了一些 `Filter`过滤器和 `web安全` 相关的基础代码。依赖于 `Servlet` API 。如果需要 Spring Security 的 web 认证服务和基于 URL 的访问控制，你需要这个 jar 包.主要包含的包有:

`org.springframework.security.web`

### Config - spring-security-config.jar

Contains the security namespace parsing code & Java configuration code. You need it if you are using the Spring Security XML namespace for configuration or Spring Security’s Java Configuration support. The main package is org.springframework.security.config. None of the classes are intended for direct use in an application.

包含了安全命名空间的解析代码和 java 配置代码，如果你需要使用 Spring Security xml 命名空间配置或 Spring Security 的 java 配置支持，你需要使用这个jar包。主要包是:`org.springframework.security.config. ` 应用不会直接使用这个 jar 包中的类。


### LDAP - spring-security-ldap.jar

LDAP authentication and provisioning code. Required if you need to use LDAP authentication or manage LDAP user entries. The top-level package is org.springframework.security.ldap.

LDAP 认证和配置代码。如果你要使用LDAP 认证或者使用LDAP 管理用户.顶层包是：` org.springframework.security.ldap.`

### ACL - spring-security-acl.jar

Specialized domain object ACL implementation. Used to apply security to specific domain object instances within your application. The top-level package is org.springframework.security.acls.

特定域对象 ACL 实现。对你应用内的特定域对象实现安全保护。顶层包是：`org.springframework.security.acls.`

### CAS - spring-security-cas.jar

Spring Security’s CAS client integration. If you want to use Spring Security web authentication with a CAS single sign-on server. The top-level package is org.springframework.security.cas.

Spring Security 的 CAS 客户端集成。 如果你想要 Spring Security 通过 CAS  单点登录服务器实现 Web 认证。顶层包是: `org.springframework.security.cas.`

### OpenID - spring-security-openid.jar

OpenID web authentication support. Used to authenticate users against an external OpenID server. org.springframework.security.openid. Requires OpenID4Java.

OpenID web 认证支持。通过外部 OpenID 服务器认证用户。 `org.springframework.security.openid`  要求  OpenID4Java.

