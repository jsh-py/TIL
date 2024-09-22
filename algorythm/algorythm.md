# 알고리즘(Algorithm)이란?

- 문제를 해결하기 위한 절차, 과정을 정리한 것

- 예시: 점심 메뉴를 정하는 과정, 조건에 따라 선택하는 것도 알고리즘

- 모든 경우의 수를 포함할 수 있어야 함

- 알고리즘을 평가할 때는 효과(목표 달성)와 효율(자원 사용) 두 가지 기준으로 봄

 

# 알고리즘의 복잡도(Complexity) 

- 알고리즘의 성능을 평가하는 척도

- 시간 복잡도(Time Complexity): 알고리즘 실행에 필요한 연산 횟수

   - Big-O, Big-Ω, Big-Θ 표기법 사용

   - 최악의 경우를 고려하여 상한 복잡도 O(n) 주로 사용

- 공간 복잡도(Space Complexity): 알고리즘 실행에 필요한 메모리 공간

   - 요즘은 메모리 용량이 커서 예전만큼 중요도 낮아짐

 

# 예시 

- 리스트에서 특정 숫자 찾기: 최악의 경우 리스트 길이만큼 탐색 필요 O(n)

- 정렬되지 않은 리스트 정렬하기: 중첩 반복문 사용하므로 O(n^2) 

- 이진 탐색(Binary Search): 정렬된 리스트에서 중간값과 비교하며 탐색 범위를 반으로 줄여나감. O(log n)

 

# 추상 데이터 타입(Abstract Data Type, ADT)

- 데이터와 그 데이터에 대한 연산을 명시한 것

- 구현 방법은 명시하지 않음. 인터페이스(함수, 입출력)만 정의

- 예시: 리스트 ADT  

   - 데이터: 순차적으로 저장된 요소들의 모음

   - 연산: append, length, find, insert, remove 등

- 추상화를 통해 인터페이스와 구현을 분리

   - 내부 구조는 숨기고 사용 방법(인터페이스)만 외부에 노출

   - 구현이 변경되어도 인터페이스가 같으면 사용에 영향 없음

- ADT를 바탕으로 자료구조 구현 시 계층적으로 상속하여 설계 가능

 

 

# 알고리즘의 복잡도(Complexity) 

- 알고리즘의 성능을 평가하는 척도

- 입력 크기에 따른 시간과 공간 사용량 분석

 

## 시간 복잡도(Time Complexity)

- 알고리즘 실행에 필요한 연산 횟수

- Big-O 표기법: 최악의 경우 상한 복잡도

   - O(1) : 상수 시간

   - O(log n) : 로그 시간

   - O(n) : 선형 시간  

   - O(n log n) : 선형 로그 시간

   - O(n^2) : 2차 시간

   - O(2^n) : 지수 시간

 

### 코드 예시 1 - O(n) 선형 탐색

```python

def linear_search(arr, x):

    for i in range(len(arr)):

        if arr[i] == x:

            return i

    return -1

```

 

### 코드 예시 2 - O(n^2) 버블 정렬 

```python

def bubble_sort(arr):

    n = len(arr)

    for i in range(n-1):

        for j in range(n-i-1):

            if arr[j] > arr[j+1]:

                arr[j], arr[j+1] = arr[j+1], arr[j]

```

 

### 코드 예시 3 - O(log n) 이진 탐색

```python

def binary_search(arr, x):

    low = 0

    high = len(arr) - 1

    while low <= high:

        mid = (low + high) // 2

        if arr[mid] == x:

            return mid

        elif arr[mid] < x:

            low = mid + 1

        else:

            high = mid - 1

    return -1

```

 

## 공간 복잡도(Space Complexity)

- 알고리즘 실행에 필요한 메모리 공간 

- 보통 변수, 자료구조, 함수 호출, 할당 등에 사용되는 공간 고려

- 빅-오 표기법으로 나타냄

   - O(1) : 상수 공간 

   - O(n) : 입력 크기에 비례하는 공간

   - O(n^2) : 2차원 배열 사용 시

 

### 코드 예시 4 - O(n) 공간 사용

```python

def sum_n(n):

    sum = 0

    for i in range(1, n+1):

        sum += i

    return sum

```

 

### 코드 예시 5 - O(n^2) 공간 사용

```python 

def matrix_multiply(A, B):

    n = len(A)

    C = [[0] * n for _ in range(n)]

    for i in range(n):

        for j in range(n):

            for k in range(n):

                C[i][j] += A[i][k] * B[k][j]

    return C

```

 

이처럼 알고리즘의 시간 및 공간 복잡도를 빅-오 표기법으로 나타낼 수 있으며, 입력 크기에 따른 성능을 분석할 수 있습니다. 

코드 예시와 함께 복잡도 개념을 설명하니 이해가 더 잘 되시길 바랍니다.

 

 

# 추상 데이터 타입(Abstract Data Type, ADT) 코드 예시

 

## 스택(Stack) ADT 구현 예시

```python

class Stack:

    def __init__(self):

        self.items = []

 

    def is_empty(self):

        return len(self.items) == 0

 

    def push(self, item):

        self.items.append(item)

 

    def pop(self):

        if not self.is_empty():

            return self.items.pop()

 

    def peek(self):

        if not self.is_empty():

            return self.items[-1]

 

    def size(self):

        return len(self.items)

```

 

## 큐(Queue) ADT 구현 예시

```python

class Queue:

    def __init__(self):

        self.items = []

 

    def is_empty(self):

        return len(self.items) == 0

 

    def enqueue(self, item):

        self.items.insert(0, item)

 

    def dequeue(self):

        if not self.is_empty():

            return self.items.pop()

 

    def front(self):

        if not self.is_empty():

            return self.items[-1]

 

    def size(self):

        return len(self.items)

```

 

## 리스트(List) ADT 구현 예시 

```python

class List:

    def __init__(self):

        self.items = []

 

    def is_empty(self):

        return len(self.items) == 0

 

    def add(self, item):

        self.items.append(item)

 

    def remove(self, item):

        self.items.remove(item)

 

    def search(self, item):

        return item in self.items

 

    def length(self):

        return len(self.items)

```

 

위 코드 예시들은 파이썬의 클래스를 사용하여 각 ADT를 구현한 것입니다. 

- 스택은 LIFO(Last-In-First-Out) 구조로, `push()`와 `pop()` 메서드를 통해 데이터를 추가/제거합니다.

- 큐는 FIFO(First-In-First-Out) 구조로, `enqueue()`와 `dequeue()` 메서드를 통해 데이터를 추가/제거합니다. 

- 리스트는 순차적인 데이터 모음으로, `add()`, `remove()`, `search()` 등의 메서드를 가집니다.

 

각 ADT는 내부 구현(`items` 리스트)을 캡슐화하고, 외부에는 인터페이스(메서드)만을 노출합니다. 

이를 통해 ADT의 사용자는 내부 구현에 대한 지식 없이도 ADT를 일관되게 사용할 수 있게 됩니다.  

만약 내부 구현이 변경되더라도(예: 리스트 대신 연결 리스트 사용), 인터페이스가 동일하게 유지된다면 ADT 사용자 코드에는 영향을 주지 않습니다.