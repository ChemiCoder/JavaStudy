#hashCode方法

1. hashCode() 方法是由一个对象导出一个整型值。

2. hashCode() 定义在 Object 类中，因此每个对象都有一个默认的散列码,其值为对象的存储地址。

3. String 的散列码是由内容导出的

```

int hash = 0;

for (int i = 0; i < length(); i++) {

hash = 31 * hash + charAt(i);

}

return hash;

```

但是字符串缓冲有着不同的散列码，StringBuffer没有定义hashCode方法。

```

StringBuilder a=new StringBuilder("aa");

StringBuilder b=new StringBuilder("aa");

System.out.println(a.hashCode()); //366712642

System.out.println(b.hashCode()); //1829164700

```

4. 如果重新定义 equals 方法，就必须重新定义 hashCode 方法，因为x.equals(y)返回true，x和y的hashCode相等，以便用户可以将对象插入散列表。

5.使用null安全的 Objects.hashCode()，参数为null，返回0。更好的做法，使用Objects.hash并提供多个参数。

```

public int hashCode() {

 return Objects.hash(name, salary, hireDay);

}

```
