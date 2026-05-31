# 内网域渗透中的 Kerberoasting 权限提升分析
在 Kerberos 协议流程中，攻击者通过低权限域账号向 KDC 发送请求。由于 KDC 内部的 TGS 服务在处理服务票据请求时，并不会校验用户是否有权访问该服务，且返回的票据是使用对应服务账号的 Hash 加密的，所以攻击者可以通过离线暴力破解的方式获取服务账号的密码，从而实现权限提升。

## 前置知识

[Kerberos协议流程](https://yuuuuukiu.github.io/posts/Kerberos%E5%8D%8F%E8%AE%AE%E6%B5%81%E7%A8%8B/)

