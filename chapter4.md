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

