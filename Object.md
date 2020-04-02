# 面向对象第一天
## this关键字的作用
当方法的局部变量和类的成员变量重名的时候，根据“就近原则”，优先使用 局部变量
如果需要访问本类当中的成员变量，需要使用格式
this.成员变量名

通过谁调用的方法，谁就是this

name：this.name可以看成person.name
```java
/*person*/
public class Person {
    String name;
    public void sayHello(String name){
        System.out.println(name + "，你好。我是" + this.name);
    }
}
/*Demo01Person*/
public class Demo01Person {
    public static void main(String[] args) {
        Person person = new Person();

        person.name = "王健林";
        person.sayHello("王思聪");
    }
}
```
## 构造方法
构造方法就是用来专门创建对象的方法，当我们通过关键字new来创建对象的时候，其实就是调用构造方法
格式：
public 类名称(参数类型 参数名称){
    方法体
}

注意事项
  1. 构造方法的名称必须和所在类的名称完全一样，大小写也相同
  2. 构造法昂发不需要写返回类型，连void都不写
  3. 构造方法不能return一个具体的返回值
  4. 如果没有编写任何构造方法，编译器会自动赠送构造方法，没有参数，方法，什么事情都不做
  5. 一点编写了至少一个方法，那么编译器将不再赠送
  6. 构造方法也可以进行重载
  
  重载：方法名称相同，参数列表不同
```java
//Student
public class Student {
    private String name;
    private int age;

    public Student(){
        System.out.println("构造方法执行了");
    }

    public Student(String name,int age){
        System.out.println("全参构造方法执行啦");
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
//Demo02Student
public class Demo02Student {
    public static void main(String[] args) {
        Student stu1 = new Student();//无参构造
        System.out.println("============");
        Student stu2 = new Student("赵丽颖",20);//全参构造
        System.out.println("name:" + stu2.getName()+", age:" + stu2.getAge());
    }
}
```
## 定义一个标准的类
标准类通常拥有四个组成部分
  1. 所有的成员变量都要使用private关键字修饰
  2. 为每一个成员变量编写一对儿Getter/Setter方法
  3. 编写一个无参数的构造方法
  4. 编写一个全参数的构造方法
 ```java
 //Student
 public class Student {
    private String name;//姓名
    private int age;//年龄

    public Student() {//无参数的构造方法
    }

    public Student(String name, int age) {//全参数的构造方法
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}
//Demo01Student
public class Demo01Student {
    public static void main(String[] args) {
        Student stu1 = new Student();
        stu1.setAge(20);
        stu1.setName("迪丽热巴");
        System.out.println("name: " + stu1.getName() + ", age: " + stu1.getAge());
        System.out.println("==============");

        Student stu2 = new Student("古力娜扎",21);//两种使用方法
        System.out.println("name: " + stu2.getName() + ", age: " + stu2.getAge());
    }
}
 ```
