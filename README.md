# mimotion
![ 刷步数](https://github.com/xunichanghuan/mimotion-run/actions/workflows/run.yml/badge.svg)
[![GitHub forks](https://img.shields.io/github/forks/xunichanghuan/mimotion-run?style=flat-square)](https://github.com/xunichanghuan/mimotion-run/network)
[![GitHub stars](https://img.shields.io/github/stars/xunichanghuan/mimotion-run?style=flat-square)](https://github.com/xunichanghuan/mimotion-run/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/xunichanghuan/mimotion-run?style=flat-square)](https://github.com/xunichanghuan/mimotion-run/issues)

# 小米运动自动刷步数

> 小米运动自动刷步数

## Github Actions 部署指南

### 一、Fork 此仓库

### 二、设置账号密码
# 新增
添加名为  **CONFIG**的变量: Settings-->Secrets-->New secret ,使用下面json模板配置多账户，支持邮箱,手机号
```
{
  "USER": "abcxxx@xx.com",
  "PWD": "password",
  "MIN_STEP": "18000",
  "MAX_STEP": "25000",
  "PUSH_DT_TOKEN": "",
  "PUSH_DT_HOUR": "",
  "PUSH_DT_MAX": "30",
  "SLEEP_GAP": "5",
  "USE_CONCURRENT": "False"
}
```
> 添加名为  **PAT** 的变量: Settings-->Secrets-->New secret

| Secrets |  格式  |
| -------- | ----- |
| PAT |   此处**PAT**需要申请，值为github token，教程详见：https://www.jianshu.com/p/bb82b3ad1d11 ,需要repo和workflow权限,此项必填，避免git push的权限错误。 |

**CONFIG**示例
```
{
  "USER": "abcxxx@xx.com",
  "PWD": "password",
  "MIN_STEP": "18000",
  "MAX_STEP": "25000",
  "PUSH_DT_TOKEN": "",
  "PUSH_DT_HOUR": "",
  "PUSH_DT_MAX": "30",
  "SLEEP_GAP": "5",
  "USE_CONCURRENT": "False"
}
```

### 三、自定义启动时间

编辑 **random_cron.sh**
修改其中**if**语句的判断时间为UTC时间，即**北京时间-8**，如北京时间8点为UTC时间0点，需要运行的时间-8就是UTC时间



## 注意事项

1. 每天运行七次，由random_cron.sh控制，分钟为随机值

2. 多账户的数量和密码请一定要对上 不然无法使用!!!

3. 启动时间得是UTC时间!

4. server酱注册地址 [点我](https://sct.ftqq.com/)

5. 如果支付宝没有更新步数,到小米运动->设置->账号->注销账号->清空数据,然后重新登录,重新绑定第三方

6. 小米运动不会更新步数，只有关联的会同步！！！！！

7. 请各位在使用时Fork[主分支](https://github.com/meyangge/mimotion-run/)，防止出现不必要的bug.

8. 请注意，账号不是 [小米账号]，而是 [小米运动] 的账号。

## 历史Star数 

[![Stargazers over time](https://starchart.cc/meyangge/mimotion-run.svg)](https://starchart.cc/meyangge/mimotion-run)
