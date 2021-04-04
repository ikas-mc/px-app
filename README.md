# Invalid App

安卓10以上,实现op/app/组件管理

https://github.com/ikas-mc/px-app/wiki


## 规则库

### 公共库
https://github.com/ikas-mc/px-repo 

包含通用的规则与模板

### 私有库
用于自定义规则,与公共库一样的结构,自行创建private项目即可

私有库使用ssh协议,在github项目设置中添加Deploy keys,然后在app设置页面上传key

https://docs.github.com/v3/guides/managing-deploy-keys/#deploy-keys


##  系统AppOps功能变更

### 系统默认的权限管理器
* 页面权限状态会同时检查权限状态与op状态(uid mode,下同)
* 修改权限时,会立即修改权限对应的op状态
* 当应用检查权限时,会根据权限组状态修正组内所有权限状态与op状态

### 系统权限与op同步机制
* 会根据权限状态自动修正权限对应的op状态,反之亦然
* 系统默认存在多种触发同步的机制,比如任意app的卸载,权限变更
* 会自动重置op状态,如package mode

### 系统AppOps管理
* 系统检查op状态时,先检查uid mode,如果uid mode已经设置就不再继续检查package mode
* 系统内置的组件对op的修改采用uid mode,所以外部App对op修改也需要采用uid mode,否则会有冲突

## AppOps补丁
如果期望AppOps实现独立控制则必须使用补丁,目前有三种方式
注意:仅针对类原生系统,第三方系统基本都有自己的修改

### 拦截所有对AppOps同步与修改(已实现)

1. 通过修改系统service.jar,然后制作magisk module

  https://github.com/ikas-mc/Prevent-Op-Sync-Patcher

2. xposed模块

  https://repo.xposed.info/module/ikas.android.projectx.hook.prevent


### ~~拦截AppOps的检查方法,采用内置规则(已实现)~~
1. ~~xposed模块~~

### 替换系统默认的权限控制器,修改内置的同步策略(未实现)

> 权限控制器
>
> https://source.android.google.cn/devices/architecture/modular-system/permissioncontroller

## ifw功能

禁用某些组件可能导致系统无限重启并进入recovery模式

临时解决方法:

https://github.com/ikas-mc/px-app/issues/1

​        
