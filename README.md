# C-p84-C-4-
C语言学习笔记 p84 初识C语言（4）
//关键字static
static用来修饰变量和函数
1.修饰局部变量-静态局部变量
2.修饰全局变量-静态全局变量
3.修饰函数-静态函数


指针所指的内存不是硬盘内存
#include<stdio.h>
#include<string.h>
int main()
{
    int a=10;//向内存申请4个字节的空间
    printf("%P\n",&a);
    int* p=&a;//p是一个变量，存放地址的变量-指针变量
    printf("%p\n",p);
    *p=20//*-解引用操作符或者叫间接访问操作符
    printf("%d\n",a);//输出20，把a的值已经改了
    return 0;
}


int main()
{
    double d=3.14;
    double* pd=&d;
    printf("%d\n",sizeof(pd));//32位平台是4字节，64位是8个字节，和指针类型的int double之类无关的
    *pd=5.5;
    printf("%lf\n",d);
    printf("%lf\n",*pd);
    return 0;
}


结构体
描述复杂对象，比如人有身高，姓名，年龄，身份证号
//创建一个结构体类型
struct Book
{
    char name[20];//C语言程序设计
    short price;//55
};

int main()
{
//利用结构体类型创建一个该类型的结构体变量
    struct Book b1={"C语言程序设计“，55};
    printf("书名:%s\n",b1. name);
    printf("价格:%d\n",b1. price);
    b1. price=15;
    printf("修改后的价格：%d\n", b1.price);
    return 0;
}
这里的price是变量，结构体的变量是可以更改的
但是name他是一个数组名，更改需要用strcpy
strcpy(b1.name,)//strcpy函数有两个变量，第一个是拷贝目标，第二个是目的地
int main()
{
    struct Book b1={"C语言程序设计“，55};
    strcpy(b1.name,"C++");
    printf("%s\n",b1.name);
    return 0;
}



int main()
{
    struct Book b1={"C语言程序设计“，55};
    struct Book *pb=&b1;
    //利用pd打印出我的书名和价格
    printf("%s\n",(*pb).name);
    printf("%s\n",(*pb).price);
    return 0;
}
简化上一个main函数
int main()
{
    struct Book b1={"C语言程序设计“，55};
    struct Book* pb=&b1;
    printf("%s\n",pb->name);//这里表示pb指向的的那个变量的name，这里是pb指向b1
    printf("%d\n",pb->price);
    return 0;
}
//.  结构体变量.成员
//->  结构体指针->成员


