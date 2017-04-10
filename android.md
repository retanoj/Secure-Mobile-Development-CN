# 避免缓存应用程序快照

## 细节

为了在界面中提供视图转换，iOS已被证明可将屏幕截图作为图像存储在设备NAND闪存的文件系统中。当应用程序暂停（而不是终止），按住主按钮或者电话或其他事件暂时中止应用程序时，会发生这种情况。这些图像通常可以包含用户和应用程序数据。在一个公开的案例中，它们包含用户的全名，出生日期，地址，雇主和信用分数。

## 建议

为了保护敏感数据，使用API​​配置或代码阻止缓存应用程序快照。

当`applicationDidEnterBackground:`方法返回时，应用程序用户界面的快照就生成了。它用于转换动画并存​​储在文件系统中。应该覆盖此方法，并在用户界面返回前删除用户界面中的所有敏感信息。这样，快照就不会包含它们。

## 参考

* [Managing Your Applications Flow](https://developer.apple.com/library/iOS/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/ManagingYourApplicationsFlow/ManagingYourApplicationsFlow.html#//apple_ref/doc/uid/TP40007072-CH4-SW47)

* [M4 - Unintended Data Leakage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M4) ; [M2 - Insecure Data Storage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M2)

* [CWE 200](https://cwe.mitre.org/data/definitions/200.html)



