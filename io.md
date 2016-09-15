#输入输出
## 读取输入
```
Scanner in=new Scanner(System.in);
String name=in.nextLine(); //输入行中有可能包含空格
String firstName=in.next(); //以空白符作为分隔符
int age=in.nextInt();
int money=in.nextDouble();
```
对于密码输入，使用Console类
```
Console cons=System.console();
String username=cons.readLine("userName:");
char[] password=cons.readPassword("password:");
```
但是如果你直接输入上面的代码，会报空指针异常,看一下stackOverflow上的解释。
>Whether a virtual machine has a console is dependent upon the underlying platform and also upon the manner in which the virtual machine is invoked. If the virtual machine is started from an interactive command line without redirecting the standard input and output streams then its console will exist and will typically be connected to the keyboard and display from which the virtual machine was launched. If the virtual machine is started automatically, for example by a background job scheduler, then it will typically not have a console.

```
##格式化输出
```
System.out.printf();
// %字符开始的格式说明符都用相应的参数替换，格式说明符尾部的转换符将指示被格式化的数值类型。
System.out.printf("hello,%s",name);
System.out.printf("%,.2f",1000/3.0); //3,333.33
```
可以使用晶态的String.format方法创建一个格式化的字符串而不是打印输出：
```
String message=String.format("%s",name);
```
java.util.Date 是 java.sql.Date 的父类（注意拼写）,前者是常用的表示时间的类，我们通常格式化或者得到当前时间都是用他。后者之后在读写数据库的时候用。
可以采用一个格式化的字符串指出要被格式化的参数索引，索引必须要紧跟%后面，并以$终止。
```
System.out.printf("%1$s %2$tB %2$te,%2$tY");
```
##控制流程
当在switch语句中使用没去常量时，不必再每个标签中指明枚举类，可以由switch的表达式确定
```
Size=a=...;
switch(a){
case Small: // no need to use Size.SMALL
    ...
    break;
}
```
###中断流程控制
**不带标签的break**，可以退出当前循环
**带标签的break**，标签必须放在希望跳出的最外层循环之前，并且必须紧跟一个冒号。
continue语句，中断正常的控制流程。将控制转移到最内层循环的首部。