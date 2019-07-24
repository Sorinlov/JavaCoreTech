# https://docs.oracle.com/javase/7/docs/api/

## 数据类型

* int     4字节   2^31 +-20亿
* short   2字节   2^15
* long    8字节   2^63
* byte    1字节   2^7

* float   4字节   有效位数 6-7位
* double  8字节   有效位数15位

* char
* boolean


## 进制前缀

* 二进制 0B 0b
* 八进制 0
* 16进制 0x 0X

* 长整型  后缀L l
* float   后缀f F
* double  后缀d D 没有后缀默认double

## 变量的声明和初始化
* int v; // 声明
* v = 12; // 初始化
* 不对变量进行初始化就使用则会报错

* final 指示常量 此变量名常全大写
* static 所修饰变量为类变量888888IyIIIIIIIIIIIIIIIIIIIIIIII

## math 库
源文件顶部加此代码 避免每次使用加上前缀Math
```
import static java.lang.Math.*;
```
* Math.PI   圆周率Π
* Math.E    e
* Math.exp
* Math.log
* Math.log10
* Math.round return long

## 强制类型转换
```
double x = 9.997;
int nx = (int) Math.round(x);
```

## 运算符
* i++   先赋值 再++
* ++i   先++ 再赋值
```
int m = 7;
int n = 7;
int a = 2*++m; // a is 16, m is 8
int b = 2*m++; // b is 14, n is 8
```
### 位运算符
* &
* |
* ^ 异或
* ~ 非

* <<
* >> 符号位填充高位
* >>> 0填充高位

## STRING
字符串变量不可修改
* s.substring(0,3); //[0,3)
* s1 + s2
* s.equals(t)
* s.equalsIgnoreCase('hello')
* 不能用 == 检测两个字符串是否相等；s,t都是reference == 检测address是否相等
* boolean startsWith(String other)
* boolean endswWith(String suffic)
* int indexOf(String str)
* int indexOf(String str, int fromIndex) 第一个字串的位置
* int lastIndexOf(String str)
* int lastIndexOf(String str, int fromIndex)
* int length()
* String replace(CharSequence oldString, CharSequence newString)
* **String substring(int beginIndex, int endIndex)**
* **String toLowerCase()**
* **String toUpperCase()**
* **String trim()** 删除头尾空格
* **String join(CharSequence delimiter, CharSequence elements)** 链接为一个新字符串


* 由许多小的字符串构建一个新的字符串时，依次用+连接效率低，费空间，因为每次会构建一个新的String 
* 可使用StringBuilder
```java
StringBuilder builder = new StringBuilder();
builder.append(ch); // appends a single character
builder.append(str); // appends a string
String completedString = builder.toString();
```

## 标准输入流
```java
import java.util.*
Scanner in = new Scanner(System.in);
System.out.print('What is ur name');
String name = in.nextline();  // 读取一行 以回车为分割符 允许空格
String firstName = in.next();
int age = in.nextInt();
```



