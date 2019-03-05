#### Java数组

- 数组：相同的数据类型的元素按一定顺序排序排列的集合，把有限个类型相同的变量用一个名字命名，然后用编号区分他们的变量集合，这个名字称为数字名，编号为下标，组成数组的各个变量称为数组元素，也称数组的分量，有时也称下标变量，可以减少内存中变量搜索时间。

  数组属于引用类型，一旦定义好大小，将不能改变。

  注意：在Java中数组的长度是不可改变的，一旦声明长度就被固定，不能变长，且具有相同的数据类型。

- 特点：![D:\markdownpad2\picture\14](\picture\14.png)

- 定义数组：

  - 常规方式：数据类型[] 数组名或 数据类型 数组变量名[] , 使用new关键字初始化对象，并指定大小。

    ```java
    String[] names = new String[4];
    names[0] = "jack";
    names[1] = "pony";
    names[2] = "robin";
    names[3] = "jobs";
    ```

  - 简洁方法：

    ```java
    String[] names = {"jack", "pony", "robin", "jobs"};
    ```

- 遍历数组：

  ```java
  String[] names = {"jack", "pony", "robin", "jobs"};
  // 标准for循环遍历数组
  for (int i = 0; i < names.length; i++){
      System.out.println(names[i]);
  }
  
  // for each 方式遍历
  for (String i: names){
      System.out.println(i);
  }
  ```

- 获取数组最大值：

  ```java
  int[] array = {111, 222, 333, 444, 555, 666};
  int maxNum = array[0];
  for (int i: array){
      if (maxNum < i){
          maxNum = i;
      }
  System.out.println(maxNum);
  }
  ```

- 数据倒序存放：

  让数组第1个元素与最后一个元素交换位置，让第2个元素与倒数第2个元素交换，以此循环，直到数组的一半为止，交换结束。

  ```java
  int array = {111, 222, 333, 444, 555, 666};
  int len = array.length;
  // 转换
  for (int i = 0; i < len / 2; i++){
      int temp = array[i];
      array[i] = array[len - i - 1];
      array[len - i - 1] = temp;
  }
  // 输出
  for (int x: array){
      System.out.println(x)
  }
  ```

- 数组的排序(冒泡排序)

  ```java
  public static int[] bubblingSort(int[] numArray) {
      for (int i = 0; i < numArray.length; i++) {
          for (int j = 0; j < numArray.length - 1; j++) {
              if (numArray[j] > numArray[j + 1]) {
                  int temp = numArray[j + 1];
                  numArray[j + 1] = numArray[j];
                  numArray[j] = temp;
              }
          }
     }
     return numArray;
  }
  ```

- 合并两个数组

  ```java
  int[] array1 = {111, 222, 333, 444};
  int[] array2 = {444, 555, 666, 777};
  int[] merArray = new int[array1.length + array2.length];
  for (int i = 0; i < array1.length; i++){
      merArray[i] = array1[i];
  }
  for (int j = 0; j < array2.length; j++){
      merArray[a.length + j] = array2[j];
  }
  // 输出新数组
  for (int x: merArray){
      System.out.println(x);
  }
  ```

- 数组的动态扩展：在Java中数组的长度是固定不能扩展，但在现实情况中，动态地扩展数组以适应程序的要求是非常常见的。

    原理：1、定义数组1，然后定义数组2，数组2的长度为数组1的长度加1。

    2、将数组1的 值全部复制给数组2

    3、将数组2的地址赋值给数组1，即A=B 即可。

  其实质不是将数组1直接加长，而是新增一个数组，将新数组的地址赋值给原数组名，进而模拟出动态扩展的功能。

  ```java
  int[] a = {11, 22, 33, 44};
  System.out.println("数组a的长度为：" + a.length);
  int[] b = new int[a.length + 1];
  for (int i = 0; i < a.length; i++) {
      b[i] = a[i];
  }
  a = b;
  System.out.println("数组a的长度为：" + a.length);
  ```

- 多维数组：以上都是一维，在实际中我们还可能使用二维数组、三维数组甚至n维数组。其实多维数组就是是数组里面嵌套一个数组。如下：

  ```java
  int[][] twoDim = new int[4][];
  twoDim[0] = new int[4];
  twoDim[1] = new int[4];
  twoDim[2] = new int[4];
  twoDim[3] = new int[4];
  // 赋值
  for (int i = 0; i < twoDim.length; i++) {
      for (int j = 0; j < 4; j++) {
          two[i][j] = i * j;
      }
  }
  ```

  以上定义了一个行和列都是4的二维数组，我们在定义二维数组是可以不用知道第二维的长度，我们也可以直接初始化定义：

  ```java
  int a[][] = {
    {1, 2, 3, 4},
    {5, 6, 7, 8},
    {9, 10, 11, 12},
    {13, 14, 15, 16}
  }
  ```

  多维数组的操作:

  ```java
  int threeDim[][][] = new int [3][4][5];
  // 赋值
  for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        for(int k = 0; k < 5; k++) {
            threeDim[i][j][k] = i * j * k;
        }
    }
  }
  // 访问
  for (int i = 0; i < 3; i++) {
    for (int j = 0; j < 4; j++) {
        for(int k = 0; k < 5; k++) {
            System.out.println(threeDim[i][j][k]);
        }
    }
  }
  ```
