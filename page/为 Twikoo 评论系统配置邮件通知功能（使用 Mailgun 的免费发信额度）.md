在使用 Twikoo 评论系统的过程中，邮件通知功能是一个重要的补充，它可以帮助管理员及时收到用户评论的通知，避免错过重要的信息。本文将详细介绍如何配置 Mailgun 的邮件通知功能。

## 一、注册 Mailgun 账号并绑定域名

首先，访问 [Mailgun](https://www.mailgun.com/) 的官方网站，查看其价格信息。Mailgun 提供每天 100 封邮件的免费发信额度，这对于个人博客来说绰绰有余。

> **注意**：免费的发信额度需要绑定信用卡。如果没有信用卡，可以选择创建虚拟信用卡，这样可以很好地控制发信额度，避免不必要的损失。

注册完账号后，需要绑定域名。以下是绑定域名的具体操作步骤：

1. 登录 Mailgun 后，选择添加自定义域名。
2. 输入你的博客域名，例如 `senjianlu.com`，并按照给定的 DNS 信息进行验证。
3. 点击右上角的 `Verify` 按钮，等待验证通过。

## 二、获取 Mailgun 的 SMTP 信息

在 Mailgun 控制台，进入 `Send` -> `Sending` -> `Domains` 中找到对应的域名。进入域名相关页面后，点击 `SMTP credentials`，即可查看到 SMTP 的相关信息。默认情况下，会创建一个 `postmaster` 用户。

重置并保存该用户的密码，即可获得完整的 SMTP 信息。接下来，我们可以使用 Python 编写一个示例代码，测试是否可以正常发信：

python
import smtplib
from email.mime.text import MIMEText
from email.header import Header

# 邮件内容
msg = MIMEText('Hello, this is a test email.', 'plain', 'utf-8')
msg['Subject'] = Header('这是一封内部测试邮件', 'utf-8')
msg['From'] = 'postmaster@senjianlu.com'
msg['To'] = '测试邮件接收者'

# SMTP 服务器信息
smtp_server = 'smtp.mailgun.org'
smtp_port = 587
smtp_user = 'postmaster@senjianlu.com'
smtp_password = '你的SMTP密码'  # 请替换为实际密码

# 收信方信息
to_addrs = ['recipient@example.com']  # 请替换为实际接收地址

# 发信
try:
    server = smtplib.SMTP(smtp_server, smtp_port)
    server.starttls()
    server.login(smtp_user, smtp_password)
    server.sendmail(smtp_user, to_addrs, msg.as_string())
    print('Send email successfully.')
except Exception as e:
    print('Failed to send email:', e)
finally:
    server.quit()


请确保可以正常发送邮件后，便可进入下一步。

## 三、配置 Twikoo 评论系统的邮件通知功能

进入博客评论模块，点击右上角的设置图标，选择配置管理，然后配置邮件通知功能，最后保存即可。在此过程中，可以进行邮件测试，确认邮件是否成功发送。

## 四、测试邮件通知功能是否正常

### 1. 配置管理员邮箱
当其他用户评论时，管理员邮箱会收到邮件通知，确保功能正常。

### 2. 测试用户发布评论
发布评论后，管理员邮箱应成功接收到邮件，验证功能的有效性。

### 3. 测试回复评论
在回复评论后，确保相关用户邮箱也能成功收到邮件通知。

## 五、设置 Mailgun 的发信上限

在 Mailgun 控制台选择 `Manage Account` 进行账户管理，设置 `Custom Message Limit`。根据自己的需求，可以将值设置为单月的发信上限，最小值为 1000，我这里设置为 1000。

👉 [野卡 | 一分钟注册，轻松订阅海外线上服务](https://bit.ly/bewildcard)

通过以上步骤，您就可以成功配置 Twikoo 评论系统的邮件通知功能，确保及时接收到用户的反馈与评论。如有任何问题，请随时参考 Mailgun 的官方文档或联系支持团队。