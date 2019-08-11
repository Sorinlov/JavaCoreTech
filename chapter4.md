## 类的结构
```
class Employee{
  private String name;
  private double salary;
  private LocalDate hireDay;
  //instance variable 类中需要操作的变量
  
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

