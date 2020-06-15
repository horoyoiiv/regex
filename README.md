# regex
regex
## [Tutorial 사이트](https://regexone.com/lesson/wildcards_dot?)  
## 목차  



## 1. dot(.)  
* **any single character**를 받아 들인다.  
* 예제  
```
[+] abc.
[+] jce.
[+] kja.
[-] abcd
```
* dot(.)은 wildcard를 의미하기에, 진짜 .을 받아들이기 위해서 역슬래시(\)를 사용.  
```
...\.
```

## 2. square bracket [ ]  

* 대괄호 역시 **any single character**, 한 문자를 위한 것이다.  
* 하지만 이 한 문자를 위한 **후보군**을 대괄호 안에 넣을 수 있다.  
```
[abc] // a 혹은 b 혹은 c 한 문자 인정
```

* 예제  

```
[+] can
[+] man
[+] fan
[-] dan
[-] ran
[-] pan
```
* 아래와 같이 표현 가능  
```
[amf]an
```

## 3. hat ^  

* 특정 문자를 **배제**한다.  
* [] 와 함께 쓰여서  

* a,b,c 를 제외한 한 문자를 인정한다.  
```
[^abc] // []안의 세 문자 모두 배제한다.
```

```
[+] hog
[+] dog
[-] bog
```
```
[^b]og  
```

##  4. range -  
* 전부 다 열거하는 것이 아니라, **range**를 설정한다.  

* [A-Z] : 대문자 A부터 Z까지만 인정  
* [A-Za-z0-9] :대문자A-Z, 소문자a-z, 숫자 0-9 까지 한 문자 인정  

* 예제  
```
대문자로 시작하는 세 자리 문자열 받기
```

```
[A-Z]..
```

## 5. \w vs \W
 
1. **\w** : 알파벳과 숫자만 인정  
2. **\W** : 그외 문자만 인정  

## 6. \d vs \D  

1. **\d** : 숫자만 인정  
2 **\D** : 숫자 아닌 것만 인정  

## 7. 연속 {}  

* curly grace  
* z{3} : 세 개의 **연속**된 z  

```
z{3} // zzz
[abc]{3}  // a 혹은 b 혹은 c가 3번 연속 등장

a{2, 5} // a가 2번 이상 5번 이하 등장
```

## 8. 별(*)과 플러스(+)  

1. * : 0 혹은 그 이상  
2. + : 1 혹은 그 이상  

* 예제  
```
aaaabcc
aabbbbc
aacc
a
```
```
a[abc]+
```

## 9. 0 또는 1  

* **?** : 하나 있어도 되고 없어도 된다.  

* b? 의미 : b가 있을 수도 있고, 없을 수도 있다.  
```
ab?c // ab 도 되고, abc 도 된다.
```
* 예제  
```
file
files
files
```
```
files?
```


## 10. \s : whitespace  

* **whitespace** : space( ), tab(\t), new line(\n), carriage return(\r)  

* 이러한 whitespace는 **\s**로 처리된다.  
* 예제  
```
1.   abc
2.  abc
3.      abc
4.abc
```
```
\d\.\s+abc
```

## 11. ^시작과 끝의 $ dollar?  
* ^ : 줄의 **시작**을 의미한다.  

* $ : 줄의 **마지막**을 의미한다.  

* 예제  
* 줄은 Mission으로 시작하여 successful로 끝나야 한다.  
```
^Mission: successful$
```

## 12. ( ) 그룹  

```
[+] file_hello.pdf
[+] file_godd.pdf
[-] file_jelly.jpg
```

```
^(file.+)\.pdf$
```

## 13. pipe |  
* or 조건식  
* 예제  
```
[+] I love cats
[+] I love dogs
[-] I love cogs  
```

```
I love (cats|dogs)  // 붙여 써야 한다.  
```


































