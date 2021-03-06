[TOC]

> Git是一个版本控制系统（Version Control System，VCS）。
### 上传本地项目到GitHub

#### 1.生成秘钥
```
$ ssh-keygen
```

#### 2.查看秘钥
```
$ cat /root/.ssh/id_rsa.pub 
```

#### 3.增加秘钥到github
登录自己的github -> Settings -> 
SSH and GPG keys -> SSH Keys -> New SSH key -> 填写刚刚查看的公钥

#### 4.验证
```
$ ssh -T git@github.com
Hi username! You've successfully authenticated, but GitHub does not provide shell access. 
```

#### 5.认证
```
$ git config --global user.email "xxx@163.com"

$ git config --global user.name "tom"
```

#### 6.在github创建一个新仓库
New Repository -> 最好填写纯英文名称（中文可能被忽略）

#### 7.创建本地仓库并上传（https方式）
```
$ mkdir git-projects

$ cd git-projects/

$ echo "# Git-Basic-Usage" >> README.md

$ git init

$ git add README.md

$ git commit -m "first commit"

$ git remote add origin https://github.com/leomei91/Git-Basic-Usage.git # 使用 https 方式

$ git push -u origin master # 这一步需要填写github账号和密码

```

#### 8.更换为ssh方式
采用ssh方式就不用每次推送都输出用户名密码了！
```
$ git remote -v

$ git remote rm origin

$ git remote add origin git@github.com:leomei91/Git-Basic-Usage.git

$ git push -u origin master

```
