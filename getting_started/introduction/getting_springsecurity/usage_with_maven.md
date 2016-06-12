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
    













