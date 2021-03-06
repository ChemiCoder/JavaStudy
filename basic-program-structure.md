# Java的基本程序设计结构

## 概述

Java对大小写敏感。类名不能使用Java保留字。类名以大写字母开头的名词，骆驼命名法。源文件的文件名必须与公共类的名字相同。

## 注释

```
// 单行注释
/**/ 多行注释
/**
*/ 自动生成文档
```

## 数据类型

### 整型

int 4字节
short 2字节
long 8字节
byte 1字节
长整型：后缀L
十六进制：0x
八进制：前缀0
二进制：0b
数字字面量加下划线：1\_000\_000

### 浮点类型

float 4字节double 8字节浮点数值不适用于禁止舍入误差的金融计算中。float类型的数值有后缀F。检测一个特定值是不是Double.NaN,

```
if(Double.isNaN(x))
```

### char类型

用于表示单个字符，通常用来表示字符常量。可以采用转义序列符`\u`表示Unicode代码单元的编码之后，还有一些用于表示特殊字符的转移序列符。
代码点：与一个编码表中的某个字符对一个的代码值。
代码单元：基本的多语言级别中，每个字符用16位表示
在Java中，char类型采用UTF-16编码描述一个代码单元。

### 变量

变量名必须是以字母开头的序列，字母包括\[a-zA-Z\] \_ $或在某种语言中代表字母的任何Unicode字符。
判断Unicode是否属于Java中的“字母”，Character类的**isJavaIdentifierStart**和**isJavaIdentifierPart**方法检测。尽量不要使用$.

变量名对大小写敏感，声明一个变量之后，必须用赋值语句对变量进行显示初始化，不能使用未被初始化的变量.
```
    int num=8;
    //也可以使用这种方式声明
    int num;num=8;
```
###常量
利用关键字final指示常量。
```
final int NUM=8;
```
关键字final表示这个变量只能被赋值一次，常量名使用全大写。某个常量可以在一个类中的多个方法中使用，将这些常量称为类常量，可以使用static final设置一个类常量。
```
public class ClassName
{ 
    public static final into NUM=8; 
    public static void main(String[] args)
        { 
            program statements 
        }
}

```
类常量的定义位于main方法的外部。
###运算符
自增运算符与自减运算符操作数不能是数值。有前缀和后缀的形式前缀，对变量先进行操作，然后再进行后续的步骤。支持三元操作符。
```
condition?expression1:expression2;
```
&&和|| 是短路操作。
###位运算
Math.sqrt();
Math.PI
####数值之间的转换
强制类型转换，语法格式在圆括号中给出想要转换的目标类型，后面紧跟待转换的变量名
```
double a=1.2354;
int b=(int) a; 
```


