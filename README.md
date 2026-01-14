### 介绍
b.wguan.top 基于 hexo + github page 搭建的个人博客站点

### hexo page 搭建教程
* 本地安装 node npm git
* npm install hexo-cli -g
* 创建仓库"用户名.github.io" clone库到本地 cd到本地仓库目录
* 创建源码分支，并切换到源码分支
    * git branch source
    * git checkout source
* 执行hexo init . 初始化一个hexo项目
* 安装自动部署到git的依赖
    * npm install hexo-deployer-git --save
    * 打开_config.yml配置   
    `deploy:`   
    `type: 'git'`   
    `repo: '仓库地址`
* 执行 hexo s 后，访问本地localhost:4000预览
* 执行 hexo clean && hexo g && hexo d 自动发布到配置的git仓库 
    * 访问 "http://用户名.github.io."
* 完成了源码在source分支，发布的静态页在主分支
    * 换台电脑只需clone源码分支，就可继续发布文章
    * 还可以在github中将源码分支设置为默认分支，因为编辑都在源码分支上，master分支只是自动生成的
### hexo 知识点
* source/_posts下每个md文件就是一篇文章
* 安装主题
    * git clone 主题仓库地址 themes/主题名
    * 配置文件 theme:主题名

