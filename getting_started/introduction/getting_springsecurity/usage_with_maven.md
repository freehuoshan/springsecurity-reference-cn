## 1.4.1　使用ＭＡＶＥＮ

通过　maven　获取　Spring Security　最简洁的依赖通常看起来像下面这样配置:

**　pom.xml **

        <dependencies>
        <!-- ... other dependency elements ... -->
        <dependency>
        	<groupId>org.springframework.security</groupId>
        	<artifactId>spring-security-web</artifactId>
        	<version>4.1.0.RELEASE</version>
        </dependency>
        <dependency>
        	<groupId>org.springframework.security</groupId>
        	<artifactId>spring-security-config</artifactId>
        	<version>4.1.0.RELEASE</version>
        </dependency>
        </dependencies>
        
If you are using additional features like LDAP, OpenID, etc. you will need to also include the appropriate Section 1.4.3, “Project Modules”.

如果你要使用额外的例如LDAP,OpenIＤ等功能，需要根据需要添加相应依赖

### Maven Repositories

All GA releases (i.e. versions ending in .RELEASE) are deployed to Maven Central, so no additional Maven repositories need to be declared in your pom.

If you are using a SNAPSHOT version, you will need to ensure you have the Spring Snapshot repository defined as shown below:

所有发布版本被发布到　maven 中央仓库，所以如果你没有配置，需要在你的　pom　文件中追加　maven　仓库配置。

如果你准备使用快照版本，需要在你的　pom　中添加下面的配置：

** pom.xml **

    <repositories>
    <!-- ... possibly other repository elements ... -->
    <repository>
    	<id>spring-snapshot</id>
    	<name>Spring Snapshot Repository</name>
    	<url>http://repo.spring.io/snapshot</url>
    </repository>
    </repositories>
   
If you are using a milestone or release candidate version, you will need to ensure you have the Spring Milestone repository defined as shown below:

如果你要使用里程碑版本或发布候选版本，需要在你的 pom 中添加如下配置:

** pom.xml ** 

    <repositories>
    <!-- ... possibly other repository elements ... -->
    <repository>
    	<id>spring-milestone</id>
    	<name>Spring Milestone Repository</name>
    	<url>http://repo.spring.io/milestone</url>
    </repository>
    </repositories>
  
### Spring Framework Bom  

Spring Security builds against Spring Framework 4.2.5.RELEASE, but should work with 4.0.x. The problem that many users will have is that Spring Security’s transitive dependencies resolve Spring Framework 4.2.5.RELEASE which can cause strange classpath problems.

One (tedious) way to circumvent this issue would be to include all the Spring Framework modules in a <dependencyManagement> section of your pom. An alternative approach is to include the spring-framework-bom within your <dependencyManagement> section of your pom.xml as shown below:

Spring Security针对的是　Spring　框架4.2.5ＲELEASE版本，但使用４.0以上的版本应该也是可以工作的。但是由于Ｓpring Security框架的传递性依赖的关系有时会出现一些奇怪的问题。

为了避免这样的问题，可以将所有 Spring　框架模块都配置到`<dependencyManagement>`中。一种有效的解决方式是添加　spring-framework-bom　模块到`<dependencyManagement>`中。就像下面这样:

** pom.xml **

    <dependencyManagement>
    	<dependencies>
    	<dependency>
    		<groupId>org.springframework</groupId>
    		<artifactId>spring-framework-bom</artifactId>
    		<version>4.2.5.RELEASE</version>
    		<type>pom</type>
    		<scope>import</scope>
    	</dependency>
    	</dependencies>
    </dependencyManagement>
    
This will ensure that all the transitive dependencies of Spring Security use the Spring 4.2.5.RELEASE modules.

这样可以确保所有传递依赖模块都是使用的Ｓｐｒｉｎｇ　４．２．５RELEAS版本

> This approach uses Maven’s "bill of materials" (BOM) concept and is only available in Maven 2.0.9+. For additional details about how dependencies are resolved refer to Maven’s Introduction to the Dependency Mechanism documentation.

>　这种解决方式只有maven　２．０．９＋版本才有效，更多关于ｍａｖｅｎ依赖的解决方案可以查看[Maven’s Introduction to the Dependency Mechanism documentation](http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)



















