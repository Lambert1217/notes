# git笔记



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

