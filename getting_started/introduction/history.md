# 1.2  历史
---

Spring Security began in late 2003 as "The Acegi Security System for Spring". A question was posed on the Spring Developers' mailing list asking whether there had been any consideration given to a Spring-based security implementation. At the time the Spring community was relatively small (especially compared with the size today!), and indeed Spring itself had only existed as a SourceForge project from early 2003. The response to the question was that it was a worthwhile area, although a lack of time currently prevented its exploration.

Spring Security始于2003年末，一开始叫“The Acegi Security System for Spring”。后来，有人在Spring的开发者邮件列表中提出了个问题：“是否有考虑过提供一个基于Spring的安全实现？”，在那个时候，Spring社区还相对小（特别是和今天相比），而Spring本身也是在2003年初才开始作为一个SourceForge项目存在。对于这个问题，回复是：”尽管现阶段还没有时间将它付诸实施，但这是一个很有价值的领域“。

With that in mind, a simple security implementation was built and not released. A few weeks later another member of the Spring community inquired about security, and at the time this code was offered to them. Several other requests followed, and by January 2004 around twenty people were using the code. These pioneering users were joined by others who suggested a SourceForge project was in order, which was duly established in March 2004.

考虑到这点，一个简单的安全实现被创建，但是没有发布。几个星期以后，Spring社区的其它成员问及了安全问题，此时，将安全实现的代码提供给了他们。陆续还有一些人来索取，到了2004年1月，已经大约有20个人在使用这个代码。这些志愿使用者中又加入了其它人，他们申请了一个SourceForge项目，并最终在2004年3月成立。

In those early days, the project didn’t have any of its own authentication modules. Container Managed Security was relied upon for the authentication process, with Acegi Security instead focusing on authorization. This was suitable at first, but as more and more users requested additional container support, the fundamental limitation of container-specific authentication realm interfaces became clear. There was also a related issue of adding new JARs to the container’s classpath, which was a common source of end user confusion and misconfiguration.

在早期，这个项目并没有任何它自己的认证模块。容器管理的安全是依赖于认证过程，与Acegi Security，转而专注于授权。最初这是合适的，但是随着越来越多的用户要求额外的容器支持，特定于容器的认证领域接口的基本限制变得越来越明显。例如：需要增加jar包到容器的classpath，这是用户错误配置的主要来源

Acegi Security-specific authentication services were subsequently introduced. Around a year later, Acegi Security became an official Spring Framework subproject. The 1.0.0 final release was published in May 2006 - after more than two and a half years of active use in numerous production software projects and many hundreds of improvements and community contributions.

Acegi安全规范认证服务随后被引入，大概一年以后，Acegi安全变成了一个官方的Spring框架的子项目。在超过2年半时间里，经过在大量生产软件项目中的积极使用及成百上千的修改、提高和社区贡献，其1.0.0最终版在2006年5月成功发布。

Acegi Security became an official Spring Portfolio project towards the end of 2007 and was rebranded as "Spring Security".

到了2007年末尾，Acegi称为官方Spring选集项目，并被更名为”Spring Security“。

Today Spring Security enjoys a strong and active open source community. There are thousands of messages about Spring Security on the support forums. There is an active core of developers who work on the code itself and an active community which also regularly share patches and support their peers.

现在，Spring Security拥有强大活跃的开源社区，在论坛上有关于Spring Security数以千
的信息支持。有活跃的核心开发人员，还有定期的共享补丁。

