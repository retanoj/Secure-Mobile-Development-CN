# 实施对缓冲区溢出攻击的保护 {#implement-protections-against-buffer-overflow-attacks}

## 细节

这里会描述三个iOS最佳代码实践来帮助开发人员减轻其应用程序遭受缓冲区溢出攻击的风险：自动引用计数（ARC），地址空间布局随机化（ASLR）和堆栈保护。

### _自动引用计数（ARC）_ 

## 修复

**启用ARC **- 启用ARC，或使用Xcode中的重构工具将现有项目迁移到ARC。

**实施完整的ASLR保护 **- 编译应用程序时提供对PIE的支持。通过在编译时使用`-PIE`参数可以启用PIE（在iOS 4.3或更高版本）。

**实施堆栈保护** - 使用`-fstack-protector-all`编译器标志编译应用程序，以保护应用程序免受缓冲区溢出攻击。

## 参考

* [Transitioning to ARC Release Notes](https://developer.apple.com/library/content/releasenotes/ObjectiveC/RN-TransitioningToARC/Introduction/Introduction.html)-[https://developer.apple.com/library/content/releasenotes/ObjectiveC/RN-TransitioningToARC/Introduction/Introduction.html](https://developer.apple.com/library/content/releasenotes/ObjectiveC/RN-TransitioningToARC/Introduction/Introduction.html)

* [Address Space Layout Randomization](https://developer.apple.com/library/prerelease/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html#//apple_ref/doc/uid/TP40002577-SW22)-[https://developer.apple.com/library/prerelease/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html\#//apple\_ref/doc/uid/TP40002577-SW22](https://developer.apple.com/library/prerelease/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html#//apple_ref/doc/uid/TP40002577-SW22)

* [Other Compiler Flags That Affect Security](https://developer.apple.com/library/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html#//apple_ref/doc/uid/TP40002577-SW26)-[https://developer.apple.com/library/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html\#//apple\_ref/doc/uid/TP40002577-SW26](https://developer.apple.com/library/content/documentation/Security/Conceptual/SecureCodingGuide/Articles/BufferOverflows.html#//apple_ref/doc/uid/TP40002577-SW26)

* OWASP Mobile Top 10: [M10 - Lack of Binary Protections](https://www.owasp.org/index.php/Mobile_Top_10_2014-M10)
* CWE: [CWE-121 - Stack-based Buffer Overflow](https://cwe.mitre.org/data/definitions/121.html), [CWE-200 - Information Exposure](https://cwe.mitre.org/data/definitions/200.html)



