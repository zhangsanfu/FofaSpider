目前处于代码初期后期会继续更新，欢迎师傅们加QQ提意见：NTYzMTY0NjE3 (防麦片)

# Fofa页面改版 近期会进行更新

# FofaSpider

本脚本基于python3开发，支持批量爬取功能，将语句写在txt中会进行批量查询

**文件中的 FofaSpider.py 是txt版 Spider.py是excel版 两者使用用法一样**

txt版不会爬取状态码

excel版会自动爬取信息同时输出到excel中 (由于爬取的是fofa中的状态码，所以有可能会出现状态码实际情况不吻合的情况)

可自定义从第几页进行爬取,爬取几页

为了防止爬取过程中被ban延长了time.sleep()的时间，平均sleep 6秒左右

## 免责声明

依据中华人民共和国网络安全法第二十七条：任何个人和组织不得从事非法侵入他人网络、干扰他人网络正常功能、窃取网络数据等危害网络安全的活动；不得提供专门用于侵入网络、干扰网络正常功能及防护措施、窃取网络数据等危害网络安全活动的程序、工具；明知他人从事危害网络安全的活动的不得为其提供技术支持、广告推广、支付结算等帮助。

使用本工具则默认遵守网络安全法

## 依赖安装

pip install -r requirements.txt

## 项目更新

`git pull`

**ps：普通用户高级语法查询只支持第一页，非高级语法搜索支持前5页，会员账号一天只能爬取1w条数据**

# 使用说明

ps：有的时候不能正常爬取的原因是因为cookie信息没有复制全

## Linux下使用

`python3 Spider.py '你的fofaCookie' -q 'domain="baidu.com"||title="百度"' `

-p 参数可自定义从第几页开始爬取，可不加不加 -p 参数则默认为1 -s 爬取几页(该参数可不加)

`python3 Spider.py '你的fofaCookie' -q 'domain="baidu.com"' -p 5 -s 10`

## Windows下使用

windows用户强烈推荐在cmder中使用，在cmd中使用没有高亮

**windows下使用不需要加引号**

同时windows的高级语法中的|| && 只能在 -r 读取txt文本的模式下使用

`python3 Spider.py 你的fofaCookie  -q domain="baidu.com" `

-p 参数可自定义从第几页开始爬取，可不加不加 -p 参数则默认为1 -s 爬取几页(该参数可不加)

`python3 Spider.py 你的fofaCookie  -q domain="baidu.com" -p 5 -s 10`

ps:windows使用过程中如果出现没结果的情况有可能是输入引号但是由于一些终端问题导致引号没有带入查询语句

解决方案：将查询语句写入txt文本 利用 -r 模式来读取数据(此bug后续会尝试解决)

## 支持批量查询语句
将查询语句写在txt文档中，一个语句换一行，格式如下:

domain="baidu.com"

domain="bilibili.com"

**Linux下**
`python3 Spider.py -r 你文本的路径 'cookie'`

**Windows下**
`python3 Spider.py -r 你文本的路径 cookie`

## 更新日志：
05.13 新增输出结果到文本功能,取消了fakeUseragent的使用

05.14 新增部分代码高亮,以及结果判断

05.18 修改了输出文件名的格式，取消了md5对文件名加密命名方式，将文件名改成时间方式，
      删去了部分多余结构，爬取过程中用户中断也会将之前爬取的信息写入txt中
      
05.20 修改了部分逻辑添加报错文本机制

05.21 修改了部分小bug

05.22 大改，使用了xlwt库需要进行依赖安装，输出中会显示状态码，输出结果改成excel表格(csv格式)，在爬取过程中会同时爬取fofa的状态码，test.py为原来的代码,修改了爬取不全的bug,循环改成for循环

05.25 增加了一个判断，修改了部分协议类数据爬不到的情况

05.26 增加了改进版，改进版中不会漏爬，但是取消了状态码的爬取

05.30 增加了 -p 参数 自定义从第几页开始爬 不加则默认为1

07.04 增加功能爬取几页

