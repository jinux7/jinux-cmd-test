# jinux-cmd-test
## npm的一个可以全局安装带有cmd下执行命令的package.

### npm package 的发布流程：
> 1)本地开发一个npm的package.
---
> 2)在此项目的根目录下打开cmd,运行
```
npm adduser
```
> 根据提示填写npm的用户名，密码啥的.
---
> 3)接着运行
```
npm publish
```
> ok,开发的npm package已经上传到了npm仓库，直接npm install ...就可以喽.
---
> 4)如果要更新已经上传了的包，还是执行
```
npm publish
```
这句话，但是必须更改一下package.json里的version的版本号.

## 接下来,就是如何写一个全局安装带有命令行工具的package了
其实，非常简单，首先，在package.json文件中加上"bin"属性，如下图
![](https://raw.githubusercontent.com/jinux7/jinux-cmd-test/master/img/1.png)
```
jinuxtestcmd
```
就是命令,再有，在bin/index.js文件中的写法,注意要有
```
#!/usr/bin/env node
```
这一句,就是这么简单,完成.见下图
![](https://raw.githubusercontent.com/jinux7/jinux-cmd-test/master/img/2.png)
---
### 本案例已经上传至npm上,使用方法
```
npm install -g jinux-cmd-test
```
安装好之后,在cmd下
```
jinuxtestcmd hello
```
就可以看到效果了.

