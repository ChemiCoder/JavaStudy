#toString
toString 返回表示对象值的字符串。

打印数组： Array.toString() 
打印多维数组： Arrays.deepToString()
##重写toString
```
public String toString() {
    return getClass().getName()
            + "[name=" + name
            + ",salary=" + salary
            + ",hireDay=" + hireDay
            + "]";
}
```
