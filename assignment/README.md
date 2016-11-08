

## 嵌入式系统导论 lab1 实验报告

#### 姓名：郑铠奇     
#### 学号：14353421

## Description
The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.

![dol-form](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/dol-form.png)

## How to install
### 1.首先在ubuntu安装一些必要的环境。
`$	sudo apt-get update`

`$	sudo apt-get install ant`

`$ sudo apt-get install openjdk-7-jdk`

`$	sudo apt-get install unzip`
### 2.解压文件

新建dol的文件夹
`$	mkdir dol`

将dolethz.zip解压到 dol文件夹中
`$	unzip dol_ethz.zip -d dol`

解压systemc
`$	tar -zxvf systemc-2.3.1.tgz`

解压后进入systemc-2.3.1的目录下
`$	cd systemc-2.3.1`

新建一个临时文件夹objdir
`$	mkdir objdir`

进入该文件夹objdir
`$	cd objdir`

运行configure。
`$	../configure CXX=g++ --disable-async-updates`

运行configure截图如下：

![configure](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/config%E5%90%8E%E6%88%AA%E5%9B%BE.png)

编译
`$	sudo make install`

编译完后cd文件目录，输入命令：
`$ ls`

目录如下：

![catalogue](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/%E7%BC%96%E8%AF%91systemc.png)

记录当前的工作路径
`$	pwd`

 ![route](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/%E8%AE%B0%E5%BD%95%E5%BD%93%E5%89%8D%E5%B7%A5%E4%BD%9C%E8%B7%AF%E5%BE%84.png)

表示我当前的工作路径为 /home/zkq/systemc-2.3.1
### 3.编译dol
进入刚刚dol的文件夹
`$	cd ../dol`
修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，
`< property name="systemc.inc" value="YYY/include"/>
< property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`

把YYY改成上页pwd的结果,这里是/home/zkq/systemc-2.3.1

然后编译
`$	ant -f build_zip.xml all`

若成功会显示build successful,如图：

![buildsuccess](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/%E7%BC%96%E8%AF%91dol.png)

接着可以试试运行第一个例子

进入build/bin/main路径下
`$	cd build/bin/main`

然后运行第一个例子
`$	ant -f runexample.xml -Dnumber=1`

成功结果如图

![success](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/%E8%BF%90%E8%A1%8C%E7%AC%AC%E4%B8%80%E4%B8%AA%E4%BE%8B%E5%AD%90%E6%88%90%E5%8A%9F.png)

## Experimental experience
这次实验初步接触了markdown语法，自动编排还是很好用的。git也很不错，上传的图片可以作为markdown的图床。但表格就比较复杂了。不过用atom的markdown插件可以实时更新，所以要调试也很方便。
