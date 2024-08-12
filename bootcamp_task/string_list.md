### 3주차 과제
```python
#######################
# String List Processing I  #
#######################

def combine_and_square(nums):
    list_a = []
    for i in nums:   #''.join(b)  a =reversed(a) hm..
        list_a.append(str(i))
    list_a = ''.join(list_a) #join은 문자열리스트만 받음
    list_a = int(list_a)
    result = list_a * list_a
        
   
    """
    주어진 리스트에서 숫자들을 결합하여 하나의 정수를 만든 뒤, 이 정수의 제곱값을 반환합니다.

    Parameters:
        nums (list of int): 정수 리스트

    Returns:
        squared (int): 결합된 정수의 제곱값

    Examples:
        >>> combine_and_square([1, 2, 3])
        1521   # 123 * 123
        >>> combine_and_square([9, 0, 9])
        826281  # 909 * 909
    """

    return result

def reverse_and_count_vowels(text):
    list_a = [] 
    for i in reversed(text): #sorted 와의 차이점 a = a.reverse() why none
        list_a.append(i)
    list_a = ''.join(list_a)
    aeiou = "aeiou"
    for i in aeiou:
        if i == "a":
            a = list_a.count("a")
        elif i == "e":
            e = list_a.count("e")
        elif i == "i":    
            ii = list_a.count("i")
        elif i == "o":
            o = list_a.count("o")
        elif i == "u":
            u = list_a.count("u")
    result = list_a , a+e+ii+o+u

    

    """
    주어진 문자열을 뒤집고, 뒤집힌 문자열에서 모음(a, e, i, o, u)의 개수를 반환합니다.

    Parameters:
        text (string): 원래의 문자열

    Returns:
        reversed_text (string): 뒤집힌 문자열
        vowel_count (int): 뒤집힌 문자열에서의 모음 개수

    Examples:
        >>> reverse_and_count_vowels("hello world")
        ("dlrow olleh", 3)
        >>> reverse_and_count_vowels("example")
        ("elpmaxe", 3)
    """
    return result
```
```python
#######################
# String List Processing II  #
#######################

def sort_and_merge(str1, str2):
    str1 = sorted(str1)
    str2 = sorted(str2)
    str1.extend(str2) #  k  = str1.extend(str2) 로 하면 none이뜸왜징
    result = ''.join(str1)



    
    
    """
    두 문자열을 각각 정렬한 후, 두 정렬된 문자열을 합쳐서 반환합니다.

    Parameters:
        str1 (string): 첫 번째 문자열
        str2 (string): 두 번째 문자열

    Returns:
        merged_string (string): 정렬 후 합쳐진 문자열

    Examples:
        >>> sort_and_merge("dacb", "gfed")
        "abcddefg"
        >>> sort_and_merge("hello", "world")
        "dehllloorw"
    """
    return result

def flatten_and_calculate(matrix):
    list_a = []
    for i in range(len(matrix)): #a = [[1,2,3],[4,5,6]] 의 범위 (0,2)
        list_a.extend(matrix[i]) #matrix[i]가 리스트이므로 #리스트확장이라서 뒤에바로붙음
    result = sum(list_a)
    



    """
    주어진 2차원 리스트를 1차원 리스트로 평탄화하고, 평탄화된 리스트의 요소 합을 반환합니다.

    Parameters:
        matrix (list of list of int): 2차원 정수 리스트

    Returns:
        sum_total (int): 평탄화된 리스트의 요소 합

    Examples:
        >>> flatten_and_calculate([[1, 2, 3], [4, 5, 6]])
        21  # [1, 2, 3, 4, 5, 6] -> 1+2+3+4+5+6
        >>> flatten_and_calculate([[7, 8], [9, 10], [11, 12]])
        57  # [7, 8, 9, 10, 11, 12] -> 7+8+9+10+11+12
    """
    return result
```
```python   
# palindrome_and_prefix.py

def is_palindrome(s):
    s = str(s).upper()
    alphabet = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    alphabet = list(alphabet) #할필요잇나
    list_a = []
    list_b = []
    for i in range(len(s)):
        if s[i] in alphabet:
            list_a.append(s[i])
        else:
            continue
    for i in range(len(s)):
        if s[-i-1] in alphabet:
            list_b.append(s[-i-1])
        else:
            continue
    list_b = ''.join(list_b)
    list_a = ''.join(list_a)
    if list_a == list_b:
        result = True
    else:
        result = False
    return result




    # '''
    # 문자열이 회문(앞뒤로 동일하게 읽히는 문자열)인지 확인하는 함수를 작성하세요.
    # 대소문자는 무시하고, 알파벳 외의 문자도 무시합니다.
    #
    # Input:
    #   - s: 문자열 (str)
    #
    # Output:
    #   - 주어진 문자열이 회문이면 True, 아니면 False를 반환합니다. (bool)
    #
    # Examples:
    #   >>> is_palindrome("A man, a plan, a canal, Panama")
    #   True
    #   >>> is_palindrome("hello")
    #   False
    # '''
    # 구현 시작
    

def longest_common_prefix(strs):
    # '''
    # 문자열 리스트를 입력받아 모든 문자열에 공통으로 포함된 가장 긴 접두사를 찾는 함수를 작성하세요.
    # 공통 접두사가 없다면 빈 문자열을 반환합니다.
    #
    # Input:
    #   - strs: 문자열 리스트 (list of str)
    #
    # Output:
    #   - 가장 긴 공통 접두사 (str)
    #
    # Examples:
    #   >>> longest_common_prefix(["flower", "flow", "flight"])
    #   "fl"
    #   >>> longest_common_prefix(["dog", "racecar", "car"])
    #   ""
    # '''
    # 구현 시작
    pass
```
```python
# anagram_and_reverse_words.py

def group_anagrams(words):
    
    # '''
    # 문자열 리스트를 입력받아 애너그램끼리 그룹으로 묶는 함수를 작성하세요.
    # 애너그램은 문자를 재배열하여 다른 단어를 만드는 것을 의미합니다.
    #
    # Input:
    #   - words: 문자열 리스트 (list of str)
    #
    # Output:
    #   - 애너그램 그룹의 리스트 (list of list of str)
    #
    # Examples:
    #   >>> group_anagrams(["eat", "tea", "tan", "ate", "nat", "bat"])
    #   [["eat", "tea", "ate"], ["tan", "nat"], ["bat"]]
    #   >>> group_anagrams([""])
    #   [[""]]
    # '''
    # 구현 시작
    pass


def reverse_words(s):
    s = str(s).split()
    list_a = []
    for i in s:
        i = list(i) # 몰랐음
        i.reverse() # reverse를 써야 될거같아서 어떻게 쪼개주지
        i = ''.join(i) #다시 조합
        i = i.split()   #문자열 전체에 리스트 씌우기 
        list_a.extend(i)
    result = ' '.join(s)
    




    # '''
    # 문자열을 입력받아 각 단어의 순서를 유지한 채로 단어 내부의 문자들을 뒤집는 함수를 작성하세요.
    # 공백은 하나로 유지합니다.
    #
    # Input:
    #   - s: 문자열 (str)
    #
    # Output:
    #   - 단어가 뒤집힌 문자열 (str)
    #
    # Examples:
    #   >>> reverse_words("The quick brown fox")
    #   "ehT kciuq nworb xof"
    #   >>> reverse_words("hello world")
    #   "olleh dlrow"
    # '''
    # 구현 시작
    return result
```