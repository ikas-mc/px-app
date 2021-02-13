# Invalid App

安卓9以上,实现op/app/组件管理


## 规则库

公用:https://github.com/ikas-mc/px-repo 

私用:添加Deploy keys,然后在app设置页面上传添加的key

## 安卓10  11 的一些问题

### appOp功能

如果需要实现忽略/单项权限控制(非权限组)等功能则必须使用补丁,否则appOp功能无法保证,原因如下

1. 系统默认的权限控制器在判断是否具有某个权限时会同时检查op状态(uid mode,下同)
2. 系统默认的权限控制器在授权或修改权限时,会立即修改op状态
3. 系统默认的权限控制器以权限组为单位,有可能导致各种状态不一致
4. 系统会自动根据权限状态修正op状态
5. 系统默认存在几种机制触发自动同步,如权限变更,任意app卸载导致权限检查
6. 系统实现单次授权等新的方式
7. 其他待补充

目前难有良好的方案,除非大量修改系统与默认权限控制器逻辑,但这与未来系统实现相悖

App目前支持的方法:

1.直接拦截所有同步方式(通过给系统service.jar打补丁或者xposed模块方式)

补丁 (非完整,待设计):https://github.com/ikas-mc/Prevent-Op-Sync-Patcher

xposed模块:App 模式页面直接安装

2.直接忽略系统内置op规则,采用app内置规则,拦截所有app op检查点

xposed模块:App 模式页面直接安装

### ifw功能

安卓10以上,使用ifw禁用组件,有可能导致系统无限重启进入recovery模式

临时解决方法:

https://github.com/ikas-mc/px-app/issues/1

​        
