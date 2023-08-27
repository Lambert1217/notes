# git笔记



---



## 报错处理

### 超时处理

- 取消代理

~~~git
	git config --global --unset http.proxy
    git config --global --unset https.proxy
~~~

- 更新DNS

~~~ git
	ipconfig /flushdns
~~~

- 设置代理

~~~git
 	// 端口号找自己电脑的网络代理
 	git config --global http.proxy http://127.0.0.1:33210
 	git config --global https.proxy https://127.0.0.1:33210
~~~



---



## 初始化处理

### 查看当前版本

```
	git --version
```



### 配置用户名和邮箱

```
	git config --global user.name "Your name"
	git config --global user.email Your_email
```



### 自动保存账户密码

```
	git config --global credential.helper store
```



### 查看所有配置项

```
	git config --global --list
```



---



## 新建仓库

### 方式一 （init）

1. 把当前目录变成Git仓库

```
	git init
```

2. 在当前目录下新建文件夹

```
	git init my_repo
```

![image-20230827141503850](./assets/image-20230827141503850.png)



![image-20230827141520927](./assets/image-20230827141520927.png)

### 方式二 （clone）

远程仓库已经创建好

```
	git clone 远程仓库地址
```



- **下图中的 `.git` 隐藏文件是用来存放Git仓库的所有数据的。（删除后就不是Git仓库了）**

​	![image-20230827140916229](./assets/image-20230827140916229.png)



---

## 工作区域

### 本地



### ![image-20230827145902373](./assets/image-20230827145902373.png)

- 工作区：当前目录（当前文件夹）
- 暂存区：临时存储区域
- 本地仓库：`git init` 创建的本地仓库



### 远程

- 远程仓库：在GitHub等网站创建的远程代码仓库

  可以 `git push` 将本地仓库的代码推送到远程仓库（需要设置好远程仓库）



---



## 添加和提交文件

### 查看仓库状态

```
	git status
```

可以查看仓库中文件的变化，有以下四种：

![image-20230827142741313](./assets/image-20230827142741313.png)

**eg:**

![image-20230827143133654](./assets/image-20230827143133654.png)

其中第一部分是修改但是没有暂存  ， 第二部分是未被跟踪（新建文件）。



### 提交到暂存区

```
git add file
```

- 可以使用 `git add .`	全部提交

![image-20230827143845993](./assets/image-20230827143845993.png)



### 提交到本地仓库

```
git commit -m "提交信息"
```

- 只会提交在暂存区中文件

- 可以使用 `git log` 查看提交记录，使用 `git log --oneline` 查看简洁的提交记录



---



## git reset 回退版本

### 三种方式

- ```
  git reset --soft 版本编号
  ```

  回退到某一个版本，并且保留工作区和暂存区的所有修改内容

- ```
  git reset --hard 版本编号
  ```

  回退到某一个版本，并且丢弃工作区和暂存区的所有修改内容

- ```
  git reset --mixed 版本编号
  ```

  回退到某一个版本，并且保留工作区，丢弃暂存区



如果回退失误可以使用 `git reflog`  查看操作前的版本号，进行回退。



---



## git diff  差异查看

- 对比工作区和暂存区

```
git diff
```

- 对比工作区和本地仓库

```
git diff HEAD
```

​		**`HEAD` 指向最新提交节点**

-  对比暂存区和本地仓库

```
git diff --cached
```

- 对比两个版本

```
git diff 版本编号1 版本编号2
```

- 对比当前版本和上一个版本

```
git diff HEAD~ HEAD
```

​		`HEAD~2`  、`HEAD~3` 分别表示前两个和前三个版本



---



## git rm 删除文件

### git rm使用

```
	git rm file
```

可以同时删除工作区和暂存区的文件



### 查看暂存区的内容

```
	git ls-files
```



---



## .gitignore 忽略文件

出了点小问题 —— 不能忽略              以后补上



---



