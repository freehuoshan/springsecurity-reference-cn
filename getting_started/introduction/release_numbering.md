# 1.3 版本号
---

It is useful to understand how Spring Security release numbers work, as it will help you identify the effort (or lack thereof) involved in migrating to future releases of the project. Each release uses a standard triplet of integers: MAJOR.MINOR.PATCH. The intent is that MAJOR versions are incompatible, large-scale upgrades of the API. MINOR versions should largely retain source and binary compatibility with older minor versions, thought there may be some design changes and incompatible updates. PATCH level should be perfectly compatible, forwards and backwards, with the possible exception of changes which are to fix bugs and defects.


我们需要明白Spring Security的版本号是如何工作的，因为它能帮助我们了解迁移到项目的新版本对我们有什么用处。每个版本使用一个标准的三元整数：MAJOR.MINOR.PATCH。它的含义是：MAJOR版本是不兼容的，大规模的API更新；尽管可能存在一些设计的改变和不兼容的更新，但MINOR版本应该最大限度的保持与其它minor版本的”源码“及”二进制“级别的兼容；PATCH版本应该保证向前和向后的完美兼容，为了修复或者发现bug，它可能会有一些异常发生变化。

The extent to which you are affected by changes will depend on how tightly integrated your code is. If you are doing a lot of customization you are more likely to be affected than if you are using a simple namespace configuration.

由于版本变化所带来的影响的程度取决于你的代码整合的紧密程度。如果你做了大量的定制工作，你将比使用一个简单的命名空间配置受到的影响大。

You should always test your application thoroughly before rolling out a new version.

在升级到新的版本之前，你总是应该对你的应用进行彻底的测试。