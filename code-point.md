#代码点和代码单元

##代码点
指与一个编码表中的某个字符对应的代码值。
例如A在Unicode标准中的表示为U+0041，这个就是字母A的代码点。
##代码单元
在基本的多语言级别中，单个字符用16位表示，称为代码单元。
UTF-16由RFC2781规定，它使用两个字节来表示一个代码点。
length方法返回采用UTF-16编码表示的给定字符串所需要的代码单元数量。

得到实际的长度，即代码点数量：
```
codePointCount(0,str.length());
```
得到第i个代码点：
```
int index=greeting.offsetByCodePoints(0,i);
int cp=greeting.codePointAt(index);
```
```
public class Main {

 public static void main(String[] args) {

 String sentence = "\u03C0 \uD835\uDD6B";

 int lengthU = sentence.length();

 int lengthP = sentence.codePointCount(0, lengthU);

 System.out.println(lengthU); // 4个code units

 System.out.println(lengthP); // 3个code points



 int i = sentence.codePointAt(2); // i=2 true i=0,1,3 false i=4 out of bound

 boolean b = Character.isSupplementaryCodePoint(i);

 System.out.println(b);

 }

}

```
[字符编码笔记：ASCII，Unicode和UTF-8](http://www.ruanyifeng.com/blog/2007/10/ascii_unicode_and_utf-8.html)
[字符编码问题，UNICODE\UTF-8\UTF-16\UTF-32\UCS\ANSI\GBK\GB2312等乱七八糟的名词](http://www.cnblogs.com/skyaspnet/archive/2011/02/18/1957770.html)
