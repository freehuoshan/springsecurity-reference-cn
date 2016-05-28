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


