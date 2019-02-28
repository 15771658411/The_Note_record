* 工作区:写代码

  > git add

* 暂存区:临时存储

  > git commit

* 本地库:历史版本

* github代码托管中心 

>  任务:维护远程库



本地库 远程库 



本地库初始化: 

> git init  初始化一个空的git仓库

设置签名

> 用户名 Email  区分不同开发人员 与github一点关系也没有
>
> 项目级别:只在当前本地库范围内有效   优先
>
> 系统用户级别:只在该系统用户帐号下有效
>
> git config -项目  /git config --global -系统用户
>
> git config user.name ,git config user.email 
>
> 项目级别存放在.git/config下
>
> 系统用户级别存在users/用户/.config

提交

> git status 查看状态
>
> git add 添加某部分      提交到暂存区      git rm --cached <>  从暂存区撤销
>
> git commit -m ""   提交到本地库

版本的前进和后退

> ｇｉｔ　ｌｏｇ　　　　查看变更记录
>
> ｈｅａｄ　　　　　　　是指针　指向当前的版本
>
> ｇｉｔ　ｌｏｇ　－－ｏｎｅｌｉｎｅ　以一行漂亮的方式显示变更记录 只显示过去
>
> ｇｉｔ　ｒｅｆｌｏｇ　移动指针步数ｈｅａｄ＠｛｝
>
> 基于索引值操作：
>
> ｇｉｔ　ｒｅｓｅｔ　－－ｈａｒｄ　９ａ６３ｅ（索引值）
>
> git reset --hard head~3 退三步不常用
>
> git reset --soft    //不会碰工作区和暂存区,只是在本地库移动指针
>
> --mixed移动指针,重置暂存区
>
> 可已通过此操作找回没删除的文件(删除前存到了本地库),

查看修改内容 

> 有了修改直接使用 git diff 文件名 查看修改内容
>
> git  diff head  和暂存区进行比较
>
> git  diff head^  文件名 和上一个版本进行比较

## 创建分支

> git  brancch 名字    创建分支
>
> git checkout 名字  切换分支
>
> git  branch -v      查看分支
>
> 必须选择要合并的那个分支上进行合并分支        :    a的修改要合并到b上,要在b分支上
>
> ``` 
> git merge a    
> ```
>
> 

 ###  合并冲突

变更为手动合并状态

> vim 文件名   编辑文件,删除特殊符号
>
>   git add 文件名 git commit -m ''    不能带具体的文件名

## git原理

哈希 加密  验证文件 sha1算法   git快照流,重复的文件指向之前的文件   svn是记录了所有 



### 创建远程库

<a href='https://guides.github.com/activities/hello-world/' >操作指南</a>

> 添加一个远程仓库的别名
>
> ``` 
> git remote add origin http://....git     //origin 就是别名
> ```

#### 推送

> ``` 
> git push origin master                  //origin别名  master分支名
> ```

#### 克隆

> ``` 
> git clone http://....git
> ```

# 推测

> 好像是本地库里面有的才会传到远程库,本地库没有或者在暂停区都不会提交到远程库
>
> 远程库克隆下来的是包含文件名的一整个项目

# 合作者

> settings ->collaborators->添加帐号->被邀请人接受邀请

## 抓取

> ``` 
> git fetch origin master //拉取操作
> ```
>
> 