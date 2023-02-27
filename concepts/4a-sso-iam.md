# 4A、SSO、IAM

**本文涉及的概念：**
* 4A，Authentication、Authorization、Account、Audit
* SSO，Single Sign-On、Single Sign-Off
* IAM、Identity and Access Management

**TODO：画一张图体现各种概念的关系**

## 1 相关场景
在看 4A、SSO、IAM 之前，我们来看下相关场景。

### 1.1 作为员工/用户
* 多套账号密码：在CRM中是老杨/密码1234，在OA中是小杨/密码9527，由于账号过多，经常忘记账号、密码，或者干脆设置同样的或简单的密码。
* 反复注册登录：在不同系统/APP中需要反复地输入账号密码登录，或者反复注册、申请审批。
### 1.2 作为企业管理员
* 管理员工的账号/权限费时费力：无法统一管理员工在公司内不同系统的账号/权限，导致员工缺少账号或拥有过多账号/权限；员工入职、转岗、离职时需要手动开通/收回员工的账号。
* 无法追踪员工的行为：员工的活动分散在企业内各个系统中，无法及时发现、统计员工的行为轨迹，制止风险行为。
### 1.3 作为开发者
* 反复造轮子：针对账号体系、注册登录、第三方登录、用户自主服务等常规和基础的功能需要反复开发。
* 用户数据难打通：即使在公司内部，也容易出现不同系统之间账号体系的设计、口径不一致的情况，导致系统之间的用户数据难以打通。

## 2 4A
### 2.1 4A 是什么
* Authentication 认证
* Authorization 授权
* Account 账号
* Audit 审计

### 2.2 4A 关注点
1. 关注用户、认证、权限和审计
2. 面向内部员工、具备人员生命周期管理
3. 具备用户登录时的访问控制
4. 关注权限统一管理
5. 用户身份变化和访问信息记录后可以事后审计

### 2.3 Authentication
广义的认证是一种信用保证形式，指第三方公证机构对组织/个人的身份、能力、资质等的认可。

狭义的认证指的是证明“主体是谁”。

#### 2.3.1 认证场景
1. 未认证的主体需要认证 - 登录
2. 已认证的主体跳转到其他应用时自动认证 - SSO(单点登录)
3. 已认证的主体访问敏感资源时需要二次认证 - MFA(多因素认证)

#### 2.3.2 认证方式
认证方式是主体证明“我是我”的手段，主要有“所知、所有、所是”三大类认证方式。
1. 所知：主体所知道的信息，比如密码、密保问题等。
2. 所有：主体所拥有的物品，比如短信验证码、数字证书、OTP等。
3. 所是：主体所拥有的生物特征，比如人脸、指纹、签名等。

认证方式和MFA息息相关。

#### 2.3.3 MFA，Multi-Factor Authentication
MFA (Multi-Factor Authentication)，多因素认证，是指使用两种以上的认证来进行身份验证，以提高账号的安全性。

### 2.4 Authorization
### 2.5 Account
### 2.6 Audit

#### 2.3.4 认证协议
认证协议主要用于在用户、业务系统、身份认证服务之间传递用户信息，告诉业务系统“此用户是谁”。

主流的认证协议/实现单点登录的方案有：
* Cookie
* JWT
* SAML
* CAS
* OIDC
* ...

#### 2.3.5 认证源
认证源指的是用户在登录当前系统时，由第三方提供认证服务，系统信任第三方的认证结果。例如使用微信登录某APP。就是将微信作为认证源。

## 3 SSO
### 3.1 SSO，Single Sign-On
SSO (Single sign-on)，单点登录(单一签入)，一种对于许多相互关连，但是又是各自独立的软件系统，提供访问控制的属性。当拥有这项属性时，当用户登录时，就可以获取所有系统的访问权限，不用对每个单一系统都逐一登录。SSO 是一种帮助用户快捷访问网络中多个站点的安全通信技术。

单点登录系统基于一种安全的通信协议，该协议通过多个系统之间的用户身份信息的交换来实现单点登录。使用单点登录系统时，用户只需要登录一次，就可以访问多个系统，不需要记忆多个口令密码。单点登录使用户可以快速访问网络，从而提高工作效率，同时也能帮助提高系统的安全性。

### 3.2 SSO，Single Sign-Off
同样，单一退出 (Single sign-off)，只需要单一的退出动作，就可以结束对于多个系统的访问权限。

### 3.3 SSO 关注点
1. 解决用户体验问题
2. 无特定类别的用户
3. 实现一点登录、全局进入，无访问控制能力。

### 3.4 SSO 实现前提
要实现SSO，需要以下主要功能：
1. **系统共享**：统一的认证系统是SSO的前提之一。认证系统的主要功能是将用户的登录信息和用户信息库相比较，对用户进行登录认证；认证成功后，认证系统应该生成统一的认证标识(ticket)，返还给用户；另外，认证系统还应该对ticket进行校验，判断其有效性。
2. **信息识别**：要实现SSO让用户只登录一次，就必须让应用系统能够识别已经登录过的用户。应用系统应该能对ticket进行识别和提取，通过与认证系统的通讯，能自动判断当前用户是否登录过，从而完成单点登录的功能。

另外：
1. **单一的用户信息数据库并不是必须的**，有许多系统不能将所有的用户信息都集中存储，应该允许用户信息放置在不同的存储中。事实上，只要统一认证系统、统一ticket的生成和校验，无论用户信息存储在什么地方，都能实现单点登录。
2. **统一的认证系统并不是说只有单个的认证服务器**。当用户在访问“应用系统1”时，由第一个认证服务器进行认证后，得到由此服务器产生的ticket。当他访问“应用系统2”时，“认证服务器2”能够识别此ticket是由第一个认证服务器产生的，通过认证服务器之间标准的通讯协议(例如SAML)来交换认证信息，仍然能够完成SSO的功能。

### 3.4 SSO 优点
SSO为所有其它应用程序和系统，以集中的验证服务器提供身份验证并结合技术，确保用户不必频繁输入密码。

使用单点登录的好处包括：
* 降低访问第三方网站的风险（不存储用户密码，或在外部管理）。
* 减少因不同的用户名和密码组合而带来的密码疲劳。
* 减少为相同的身份重新输入密码所花费的时间。
* 因减少与密码相关的调用IT服务台的次数而降低IT成本。

### 3.5 SSO 缺点
* 不利于重构：因为涉及的系统很多，要重构必须要兼容所有的系统，可能很耗时。
* 无人看守桌面时有安全风险：因为只需要登录一次，所有的授权的应用系统都可以访问，可能导致一些很重要的信息泄露。

## 4 IAM
### 4.1 IAM，Identity and Access Management
IAM (Identity and Access Management)，即身份认证和访问管理。Gartner 对 IAM 的定义是：“让正确的人在正确的时间以正确的理由访问正确的资源”。其核心功能包括：
* 认证(Authentication)管理
* 授权(Authorization)管理
* 账号(Account)管理
* 审计(Audit)管理

传统的 IAM 提供商又被称为 4A 厂商，他们为企业集成现有系统，构建用户管理、身份认证、权限管理、审计整合于一体的集成应用平台。

基于场景划分，IAM可以分为三大类：
1. EIAM (Employee Identity and Access Management)
2. CIAM (Customer Identity and Access Management)
3. RAM (Resource and Access Management)

#### 4.1.1 EIAM
EIAM (Employee Identity and Access Management)，指管理企业内部员工的IAM，主要解决员工使用的便捷性和企业管理的安全性相关问题。
 
在产品形态上，EIAM有以下特点：
* 需要集成企业的云应用、本地应用
* 需要集成不同的身份源
* SSO和MFA很常用
* 不同企业所需的访问控制力度不同

#### 4.1.2 CIAM
CIAM (Customer Identity and Access Management)，指管理企业外部客户/用户的IAM，主要解决用户数据打通和开发成本与标准化相关问题。

在产品形态上，CIAM有以下特点：
* 在用户端常见到的是单点登录和授权登录
* 提供通用的组件给开发者直接使用
* 更强调高性能和高可用

#### 4.1.3 RAM
云厂商的IAM，有时称为RAM (Resource and Access Management)，指管理企业云资源的IAM，主要用于管理云资源的访问控制。

在产品形态上，云厂商IAM有以下特点：
* 强调授权的灵活性和企业管理的安全性
* 支持多种类型的账号进行认证或被调用
* 一般只关注管理自家的云资源

### 4.2 IAM 关注点
1. 面向员工、合作伙伴、顾客、设备、应用、特权账号、物理设备等，实现全生命周期管理
2. 实现 Service All In 的大点，将B/S、C/S不同类别的应用、不同浏览器的访问统一纳管
3. 实现应用级别的细粒度权限、AP操作、数据权限统一管理
4. 访问控制从静态转向动态，具备实时风险发现极致和风险闭环管理的能力
5. 实现身份能力的云服务化，增强用户隐私管理

## 参考资料
1. [SSO、4A到IAM 的进化](https://zhuanlan.zhihu.com/p/464185329)
2. [单点登录](https://zh.wikipedia.org/zh-cn/%E5%96%AE%E4%B8%80%E7%99%BB%E5%85%A5)
3. [SSO](https://baike.baidu.com/item/SSO/3451380)
4. [Introduction to Single Sign-On](http://www.opengroup.org/security/sso/sso_intro.htm)
5. [IDaaS 已经替代传统 IAM 成为企业标配](https://zhuanlan.zhihu.com/p/298198878)
6. [一文读懂IAM（身份与访问管理）](https://www.woshipm.com/it/4681031.html)