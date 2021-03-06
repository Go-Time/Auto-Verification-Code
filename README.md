# 基于浏览器的万能验证码自动输入

致程序猿、高自动化测试工程师、高级渗透工程师等计算机行业人员的福利：

- Q1：程序还没有上jwt、Redis等session持久化，导致每次更新重启都要输入验证码，心累..
- Q2：又来测试任务了，用多个账号在系统中创建业务逻辑,啥？这验证码是I还是1..这是o还是0...
- Q3：渗透众测中，手工注入时...这个验证码太影响思路了，试一次就要输入一下..
- Q4：我是一个运营...

## 功能说明

- **高速**：以毫秒级识别网站上的英文+数字验证码省去手敲烦恼（准确率高达90%）
- **智能**：对于新网站采用自动查找验证码图片位置，进行识别，新旧网站无缝切换（若未识别DOM中验证码
  位置，可手动确定位置，网站结构未修改只需一次即可）
- **隐私**：仅上传验证码图片及网站验证码DOM层级，其他信息一概不获取
- **轻松**：配合Chrome的记住密码功能，打开网站只需点击下一步即可，提高登录速度88.88%以上

## 视频演示

无意与侵犯视频中的网站，仅作演示使用，如有侵权，请联系我及时删除，谢谢。  
![](https://like996.icu:1205/165106-HD.gif)

## 下载最新版

[本地下载](https://like996.icu:1205/crab-code-demo.user.js) [分流下载](https://greasyfork.org/zh-CN/scripts/418942)
> 需先安装[Tampermonkey](https://www.tampermonkey.net/) 、 [查看安装Tampermonkey帮助](https://like996.icu:1205/help.html#q0) 

## 流程图

![](https://like996.icu:1205/flow.jpg)

## 计划任务

- **Server** + **Agent** 实现智能更新，规则库同步

## 更新记录

#### V3.0 2021-08-15

1、增加盲人语音提示模式，可自行关闭
2、增加黑名单可控制模式，关闭后验证码图片崩溃不自动拉黑
3、增加其他一些细节

#### V2.9 2021-06-28

1、支持更多vue等框架的触发规则，避免填写验证码后未触发事件导致无效
2、增加VIP模式，详情加群咨询

#### V2.8 2021-06-05

1、规则调优，src属性采用首匹配，避免出现网址后面拼接随机数
2、优化初次添加规则逻辑，实现无需刷新页面首次添加规则后刷新验证码仍然有效
3、删除部分无用代码

#### V2.7 2021-05-14

1、支持vue等前端框架的各类验证码变更事件
2、新增关闭自动查找验证码功能
3、新增关闭提示信息功能

#### V2.6 2021-05-08

1、将发包模式改为GM_xmlhttpRequest，以解决部分跨域问题
2、不再等待页面加载完成，载入网页立即执行脚本，解决部分网站特别卡顿问题
3、将验证码前端缓存时间增加，避免挂机时一直识别同一个验证码
4、name规则加权

#### V2.5 2021-03-23

1、界面增加“设置识别码”功能
2、修复识别错误网站黑名单功能不生效问题

#### V2.4 2021-03-15

1、修复打印功能页面出现异常问题
2、优化src选择器遇到base64图片提取错规则问题
3、修改错误提示信息默认展示秒数

#### V2.3 2021-03-08

1、增加升级提示
2、展示当前小时剩余识别数

#### V2.2 2021-02-21

1、优化抓取元素规则，避免抓取错误的元素属性

#### V2.1 2021-01-17

1、修复部分用户页面顶部会出现灰条
2、增加src选择器
3、增加判断手动添加规则时，如果当前选中多个元素，本规则作废。

#### V2.0 2021-01-15

1、增加了对于元素唯一判断（避免错误规则）
2、增加了alt、placeholder元素得添加规则
3、当验证码暂时不可见时不进行识别

#### V1.9 2021-01-04

1、优化填写识别授权码提示。
2、同一验证码仅识别一次，避免重复多次提醒。
3、屏蔽错误提示“ajax请求失败”

#### V.1.8 2020-12-27

1.增加用户注册功能
2.用户邀请他人注册并识别即可永久增加识别次数
3.识别错误的验证码不占用识别次数

#### V1.7 2020-12-22

1.修复后端bug
2.修复手动添加规则时会提示已识别过验证码问题

#### V1.6 2020-12-19

1.后端重构，加快识别效率
2.增加用户体系

#### V1.5 2020-10-25

1.更换域名
2.修复识别频繁发包问题
3.增加域名黑名单，错误只有一次机会
4.提示信息增加关闭功能

#### V1.4 2020-09-23

1.检测到跨域后提醒用户重新选择验证码
2.修复vue框架下验证码绑定无效问题
3.优化验证码结果缓存，手动识别时需要刷新验证码

#### V1.3 2020-09-12

框架基本功能完成
