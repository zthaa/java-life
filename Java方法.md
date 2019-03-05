### Java方法

- 方法： java语句的集合，每个方法实现一个特定的功能。解决一类问题的步骤有序的集合、必须在类中、在程序中创建、在其他地方引用

  优点： 使程序变得简单、易懂。

              有利于程序的维护。

              提高开发效率。

              提高代码的重用率。

  方法的格式：类似其他语言的函数，声明格式如下：

  ```java
  [修饰符1 修饰符2 ···] 返回值类型 方法名(形参列表) {
      Java语句;
  }
  // 如main方法
  public static void main(String[] args) {
      代码块；
  }
  ```

具体说明：![D:\markdownpad2\picture\13](\picture\13.png)

方法的返回值：

    return 返回值

- 递归：方法内部调动用本方法（函数）

  特点：

         1、自身调用自身

          2、在使用递归算法时、一定要设计一个递归结束条件（基线条件），也成为递归的出口       

           3、在递归算法的效率低容易造成内存的溢出    

  斐波那契数列递归实现：

  ```java
  public static int fibonacci(int num) {
      if (num == 0) {
          return 0;
      }
      if (num == 1) {
          return 1;
      }
      return fibonacci(num - 1) + fibonacci(num - 2);
  }
  ```


