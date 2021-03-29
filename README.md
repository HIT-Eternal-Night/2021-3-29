# 2021-3-29
对字符串函数的学习理解
1、strlen：    size_t strlen(const char*s);
功能：返回s的字符串的长度（不包括结尾的0）
#include <stdio.h>
#include <string.h>

int mylen(const char* s)
{
	int idx = 0;
	while (s[idx] != '\0')
	{
		idx++;
	}
	return idx;
}

int main(int argc,char const*argv[])
{
	char line[] = "Hello";
	printf("mylen  = %lu\n", mylen(line));
	printf("strlen = %lu\n",strlen(line));
	printf("sizeof = %lu\n",sizeof(line));
	return 0;
} 
这里我们写了一个功能和strlen一样的函数，来说明其工作原理。

2、strcmp：int strcmp(const char* s1,const char*s2);
功能：比较两个字符串，并返回值：
0：s1 == s2   1：s1 > s2   -1：s1 < s2
#include <stdio.h>
#include <string.h>

int mycmp(const char* s1,const char* s2)
{
	while ( *s1 == *s2 && *s1 != '\0')
	{
		s1++;
		s2++;
	}
	if (*s1 - *s2 > 0)
	{
		return  1;
	}
	else
	{
		return -1;
	}
}

int main(int argc,char const*argv[])
{
	char s1[] = "abc";
	char s2[] = "abc ";
	printf("%d\n",strcmp(s1,s2));
	printf("%d\n", mycmp(s1,s2));	
	return 0;
} 
这里我们写了一个功能和strcmp一样的函数，来说明其工作原理。
注意在不同的编译器上，函数的返回值可能为s1与s2的ASCII码差值
