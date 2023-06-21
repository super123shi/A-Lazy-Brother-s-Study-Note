# c++循环嵌套语句

## 嵌套if语句

---


	
```c++
int main(){   嵌套if语句 
    int score = 0;
    cout<<"请输入分数"<<endl;

    cin>>score;

    cout<<"分数为"<<score<<endl;

    if(score>600)
    {

        cout<<"一本"<<endl;
        if(score>700)
        {
            cout<<"北大"<<endl;
        }
        else if(score>650)
        {
            cout<<"中大"<<endl; 
        }
        else
        {
            cout<<"普本"<<endl;
        }
    }
    else if(score>500)
    {
        cout<<"二本"<<endl;
    }
    else if(score>400) 
    {
        cout<<"三本"<<endl; 
    }
    else
    {
        cout<<"未考上"<<endl; 
     } 
   system("pause");
    return 0;
} 
```

---

###  嵌套if实例 

 	
 	//三只小猪称体重
	 

```c++
int main(){
     int n1=0;
     int n2=0;
     int n3=0;
     cout<<"请输入1猪的体重" <<endl;
     cin>>n1;
     cout<<"请输入2猪的体重" <<endl;
     cin>>n2;
     cout<<"请输入3猪的体重" <<endl;
     cin>>n3;
     cout<<"三只猪的体重分别是"<<n1<<"\n"<<n2<<"\n"<<n3<<"\n"<<endl;

     if(n1>n2) //n1比n2重 
     {
        if(n1>n3)//n1比n3重 
         {
            cout<<"n1重"<<endl; 
          } 
          else//n3比n1重 
          {
            cout<<"n3重"<<endl; 
          }
           }
     else//n2比n1重 
     {
        cout<<"n2重"<<endl;
      } 
        system("pause");
        return 0;
     }

 
```


##  三目运算符 
 //语法：式1 ？ 式2 ： 式3

 //如果式1的值为真，执行式2，并且返回式2的结果
 //如果式1的值为假，执行式3，并且返回式3的结果 

```c++
 int main()
 {
 	int a,b,c;
 	a=10;
 	b=20;
 	c=0;
 	c=(a>b?a:b);
 	//cout<<c<<endl;
 	
 	//三目运算符返回一个变量可以继续赋值
	(a>b?a:b)=200;
	cout<<"a="<<a<<endl;
	cout<<"b="<<b <<endl;
 	
 	system("pause");
 	return 0; 
 } 
```




##  switch 执行多条分支语句 

```c++
//语法：
 /*
 switch（）
 {
 	case 1:执行语句1;
	break;
	
	case 2:执行语句2;
	break;
	
	...
	
	default:执行语句3;
	break; 
  } 
  */
  
 int main()
 {
 	//给电影打分
	 //10~9 经典
	 //8~7 非常好
	 //6~5 一般
	 //5以下 不好看
	 
	 //提示用户给电影打分
	 cout<<"请给电影打分"<<endl;
	 
	 //用户开始打分
	 int score=0;
	 cin>>score;
	 cout<<"您的打分为："<<score<<endl; 
	 //根据打分来提示用户最后的结果
	  switch(score)
	  {
	  	case 10:
	  		cout<<"您认为是经典电影"<<endl;
	  		break;
	  	case 9:
	  		cout<<"您认为是经典电影"<<endl;
	  		break;
	  	case 8:
	  		cout<<"您认为该电影非常好"<<endl;
	  		break;
	  	case 7:
	  		cout<<"您认为该电影非常好"<<endl;
	  		break;
	  	case 6:
	  		cout<<"您认为该电影一般"<<endl;
	  		break;
	  	case 5:
	  		cout<<"您认为该电影一般"<<endl;
	  		break;
	  	default:
		    cout<<"您认为该电影不好看"<<endl;
	  		break;
	  		
	  }
	 //score只能是整型或者字符型
	  
 	system("pause");
 	return 0;
 }
```

---
## while

```c++

int main()
{

int num=0;
while(num<10)
{
	num++;
	cout<<num<<endl;
}
//	cout<<num<<endl;
	system("pause");
	return 0;
 } */


 int main(){
 	
 	
 	//添加一个随机种子，利用系统当前时间生成随机数
	srand((unsigned int )time(NULL)); 
 	
 	//猜数字游戏
	//系统生成随机数
	int num=rand() % 100+1; 

//玩家进行猜测

cout<<"请输入猜测的数字"<<endl;
int val=0;

//判断玩家的猜测

while(1)
{
cin>>val;
if(val>num)
{
	cout<<"猜测过大"<<endl;
	
}
else if(val<num)
{
	cout<<"猜测过小"<<endl;
}
else
{
	cout<<"猜对了"<<endl; 
}
}
//猜对退出游戏
//猜对 猜测结果 过大或过小，重返猜测步骤 
 	system("pause");//system("pause");按任意键结束
 	return 0;
 }
 
```


---
## do ...while
语法：
do{循环语句} while(循环条件)； 
 与while 的区别是先执行循环语句在执行循环条件 

```c++
int main()
{
	int n=0;
	do{
		cout<<n<<endl;
		n++;
	} while(n<10);
	system("pause");
	return 0;
}`
```

---
### do... while实例

利用do...while求三位数中的水仙花数
水仙花数：一个三位数，它的每个位上的数字的3次幂之和等于它本身
例如： 

```math
1^3+5^3+3^3=153
```
#### 解题思路：

获取个位：让这个三位数对10取模
获取十位：先对这个数对10取余，得到两位数，在对10取余
获取百位：直接对100取余

```c++
#include<iostream>
#include<stdlib.h>
#include<ctime>
using namespace std;

/*
水仙花数：一个三位数，它的每个位上的数字的3次幂之和等于它本身
例如： 1^3+5^3+3^3=153 
利用do...while语句 求所有的三位数重的水仙花数 
*/
int main()
{
	//先打印所有三位数
	int n=100;
	

    do	//从三位数中选取水仙花数 
    {
        int a=0;//个位 
        int b=0;//百位 
        int c=0;//十位 

        a=n%10;
        b=n/10%10;
        c=n/100;

        if(a*a*a+b*b*b+c*c*c==n)
        {
            cout<<n<<endl;
        }
        n++;
    } while(n<1000);

    system("pause");
    return 0;
    
 }
```


---
## for循环
/*
满足循环条件，执行循环语句
for(起始表达式；条件表达式；末尾循环体)
{
	循环语句； 
} 
*/

//敲桌子游戏：从1开始数到100，如果数字的个位含有7或者十位含有7，或者该数字是7的倍数 ，打印敲桌子，其余数字直接打印输出 

```c++

int main()
{
	/*先输出1-100
	从这些数字中找到特殊数字，改为敲桌子
	特殊数字
	
    7的倍数  可以整除7，对7取模为0 i%7==0
    个位有7  对10取模为7 i%10==7
    十位有7  对10整除为7i/10==7*/
    for(int i =1;i<101;i++)
    {

        if(i%7==0||i%10==7||i/10==7)//如果是特殊数字 打印 
        {
            cout<<"敲桌子"<<endl;
        }
        else
        {
            cout<<i<<endl;
        }
     } 

    system("pause");
    return 0;
    }
```
---

## 嵌套循环 



```c++
int main()
{
	//打印一行星星 
	 for(int i=0;i<10;i++)
	 {
	 	for(int j=0;j<10;j++){		 
	 		cout<<"* ";
		 }
		 cout<<endl;
	}
    system("pause");
    return 0;
 }
```
---
### 打印乘法表
乘法表相当于：
行数*列数=计算结果

	int main()
	{
		for(int i=1;i<10;i++)
		{
			for(int j=1;j<=i;j++)
			{
				cout<<j<<" * "<<i<<" = "<<j*i<<" ";
				
			}
			cout<<endl;//endl相当于\n 
		}
	    system("pause");
	    return 0;
	}
---
1 * 1 = 1
1 * 2 = 2 2 * 2 = 4
1 * 3 = 3 2 * 3 = 6 3 * 3 = 9
1 * 4 = 4 2 * 4 = 8 3 * 4 = 12 4 * 4 = 16
1 * 5 = 5 2 * 5 = 10 3 * 5 = 15 4 * 5 = 20 5 * 5 = 25
1 * 6 = 6 2 * 6 = 12 3 * 6 = 18 4 * 6 = 24 5 * 6 = 30 6 * 6 = 36
1 * 7 = 7 2 * 7 = 14 3 * 7 = 21 4 * 7 = 28 5 * 7 = 35 6 * 7 = 42 7 * 7 = 49
1 * 8 = 8 2 * 8 = 16 3 * 8 = 24 4 * 8 = 32 5 * 8 = 40 6 * 8 = 48 7 * 8 = 56 8 * 8 = 64
1 * 9 = 9 2 * 9 = 18 3 * 9 = 27 4 * 9 = 36 5 * 9 = 45 6 * 9 = 54 7 * 9 = 63 8 * 9 = 72 9 * 9 = 81

---
## 跳转语句
用来跳出循环或选择语句
break
continue
goto

### break
使用：出现在switch中，作用是终止case并跳出switch
出现在循环语句中，作用是==跳出当前的循环语句==
出现在嵌套循环中，跳出最内层的循环语句
### continue
在一个循环语句中==跳过本次循环中未执行的语句==

```c++
//嵌套循环 
int main()
{
	for(int i =0;i<101;i++)
	{
		//如果奇数输出，偶数不输出 
		if(i%2==0)
		{
			continue;
		 } 
		 cout<<i<<endl;
	}
	system("pause");
	return 0;
}
```