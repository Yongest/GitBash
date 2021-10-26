## Git 提交代码 ##

**git 操作基本步骤 :** 

### **前端小组提交代码** ###

代码合并提交包括四种情况:

- **master(主支) 合并提交** 
- **branch(分支) 合并提交**
- **master(主支) + branch(分支)**
- **branch(分支) + branch(其他成员分支) 合并提交**

#### 创建并切换到新分支zhang

- ** git checkout -b zhang **
### master(主支)合并提交 操作步骤 ###

在控制台输出: 

**1.** 先查看本地修改文件的状态	
		
	git status

**2.** 添加所有已修改的文件到缓存中

	git add * 
或者

	git add .
或者

	git add -A

**3.** 提交所有代码到本地,并且认真填写代码描述(方便以后查阅更改)

	git commit –am "代码描述"

**5.** 提交后必须执行更新代码操作
	
	git pull

**6.** 如果出现冲突,必须手动解决冲突后再执行提交到到服务器的git仓库

	git push origin master
	
**7.** 创建zhang分支,并且切换到zhang分支
	git checkout -b zhang

### branch(分支)合并提交 ###

重复主线合并前 **5** 步操作 ,第 **6** 步提交代码需要再将 `master` 更改为对应的 `分支` 名称(branchname)

	git push origin branchname

### master(主支) + branch(分支) ###


重复主线合并前 **4** 步操作 , 第 **5** 先 `merge` (合并) 其他**branch(分支)** 名称(branchname) 内容后,再更新代码操作

	git merge branchname

再执行更新代码操作

	git pull
	

第 **6** 步提交代码需要再将 `master` 更改为对应的 `分支` 名称(branchname)

	git push origin branchname

### branch(分支) + branch(其他成员分支)合并提交 ###

重复主线合并前 **5** 步操作 ,第 **6** 步提交代码需要再将 `master` 更改为对应的 `分支` 名称(branchname)

	git push origin branchname



## Git 解决冲突 ##

在 `git pull` 更新或者 `merge` 合并其他分支后出现 以下提示 ,说明文件出现冲突

![](https://i.imgur.com/ZSXbuSs.png)

解决冲突需要到文件冲突所在行手动修改内容,更改后需要重新 `git add  ` 和 `git commit` 操作 才可提交,接下来的版本以解决冲突后的文件内容为主.

## Git 常用命令 ##

**从git仓库克隆代码到本地** 

	git clone xx@192.168.1.10:/src	 

**查看git仓库的源**  

	git remote –v 
                 
**查看git的状态**  
 
	git status 

**添加所有代码**

	git add –A  

**提交所有代码**        
           
	git commit –am "first commit"   

**推送本地代码到服务器的git仓库里面**

	git push origin master     
      
**从服务器的git仓库分支中拉取到本地**

	git pull                      

**查看提交日志**

	git log

- -[length] :  参数用于指定显示多少条日志 配合 `head` 和 `tail`

- -fileName :  fileName为任意文件名，查看指定文件的提交信息

- -branchName : branchName为任意一个分支名字，查看莫个分支上的提交记录

- --commiter : 查看指定提交者的日志信息

**修改最近一次commit**

	git commit --amend

**丢弃最新的提交**

最新一次的commit的内容有问题，想要丢弃这次提交，

	涉及到的命令： git reset


	
## 其他 ##
**如何通过免密码克隆及推送**

1.在本地客户端使用这个命令 `ssh-keygen bash` ,然后输入自己的名称


2.找到公钥和私钥的位置(默认[window环境下]存放在 `C:\Users\Administrator\.ssh` 中)，将公钥放在服务器的git仓库里，私钥追加到本地即可实现无密码登录 
![](https://i.imgur.com/DJ9XpkK.png)

后缀.pub :为公钥,作用是 **免密码访问** 拥有该公钥的服务器,一般直接交给运维人员即可.

----文档参考 : [https://files.cnblogs.com/files/ma6174/git-tutor.pdf](https://files.cnblogs.com/files/ma6174/git-tutor.pdf)

----参考文档：[https://mp.weixin.qq.com/s/K7004_PVFW0kj8vcFh0s6Q](https://mp.weixin.qq.com/s/K7004_PVFW0kj8vcFh0s6Q)
	 






