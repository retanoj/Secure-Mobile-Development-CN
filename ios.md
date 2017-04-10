# 谨慎使用钥匙串

## 细节

iOS提供钥匙串功能来安全存储数据。然而，在一些情况下，钥匙串可能会受到影响并被解密。

在iOS 7以上版本的所有版本中，如果攻击者可以访问加密的iTunes备份，钥匙串可能会部分受到损害。这是由于在创建iTunes备份时iOS会重新加密钥匙串条目，当iTunes备份可用并且备份加密的密码已知时，钥匙串可以部分解密。但是，未加密的iTunes备份不允许解密钥匙串项。

如果设备已越狱，钥匙串访问控制将无效。在越狱的情况下，在设备上运行的任何应用程序都可能会读取每个其他应用程序的钥匙串项。

最后，对于存在BootROM利用的旧设备（例如iPhone 4），钥匙串可以被具有物理访问设备的攻击者所获取。

## 建议

在钥匙串中存储数据时，请使用允许应用程序正常运行的最严格的保护类（由`kSecAttrAccessible`属性定义）。例如，如果您的应用程序不是设计为在后台运行，请使用`kSecAttrAccessibleWhenUnlocked`或`kSecAttrAccessibleWhenUnlockedThisDeviceOnly`。

为防止通过iTunes备份暴露钥匙串项目，请在实际中使用`ThisDeviceOnly`保护类。

最后，对于高度敏感的数据，请考虑使用应用级加密来增强钥匙串提供的保护。例如，依赖用户输入密码以在应用程序中进行身份验证，然后在将数据存储到钥匙串之前使用该密码加密数据。

## 参考

* [Keychain Services Programming Guide](https://developer.apple.com/library/ios/documentation/security/Conceptual/keychainServConcepts/01introduction/introduction.html#//apple_ref/doc/uid/TP30000897)

* [M2 - Insecure Data Storage](https://www.owasp.org/index.php/Mobile_Top_10_2014-M2) ; [M5 - Poor Authorization and Authentication](https://www.owasp.org/index.php/Mobile_Top_10_2014-M5)

* [CWE-312: Cleartext Storage of Sensitive Information](https://cwe.mitre.org/data/definitions/312.html)
* [CWE-522: Insufficiently Protected Credentials](https://cwe.mitre.org/data/definitions/522.html)



