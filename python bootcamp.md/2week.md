## 함수(function)
**명령창에 파이썬 실행 > 인터프리터 작동**


```python
def calculater(x,y): 
    return x * y   #메모리에 저장  
    #문법 , 작동원리
x = 10
y = 20

result = calculater(x,y)
```
`parameter` : 함수를 만들어서 이름을 쓰고 *선언*.입력 인풋값  
 `argument` : 함수에 실제값을 넣는 것을 의미.  
`control +shift + enter` : 터미널 열기  
`control + a ` : 코드 모두 집기
## 함수의 형태 

```python
def a(x): 
    return x * x # 입력값, 반환값 존재

x = 2
print(a(x)) 
```
```python
def a(x):
    print(x ** x) # 입력값 존재 return값 X
    # null 값으로 저장  프린트는 되는데 리턴값이 업어서 NONE  
    
x = 2 
print(a(x)) 

a.sort() 
sorted(a) #반환값 ON 
```
**함수 내에서 선언된 X 값과 밖에서 정의된 X값은 다른 메모리 주소를 가짐**

## 입출력
```python
print("enter yout name")
somebody = input() #인풋값 somebody 메모리에 저장
print ("hello " , somebody , "how are you today")  
```
```python
temperature = float(input("온도를 입력하세요 : "))
print(temperature)
```
### 포맷함수, f-string
```python
print("{}, 안녕하세요" , "{}".format(1, 2))  
```
```python
name = "sungchul"
age = 41
#변수선언 후 f {변수명}이 들어감
print(f"hello,{name} you are {}")  
print(f "{name:>20}") #우로 20칸 정렬
print(f "{name:*<20}") #좌로 20칸 정렬하고 별표로 채워라
print(f "{name:*^20}") # 가운데 정렬 나머지 별표로 채워라
number = 3.141592
print(f"{number:.2f}") #소수점 두자리 까지  출력  
```
# 조건문
**조건을 나타내는 기준과 실행해야 할 명령으로 구성**  
if <조건> : 조건은 t/f가 구분되어야 한다.
### 메모리 개념
a = [5,4,3,2,1]  > a라는 메모리에 할당.  
b = a       >b를 a 메모리에 할당      
a is b  > True
+ `파이썬`은 `-5 부터 256까지` `같은 메모리`를 가짐. 
+  a = 257 , b = 257 a is b > `false` *`각각의 메모리`*  "메모리주소" "변수값"  
   
### 삼항 연산자
```python
value = 12
"hello" if value % 2 == 0 else False
"hello" if value % 2 == 1 else "world"
value = 55
"hello" if value % 2 else "world"
# 나머지 값 1 값이 존재 > TRUE > hello 반환
# 나머지 값 0일시 값이 존재 X > WORLD 반환
```

## 반복문 loop
**정해진 동작을 반복적으로 수행하게 하는 명령문**  
**`반복 시작 조건`, `종료 조건`, `수행 명령`으로 구성**
`range(시작값,직전값,건너뛰는정도)`
### for loop
 `반복실행 횟수를 명확히 알 때`
```python
for i in range(0,5):
    print(i)

```
### while loop
`반복실행 횟수가 명확하지 않을 때`
`코드에 의해서 종료시점이 결정된다.`

### 반복의 제어 break, continue
```python
for i in  range(10):
    if i == 5 :
        break # or continue
    print(i)

# 반복조건이 만족하지 않을 경우 반복 종료시 1회 수행 else
print("end of program") 






 



