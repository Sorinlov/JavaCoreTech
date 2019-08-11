## 类的结构
```
class Employee{
  //instance variable 类中需要操作的变量
  
  public String company; //对所有类可见
  String department; //对本包可见 不需要修饰符
  private String name; //仅对本类可见
  private double salary;
  protected LocalDate hireDay; //对本包和所有子类可见 子类可直接访问不需要调用方法
  
  
  private static int id = 1;
  //静态域 属于类的域
  
  //constructor
  public Employee(String n, double s, int year, int month, int day){
    name = n; // this.name = n
    salary = s;
    hireDay = LocalDate.of(year, month, day);
  }
  
  //调用另一个constructor
  public Employee(double s){
    this("Employee #" + id, s);
    id++;
  }
  
  //初始化块
  {
    id = nextId;
    nextId++;
  }
  
  // methods
  
  
}
```

## 类的访问权限
```java
class Emplopyee{
  public boolean equals(Employee other){
    return name.equals(other.name);
  }
}

if(harry.equals(boss))
```
harry.equals() 可以访问harry的私有域 也可访问boss的私有域 因为equals属于Employee类 可访问其任何一个对象的私有域

## 类的继承
```java
public class Manager extends Emplyee{
  
  //子类构造器
  public Manager(String name, double salary, int year, int month, int day){
    super(name, salary, year, month, day); //调用超类构造器
    bonus = 0;
  }
  //this两个用途，一是调用隐式参数，二是调用该类其他构造器；super两个用途，一是调用超类方方法，二是调用超类构造器
  
  //增加域和方法
  private double bonus;
  public void setBonus(double bonus){
    this.bonus = bonus;
  }
  //覆盖超类方法
  public double getSalary(){
    double baseSalary = **super**.getSalary();
    return baseSalary + bonus;
  }
}
```
## 多态
```java
staff[0] = new Manager();
staff[1] = new Employee();
staff[2] = new Employee();

for (Employee e : staff)
  System.out.println(e.getName() + " " + e.getSalary());
  
//staff[0] 不能实现多态 会报错
```
e可以只是多种实际类型 称为多态；自动选择调用哪个方法的现象成为动态绑定

## final类 组织继承
```
public final class Excutive extends Manager{
}
```

## 强制类型转换
```
Manager boss = (Manager) staff[0]; //将manger转换成employee再转回去 可以实现
Manager boss = (Manager) staff[1]; //error 进行向下的类型转换 会报错
```

## 抽象类
```
public abstract class person{
  private String name;
  public Person(String name){
    this.name = name;
  }
  public abstract String getDescription(); //抽象方法
  public String getName(){
    return name;
  }
}

## hashcode
## toString

## 泛类型
* 采用类型参数的泛类型
* 尖括号将类型括起来
```
ArrayList<Employee> staff = new ArrayList<Employee>(); //右边尖括号中的类可省略不写

```
