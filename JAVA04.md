# JAVA04

## TASK1：

补全函数：

``` java
//这个函数用于判断传入的年份是否为闰年
//是闰年返回1，不是闰年返回2
bool isLeapYear(int year){
 		if(year%400==0)
 		return 1;   //年份被400整除，是闰年
 		else if(year%100==0)
 		return 2;   //年份是100的整数倍，但不能被400整除，不是闰年
 		else if(year%4=0)
 		return 1;    //年份不是100的整数倍，能被4整除，是闰年
 		else 
 		return 2;   //年份不能被4整除，不是闰年
}
```

## TASK2：

补全函数：

``` java
void print(int n) {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                if (i > n / 2 + 1) {
                    // 处理菱形下半部分
                    if ((j == i - n / 2) || (j == n + n / 2 - i + 1)) {
                        System.out.print("*");
                    } else {
                        System.out.print(" ");
                    }
                } else {
                    // 处理菱形上半部分
                    if ((j == n / 2 + 2 - i) || (j == n / 2 + i)) {
                        System.out.print("*");
                    } else {
                        System.out.print(" ");
                    }
                }
            }
            System.out.print("\n");  // 换行
        }
    }
```

