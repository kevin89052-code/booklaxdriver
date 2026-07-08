# BookLAXDriver 安全搭建路线图

域名：booklaxdriver.com

目标：先做一个可信、快速、安全的私人司机预约网站，再逐步接入支付、短信、后台订单和广告投放。

## 第 1 步：官网先上线

目标：客户打开 booklaxdriver.com，可以看到服务、车型、保障、预约表单。

要做：

- 上传 `outputs/private-driver-platform` 文件夹到 Netlify
- 绑定 `booklaxdriver.com`
- 开启 HTTPS
- 确认手机端页面好看、按钮能点、预约信息能复制或发 WhatsApp

安全原则：

- 网站不保存银行卡号
- 网站不收集多余个人资料
- 所有预约先通过 WhatsApp 人工确认

## 第 2 步：支付和绑卡

目标：客户必须完成定金、全款或信用卡预授权，司机才锁定时间。

推荐先用 Stripe Checkout 或 Stripe Payment Links。

要做：

- Stripe 创建定金支付链接
- Stripe 创建全款支付链接
- 预授权/保存卡功能先不要硬做复杂，确认业务流程后再上
- 把网站 `CONFIG` 里的 Stripe 链接换成你的真实链接

安全原则：

- 卡号只进 Stripe，不进我们的网站
- 不在聊天记录里收客户银行卡
- 退款、取消费、等待费规则写清楚

## 第 3 步：服务条款和隐私政策

目标：方便处理取消、空跑、等待费、争议和广告审核。

要做：

- 写隐私政策
- 写服务条款
- 写取消政策
- 写等待费和空跑费说明
- 写保险说明，避免夸大承诺

建议：上线正式收款前，让加州当地律师确认条款。

## 第 4 步：订单后台

目标：不靠手工复制订单，避免漏单。

可以逐步接：

- Google Sheets 订单表
- Airtable 后台
- Stripe 付款记录
- Twilio 短信通知
- 邮件自动确认

第一个版本建议：预约表单 + WhatsApp + Stripe 支付记录，够轻、够快。

## 第 5 步：广告投放

优先顺序：

1. Google 搜索广告
2. 小红书内容
3. 华人微信群/留学生群
4. Instagram / TikTok 短视频

关键词：

- LAX private driver
- LAX black SUV
- LAX airport chauffeur
- LAX airport pickup
- Chinese driver LAX
- LAX to Irvine SUV

## 不要一开始做的事

- 不要自己做银行卡保存系统
- 不要一开始做复杂 App Store 原生 App
- 不要买一堆插件和主机套餐
- 不要直接大额投广告
- 不要承诺无法证明的保险或安全话术

## 当前可上线文件

网站文件夹：

`outputs/private-driver-platform`

本地预览入口：

`outputs/private-driver-platform/index.html`
