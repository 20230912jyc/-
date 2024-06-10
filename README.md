
# GitHub笔记

## 关键字查询
  1. awesome,去此标签类别中查询项目
  2. python tutorial,查询资料，书籍，文档
  3. socket sample, 查询对应技术的代码样本

## github 三要素

### Repsitory 仓库
   * 仓库是github项目管理存储基本单位.
   * 一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为public,private

### Commit 提交

   * 程序员在整个开发周期，有大量的对代码资源的迭代和修改，都可以通过commit的方式进行记录，便于程序员回溯代码，即使这些代码被删除
   * 提交便于使用者观察整个工程的开发流程以及设计流程

### Branch 分支
   * 在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认的仓库主分支为master/main
   * 不仅可以管理代码存储，还便于多人协作开发
[例图](C://Users//86185//Desktop//github图片//仓库.png)

## 仓库内容
   1. Code，资源存储，代码资源，二进制，项目管理脚本，许可证等等
   2. issues，使用时遇到bug或进行提交，等待反馈
   3. README，使用makedown语言编写，工程自述文件，开发进度，版本更新，使用介绍
   4. LICENSE 许可证
    * GPL 2.0.3.0 
    * Apahce 2.0
    * Mit
    * 这些许可证，给使用者最大使用权限以及最小的限制

## Git软件，分布式版本控制系统
    * 仓库管理软件，使用git管理私人代码或企业代码

[例图](C://users//86185//Desktop//github图片//git软件分布式管理控制系统.png "悬停")
    * 仓库管理软件，使用git管理私人代码或企业代码

## 设备认证
   1. 如何让网站的账户与设备绑定，后续完成代码的管理，上传下载
```c
   git init //创建本地仓库 后续对仓库的操作，都要在仓库位置（master）
   git config --list //查看git的配置文件
   git config --global user.email "邮箱"
   git config --global user.name "用户名" //以上两步是为了SSH远程访问
   ssh-keygen -t rsa -C "注册邮箱" //创建本地密文
```  
   * 去对应的目录查找密文文件
   * 到rsa.pub复制密文，粘贴 setting -> SSH key and GPG ->new ssh key ->粘贴//在网站上操作
```c
   ssh -T git@github.com //测试关联是否成功
    //如果出现hi...证明成功
```
   2. 为目标仓库起别名，定位目标仓库，后续上传
```c
   git remote add origin "ssh地址" //为ssh仓库地址创建别名为origin
   git remote remove origin //删除origin别名
   git remote add origin "ssh地址" //为ssh仓库地址创建别名为origin
```
## 本地设备与云端仓库的交互逻辑
```c
    git add code.c //添加内容
    git rm //删除本地文件并删除仓库数据
    git restroe //恢复被删除（仓库存在）
```

## 代码更新的依赖关系被破坏
本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，导致本地内容无法再次提交，先拉取git pull云端内容，与本地内容合并或操作，而后再次推即可
```c
    git pull --rebase origin master
    git rebase --skip //忽略旧版，更新本地后可以上传
    git rebase --abort //忽略新版，此时还不能上传
    git rebase --continue //版本合并，解决冲突后可以直接上
```

## 下载开源代码
```c
    git clone "https仓库地址"  //下载开源项目code资源
```

## 分支Branch
关于分支的相关命令，创建分支，选择分支，合并分支等等






## Makedown 语言
Makedown 文本修饰语言，用特殊符合修饰正文效果
## 修饰操作符

# (一级标题)
## (二级标题)
### （三级标题）
#### （四级标题）
##### （五级标题）

## 正文内容

  输入正文内容，但是如果需要执行，用\<br\>

## 输入正文 
  
  *一段测试文本*

  **一段测试文本**

  ***一段测试文本***

  ~~一段测试文本~~

  这是一段测试文本 ，这个`关键字`，将重点表示

## 分割线\-\-\-表示分割
  
---

## 引用\>
> 一级引用 
>> 二级引用
>>> 三级引用

## 列表
## 无序列表\*
* 一级列表
  * 二级列表
    * 三级列表

* 二次元
  * 原神
    * 雷电将军

* FPS
  * PUBG
  * APEX

## 有序列表1.
1. 计算机科学与技术
   1. 数字化
   2. 软件工程


## 混合列表
1. 瓦罗兰特 
   * 火男
   1. jeet



## 创建表格
名称|能力|排名
--|:--:|--:
钢铁侠|有钱|1
蜘蛛侠|帅|2
雷神|NB爹|3

## 代码
```c
      #include<stdio.h>
      int main(void){
	printf("test code\n");
	return 0;
      }

```
```cpp
	#include<stdio.h>
	using namespace std;
```
```python
	import<os>
```
```bash
	echo "测试"
	ls -l
	ps aux
```
### 超链接
[Github](https.github.com)


## 执行
   1. 先vi 名字
```c
   //写完后
   git add 名字
   git commit -m "网站名"
   git push origin master
```
