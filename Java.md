# 数组第一天
## 数组的特点：
 1. 数组是一种引用数据类型
 2. 数组当中的多个数据，类型必须统一
 3. 数组的长度在程序运行期间不可改变
## 两种常见的初始化基本方式：
- 动态初始化（指定长度）
    - 格式：数据类型[] 数组名称 = new 数据类型[数组长度];
    ```java
    public class Demo01Array {
        public static void main(String[] args) {
            //格式：数据类型[] 数组名称 = new 数据类型[数组长度]
            int[] number = new int[300];

            //创建一个数组能存放10个double类型的数据
            double[] numberB = new double[10];
        }
    }
    ```
- 静态初始化（指定内容）
    - 标准格式：数据类型[] 数组名称 = new 数据类型[] {元素1, 元素2, 元素3, ……}
    ```java
    public class Demo02Array {
        public static void main(String[] args) {
            //直接创建一个数组，里面是int数字：5,15,25
            int[] arrayA = new int[] {5, 15, 25};

            //创建一个String数组
            String[] arrayB = new String[] {"Hello", "World", "Java"};
        }
    }
    ```
    - 省略模式：数据类型[] 数组名称 = {元素1, 元素2, 元素3, ...};
    - 注意事项：
        1. 静态初始化没有指定长度，但是仍然会自动推算得到长度。
        2. 静态初始化标准格式可以拆分成两个步骤。
        3. 动态初始化也可以拆分成两个步骤。
        4. 静态初始化一旦使用省略格式，就不能拆分成两个步骤了。
    - 使用建议：
        - 如果不确定数组当中的具体内容，用动态初始化；否则，已经确定了具体的内容，用静态初始化。
    ```java
    public class Demo03Array {
        public static void main(String[] args) {
            //省略格式的静态初始化
            int[] arrayA = {10, 20, 30};

            //静态初始化的标准格式，可拆分成两个步骤
            int[] arrayB;
            arrayB = new int[] {11, 21, 31};

            //静态初始化也可以拆分成两个步骤：
            int[] arrayC;
            arrayC = new int[5];
        }
    }
    ```
## 使用数组中的元素
- 访问数组元素的格式：数组原始名称[索引值]
- 索引值：就是一个int数字，代表数组当中元素的编号
- 【注意】索引值就是从0开始，一直到“数组长度-1”为止
```java
  public class Demo04Array {
    public static void main(String[] args) {
        //静态初始化的省略格式
        int [] array = {10, 20, 30};

        System.out.println(array[0]);
        System.out.println(array[1]);
        System.out.println(array[2]);
        System.out.println("===============");

        for (int i = 0; i < 3; i++) {
            System.out.println(array[i]);

        }
        System.out.println("===============");

        //将数组当中的某一个单个元素，赋值给变量
        int num = array[0];
        System.out.println(num);
        }
    }  
```
## 访问数组元素进行赋值
- 使用动态初始化数组的时候，其中元素会自动拥有一个默认值。
- 规则如下
1. 如果是整数类型,默认是0;
2. 如果是浮点类型,默认是0.0;
3. 如果是字符类型，默认是'\u0000';
4. 如果是布尔类型，默认是false;
5. 如果是引用类型，默认为null
- 注意事项：静态初始化也有默认值的过程，只不过系统自动将默认值替换为大括号中的具体数值
```java
public class Demo05ArrayUse {
    public static void main(String[] args) {
        int[] array = new int[3];

        System.out.println(array);//内存地址值
        System.out.println(array[0]);// 0
        System.out.println(array[1]);// 0
        System.out.println(array[2]);// 0
        System.out.println("=============");

        //将123赋值交给数组中的1号元素
        array[1] = 123;
        System.out.println(array[0]);// 0
        System.out.println(array[1]);// 123
        System.out.println(array[2]);// 0

    }
}
```
