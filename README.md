# Invalid App

For Android 10+,Appops/App/Component Management

https://github.com/ikas-mc/px-app/wiki

<img src="https://raw.githubusercontent.com/ikas-mc/px-app/main/docs/screenshots/appops.png" width=260 > <img src="https://raw.githubusercontent.com/ikas-mc/px-app/main/docs/screenshots/record.png" width=260 >


## Download
https://github.com/ikas-mc/fdroid-repo

Note   
This app is a personal research app  
This app may cause damage to your system or application, Please bear the consequences 

This app requires root or Sui/Shizuku  
Root mode does not support running in background, if you need background, Please use Sui/Shizuku  
Sui/Shizuku : https://github.com/RikkaApps/Sui


## Rule  Repo

### Public git repo

https://github.com/ikas-mc/px-repo  
Common rules and templates 

### Private git repo

Custom rules, the same structure as the public library  
You need create a private repo by yourself 

Private repo uses ssh protocol, add Deploy keys in the github project settings, and then upload the key on the app settings page  
https://docs.github.com/v3/guides/managing-deploy-keys/#deploy-keys


## AppOps patch
Android 10+ may modify/synchronize/reset AppOps by default  
If you want to independently set the appops, you must prevent this modification behavior of the system 

Ref wiki:https://github.com/ikas-mc/px-app/wiki/AppOps  
Note: Only support vanilla system, third-party system have their own modifications 

#### Hook AppOps
Choose one of the following 2 options 

1. Magisk module  
Modify the system service.jar, and then make magisk module  
https://github.com/ikas-mc/Prevent-Op-Sync-Patcher

2. Xposed module  
https://repo.xposed.info/module/ikas.android.projectx.hook.prevent


## ifw

Note:  
Disable some components may cause the system to restart indefinitely and enter recovery mode 

Temporary solution:  
https://github.com/ikas-mc/px-app/issues/1

## source
Not open source yet  
The plug-in source code can refer to:  
https://github.com/ikas-mc/Prevent-Op-Sync-Patcher