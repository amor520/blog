---
title: nodejs邮件发送就是这么简单
tags:
  - 邮件发送
categories:
  - nodejs
---

#### 调用方法：

`sendMail('amor_zhang@qq.com','这是测试邮件', 'Hi Amor,这是一封测试邮件');`
<!-- more -->
#### 支持服务：

```
'1und1',
'AOL',
'DebugMail.io',
'DynectEmail',
'FastMail',
'GandiMail',
'Gmail',
'Godaddy',
'GodaddyAsia',
'GodaddyEurope',
'hot.ee',
'Hotmail',
'iCloud',
'mail.ee',
'Mail.ru',
'Mailgun',
'Mailjet',
'Mandrill',
'Naver',
'OpenMailBox',
'Postmark',
'QQ',
'QQex',
'SendCloud',
'SendGrid',
'SES',
'SES-US-EAST-1',
'SES-US-WEST-1',
'SES-EU-WEST-1',
'Sparkpost',
'Yahoo',
'Yandex',
'Zoho'
```

#### 安装如下包：

`npm install nodemailer --save`

`npm install nodemailer-smtp-transport --save`

package version:

```
"nodemailer": "^2.3.2",
"nodemailer-smtp-transport": "^2.4.2",
```


#### config.js:

```javascript
module.exports = {
       //邮件配置
    email: {
        service: 'QQ',
        user: '你的邮箱',
        pass: '你的密码',
    }
}
```

#### mail.js

```javascript
/**
 *
 * @Description 邮件发送
 * 调用方法:sendMail('amor_zhang@qq.com','这是测试邮件', 'Hi Amor,这是一封测试邮件');
 * @Author Amor
 * @Created 2016/04/26 15:10
 * 技术只是解决问题的选择,而不是解决问题的根本...
 * 我是Amor,为发骚而生!
 *
 */

var nodemailer = require('nodemailer')
var smtpTransport = require('nodemailer-smtp-transport');
var config = require('./config')

smtpTransport = nodemailer.createTransport(smtpTransport({
    service: config.email.service,
    auth: {
        user: config.email.user,
        pass: config.email.pass
    }
}));

/**
 * @param {String} recipient 收件人
 * @param {String} subject 发送的主题
 * @param {String} html 发送的html内容
 */
var sendMail = function (recipient, subject, html) {

    smtpTransport.sendMail({

        from: config.email.user,
        to: recipient,
        subject: subject,
        html: html

    }, function (error, response) {
        if (error) {
            console.log(error);
        }
        console.log('发送成功')
    });
}

module.exports = sendMail;
```
#### 代码地址：
<div class="github-card" data-github="amor520/nodemailer-nodemailer-smtp-transport" data-width="400" data-height="" data-theme="medium"></div>
<script src="//cdn.jsdelivr.net/github-cards/latest/widget.js"></script>
