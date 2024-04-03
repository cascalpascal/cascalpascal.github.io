---
layout: post
author: Cascal Pascal
tags:
  - language
  - python
  - chobo python
---

>**Course**
>
>[[DevRoad] Python Developer: Chobo-Python](https://cascalpascal.github.io/devroad-python-developer)

>**Bookmarks**
>
>- [사칙연산](#사칙연산)
>
>- [Variable](#variable)
>
>- [List](#list)
>
>- [Interpreter와 Compiler](#interpreter와-compiler)

---

<br/><br/>


# 사칙연산

divmod() 함수를 써서 몫과 나머지를 한 번에 계산할 수 있다.

```
>>> divmod(50, 8)
(6, 2)
```

### 1.1.2 연습문제

Q) a = 550, b= 600일 때 c의 값은?

![python-1-1-2-exercise](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240312230104.png?raw=true)

A)

```
>>> import math
>>> math.sqrt(550**2+600**2)
813.9410298049853
```

<br>

# Variable

- ```변수 = 변수 * 값``` 형식의 문장은 ```변수 * = 값```으로 줄여서 표현할 수 있다.
  
```
>>> price = 5000
>>> price = price * 0.85
>>> price
4250.0
```

```
>>> price = 5000
>>> price *= 0.85
>>> price
4250.0
```

- 변수에 숫자가 아닌 문자열을 넣을 때는 따옴표를 붙여야 한다.

```
>>> a = 'flower'
>>> b = 'dog'
>>> a + b
flowerdog
```

### 1.2.1 연습문제

Q) 다운로드 속도가 초당 800kB이고 다운로드하는 데 걸린 시간이 110초라고 할 때, 다운로드한 파일의 크기는 몇 MB인가?

A)

```
>>> r = 0.8
>>> t = 110
>>> r * t
88.0
```


<br/><br/>


# List

- len() 함수는 리스트에 element가 몇 개 들어 있는지 보여준다.
  
```
>>> nickname = ['Mr.Frog', 'Froggy', 'Caspal', 'Lizardus']
>>> len(nickname)
4
```

- 특정 위치의 element를 나타낼 수 있다.

```
>>> nickname[2]
'Caspal'
```

- 리스트 안의 element를 지울 수 있다.

```
>>> nickname.remove('Caspal')
>>> nickname
['Mr.Frog', 'Froggy', 'Lizardus']
```

<br>

# Interpreter와 Compiler

컴퓨터에선 스위치의 on/off를 1과 0으로 나타내고, 스위치 하나를 bit라고 한다. 컴퓨터에 일을 시키려면 컴퓨터가 알아들을 수 있는 말로 지시를 내려야 한다. 이럴 때 쓰이는 프로그래밍 언어를 low-level language라고 한다. 반면에 사람이 쓰는 언어를 쓰는 프로그래밍 언어는 high-level language라고 한다. 그런데 high-level language도 프로그램을 작성한 다음에 컴퓨터가 알아들을 수 있게 번역하는 방법에 두 종류가 있다. 한마디 할 때마다 동시통역해주는 방식을 **Interpret** 라고 하고, 말하는 것을 처음부터 끝까지 듣고 나서 한꺼번에 바꿔주는 것을 **Compile** 방식이라고 한다. 파이썬은 우리의 명령을 한 줄씩 해석해서 일하는 Interpreter 방식이다.

### 1.6.1 연습문제

Q) 사용자에게 정수를 입력받아, 그 수의 제곱을 계산해 출력하는 파이썬 스크립트를 작성하시오.

A)

```python
print('제곱 계산하기 \n')  
leg = int(input('입력: '))  
value = (leg ** 2)  
print('출력:', value)
```


<br>


---

## Reference

[https://wikidocs.net/43](https://wikidocs.net/43)
