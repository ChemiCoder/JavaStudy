##一. 构造器

构造器的作用是构造并初始化实例对象。当创建一个对象时，系统为这个对象的属性进行初始化。

##二. 语法

```

class 类名

{

 变量声明;

 类的名称(参数列表)

 {

 方法体

 }

}

```

构造器和类要有相同的名字，同时避免在构造器中定义与实例域重名的局部变量。例如

```

class student

{

 private String name;

 private int studentID;

 //构造器

 public student(String n,int m){

 name=n;

 studentID=m;

 /*定义与实例域重名的局部变量

 *这种错误很难被发现

 String name=n;

 int studentID=m;

 */

 }

}

```

##三. 特点

 - 构造器和类具有相同的名字

 - 一个类可以有多个构造器

 - 构造器可以有0、1或多个参数

 - 构造器没有返回值和返回类型

 - 构造器不能被显示调用，总是与new运算符仪器被调用，在创建一个类的新队形的同时，系统会自动调用该类的构造器为新对象初始化。

在java的每个类中，至少要有一个构造器，没有定义的话，编译器将自动插入缺省的构造器。

这种默认初始化被所有数值类型设为`0`，布尔值为`false`，所有引用类型的属性设置为`null`

##无参数构造器

如果类中提供了至少一个构造器，但是没有提供无参数的构造器，构造对象没有提供参数就会被视为不合法。

```

class student

{

 private String name;

 private int studentID;

 //构造器

 public student(String name,int studentID){

 this.name=name;

 this.studentID=studentID;

 }

}

student=new student(); //产生错误

```

解决方法：可以为java类保留无参数的构造器，为一个类编写了有参数的构造器，同时建议为该类编写一个无参数的构造器。一般把构造器设置为public访问权限，设置为private是为了阻止其他类创建该类的实例。

##四.构造器重载和调用

###1.方法签名

一个方法的签名包括方法名、参数类型和个数，但不包括返回值。

类的定义中存在两个或两个以上的同名成员方法，为了使编译器能区分同名的成员方法，使同名方法的参数个数或参数的数据类型不同，从而使编译器能够挑选具体执行某个方法。

```

class student

{

 private String name;

 private String major;

 private String school;

 private int studentID;

 //构造器1

 public student(String name,int studentID){

 this.name=name;

 this.studentID=studentID;

 }

 //构造器2

 public student(String school){

 this.school=school;

 }

 //构造器3

 public student(String major,int studentID){

 this.major=name;

 this.studentID=studentID;

 }

}

```

###2.调用另一个构造器

```

class student

{

 private String name;

 private String major;

 private String school;

 private int studentID;

 //构造器1

 public student(String name,int studentID){

 this("大山高中") //调用另一个构造器

 this.name=name;

 this.studentID=studentID;

 }

 //构造器2

 public student(String school){

 this.school=school;

 }

```

###3.显式调用父类构造器

 当我们想调用超类的的某个方法，但是当前类也有相同的方法，这时可以使用`super`关键字(只是一个指示编译器调用超类方法的特殊关键字）。

```java

class A{

 public A(){

 System.out.print("A");

 }

}

class B extends A{

 public B(){

 super();//调用父类构造方法，打印A

 System.out.print("B");

 }

}

```
