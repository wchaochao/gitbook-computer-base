# 加密

标签（空格分隔）： 计算机基础

---

对数据进行加密，防止窃取

## 加密技术

* 对称加密：同一密钥进行加密、解密
* 非对称加密：公钥加密，私钥解密

### RSA算法

广泛应用于互联网的非对称加密

通过大素数创建公钥、私钥

![RSA创建密钥](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/rsa-key.png)

公钥加密，私钥解密

![RSA加密解密](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/rsa-encrypt.png)

## 数字签名

用于确认文件内容是否完整有效

* 发送者对明文进行MD5运算获取信息摘要，并进行私钥加密
* 接受者对明文进行MD5运算并与解密后的信息摘要进行对比

![数字签名](https://raw.githubusercontent.com/wchaochao/images/master/gitbook-computer-base/digital-signature.png)
