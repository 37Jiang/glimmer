# JAVA05：

## TASK1：

#### 1.

``` java
public class Person {
    private String name;
    private int age;
    private int sex;

    public Person(String name, int age, int sex) {
        this.name =name;
        this.age =age;
        this.sex =sex;
    }
    private void eat() {
        System.out.println(name+"正在吃东西");
    }

    private void sleep() {
        System.out.println(name+"正在睡觉");
    }

    private void dadoudou() {
        System.out.println(name="正在打豆豆");
    }
}
```

用到**this**关键词了

**它的作用是：**引用实例变量，把构造方法中的参数的值赋给实例变量

#### 2.

创建对象并赋值：

``` java
public class wwglimmer {
    public static void main(String[] args) {
    
        Person person1 = new Person("王文", 18, 1);   // 使用构造函数创建 Person 对象并赋值
        
    }
}
```

**对象和类的关系**：

类是抽象的，它只有变量和方法，通过类可以创造多个对象。对象是具体的，是类的实例或者实体化（？可能形容得不准确），每个对象都有类定义的属性和方法

#### 3.

**各种访问修饰符的限制范围：**

**public：**可以被任何类访问，包括包内或者包外的类

**protected：**只能被同一个包内的类或者继承这个包的子类可以访问

**private：**只能被当前类访问，无法被包内其他类或包外所有类访问

**默认（如果不加访问修饰符）**：只能被同一个包里的类访问

## TASK2：

``` java
`public class Person {
    private String name;
    private int age;
    private int sex; 
   
    private static int number = 0;  // 定义静态变量：统计当前存在的 Person 对象数量
   
    public Person(String name, int age, int sex) {
        this.name = name;
        this.age = age;
        this.sex = sex;
        number++;       // 每创建一个对象，增加计数
    }
    public static int count() {     // 静态方法：返回当前存在的 Person 对象数量
        return number;
    }
    private void eat() {
        System.out.println(name+"正在吃东西");
    }
    private void sleep() {
        System.out.println(name+"正在睡觉");
    }
    private void dadoudou() {
        System.out.println(name="正在打豆豆");
    }
        @Override
    protected void finalize() throws Throwable {
        number--;      // 对象销毁时计数减少
        super.finalize();
    }
}
```
问题：代码中明明没有提到父类，为什么会用super，为什么要重写（Override）
解答：虽然在Person类里没有提到父类，但实际上如果没有写继承哪个父类，每个JAVA类就会默认继承object类，即以object作为父类。而object类中的finalize方法是一个空方法，不执行任何具体操作。所以如果 Person`类想在对象销毁时减少number，就需要通过重写
ps：好像finalize因为缺点过多被弃用了，时间紧迫，看来我只能之后~~进微光后~~再学其他方法来解决这个问题了qaq
