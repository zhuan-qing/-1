# 实验一 数据类型、运算符与表达式
## 一、实验目的
1、熟悉数据类型和运算符有哪些。
2、熟悉字符串函数的用法。
3、用之前学过的知识,创造自己的字符串的函数,并运行程序。
4、熟练掌握使用字符串函数的有关操作。
5、进一步熟悉 C 程序的编辑、编译、连接和运行的过程。

## 二、实验准备
1、复习字符串的概念和特性。
2、复习字符串的几种表示方式。
3、复习字符串数组和函数的内容。

## 三、实验内容
1、下面列出一些字符串函数:strlen、strcmp、strchr、strrchr、strstr、strcasestr、strcpy。
搜索信息了解到,使用字符串函数需要头文件 #include <string.h>

2、下面我们来研究strlen函数的用法
(1)strlen函数基本用法
运行下面的程序,请回答strlen函数的作用是什么?strlen函数和sizeof函数的区别是什么?
#include <stdio.h>
#include <string.h>
int main() {
	char a[] = { "hello" };
	printf("sizeof(a)=%lld\n", sizeof(a));
	printf("strlen(a)=%lld\n", strlen(a));
	return 0;
}
 
 运行结果如下:
sizeof(a)=6
strlen(a)=5
我们观察到,strlen函数和sizeof函数的作用都是返回字符串的长度,但是strlen函数返回字符串的长度不包括'\0'。

(2)创造自己的strlen函数
运行下面的程序,观察此方案是否可行。
#include <stdio.h>
#include <string.h>
//函数声明
int mylen(const char* a);
int main() {
	char a[] = { "hello" };
	printf("strlen(a)=%lld\n", strlen(a));
	printf("mylen(a)=%d", mylen(a));
	return 0;
}
//自定义strlen函数
int mylen(const char* a) {
	int cnt = 0;
	while (a[cnt] != '\0') {
		cnt++;
	}
	return cnt;
}

运行结果如下:
strlen(a)=5
mylen(a)=5
我们观察到,自己创造的mylen函数可以运行,并且和strlen的作用相同。

## 四、实验总结
(1)使用strlen函数计算出的字符串长度是字符串开头字符到终止空字符（也即'\0'）之间的字符数。
(2)经过查询资料,我们还了解到了其他字符串函数的用法,例如:
    ⅰ. strchr		在字符串中从左往右寻找单个字符
    ⅱ. strrchr		在字符串中从右往左寻找单个字符
    ⅲ. strstr		 	在字符串中找字符串
    ⅳ. strcasestr		在字符串中找字符串(忽略大小写)
