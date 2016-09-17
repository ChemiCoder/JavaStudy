#ArrayList
ArrayList 是一个采用类型参数（type parameter）的泛型类（generic class），需要

在实例化的时候指定其类型参数（即其需要存储的类类型），可选的指定初始容量。但在添加或删除元素时，具有自动调节其容量的功能

```

ArrayList<Employee> staff = new ArrayList<Employee>();

// Java7，可以省去右边的类型参数

ArrayList<Employee> staff = new ArrayList<>();

```

##区别

数组列表的容量`new ArrayList<>(100)`与设定数组的大小为100的区别：

数组分配100个元素的存储空间

容量为100是指具有存储100个元素的千里，但是在最初、甚至完成初始化构造之后，数组列表根本不含有其他元素。

##方法

- ensureCapacity(int size) 预估可能存储的元素数量

- size() 返回数组列表中包含的实际元素数量

- trimToSize() 将存储区域的大小调整为当前元素数量所需要的存储空间数目。

时使用

- set(int index, T obj) 设置、更新索引处元素

- add(T obj) 往数组列表添加元素

- add(int index, T obj) 在指定位置后添加元素

（使用add方法为数组添加新元素，不要使用set方法，它只能替换数组中已经存在的元素内容）

- get(int index) 访问索引处元素

- remove(int index) 删除一个元素

##类型化与原始数组列表的兼容性

将一个原始ArrayList赋给一个类型化ArrayList会得到一个警告，而且使用类型转换不仅无法避免，还会产生另一个警告信息。对此我们在没有发现违反规则的现象，将所有类型化数组泪飙转换为原始ArrayList对象。

可以使用@SuppressWarning("unchecked") 来标注这个变量能够接受类型转换。



