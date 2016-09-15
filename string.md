#字符串

Java字符串就是Unicode字符串，可以通过substring方法提取一个子串，第二个参数是不想复制的第一个位置，其优点是容易计算子串的长度。

拼接，允许使用”+“连接两个字符串

String，不能修改Java字符串中的字符，将String类对象称为不可变字符串。优点是编译器可以让字符串共享。

想检测两个字符串是否相等：equals();不区分大小写可以equalsIgnoreCase();

不能使用==运算符检测两个字符串是否相等。只有字符串常量是共享的，+或substring等操作产生的结果并不是共享的。
##构建字符串
每次拼接字符串都会构建一个新的String对象，耗时也浪费空间，使用StringBuilder类可以避免这个问题。
```
StringBuilder builder=new StringBuilder;
builder.append(str);
String complete=builder.toString();
```


