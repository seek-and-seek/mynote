数据类型

~~~c++
bool false/true   1bybe 256个数
  char a = 'a' //单引号表示字符  1byte
    int      4字节
    float 1.235e2 有效数字6-7位  4
    double 15-16位有效数字 8
    long long 8
    long double 16
    
 1Byte = 8bit
    //注意的点：
    10000000LL 表示它是long long 类型 防止它变成负数（表示符号的那一位也被占了来表示数，但因为他还是识别符号位，1表示负数）
    1234.5f //表示它一定为浮点数
~~~

输入，输出

~~~c++
#include<iostream>
#include<cstdio>
using namespace std;
int main(){
int a,b;
cin>>a>>b;
cout<<a+b<<endl;
    scanf("%d%d",&a,&b);
    printf("a+b=%d\na*b=%d\n",a + b,a *b);
    scanf("%.1f %.2f")//浮点数，b
        %c  //会读入空格 不能输入空格，cin会读入空格
        scanf("%lf"，&a); //double
    	print（"%lf",a）
    return 0;
}
long long %lld
//注意的点：scanf("%c%c",&a,&b);//会读入空格
~~~

四则运算

~~~c++
//注意
int a = 5 %2; 1
int b = -5 % 2; -1  //和正常的运算不一样’
    A++ //只对证书有效
    a += b a = a+b;
    a /=b
~~~

变量的强制转换

~~~c++
int a = (int)b;
下取整 
    //整数和char运算全部转变为整数
    //其他的也要注意
    如浮点数和整数
    //向大的转
~~~

~~~c++
#include<iostream>
cin>>
    cout<<
    scanf()
    printf()
~~~



~~~C++
#include<iostream>
using namespace std;
int main(){
    int num;
    int n[7] = {100,50,20,10,5,2,1};
    cin>>num;
    cout<<num<<endl;
    for(int i = 0;i<7;i++){
        printf("%d nota(s) de R$ %d,00\n",num/n[i],n[i]);
        num = num % n[i];
    }
    return 0;
}
//c++的数组必须先指定chan
~~~

