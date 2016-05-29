# 第一部分.  前言
---

Spring Security provides a comprehensive security solution for Java EE-based enterprise software applications. As you will discover as you venture through this reference guide, we have tried to provide you a useful and highly configurable security system.

*Spring Security*  为基于JavaEE的企业应用提供了全面的安全解决方案。通过这份指南你会发现，我们尝试为你提供一个可用的和高度可配置的安全系统

Security is an ever-moving target, and it’s important to pursue a comprehensive, system-wide approach. In security circles we encourage you to adopt "layers of security", so that each layer tries to be as secure as possible in its own right, with successive layers providing additional security.

一个软件需要什么样的安全各有不同，重要的是要有一个全面系统的方法。在安全邻域，我们强烈建议你采取“layers of security”(安全层),使每一层在它自己的权限范围内尽可能安全，连续层提供额外的安全。

The "tighter" the security of each layer, the more robust and safe your application will be

安全层越密集，你的应用也会更健壮更安全

At the bottom level you’ll need to deal with issues such as transport security and system identification, in order to mitigate man-in-the-middle attacks.

在最底层，你需要解决诸如传输的安全,系统识别等问题，以减少中间人的攻击
（注:中间人[维基百科](https://zh.wikipedia.org/wiki/%E4%B8%AD%E9%97%B4%E4%BA%BA%E6%94%BB%E5%87%BB)）

 Next you’ll generally utilise firewalls, perhaps with VPNs or IP security to ensure only authorised systems can attempt to connect.
 
 接下来，你通常会利用防火墙,也许使用VPN或ip安全确保只有被授权的系统能够链接。
 
  In corporate environments you may deploy a DMZ to separate public-facing servers from backend database and application servers. 
  
 在企业环境，你可以部署一个 DMZ（注:DWZ：[维基百科](https://zh.wikipedia.org/wiki/DMZ)） 将面向用户的服务器与后台数据库和应用服务器分割开。
 
 Your operating system will also play a critical part, addressing issues such as running processes as non-privileged users and maximising file system security
 
你的操作系统也是重要的一个环节，例如：运行的进程应该以非特权用户运行，并最大限度地提高文件系统的安全性问题

Hopefully somewhere along the way you’ll be trying to prevent denial of service and brute force attacks against the system.

希望在这个过程中你能够阻止一些非法请求和暴力攻击。

An intrusion detection system will also be especially useful for monitoring and responding to attacks, with such systems able to take protective action such as blocking offending TCP/IP addresses in real-time

一个用于检测和响应攻击的入侵检测系统是非常有用的，例如：能够实时的采取动作阻断该TCP/IP.

 Moving to the higher layers, your Java Virtual Machine will hopefully be configured to minimize the permissions granted to different Java types, and then your application will add its own problem domain-specific security configuration.
 
 说完最底层，再看上层，Jvm能够为不同的java类型授予不同权限，你的应用程序能够增加它自己的特定领域安全配置
 
 Spring Security makes this latter area - application security - much easier.
 
 
 SpringSecurity  使得后一领域--应用安全--更简单
 
 Of course, you will need to properly address all security layers mentioned above, together with managerial factors that encompass every layer. A non-exhaustive list of such managerial factors would include security bulletin monitoring, patching, personnel vetting, audits, change control, engineering management systems, data backup, disaster recovery, performance benchmarking, load monitoring, centralised logging, incident response procedures etc
 
 当然，你需要处理好以上提到的所有安全层，以及每一层的管理要素。这样的管理因素大体包括安全公告监测，补丁，人事审查，审计，变更控制，工程管理系统，数据备份，灾难恢复，性能基准测试，负载监控，集中式日志记录，事件响应程序等
 
 With Spring Security being focused on helping you with the enterprise application security layer, you will find that there are as many different requirements as there are business problem domains. A banking application has different needs from an ecommerce application. An ecommerce application has different needs from a corporate sales force automation tool. These custom requirements make application security interesting, challenging and rewarding.
 
 SpringSecurity 旨在企业应用安全层对你进行帮助，因为涉及到商业领域，所以有许多不同需求。比如：一个银行应用与一个电商应用在需求上由很大不同，电商应用和一个企业自动化销售工具的需求又有很大不同。这些定制化需求使得应用安全有趣，充满挑战性而且有回报。
 
 Please read Part II, “Getting Started”, in its entirety to begin with. This will introduce you to the framework and the namespace-based configuration system with which you can get up and running quite quickly. To get more of an understanding of how Spring Security works, and some of the classes you might need to use, you should then read Part III, “Architecture and Implementation”. 
 
 
 请阅读[第二部分 入门](http://wangxj.net/springsecurity-reference-cn/getting_started/index.html)这是整体的开始，这部分向你介绍了框架和基于命名空间的配置系统，你配置好应用很快的运行起来。想要了解springsecurity是如何工作的，或者你可能需要使用的一些类请阅读[第三部分  结构和实现](http://wangxj.net/springsecurity-reference-cn/architecture_implementation/index.html)
 
 The remaining parts of this guide are structured in a more traditional reference style, designed to be read on an as-required basis. We’d also recommend that you read up as much as possible on application security issues in general. Spring Security is not a panacea which will solve all security issues. It is important that the application is designed with security in mind from the start. Attempting to retrofit it is not a good idea. In particular, if you are building a web application, you should be aware of the many potential vulnerabilities such as cross-site scripting, request-forgery and session-hijacking which you should be taking into account from the start. 
 
 
 本指南的其余部分是更传统的引用样式结构，设计用于按需进行阅读。我们建议你尽可能多了解一些普遍安全问题。Spring Security不是万能的，不能解决所有安全问题。重要的是在应用设计开始之初就考虑到安全性。后期改造不是一个好的主意。特别是，如果你正在构建一个Web应用程序，你应该知道许多潜在的漏洞，比如：跨站脚本、请求伪造和会话劫持。这些你开始就应该考虑。
 
 The OWASP web site (http://www.owasp.org/) maintains a top ten list of web application vulnerabilities as well as a lot of useful reference information.
 
 这个网站 OWASP （[http://www.owasp.org/](http://www.owasp.org/)） 维护了一个10大网站应用漏洞列表和一些有用的参考信息。
 
 We hope that you find this reference guide useful, and we welcome your feedback and suggestions.

Finally, welcome to the Spring Security community.

我们希望这个参考手册对你来说比较有用，欢迎你的反馈和建议。

最后欢迎你来到[Spring Security](http://docs.spring.io/spring-security/site/docs/current/reference/htmlsingle/#community)社区。
  





