# JAVA06:

## TASK1：

``` 
public class Dish_0{
    private String name; //菜品名称
    private double price; //菜品价格
    
    public Dish(String name, double price) {
        this.name = name;
        this.price = price;
    }

    public void profile() {
        System.out.println(番茄炒蛋是普通的大众菜肴，烹调方法比较简单，而且营养搭配合理。色泽鲜艳，口味宜人，深受大众喜爱。其营养价值丰富，具有营养素互补的特点以及健美抗衰老的作用。番茄含有丰富的胡萝卜素、维生素C和B族维生素，番茄红素具有独特的抗氧化能力。鸡蛋含有大量的维生素和矿物质及有高生物价的蛋白质。蛋黄中含有丰富的卵磷脂、固醇类等，对神经系统和身体发育有非常好的作用，深受人们的喜爱。");
    }
}

public class Dish_1 extends Dish {
    public Dish_1() {
        super("成都米线", 11.0); // 菜品名称和价格
    }

    @Override
    public void profile() {
        System.out.println("米线，现已加入成电食堂必吃榜！！（本人自封）又称米丝或米面，是我国有悠久历史的传统食品，既可作为主食，又可作为小吃，是成都人经常食用的米制品");
    }
}

public class Dish_2 extends Dish {
    public Dish_2() {
        super("🔥红烧肉🔥", 15.0);
    }

    @Override
    public void profile() {
        System.out.println("红烧肉是指五花肉经过炖煮后，色泽红亮，好吃到爆，一定带给你烧烧的感受🔥🥵");
    }
}
```

我在过程中遇到并思考的问题：为什么调用该Dish_0的profile方法时不直接用super.，而要重写

解答：super.profile是直接将方法移过来操作，无法对方法的内容进行修改，这样就会导致菜品介绍都是”番茄炒蛋是普通的大众菜肴.......“ 所以需要重写profile方法来进行与番茄炒蛋不同的介绍

## TASK2：

**Order**：

``` 
public interface Order{
       void cook()；
       boolean check();
}       
```

**实现接口**:

``` 
public class Dish_1 extends Dish_0 implements Order {
    public Dish_1() {
        super("成都米线", 11.0);
    }
    
    @Override
    public void cook() {
        System.out.println("将米线放入锅里煮，煮熟后挑出加调料即可食");
    }

    @Override
    public boolean check() {
        Random random = new Random();  //创建了一个Random类的实例，Random类用来生成伪随机数
        return random.nextBoolean(); //调用Random类中的nextBoolean()方法，随机返回 true 或 false
    }
}

   //Dish_2的操作同理，我就不赘述了
```

**完成厨师类System的manageOrder函数**:

``` 
public class System {     //厨师类System
    private static int orderNumber = 1;    // 对订单编号
    public void manageOrder(List<Order> dishes) {

        for (Order dish : dishes) {        // 检查订单中的每一个菜品，检查是否可以烹饪
            if (!dish.check()) {  // 如果检查发现原料不足
                System.out.println("取消订单");
                return;  // 订单取消，直接退出函数
            }
        }

        for (Order dish : dishes) {
            dish.cook();  // 调用每个菜品的cook方法
        }

        System.out.println("订单编号: " + orderNumber);
        orderNumber++;  // 订单处理完后编号加一，进入下一个订单
    }
      if (customer instanceof TableCustomer) {
            TableCustomer tableCustomer = (TableCustomer) customer;
            System.out.println("餐品将送到餐桌编号: " + tableCustomer.tableId);
        } else if (customer instanceof WechatCustomer) {
            WechatCustomer wechatCustomer = (WechatCustomer) customer;
            if (wechatCustomer.takeout) {
                System.out.println("餐品将送到外卖地址: " + wechatCustomer.address);
            } else {
                System.out.println("堂食顾客，无需额外操作。");
            }
        }
    }
}
```

写的好崩溃QAQ，java从入门到放弃（bushi）