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
>- [while 반복문](#while-반복문)
>- [조건문](#조건문)
>- [and/or 연산자](#and/or-연산자)
>- [for 반복문](#for-반복문)
>- [match-case](#match-case)
>- [for-else와 while-else](#for-else와-while-else)

---


<br>

# while 반복문

## while 문

```1, 2, 3, …, 8, 9, 10```를 다음과 같이 while 반복문을 이용하여 출력할 수 있다.

```python
num=1
while num<=10:
    print(num)
    num=num+1
```


### 2.1.1 연습문제

Q) ```input()```으로 사용자로부터 정수 한 개를 입력 받고, 그 숫자를 숫자 크기만큼 반복해서 출력하는 while문을 사용한 파이썬 스크립트를 작성하시오.

A)
```python
num = int(input())

i = 0
while i < num:
    print('', num)
    i += 1
```

### 2.2.2 연습문제

Q) 정수 한 개를 입력 받아, 1부터 입력 받은 수까지 각각에 대해 제곱을 구해 프린트하는 while문을 사용한 프로그램을 작성하시오.

A)
```python
num = int(input())

i = 1
while i <= num:
	print('',i**2)
	i += 1
```

### 2.2.3 연습문제

Q) 고무 공을 100미터 높이에서 떨어뜨리는데, 이 공은 땅에 닿을 때마다 원래 높이의 3/5만큼 튀어오른다. 공이 열 번 튈 동안, 그때마다 공의 높이를 계산하시오.

A1)

```python
num = 100
jump = 3/5

i = 1
while i <= 10:
	print(i, num*jump**i)
	i = i + 1
```

출력:

```
1 60.0
2 36.0
3 21.599999999999998
4 12.959999999999999
5 7.775999999999998
6 4.665599999999999
7 2.799359999999999
8 1.6796159999999993
9 1.0077695999999996
10 0.6046617599999997
```

다음과 같이 ```round()```함수를 사용하여 소수점 아래 3자리까지 출력할 수 있다.

```python
num = 100
jump = 3/5

i = 1

while i <= 10:
	answer = num*jump**i
	print(i, round(answer, 3))
	i = i + 1
```

출력:

```
1 60.0
2 36.0
3 21.6
4 12.96
5 7.776
6 4.666
7 2.799
8 1.68
9 1.008
10 0.605
```

### 2.2.4 연습문제

Q) 다음 코드의 출력값을 예상하시오.
```python
number = 358

rem = rev = 0
while number >= 1:
    rem = number % 10
    rev = rev * 10 + rem
    number = number // 10

print(rev)
```

A)

while문 첫 번째 바퀴: rem = 8, rev = 8, number = 35

while문 두 번째 바퀴: rem = 5, rev = 8x10+5 = 85, number = 3

while문 세 번째 바퀴: rem = 3, rev = 853, number = 0

while문 종료.

따라서, 답은 853.

<br>

---

# 조건문

## 파이썬의 if와 else

```python
a = 1234 * 4
b = 13456 / 2

if a > b: # 만약 a가 b보다 크면
	print('a') # 'a'를 출력한다.
else: # 그렇지 않으면 
	print('b') # 'b'를 출력한다.
```

## elif

```elif```를 사용해 여러 개의 조건을 작성할 수 있다.

```python
c = 15 * 5
d = 15 + 15 + 15 + 15 + 15

if c > d:
    print('c is greater than d')
elif c == d:
    print('c is equal to d')
elif c < d:
    print('c is less than d')
else:
    print('I don\'t know')
```

## 나머지 계산을 이용하는 if문

```python
a = 48
b = 4

if a % b == 0:
    print(f'{a}는 {b}로 나누어 떨어집니다.')
elif a % b != 0:
    print(f'{a}는 {b}로 나누어 떨어지지 않습니다.')
```

## 조건에 따라 반복문 중단하기

```break```를 사용하면 반복문에서 빠져나올 수 있다.

```python
max = 10 

while True: 
    num = int(input()) 
    if num > max:
        print(num, 'is too big!') 
        break
```

### 2.2.1 연습문제

Q) ```input()```을 사용해 사용자로부터 입력 받은 값을 한글로 출력하는 프로그램을 작성하시오. 단, 사용자는 1 이상 3 이하의 정수 중 하나를 입력한다고 가정한다.

A)
```python
num = int(input())

if num == 1:
    print('일')
elif num == 2:
    print('이')
elif num == 3:
    print('삼')
else:
    print('오류')
```

### 2.2.2 연습문제

Q) 백만 이상의 숫자를 입력받았을 때 1~10만자리 숫자를 생략하고 ‘M’을 붙여서 출력하게 코드를 작성하시오

A)

```python
num = int(input())
result = str(num)

if num >= 1000000:
    result = str(num // 1000000) + 'M'
elif num >= 0:
    pass

print(result)
```


### 2.2.3 연습문제

Q) ```input()```으로 사용자로부터 입력 받은 정수를 계속 더해가다가, 음수가 입력되면 중단하고 그 전까지 계산한 값을 출력하는 스크립트를 작성하시오.

A)
```python
value = 0

while True:
    num = int(input())
    if num >= 0:
        value = num + value
    else:
        print(value)
        break
```

### 2.2.5 연습문제

Q) 그레고리력의 윤년 규칙은 다음과 같다. 이 규칙에 따라, 연도를 입력 받아 윤년인지 아닌지 출력하는 스크립트를 작성하시오.

![Pasted image 20240320225008.png](https://github.com/cascalpascal/cascalpascal.github.io/blob/master/assets/images/favicon/Pasted%20image%2020240320225008.png?raw=true)

A)

```python
year = int(input())
leap = None

if year % 4 == 0:
    if year % 100 == 0:
        if year % 400 == 0:
            leap = True
        else:
            leap = False
    else:
        leap = True
else:
    leap = False

if leap == True:
    print(f'출력 연도 {year}년은 윤년입니다.')
else:
    print(f'출력 연도 {year}년은 평년입니다.')
```

<br>


# and/or 연산자
## if 문에 and/or를 사용

```python
s = 'banana'

if 'a' in s:
    if 'b' in 'banana':
        print('banana에는 a도 있고 b도 있어요!')
```

위의 스크립트를 and를 사용하여 다음과 같이 줄일 수 있다.

```python
if 'a' in s and 'b' in s:
    print('banana에는 a도 있고 b도 있어요!')
```

## if 문 없이 and/or만 사용

```
>>> 'a' in s
True
>>> 'b' in s
True
>>> 'c' in s
False
```

위의 bool 값을 다음과 같이 변수에 넣을 수 있다.

```
>>> a_in_s = 'a' in s 
>>> a_in_s 
True
```

## and/or 연산 순서

파이썬에서는 and/or의 왼쪽 항을 먼저 계산하고, 오른쪽 항은 필요할 때만 계산한다.

예를 들어, 아래 스크립트에선 0인 b 값을 분모로 하여 나눗셈을 시도하기 때문에 오류가 발생한다.

```
>>> a = 3
>>> b = 0
>>> a / b 
Traceback (most recent call last): File "<stdin>", line 1, in <module> ZeroDivisionError: division by zero
```

하지만 이 나눗셈을 아래처럼 and의 오른쪽 항에 넣으면 오류가 생기지 않는다. 이는 파이썬이 왼쪽 항에서 이미 결과가 나오므로 오른쪽 항은 계산하지 않고 넘어가기 때문이다.

```
>>> (a * b) > 0 and (a / b) > 0 
False
```

### 2.2.7 연습문제

Q) 미국과 달리, 우리나라에서는 보통 1955~1963년생을 ‘베이비붐 세대’로 본다. 사용자가 한국인인지에 따라 세대를 구분할 수 있게 스크립트를 작성하여라. 베이비붐 세대는 1963년생까지는 미국인과 한국인 모두 베이비붐 세대이므로 국적을 묻지 않아도 되고, 1964년생이면서 미국인일 경우 베이비붐 세대이다.

A)
```python
year = int(input('What year were you born? '))
gen = None

if year <= 1924:
    gen = 'the Greatest Generation'
elif year <= 1945:
    gen = 'the Silent Generation'
elif year <= 1963 or (year<= 1964 and input("Are you American?(y/n)").lower()[0] == 'y'):
    gen = 'a baby boomer'
    
print(f"You're {gen}.")
```

  > ```lower()```함수를 사용하여 영문 대문자를 소문자로 바꾼 값을 돌려준다.


<br>


# for 반복문

for문은 sequence를 이용해서 원하는 명령을 반복할 때 쓰인다. for문을 이용하여 list의 elements와 문자열 길이를 출력하는 스크립트를 아래와 같이 작성하였다.

```
>>> nickname = ['Mr.Frog', 'Froggy', 'Caspal', 'Lizardus']
>>> for x in nickname:
...	print(x, len(x))
```

 출력은 아래와 같다.

```
Mr.Frog 7
Froggy 6
Caspal 6
Lizardus 8
```

## range()

```range()```는 괄호 내의 인자의 범위 안의 정수들을 만들어준다.

```
>>> list(range(2,7))
[2, 3, 4, 5, 6]
```

for문에  ```range()```를 다음과 같이 사용하면 코드를 줄일 수 있다.

```
>>> a = [4, 5, 6, 7]
>>> for i in a:
...     print(i)
...
```

위의 리스트를 사용한 예제는 아래의 ```range()```를 사용한 예제와 출력이 같다.

```
>>> for i in range(4, 8):
...     print(i)
...
```

### 2.3.1 연습문제

Q)  사용자로부터 정수를 한 개 입력 받아, 그 숫자의 크기만큼 그 숫자를 반복해서 출력하는 파이썬 스크립트를 작성하시오. for문을 사용하시오.

A)
```python
num = int(input())

for i in range(num):
    print('',num)
```

### 2.3.2 연습문제

Q) 사용자로부터 정수를 한 개 입력 받아 1부터 입력 받은 수까지 각각에 대한 제곱을 구해 출력하는 스크립트를 작성하시오.

A)
```python
num = int(input())

for i in range(1, num + 1):
    print(i, i**2)
```

### 2.3.3 연습문제

Q) 프로그램은 먼저 최소와 최대의 안전 온도를 나타내는 두 개의 정수를 읽는다. 그 다음에, 장치가 제공하는 온도(정수)를 계속 읽는다. 화학 반응이 완료되면 장치는 끝을 알리는 `-999`를 보낸다. 기록된 온도가 올바른 범위에 있을 경우(최솟값 또는 최댓값과 같아도 된다) `Nothing to report`를 표시해야 한다. 하지만 온도가 위험 수준에 도달하면 `Alert!`를 표시하고 온도 측정을 중단한다(장치가 온도값을 계속 보내더라도).

A)
```split()```을 사용하여 문자열을 분할한 리스트를 얻을 수 있다. ```input()```로 문자열을 입력받을 때에도, 문자열을 분할했을 때 리스트 원소가 몇 개가 될지 미리 정해져 있다면 ```split()```으로 얻은 결과를 바로 변수에 할당할 수 있다. 원소 개수를 미리 알 수 없다면 for문을 이용해야 한다.

```python
temp = input().split()

min = int(temp[0])
max = int(temp[1])

rec = int(input())

while rec != -999:
    if rec in range(min, max):
        print('Nothing to report')
        rec = int(input())
    else:
        print('Alert!')
        break
```

출력:
```
30 60
31
Nothing to report
32
Nothing to report
33
Nothing to report
65
Alert!
```


<br>


# match-case

## 홀수, 짝수 판별

```python
for n in range(1, 6):
    match n % 2:
        case 0:
            print(f"{n} is even.")
        case 1:
            print(f"{n} is odd.")
```

위의 코드는 1부터 6까지 정수에 대하여, 각각이 홀수인지 짝수인지 출력하는 스크립트이다. ```n```을 2로 나눈 나머지가 0이면 짝수, 1이면 홀수라고 출력한다.

```
1 is odd.
2 is even.
3 is odd.
4 is even.
5 is odd.
```

## FizzBuzz

피즈 버즈 플레이어는 자기 차례가 되면 숫자를 증가시키되, 3으로 나누어 떨어지는 숫자는 ‘피즈(Fizz)’로, 5로 나누어 떨어지는 숫자는 ‘버즈(Buzz)’로 바꾼다.

```python
for n in range(1, 16):
    match (n % 3, n % 5):
        case (0, 0):
            print("FizzBuzz")
        case (0, _):
            print("Fizz")
        case (_, 0):
            print("Buzz")
        case _:
            print(n)
```

```match()```안에 ```n % 3```과 ```n % 5```는 두 개의 식이 있고, 그 아래의 ```case```에서 각각을 평가한다. ```case(0, 0)```은 3으로 나눈 나머지도 0이고, 5로 나눈 나머지도 0인 경우를 가리킨다. 따라서 'FizzBuzz'를 출력한다. ```case_```에서 밑줄(```_```)은 아무 값이나 상관없다는 뜻이므로, 3으로도, 5로도 나누어 떨어지지 않는 경우를 가리킨다. ```case(0, _)```은 3으로 나눈 나머지가 0인 경우를 말하며 'Fizz'를 출력한다. ```case(_, 0)```은 5으로 나눈 나머지가 0인 경우를 말하며 'Buzz'를 출력한다. 출력 결과는 다음과 같다.

```
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
```


<br>


# for-else와 while-else

## for-else

```python
for x in [1, 2, 3]:
    print(x)
    if input() == 'stop':
        break
else:
    print("리스트의 원소를 모두 출력했어요")
```

## while-else

```python
countdown = 5

while countdown > 0:
    print(countdown)
    countdown -= 1
    if input() == '중단':
        break
else:
    print('발사!')
```

<br>

---

## Reference
[https://wikidocs.net/55](https://wikidocs.net/55)
