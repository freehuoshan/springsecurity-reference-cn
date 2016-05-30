# 第二部分  入门

The later parts of this guide provide an in-depth discussion of the framework architecture and implementation classes, which you need to understand if you want to do any serious customization. In this part, we’ll introduce Spring Security 4.0, give a brief overview of the project’s history and take a slightly gentler look at how to get started using the framework. In particular, we’ll look at namespace configuration which provides a much simpler way of securing your application compared to the traditional Spring bean approach where you have to wire up all the implementation classes individually.


在本指南后边有深入讨论框架的结构和实现，如果你想要深度定制Springsecurity 你需要了解它们。而在这个部分，我们将介绍Spring Security 4.0，简要介绍这个项目的历史，并采用一种循序渐进的方式说明如何开始使用Spring Security框架。我们会特别讲解其命名空间（namespace）配置的使用，因为相比传统的需要自己装配所有实现类的Spring Bean方法，它提供了一种更简单的方式来保护你应用的安全。

We’ll also take a look at the sample applications that are available. It’s worth trying to run these and experimenting with them a bit even before you read the later sections - you can dip back into them as your understanding of the framework increases. Please also check out the project website as it has useful information on building the project, plus links to articles, videos and tutorials.

我们也会介绍项目主页上提供的示例应用。在进行后续的阅读之前，先运行一下它们并进行一些实验是值得的，随着你对Spring Security框架了解的逐渐增加，你可以回过头来看看它们。同时，请持续关于这个项目的站点：[http://projects.spring.io/spring-security/](http://projects.spring.io/spring-security/), 上面有许多关于如何编译此项目的有用信息，包括文章、视频及教程。




