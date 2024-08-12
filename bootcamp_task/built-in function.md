## 과제 내장함수    

    `iterable`:반복이 가능한타입 문자열 ,리스트 등등
`is_digit` : 문자열값이 정수값으로 바꿀 수 있으면 TRUE로 반환

`strip()` : 문자열에서 앞뒤공백제거 

`split()` : 문자열을 ()기준에서 리스트로 쪼개줌 

`''.join()` : 리스트를 ''기준에서 문자열로 바꿔줌

```python
a = "     안 녕 하 세 요        "
a.is_digit() >> False
a.strip(' ') >> "안 녕 하 세 요"
a.split(" ") >>  [''....'안','','녕','',...]
''.join(a) >> "안녕하세요"
' '.join(split()) >> "안 녕 하 세 요"

a = "abcdefg"
a = list(a) >> ["a","b","c","d","e","f","g"]
```
`map(function,iterable)` : function: 각 요소에 적용할 함수,  iterable: 함수를 적용할데이터 집합 
    
`set()` : 중복값을 없애주는 집합 https://ctkim.tistory.com/entry/Python-%EC%9E%85%EB%AC%B8-%EA%B0%95%EC%A2%8C-12-%ED%8C%8C%EC%9D%B4%EC%8D%AC-%EC%A7%91%ED%95%A9Set-%EC%A0%95%EB%A6%AC-%EB%B0%8F-%EC%82%AC%EC%9A%A9%EB%B2%95     
`isalpha()` : 문자열이 문자로 이루어져 있는지 True, False 반환 

```python
x = [1,2,3,4,5] 
x = ''.join(map(str,x)) >> "12345"
x = list(map(str,x)) >> ['1','2','3','4','5']
text  = "abcdefg"
text = text[::-1] >> "gfedcba" 반환 
```
`min(iterable,디폴트,혹은 KEY=FUNCTION)`: 들어오는 ITERABLE 값중 가장 작은 값을 반환 