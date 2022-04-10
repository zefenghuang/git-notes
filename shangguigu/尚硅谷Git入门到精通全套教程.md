[https://www.bilibili.com/video/BV1vy4y1s7k6?spm_id_from=333.337.search-card.all.click](https://www.bilibili.com/video/BV1vy4y1s7k6?spm_id_from=333.337.search-card.all.click)

# 大纲

![image-20220409181300990](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409181300990.png)





# Git概述

![image-20220409191549894](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409191549894.png)

- 工作区：代码存放的磁盘的目录的位置
- 暂存区：将工作区写的代码添加的暂存区，临时存储
- 本地库：暂存区的代码提交本地库，会生成对应的历史版本，此时代码删不掉





# Git常用命令

![image-20220409200703608](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409200703608.png)

- git log和git reflog相似，信息更全
- 签名的作用是区分不同操作者身份，用户的签名信息在每一个版本的提交信息中能够看到。以此确认本次提交是谁做的，git首次安装必须设置用户签名。
- 用户签名和将来登录GitHub的账号没有任何关系，用户签名只代表了windows本地的git客户端
- 想要新建一个本地仓库，直接新建一个文件，在文件中用命令git init即可初始化本地库
- Git切换版本，底层其实是移动的HEAD指针





# Git分支

![image-20220409214801246](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409214801246.png)

![image-20220409215127046](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409215127046.png)

合并分支发生冲突后，使用手动合并，合并完成后先使用git add命令，再使用git commit命令，此时git commit命令不能带文件名





# 团队协作

- **团队内协作**

![image-20220409221054737](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409221054737.png)

团队人员A、B、C先各自建立自己的本地库，其中A可以先push到远程库，再B和C从远程库clone到自己的本地库，其B和C在修改代码后再push到远程库，此时A可以从远程库pull代码

- **跨团队协助**

![image-20220409221655921](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220409221655921.png)

团队B（东方不败）先从团队A（岳不群）fork代码到自己的远程库再clone到自己的本地库，再修改后push到自己的本地库，再向A发送Pull request请求，经A审核后再决定是否合并





# GitHub操作

- **创建远程仓库**

```
git remote -v //查看当前所有远程地址的别名
git remote add 别名 远程地址 //为远程库起别名
```

- **推送本地分支到远程仓库**

```
git push 别名 分支 //本地分支推送到远程库（别名）尚
```

![image-20220410011005526](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20220410011005526.png)

推送过程出现这个问题，原因是github不再支持使用密码push的方式，解决方案：一、使用SSH  二、使用Personal access token

这里使用第二种解决：

1. 点击你的GitHub头像 -> 设置 -> 开发者设置 -> Personal access tokens -> Generate new token
2. 使用命令git remote add 远程仓库别名 https://你的token@远程仓库地址，完成再push

- **拉取远程库到本地库**

```
git pull <远程主机名> <远程分支名>:<本地分支名>
//如果远程分支是与当前分支合并，则冒号后面的部分可以省略。
```

- **克隆**

```
git clone 链接
```

clone会拉取代码，初始化本地仓库，创建别名

**ssh免密登录**

1. 在c盘的用户文件夹中打开git使用下面的命令，然后三次回车

   ```
   ssh-keygen -t rsa -C 邮箱地址
   //-t 即指定密钥的类型，密钥的类型有两种，一种是RSA，一种是DSA
   /*C表示提供一个注释，用于识别这个密钥。
   “邮箱地址（因为邮箱地址具有唯一性所以一般用这个）”：用于识别这个密钥的注释，引号里的内容为注释的内容，所以" "里面不一定填邮箱，可以输入任何内容。*/
   ```

2. 在SSH and GPG keys里面创建信的SSH key将公钥复制到里面

3. 拉取分支

   ```
   pull ssh链接 分支
   ```

4. 推送分支

   ```
   push ssh链接 分支
   ```





# Idea集成Git







# 码云







# GitLab