####  后端JAVA 01

### Task 1：

1. 

- 什么是**JDK**：JDK全称Java Development Kit ，意思是Java工具包。简单来说就是把适用于Java开发所需要的工具打包在一起了，包含Java编译器，程序打包工具，程序运行环境等，它让程序员编写Java程序

- 什么是**JRE**：JRE全称Java Runtime Environment，即Java运行环境。和它的名字一样，它的作用就是充当运行Java所需的环境，它让编写好的Java程序可以运行，JRE包括JVM和Java类库

- 什么是**JVM**：JVM全称Java Virtual Machine，即Java虚拟机。JVM是Java运行环境的核心，它就是一个虚拟计算机，接收编码后的Java程序，进行解释或编译执行

- 三者的关系：**JDK包含JRE，而JRE又包含JVM。**JDK是全套工具包，所以会包含运行环境JRE。JVM作为JRE的核心，将字节码转化为机器代码，所以是JRE的一部分

- 为什么有了它们就可以运行Java：它们是协调运作的，首先用JDK中的编译器将java源代码编译成字节码，然后将其在运行环境JRE上运行，最后作为桥梁的JVM将字节码转化为机器代码，并对其进行解释和编译

    

### TASK 2：

2. 

- 配置了什么环境变量：

  **JAVA_HOME**用于定位JDK，**PATH**使java，javac等命令能在任何目录下运行，**CLASSPATH**指定运行时除JDK自带的类库外还需要哪些外部的类库

- 为什么配置环境变量后，就可以在命令行执行相关命令：

  **省流：**配置环境后，操作系统就能根据变量找到并执行相应的程序             **详细版**：点击运行相关命令，操作系统根据PATH找到可执行文件，JAVA_HOME告诉操作系统JDK的位置，命令行解释器就能在PATH指定的目录里找到名为java的可执行文件并执行

### TASK3:

3. 运行截图：![image](https://github.com/user-attachments/assets/86815175-d2b8-434c-b65f-2567053ca43b)

ps：一开始一直没运行成功，告诉我没有扩展程序，我就以为环境配错了，去看就发现把变量新建到个人变量里而不是系统变量里面了😓改了之后再运行发现还是不行，以为环境还没配好，上网搜发现其实环境没有问题了，只是没有差了一步在vscode里下载扩展程序。这波属于歪打正着发现环境配错了

4. Java文件编译和运行过程中涉及的文件及作用：

- **源文件 （.java）**： 包含了Java类的定义
- **Jav-a编译器javac**：将源代码文件编译成**字节码文件**（拓展名为.class 是JVM能理解的中间代码）
- **可执行的jar文件（.jar）**：是一个Java程序被打包而形成的JAR文件，是一个压缩包，可以被直接运行

### TASK4:

我下载好intellij idea后，点击java文件发现没有运行按钮，在网上搜了花了一个多小时用了几种方法都没有成功，这下老实了，我还是乖乖用vscode吧，可能是和intellij idea无缘吧🤦‍，时间紧张，还是以后有机会再试试吧，只能与它错过了![查看源图像](https://th.bing.com/th/id/OIP.jENT6O_c2NzcI0XJy91lawHaFq?rs=1&pid=ImgDetMain)



后续：看到第二题要用Intellij IDEA我又老实了，又花了一个半小时重新安装启动配置，这次我是一步也不敢自己操作，全程看网上教程给IDEA匹配JDK，终于成功了最后。所以之前失败的原因可能是因为看着IDEA给的提示乱点乱配，所以一直都搞不出来
![image](https://github.com/user-attachments/assets/c34b94cc-3f43-45ba-83b5-c4f0116a168d)




### TASK5：

5. 

- .git/目录是什么：.git/目录是Git的**版本库**

- .git目录里放了什么：

  - hooks：存放了一些shell脚本

  - info：存放了git仓库的一些信息

  - logos：存放所有更新的引用记录

    - refs
      - heads：本地分支的对象
      - remotes：远程的所有分支对象

    -  HEAD：所有的操作记录

  - objects：存放所有的git对象
  - refs：引用
    - heads：所有的本地分支
    - tags：里程碑
    - remotes：远程仓库信息

- fork和clone有什么区别：

  fork是将别人github仓库里的代码复制到自己的github仓库里，clone是将自己的github仓库里带代码克隆到本地的电脑中

- Pull Request和push有什么区别:

  从英文翻译来就很容易理解，push是将代码直接推到仓库里，如将我本地电脑的代码推到自己的github仓库中，pull是别人从我的github仓库中拉取代码合并到他的github仓库中，由于我没有权限把代码未经允许直接推（push）给别人，所以只能申请让别人来拉取（pull）我的代码，所以叫pull request

- **工作区**：平时存放代码的地方，是可以看到的

  **暂存区**：.git目录下的index文件 用于临时存放改动

​       **本地仓库**：将文件保存在本地的仓库，保存文件被提交的各个版本

​       **远程仓库**：不在本地的仓库，比如在github网站上，可与本地仓库进行数据交换

​      **如何在四个区内移动**：按git int在工作区新建一个代码库**→**按git add +文件名将文件从工作区移动到暂存区→按git commit -m“注释”将文件从暂存区提交到版本库→按git push将本地仓库的文件上传到远程仓库

- 什么是git冲突：多个程序员同时对一个仓库的代码进行修改，且他们修改的部分互相矛盾，就会出现git冲突

  冲突发生的条件是什么：

  当两个或多个开发者同时对同一段代码进行修改，并且这些修改是相互冲突的，或者两个开发者几乎同时提交更改，并且这些更改影响到相同的代码区域，那么在后续的合并操作中可能会发生冲突

  有哪些操作会引发冲突：

  合并分支，拉取代码（pull），推送代码（push），切换分支，撤销更改

- [拓展]：

  如果在某个分支修改没有提交就切换到另一个分支，工作区的文件会保持当前的修改，但如果新分支的文件与原分支修改的文件有冲突，就会程序就会停下来报错



ps：做Java01一共用了六个半小时我有一点点相似，，，Task6还是等我做完所有题后看有没有时间再完成吧，，，求学长学姐疼我

最后几句：我服了想提交这个用了三个小时，明明昨天都能上传到github的，今天就不行了，给我各种报错，我每个都去搜，改了之后又给我报错，，，，我心态有亿点点崩溃，最后在今天十二点终于找到问题根本了：我在昨天做完第一题后就自己乱搞，一个不注意就把本地的readme删掉了。 
