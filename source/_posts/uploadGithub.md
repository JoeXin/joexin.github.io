---
title: 本地上传到Github
date: 2017-07-18
tags: [Github]
---

## 本地上传到github的步骤说明


##### 第一步： 建立git仓库


`git init`


##### 第二步： 将项目的所有文件添加到仓库中


`git add .`


如果想添加特定的文件，把.换成特定的文件名即可。


#### 第三步： 将add 文件commint 到仓库中去


`git commint -m ‘注释语句’`


##### 第四步：在github 上创建自己的repository


##### 第五步：将本地的仓库关联到githhub上


##### 第六步： 上传前，要记得pull 一下.


`git pull origin master` 


##### 第七步：上传代码到github远程仓库


`git push -u origin master`


执行完后，如果没有异常，等待执行完就上传成功了，中间可能会让你输入Username和Password，你只要输入github的账号和密码就行了