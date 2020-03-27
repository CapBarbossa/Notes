`git log`所作用的scope是branch，每一个分支有自己所属的独特的log记录.
`git tag`作用的对象是commit记录.
`git log --graph --oneline --decorate`   高逼格的查看log记录.除此之外，使得查看的内容更加可读，very good. truely!

#有讲究的拷贝
	#指定tag版本
`git clone --branch v1.1.0 <repo>`
	#指定拷贝最新的commit
`git clone -depth=1 <repo>`

# 将本地的目录push到github
	1.首先在github上面建一个空的reposity
	2.在本地目录建立一个本地的reposity: `git init`一条命令搞定
	3.关联本地和github的reposity: `git remote add <diy_url_name> https://github.com/CapBarbossa/test007.git`
	4.push吧: git push -u <diy_url_name> branch_name   			

# 添加快捷键设置 `git config --system alias.ci commit`
# way2- 直接在配置文件中写:
```git config: /etc/gitconfig
# system: /etc/gitconfig; global: $home/.gitconfig; local: ./.git/
# 注意: 这些目录在第一次时并不存在,可以手动创建(touch /etc/gitconfig),也可通过命令: git config --system alias.ci commit
[alias]
	ci = commit
	br = branch
	st = status
	co = checkout
[core]
	editor = vim
[user]
	name = CapBarbossa
```



