---
title: Ionic3升级node20
date: 2025-09-01 16:00:00
categories: 
- 记录
tags:
- ionic3
---
## Ionic3升级node20
### 迁移node-sass到node，解除node版本强依赖
<!--more-->

### 已修改:  
### 1. ionic-app-script-3.2.5.tgz [点击下载](/public/ionic-app-script-3.2.5.tgz)
- node-sass依赖库迁移改为sass  
### 2. ng-packagr-3.0.6.tgz [点击下载](/public/ng-packagr-3.0.6.tgz)
- node_modules/ng-packagr/lib/ng-v5/entry-point/resources/stylesheet.transform.js中的node-sass使用迁移到sass

### 3.ion-angular+3.9.10.patch [点击下载](/public/ion-angular+3.9.10.patch)

- 使用补丁工具实现node_modules/ionic-angular/themes/ionic.functions.scss中node-sass使用迁移到sass

### 4./deep/使用
- 替换为 ::ng-deep

### 5. scss中color使用要在全局scss定义方法
```
@function color($map-name, $key) {
  @return map-get($map-name, $key);
}
```

### 6. tsconfig.json修改
- compilerOptions中加上"types": ["node"]

** 将以上tgz通过npm i ./*/*.tgz安装  
** 将补丁通过patch-package使用  
** 原理是将node-sass迁移到node，解除对node版本的强依赖

