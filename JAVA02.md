#### JAVA02：

## TASK1:

**（1）解释代码每个部分**：

- 第一部分：```**package com.ISEKAI**```;    包声明，指定该文件所属包

  - **什么是包**（package）：包（package）相当于文件夹，是用于区别类名的命名空间

  - **包的作用是什么**：
    - 把功能相似的代码和接口组织等放在一起，便于查找和分类，层次清晰
    - 可以把相同名字的类放在不同的包内，避免这些类因命名相同而产生冲突
    - 包可以控制访问权限，可以限制成员访问不同的包

- 第二部分：```**import com.ISEKAI.tool.Print```;    

  - **导入语句**

  ​       用于导入外部的类或包，以便在当前本地的Java类中使用

- 第三部分：

  ```
  public class HelloWorld {
          public static void main(String[] args){
              Test.test();
          }
  }
  ```

  定义了公开类HelloWorld ，定义了main方法作为Java程序的入口点，在这个main方法中调用了名为test的静态方法，这个静态方法属于Test类

  - **主类**

  类的名字与文件名相同，并包含main函数的类叫主类。主类是程序执行的入口

  - **什么是main函数**：main函数是JVM（Java自带虚拟机）开始执行程序的地方，它可以接收命令行传来的参数（这些参数被包装在String[] args中）。简单来说它相当于指挥家，作为起点，调用组织程序各部分的进行，是程序的核心

- **第四部分：** 

- ```
  class Test{
      public static void test(){
          Print.print("Hello World");
      }
  }
  ```

  定义了一个名为Test的类，定义了名为test的公开静态方法，调用名为Print的类的print方法，打印Helllo W orld

- 一个单文件java程序的基本结构：

  **包声明**（对包进行定义，指名当前类所属的包）→**导入语句**（导入其他的类或包）→**定义主类**→**定义主方法**（程序入口）→**在方法中编写具体操作的代码**→**定义其他类**→**定义方法**→..........

**（2）:**

在运行代码的时候疯狂报错，程序包com.ISEKAI.tool不存在，在我一共花了六七个小时疯狂在网上搜索解决方法一一对照结果无一能行后，我去看了看Task2的任务介绍，终于找到关键所在，原来代码里的那些软件包和类都是要自己创建的。所以我犯错的原因是：我在上面问题的回答里说导入语句是导入外部的包，所以一直认为导入的应该是远程的东西，是在网上的，而不用自己创建。太好了困扰我好多时间的问题终于解决了，我明明马上都要放弃了，一直郁郁寡欢想找人安慰一下，这下突然解决了我特别舒畅.....

修改后的main函数

``` 
package com.ISEKAI.tool;

public class Print {
    public static void print(String HelloWorld) {
        System.out.println(111);
        System.out.println(222);
        System.out.println(333);
    }
}
```

![image](https://github.com/user-attachments/assets/3db66fdf-e408-4b87-9df3-ee87e762bb92)


### TASK2：

在Task1成功后做Task2简直是易如反掌啊易如反掌（bushi）(●'◡'●)



Print.java中的代码：

``` 
package com.ISEKAI.tool;

public class Print {
    public static void print(String HelloWorld) {
        System.out.println(HelloWorld);
    }
}

```

![image](https://github.com/user-attachments/assets/61d68927-6fb4-4e1f-9991-942799b9a284)


