# project-x app




## 安卓10

安卓10以上,使用ifw禁用组件,有可能导致系统无限重启进入recovery模式


https://github.com/aosp-mirror/platform_frameworks_base/blob/android10-dev/services/core/java/com/android/server/RescueParty.java


解决方法 :

      "persist.sys.enable_rescue" //配置为false
 
 如果已经无法进入系统,需要删除所有ifw配置文件

        
