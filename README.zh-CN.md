# Invalid App

安卓10以上,实现op/app/组件管理  
https://github.com/ikas-mc/px-app/wiki

<img src="https://raw.githubusercontent.com/ikas-mc/px-app/main/docs/screenshots/appops.png" width=260 > <img src="https://raw.githubusercontent.com/ikas-mc/px-app/main/docs/screenshots/record.png" width=260 >


## 下载
https://github.com/ikas-mc/fdroid-repo

注意  
本应用为个人研究性app,不建议普通用户使用  
本应用可能对系统或者应用造成损坏,请自行承担相应后果

本应用需要root或者Sui或者Shizuku(adb模式功能受限)  
root模式不支持后台运行,如果需要后台运行,请使用Sui/Shizuku  
https://github.com/RikkaApps/Sui


## 规则库

### 公共库
https://github.com/ikas-mc/px-repo  
通用的规则与模板

### 私有库
自定义规则,与公共库一样的结构,需要自行创建private库  
私有库使用ssh协议,在github项目设置中添加Deploy keys,然后在app设置页面上传key  
https://docs.github.com/v3/guides/managing-deploy-keys/#deploy-keys


## AppOps补丁
安卓10+默认可能会对AppOps进行修改/同步/重置,如果独立控制权限与Appops,必须阻止系统这种默认行为  
具体可以参考wiki:https://github.com/ikas-mc/px-app/wiki/AppOps   
注意:仅针对类原生系统,第三方系统基本都有自己的修改  

#### 拦截所有对AppOps同步与修改(已实现)
通过magisk module制作补丁或者使用xposed模块  

1. 通过修改系统service.jar,然后制作magisk module  
https://github.com/ikas-mc/Prevent-Op-Sync-Patcher

2. xposed模块  (已废弃)
https://repo.xposed.info/module/ikas.android.projectx.hook.prevent


#### ~~拦截AppOps的检查方法,采用内置规则(已废弃)~~
1. ~~xposed模块~~

#### 替换系统默认的权限控制器,修改内置的同步策略(未实现)

> 权限控制器
>
> https://source.android.google.cn/devices/architecture/modular-system/permissioncontroller

## ifw功能
禁用某些组件可能导致系统无限重启并进入recovery模式  
临时解决方法:  
https://github.com/ikas-mc/px-app/issues/1

## 源码
暂不开源  
插件源码可以参考:  
https://github.com/ikas-mc/Prevent-Op-Sync-Patcher
