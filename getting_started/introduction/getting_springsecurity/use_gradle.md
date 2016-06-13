## 1.4.2　Gradle

A minimal Spring Security Gradle set of dependencies typically looks like the following:

使用gradle配置Spring Security依赖，简洁的配置就像下面这样：

** build.gradle **

    dependencies {
    	compile 'org.springframework.security:spring-security-web:4.1.0.RELEASE'
    	compile 'org.springframework.security:spring-security-config:4.1.0.RELEASE'
    }
    
If you are using additional features like LDAP, OpenID, etc. you will need to also include the appropriate Section 1.4.3, “Project Modules”.

如果你要使用 LDAP,OpenID等额外功能，你需要添加相应依赖模块[Section 1.4.3, “Project Modules”.](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#modules)

### Gradle Repositories

All GA releases (i.e. versions ending in .RELEASE) are deployed to Maven Central, so using the mavenCentral() repository is sufficient for GA releases.

所有发布版本都被发布到了　Maven　中央仓库，所以使用 mavenCentral()　可以获取所有需要的模块

** build.gradle **

    repositories {
    	mavenCentral()
    }

If you are using a SNAPSHOT version, you will need to ensure you have the Spring Snapshot repository defined as shown below:

如果你要使用快照版本，确保已经配置了 Spring 快照仓库，就像下面这样:

** build.gradle **

    repositories {
    	maven { url 'https://repo.spring.io/snapshot' }
    }

If you are using a milestone or release candidate version, you will need to ensure you have the Spring Milestone repository defined as shown below:

如果你要使用里程碑版本，或发布候选版本，确保以及配置了　Spring　里程碑版本仓库，就像下面这样：

** build.gradle **

    repositories {
    	maven { url 'https://repo.spring.io/milestone' }
    }

### 使用 Spring4.0.x 和　Ｇradle

By default Gradle will use the newest version when resolving transitive versions. This means that often times no additional work is necessary when running Spring Security 4.1.0.RELEASE with Spring Framework 4.2.5.RELEASE. However, at times there can be issues that come up so it is best to mitigate this using Gradle’s ResolutionStrategy as shown below:

Gradle　在解决传递性依赖时默认使用最新版本，这意味着如果使用　Spring Security4.1.0ＲＥＬＥＡＳＥ和Spring 4.2.5 RELEASE不会由额外的问题发生可以成功运行。然而也有可能有时会发生一些奇怪的问题，所以最好的方式是使 Gradle　的[Gradle’s ResolutionStrategy](https://docs.gradle.org/current/dsl/org.gradle.api.artifacts.ResolutionStrategy.html),像下面这样:

** build.gradle **

    configurations.all {
    	resolutionStrategy.eachDependency { DependencyResolveDetails details ->
    		if (details.requested.group == 'org.springframework') {
    			details.useVersion '4.2.5.RELEASE'
    		}
    	}
    }

This will ensure that all the transitive dependencies of Spring Security use the Spring 4.2.5.RELEASE modules.

这可以确保　Spring Security　的传递依赖总是使用　Ｓpring 4.2.5　RELEASE　版本模块

> This example uses Gradle 1.9, but may need modifications to work in future versions of Gradle since this is an incubating feature within Gradle.

这个例子使用的　Gradle　１．９　版本，在将来的版本中使用可能需要做些修改。

