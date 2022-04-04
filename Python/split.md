### 문자열을 나눠서 리스트로 만드는 함수

함수의 모양
문자열.split()
문자열.split('구분자')
문자열.split('구분자', 분할횟수)
문자열.split(sep='구분자', maxsplit=분할횟수)

-sep='구분자'
 기본값은 none 이며 이때는 띄어스기 엔터를 기준으로 나눔
 문자열.split(sep=',') 라고 한다면 ','를 기준으로 나눔
 
 -maxsplit='분할횟수'
 기본값은 -1이며 이때는 자를 수 있을 때 까지 자름
 앞에 sep파라미터가 없다면 사용할 수 없음
 ```
 >>> a = 'hello world'
>>> a.split()
['hello', 'world']
>>> a.split(2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: must be str or None, not int
```
sep를 지정하지 않아서 오류가 나오는 모습


예시
```
>>> b = 'apple, pineapple, peanut'
>>> b.split('a')
['', 'pple, pine', 'pple, pe', 'nut']
>>> b.split('a', 2)
['', 'pple, pine', 'pple, peanut']
>>> c = b.split('a')
>>> c
['', 'pple, pine', 'pple, pe', 'nut']
>>> c[2]
'pple, pe'

```
