#equals方法

Object类中的方法用于检测一个对象是否等于另外一个对象，在Object类中，判断两个对象是否具有相同的引用。

- 自反性：对于任何非空引用x,x.equals(x) 返回true

- 对称性：对于任何引用x和y, x.equals(y)为true，y.equals(x)也相同

- 传递性：对于对于任何引用x、y和z，x.equals(y)为true，y.equals(z)为true，x.equals(z)也为true

- 一致性：x和y引用的对象没有发生变换，调用结果总是相同

- 对于任意非空引用x,x.equals(null),返回false。

一个成熟的equals检验：

```

public boolean equals(Object other){

 //是否引用同一个对象

 if(this==other) return ture;

 //检测other是否为空

 if(other==null) return false;

 //比较是否属于同一个类

 if(getClass()!=other.getClass()) return false; // 比较子类拥有统一的语义，用instanceof检测if(!(other instanceof ClssName)) return false;

 // other转换为相应的类类型变量

 ClassName otherObj=(ClassName) other;

 //对所有需要比较的域进行比较，==比较基本类型，使用equals比较对象域。

 return filed1==otherObj.filed1&& Objects.equals(fields2,otherObj.field2)

}

```

对于数组的比较，使用Arrays.equals方法检测相应的数组元素是否相等。
