# 常用API
## Scanner类
1. 获取int类型: int num = sc.nextInt();
2. 获取字符创： String str = sc.next();
```java
import java.util.Scanner;//导包
public class Demo01Scanner{
  public static void main(String[] args){
    //备注：System.in代表从键盘进行输入
    Scanner sc = new Scanner(System.in);
    //获取键盘输入的int数字
    int num = sc.nextInt();
    System.out.println("输入的int数字是：" + num); 
  }
}
```
## 匿名对象的说明
创建对象的标准格式：

类名称 对象名 = new 类名称();

匿名对象就是只有右边的对象，没有左边的名字和赋值运算符

new 类名称();

注意事项：匿名对象只能使用唯一的一次，下次再用不得不在创建一个对象。

使用建议：如果确定一个对象只需要使用唯一的一次，就可以用匿名对象。
```java
public class Demo01Anonymous {
    public static void main(String[] args) {
        //左边的one就是对象的名字
        Person one = new Person();
        one.name = "高圆圆";
        one.showName();
        System.out.println("=============");

        //匿名对象
        new Person().name = "赵又廷";
        new Person().showName();//

    }
}
=========================================================================

import java.util.Scanner;

public class Demo02Annymous {
    public static void main(String[] args) {
//        Scanner sc = new Scanner(System.in);
//        int num = sc.nextInt();

        //匿名对象的方式
//        int num = new Scanner(System.in).nextInt();
//        System.out.println("输入的是" + num);

        //使用一般写法传入参数
//        Scanner sc = new Scanner(System.in);
//        methodParam(sc);

        //使用匿名对象进行传参
//        methodParam(new Scanner(System.in));

        Scanner sc = methodReturn();
        int num = sc.nextInt();
        System.out.println("输入的是：" + num);
    }

    public static void methodParam(Scanner sc){
        int num = sc.nextInt();
        System.out.println("输入的是：" + num);
    }

    public static  Scanner methodReturn(){
//        Scanner sc = new Scanner(System.in);
//        return sc;
        return new Scanner(System.in);
    }
}
```
