#数组
##定义
```
int[] a;
```
创建一个数字数组的时候，所有元素都初始化为0、boolean数组的元素会初始化为false、对象数组的元素会初始化为一个特殊值null。
##for each循环
```
for(variable:collection) statement;
```
打印数组所有元素
```
Arrays.toString(a);
```
##数组初始化
```
int[] a={1,2,3,4};
a=new int[]{1,2,3,4};
```
##数组拷贝
允许将一个数组变量拷贝给另一个数组变量，两个变量将引用同一个数组。
```
int[] a=Arrays.copyOf(b,b.length);
//第一个参数为数组，第二个参数为新数组的长度
```
##命令行参数
带一个String arg[]参数的卖弄方法，这个参数表名main方法将节接收一个字符串数组，也就是命令行参数。
程序名并没有存储在args数组中。
##排序
```
Arrays.sort(result);//采用快速排序的方法
//快速打印一个二维数组的数据元素列表
System.out.println(Arrays.deepToString(a)); //输出格式[[1,2],[3,4]]
```
