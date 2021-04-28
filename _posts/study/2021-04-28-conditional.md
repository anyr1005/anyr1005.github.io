---
layout: post
title:  "[C++] 조건문(if-else, switch)"
subtitle:   "조건문 정리"
categories: study
tags: C++
comments: true
---
## 개요
> 조건문인 if-else문과 swich문에 대해 정리<br/>
(공부한 내용을 정리하는 것이라 부족하거나 잘못된 부분이 있을 수 있습니다.)

- 목차
    - [조건문](#조건문)
	- [if-else문](#if-else문)
    - [switch문](#switch문)


## 조건문
---
주어진 조건이 참인지 거짓인지에 따라 서로 다른 문장을 실행하게 된다. 

조건문의 종류에는 if-else문과 switch문이 있다.

***

## if-else문
---
if-else문은 다음과 같은 구조이다.

```c++
if(//조건식)
{
    //조건식이 참이면 실행할 문장
}
else
{
    //참이 아닐 경우 실행할 문장
}
```
### -예제-

```c++
#include<iostream>

using namespace std;

int main()
{
	int x = 1;
	int y = 2;
	if (x > y)
	{
		cout << "x는 y보다 큽니다." << endl;
	}
	else if (x < y) //또 다른 조건이 있을 경우 else if를 사용한다.
	{
		cout << "x는 y보다 작습니다." << endl;
	}
	else
	{
		cout << "x는 y와 같습니다." << endl;
	}

	return 0;
}
```
![그림1](../../../../assets/img/study/conditional1.jpg){:width="400"}
***

## switch문
---
switch문은 다음과 같은 구조이다.
```c++
int num = 1;
switch(num)
{
case 0:
    //num가 0이면 실행
break;

case 1:
    //num가 1이면 실행
break;

default:
    //위의 모든 조건에 거짓일 경우 실행
break;
}
```

if-else문과 다르게 switch문은 관계연산자 중 == 로만 비교를 하게 된다.

위의 예시에서는 int 자료형을 예시로 들었지만 char 형 등 값을 비교할 수 있는 것은 모두 가능하다.

```c++
char ch = 'a';
switch(ch)
{
case 'a':
    //ch == 'a' 이면 이 부분 실행
break;
case 'b':
    //ch == 'b' 이면 이 부분 실행
break;
case 'c':
    //ch == 'c' 이면 이 부분 실행
break;
default:

break;
}

//이런 수식도 가능하다
int x = 1;
int y = 2;
switch (y - x)
{
case 1:
	//1이면 여기 실행
	break;
case 2:
	//2이면 여기 실행
	break;
default:
	break;
}
```
<br/>

### -예제-

```c++
#include<iostream>

using namespace std;

int main()
{
	int num = 1;

	switch (num)
	{
	case 1:
		cout << "num은 1입니다." << endl;
	break;
	case 2:
		cout << "num은 2입니다." << endl;
	break;
	default:
		cout << "num은 1 혹은 2가 아닙니다." << endl;
	break;
	}
	return 0;
}
```
![그림2](../../../../assets/img/study/conditional2.jpg){:width="400"}

#### Switch 문은 case 뒤에 break를 반드시 해주어야한다!

위의 예제를 break를 해주지 않게 되면 다음과 같은 상황이 일어난다.
```c++
#include<iostream>

using namespace std;

int main()
{
	//x는 20, y는 30으로 설정
	int num = 1;

	switch (num)
	{
	case 1:
		cout << "num은 1입니다." << endl;
	break;
	case 2:
		cout << "num은 2입니다." << endl;
	default:
		cout << "num은 1 혹은 2가 아닙니다." << endl;
	}
	return 0;
}
```

![그림3](../../../../assets/img/study/conditional3.jpg){:width="400"}

break문이 없기 때문에 다음 case절의 문장들이 계속해서 실행되어 switch문의 끝까지 실행되게 된다.
그렇기 때문에 원하는 값을 얻기 위해서 case마다 꼭 break를 넣어주어야 한다.

***

#### [참고자료]
천인국, 『어서와 C++은 처음이지』, 인피니티북스(2018)