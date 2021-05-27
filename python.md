# 파이썬

참조 : https://wikidocs.net/book/1

```python
Python 3.9.5 (tags/v3.9.5:0a7dcbd, May  3 2021, 17:27:52) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> print("hello")
hello

#사칙연산+나머지
>>> 1+1
2
>>> 2-1
1
>>> 2*3
6
>>> 4/2
2.0
>>> 4%3
1
>>> 10/3
3.3333333333333335
>>> 10//3
3

#int형 계산
>>> 3//10
0
>>> 10//3
3

#키워드
>>> a = True
>>> a
True
>>> b = False
>>> b
False

#변수 사용
>>> a=4
>>> b=3
>>> a/b
1.3333333333333333

#문자열 '' "" 둘다 사용 가능
>>> message = 'hello'
>>> message
'hello'
>>> message = "welcome"
>>> message
'welcome'
>>> msg = "I'm a boy"
>>> msg
"I'm a boy"

#문자열+int형은 에러 문자열*int는 가능
>>> "hello"+2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
>>> "hello"+"2"
'hello2'
>>> "hello"*3
'hellohellohello'
```



## 1. 문자열

#### 1. 문자열 슬라이싱

![img](https://wikidocs.net/images/page/2838/02.09.png)![img](https://wikidocs.net/images/page/2838/02.10.png)

```python
>>> message = "hello world"
>>> message
'hello world'
>>> message[1]
'e'
>>> message[:5]
'hello'
>>> message[:4]
'hell'
>>> message[6:]
'world'
>>> message[-6:]
' world'
>>> message[-5:]
'world'
>>> message[-5:-2]
'wor'
```



#### 2. 문자열 길이 : len

```python
>>> len(message)
11
```



#### 3. 문자열 입력

```python
>>> result = input("입력하시오")
입력하시오 안녕
>>> result
' 안녕'
```



#### 4. casting

```python
>>> a = input("입력: ")
입력: 10

#문자열->숫자
>>> b = int(a)
>>> b
10
>>> a
'10'
>>> a*10
'10101010101010101010'
>>> b*10
100

#숫자->문자열
>>> b=str(b)
>>> b
'10'
>>> b*10
'10101010101010101010'

```



#### 5. format() 함수 : 형식을 갖춘 문자열을 만들 때 사용

"{:}".format()

: 가 의미하는게 조건을 주겠다는 말임

![img](https://t1.daumcdn.net/cfile/tistory/996C663F5F5048921D)

이렇게 인덱스도 되고 변수도 된다.

```python
>>> a = "My name is {0}. I am {1} years old.".format('maeng',40)
>>> a
'My name is maeng. I am 40 years old.'

# 변수로 대입하기
s3 = 'number : {num}, gender : {gen}'.format(num=1234, gen='남')
print(s3)
```

그외 여러가지

참조 : https://blockdmask.tistory.com/424 



#### 6. is함수





#### 7. in 연산자 : 원하는 부분이 문자열 안에 존재하는지 확인

```python
>>> a = "Good Morning"
>>> "Good" in a
True
>>> "X" in a
False
>>> "G" in a
True
```



#### 8. split() 함수 : 매개변수로 입력한 문자열을 기준으로 원본 문자열을 나눠 리스트를 만든다.

파이썬은 배열이 list가 기본형이다.

```python
>>> a = "apple, orange, kiwi"
>>> b = a.split(",")
>>> b
['apple', ' orange', ' kiwi']
>>> type(b)
<class 'list'>
```





## 2. 반복문, 조건문

:과 들여쓰기가 {} 역할을 한다

```python
for letter in 'Hello':
    print(letter)
    pass   
H
e
l
l
o
```



`end = " "` :  다음줄로 넘기지 않고 그 줄에 계속해서 출력하기 위해서이다.

```python
numbers = [1,4,6,8]
for num in numbers:
    print(num, end = " ")
    pass
    
1 4 6 8 
```



range(숫자) : 0~숫자-1까지

```python
for i in range(1, 10):
    if(i%2 == 0): 
        print(i, end = " ")
        pass
    pass
    
0 2 4 6 8 
```



## 함수

```python
def 함수이름(매개변수):
    <수행할 문장>
    ...
	return 결과값

def add(a, b): 
    result = a + b 
    return result
```



여러 개의 입력값을 받는 함수

> *는 포인터라고 생각하면됌. 저기 주소를 가져와서 여러개 입력 받을 수 있음

```python
def add_many(*args):
	result = 0;
	
```



여러 개의 출력값을 갖는 함수

```python
def add_and_mul(a,b);
	return a+b, a*b
	
result1,result2 = add_and_mul(3,4)

result1은 7 result2는 12
```





## 파일 읽고 쓰기

### 1. 쓰기

```python
# 파일 만듬
file = open("new_text.txt","w")
# 파일에 데이터 입력
for i in range(1,11):
    data = "{}번째 줄입니다.\n".format(i)
    file.write(data)
    pass
file.close()
```

<img src="./img/text.png" style="zoom:50%;" />



### 2. 읽기

```python
file = open("Abc1115.txt","r")
lines = file.readlines()
file.close()

# 첫 줄 출력
print(lines[0])
# 몇줄이냐?
print(len(lines))

# 모든 줄 출력
for line in lines:
    print(line)
    pass
```

결과값

```python
==================== RESTART: C:/dev/dev/test_py/example2.py ===================
990001addx 17 29 16 49 43154CAC
1000

990001addx 17 29 16 49 43154CAC

990002stch 30  9 48 25 81193CAA

990003gali 93 60  6 84 36279ACA

...
```



## 모듈 불러오기

우리가 만든 mod1.py 파일, 즉 모듈을 파이썬에서 불러와 사용하려면 어떻게 해야 할까?

먼저 다음과 같이 명령 프롬프트 창(cmd)을 열고 mod1.py를 저장한 디렉터리로 이동한 다음 대화형 인터프리터를 실행한다.

`mod1.py`

```python
def add(a,b):
    return a+b

def sub(a,b):
    return a-b
```

`cmd`

``` cmd
# 이렇게 파이썬으로 드감
C:\dev\dev\test_py>python
Python 3.9.5 (tags/v3.9.5:0a7dcbd, May  3 2021, 17:27:52) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.

# mod1.py를 불러오기
>>> import mod1

# 함수 사용
>>> print(mod1.add(3,4))
7
>>> print(mod1.sub(3,4))
-1
>>> exit()
```



`mod1.py`

```python
# mod1.py 
def add(a, b): 
    return a+b

def sub(a, b): 
    return a-b

print(add(1, 4))
print(sub(4, 2))
```

`cmd`

단지 mod1.py 파일의 add와 sub 함수만 사용하려고 했는데 import mod1을 수행하는 순간 mod1.py가 실행이 되어 결괏값을 출력한다

``` cmd
C:\dev\dev\test_py>python
Python 3.9.5 (tags/v3.9.5:0a7dcbd, May  3 2021, 17:27:52) [MSC v.1928 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import mod1
5
2
```



이러한 문제를 방지하려면 mod1.py 파일을 다음처럼 변경해야 한다.

`mod1.py`

```python
# mod1.py 
def add(a, b): 
    return a+b

def sub(a, b): 
    return a-b

if __name__ == "__main__":
    print(add(1, 4))
    print(sub(4, 2))
```

`cmd`

``` cmd
>>> import mod1
>>>
```



**`__name__` 변수란?**

파이썬의 `__name__` 변수는 파이썬이 내부적으로 사용하는 특별한 변수 이름이다. 만약 `C:\doit>python mod1.py`처럼 직접 mod1.py 파일을 실행할 경우 mod1.py의 `__name__` 변수에는 `__main__` 값이 저장된다. 하지만 파이썬 셸이나 다른 파이썬 모듈에서 mod1을 import 할 경우에는 mod1.py의 `__name__` 변수에는 mod1.py의 모듈 이름 값 mod1이 저장된다.