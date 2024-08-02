```python
#######################
# Test Processing I   #
#######################


def normalize(input_string):
    input_string = str(input_string).lower() #str
    list_a = []
    for i in range(len(input_string)):
        if input_string[i] != " ":
            input_string = input_string[i:]
            break
        

    for i in range(len(input_string)):
        if input_string[-i-1] != " ":
            input_string = input_string[:-i-1]
            break
    
        

    """
     인풋으로 받는 스트링에서 정규화된 스트링을 반환함
     아래의 요건들을 충족시켜야함
    * 모든 단어들은 소문자로 되어야함
    * 띄어쓰기는 한칸으로 되어야함
    * 앞뒤 필요없는 띄어쓰기는 제거해야함

         Parameters:
             input_string (string): 영어로 된 대문자, 소문자, 띄어쓰기, 문장부호, 숫자로 이루어진 string
             ex - "This is an example.", "   EXTRA   SPACE   "

         Returns:
             normalized_string (string): 위 요건을 충족시킨 정규회된 string
             ex - 'this is an example.'

         Examples:
             >>> import text_processing as tp
             >>> input_string1 = "This is an example."
             >>> tp.normalize(input_string1)
             'this is an example.'
             >>> input_string2 = "   EXTRA   SPACE   "
             >>> tp.normalize(input_string2)
             'extra space'
    """
    normalized_string = input_string
    return normalized_string


def no_vowels(input_string):
    

   

    """
    인풋으로 받는 스트링에서 모든 모음 (a, e, i, o, u)를 제거시킨 스트링을 반환함

        Parameters:
            input_string (string): 영어로 된 대문자, 소문자, 띄어쓰기, 문장부호로 이루어진 string
            ex - "This is an example."

        Returns:
            no_vowel_string (string): 모든 모음 (a, e, i, o, u)를 제거시킨 스트링
            ex - "Ths s n xmpl."

        Examples:
            >>> import text_processing as tp
            >>> input_string1 = "This is an example."
            >>> tp.normalize(input_string1)
            "Ths s n xmpl."
            >>> input_string2 = "We love Python!"
            >>> tp.normalize(input_string2)
            ''W lv Pythn!'
    """
    aeiou = "aeiouAEIOU"
    aeiou = list(aeiou)

    input_list = []
    for i in input_string :
        if i not in aeiou:
            input_list.append(i)
    

        
    input_list = ''.join(input_list)
    
    return input_list
```
```python
#######################
# Test Processing II  #
#######################


def digits_to_words(input_string):
    list_input = []
    list_input_2 = [] #결과
    number_list = ['zero','one','two','three','four','five','six','seven','eight','nine']
    for i in input_string:
        if '0' <= i <= '9':
            list_input.append(i)
    if list_input == []:
        list_input_2 = ' '.join(list_input_2) #숫자 존재 x 빈 문자열

        
    list_input = ''.join(list_input) #문자열이되
    for i in list_input:
        k = number_list[int(i)]
        list_input_2.append(k)
    
    list_input_2 = ' '.join(list_input_2)
    digit_string = list_input_2


    """
    인풋으로 받는 스트링에서 숫자만 추출하여 영어 단어로 변환하여 단어들이 연결된 스트링을 반환함
    아래의 요건들을 충족시켜야함
    * 반환하는 단어들은 영어 소문자여야함
    * 단어들 사이에는 띄어쓰기 한칸이 있음
    * 만약 인풋 스트링에서 숫자가 존재하지 않는 다면, 빈 문자열 (empty string)을 반환함

        Parameters:
            input_string (string): 영어로 된 대문자, 소문자, 띄어쓰기, 문장부호, 숫자로 이루어진 string
            ex - "Zip Code: 19104"

        Returns:
            digit_string (string): 위 요건을 충족시킨 숫자만 영어단어로 추출된 string
            ex - 'one nine one zero four'

        Examples:
            >>> import text_processing2 as tp2
            >>> digits_str1 = "Zip Code: 19104"
            >>> tp2.digits_to_words(digits_str1)
            'one nine one zero four'
            >>> digits_str2 = "Pi is 3.1415..."
            >>> tp2.digits_to_words(digits_str2)
            'three one four one five'
    """
    
    return digit_string

"""
컴퓨터 프로그래밍에 많은 명명 규칙이 있지만, 두 규칙이 특히 흔히 쓰입니다. 
첫번째로는, 변수 이름을 'underscore'로 나눠준다거나, (ex. under_score_variable)
두번째로는, 변수 이름을 대소문자 구별해 구분자 (delimiter)없이 쓰는 경우가 있습니다. 
이 두번째의 경우에는 첫번째 단어는 소문자로, 그 후에 오는 단어들의 첫번째 글자들은 대문자로 쓰입니다 (ex. camelCaseVariable). 
"""


def to_camel_case(underscore_str):    
    a_list = [] 
    b_list = []

    for i in underscore_str:
        a_list.append(i)
    for i in range(len(a_list)) :
        if a_list[i] == "_":
            a_list = a_list[i+1:] # 왜 i+1인지
        else:
            break
    for i in range(len(a_list)) :
        if a_list[-i-1] == "_": # 왜 -i-1인지
            a_list = a_list[:-i-1]
        else:
            break
                     
    k = 0
    while k <= len(a_list) - 1:
           #len 
        if a_list[k] == "_":
          b_list.append(str(a_list[k+1]).upper()) #str 
          k = k + 1
          
          
        else:        
          b_list.append(a_list[k])
          k = k + 1
    # return b_list
    
    b_list = ''.join(b_list)

            
    """
    이 문제에서 첫번째 규칙 'underscore variable' 에서 두번째 규칙 'camelcase variable'으로 변환함
    * 앞과 뒤에 여러개의 'underscore'는 무시해도 된
    * 만약 어떤 변수 이름이 underscore로만 이루어 진다면, 빈 문자열만 반환해도 됨

        Parameters:
            underscore_str (string): underscore case를 따른 스트링

        Returns:
            camelcase_str (string): camelcase를 따른 스트링

        Examples:
            >>> import text_processing2 as tp2
            >>> underscore_str1 = "to_camel_case"
            >>> tp2.to_camel_case(underscore_str1)
            "toCamelCase"
            >>> underscore_str2 = "__EXAMPLE__NAME__"
            >>> tp2.to_camel_case(underscore_str2)
            "exampleName"
            >>> underscore_str3 = "alreadyCamel"
            >>> tp2.to_camel_case(underscore_str3)
            "alreadyCamel"
    """
    
    return b_list
```
```python
 # -*- coding: utf-8 -*-

from operator import truediv
import random
from re import T, U
from turtle import clear
from unittest import result


def get_random_number():
    # Helper Function - 지우지 말 것
    # 100부터 999까지 수를 램덤하게 반환함
    return random.randrange(100, 1000)


def is_digit(user_input_number):
    if str(user_input_number).isdigit()  == True :
         result = True
             
    elif str(user_input_number).isdigit() == False:
         result = False
    # '''
    # Input:
    #   - user_input_number : 문자열 값
    # Output:
    #   - user_input_number가 정수로 변환 가능할 경우는 True,
    #     그렇지 않을 경우는 False
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.is_digit("551")
    #   True
    #   >>> bg.is_digit("103943")
    #   True
    #   >>> bg.is_digit("472")
    #   True
    #   >>> bg.is_digit("1032.203")
    #   False
    #   >>> bg.is_digit("abc")
    #   False
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당

    
    # ==================================
    return result


def is_between_100_and_999(user_input_number):
    
    # '''
    # Input:
    #   - user_input_number : 문자열 값
    #                         입력된 값은 숫자형태의 문자열 값임이 보장된다.
    # Output:
    #   - user_input_number가 정수로 변환하여 100이상 1000미만일 경우 True,
    #     그렇지 않을 경우는 False
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.is_between_100_and_999("551")
    #   True
    #   >>> bg.is_between_100_and_999("103943")
    #   False
    #   >>> bg.is_between_100_and_999("472")
    #   True
    #   >>> bg.is_between_100_and_999("0")
    #   False
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    int_user_input_number = int(user_input_number) #숫자형태의 문자열 값임이 보장
    if 100 <= int_user_input_number and int_user_input_number < 1000:   
        result = True
    else:
        result = False

    

    # ==================================
    return result


def is_duplicated_number(three_digit):
    # '''
    # Input:
    #   - three_digit : 문자열로 된 세자리 양의 정수 값
    #                   문자열로 된 세자리 양의 정수값의 입력이 보장된다.
    # Output:
    #   - three_digit 정수로 변환하였을 경우 중복되는 수가 있으면 True,
    #     그렇지 않을 경우는 False
    #   ex) 117 - True, 123 - False, 103 - False, 113 - True
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.is_duplicated_number("551")
    #   True
    #   >>> bg.is_duplicated_number("402")
    #   False
    #   >>> bg.is_duplicated_number("472")
    #   False
    #   >>> bg.is_duplicated_number("100")
    #   True
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    three_digit = int(three_digit)
    if three_digit[0] == three_digit[1]: #문자열이라서 가능
        result == True
    elif three_digit[1] == three_digit[2]:
        result == True
    elif three_digit[0] == three_digit[2]:
        result == True
    else:
        result == False
    

    # ==================================
    return result


def is_validated_number(user_input_number):
    


    

    # '''
    # Input:
    #   - user_input_number : 문자열 값
    # Output:
    #   - user_input_number 값이 아래 조건이면 True, 그렇지 않으면 False를 반환
    #        1) 숫자형 문자열이며, 2) 100이상 1000미만이며, 3) 중복되는 숫자가 없을 경우
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.is_validated_number("amvd")
    #   False
    #   >>> bg.is_validated_number("402")
    #   True
    #   >>> bg.is_validated_number("472")
    #   True
    #   >>> bg.is_validated_number("100")
    #   False
    #   >>> bg.is_validated_number("1000")
    #   False
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    if is_digit(user_input_number) == True:
        result == True
    if is_digit(user_input_number) == False:
        result == False
    if is_between_100_and_999(user_input_number) == True:
        result == True  
    if is_between_100_and_999(user_input_number) == False:
        result ==False
    if is_duplicated_number(user_input_number) == True:
        result == True
    if is_duplicated_number(user_input_number) == False:
        result == False

    # ==================================
    return result


def get_not_duplicated_three_digit_number():
    # '''
    # Input:
    #   - None : 입력값이 없음
    # Output:
    #   - 중복되는 숫자가 없는 3자리 정수값을 램덤하게 생성하여 반환함
    #     정수값으로 문자열이 아님
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.get_not_duplicated_three_digit_number()
    #   125
    #   >>> bg.get_not_duplicated_three_digit_number()
    #   634
    #   >>> bg.get_not_duplicated_three_digit_number()
    #   583
    #   >>> bg.get_not_duplicated_three_digit_number()
    #   381
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    # get_random_number() 함수를 사용하여 random number 생성
    random_number = get_random_number()
    if is_duplicated_number(random_number) == True:
        result = random_number
    else:
        get_not_duplicated_three_digit_number() 

        

    



    

    # ==================================
    return result


def get_strikes_or_ball(user_input_number, random_number):
    # '''
    # Input:
    #   - user_input_number : 문자열값으로 사용자가 입력하는 세자리 정수
    #   - random_number : 문자열값으로 컴퓨터가 자동으로 생성된 숫자
    # Output:
    #   - [strikes, ball] : 규칙에 따라 정수형 값인 strikes와 ball이 반환됨
    #   변환 규칙은 아래와 같음
    #   - 사용자가 입력한 숫자와 컴퓨터가 생성한 숫자의
    #     한 숫자와 자릿수가 모두 일치하면 1 Strike
    #   - 자릿수는 다르나 입력한 한 숫자가 존재하면 1 Ball
    #   - 세자리 숫자를 정확히 입력하면 3 Strike
    # Examples:
    #   >>> import baseball_game as bg
    #   >>> bg.get_strikes_or_ball("123", "472")
    #   [0, 1]
    #   >>> bg.get_strikes_or_ball("547", "472")
    #   [0, 2]
    #   >>> bg.get_strikes_or_ball("247", "472")
    #   [0, 3]
    #   >>> bg.get_strikes_or_ball("742", "472")
    #   [1, 2]
    #   >>> bg.get_strikes_or_ball("472", "472")
    #   [3, 0]
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    pass

    # ==================================
    return result


def is_yes(one_more_input):
    # '''
    # Input:
    #   - one_more_input : 문자열값으로 사용자가 입력하는 문자
    # Output:
    #   - 입력한 값이 대소문자 구분없이 "Y" 또는 "YES"일 경우 True,
    #     그렇지 않을 경우 False를 반환함
    # Examples:
    #   >>> import baseball_game as bg
    # >>> bg.is_yes("Y")
    # True
    # >>> bg.is_yes("y")
    # True
    # >>> bg.is_yes("Yes")
    # True
    # >>> bg.is_yes("YES")
    # True
    # >>> bg.is_yes("abc")
    # False
    # >>> bg.is_yes("213")
    # False
    # >>> bg.is_yes("4562")
    # False
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    if str(one_more_input).upper() == "Y" or str(one_more_input).upper() == "YES":
        result = True
    else:
        result = False
    

    # ==================================
    return result


def is_no(one_more_input):
    # '''
    # Input:
    #   - one_more_input : 문자열값으로 사용자가 입력하는 문자
    # Output:
    #   - 입력한 값이 대소문자 구분없이 "N" 또는 "NO"일 경우 True,
    #     그렇지 않을 경우 False를 반환함
    # Examples:
    #   >>> import baseball_game as bg
    # >>> bg.is_no("Y")
    # False
    # >>> bg.is_no("b")
    # False
    # >>> bg.is_no("n")
    # True
    # >>> bg.is_no("NO")
    # True
    # >>> bg.is_no("nO")
    # True
    # >>> bg.is_no("1234")
    # False
    # >>> bg.is_no("yes")
    # False
    # '''
    # ===Modify codes below=============
    # 조건에 따라 변환되어야 할 결과를 result 변수에 할당
    if str(one_more_input).upper() == "N" or str(one_more_input).upper() == "NO":
        result = True
    else:
        result = False

    # ==================================
    return result


def main():      
    print("Play Baseball")
    pass

    print("Thank you for using this program")
    print("End of the Game")

if __name__ == "__main__":
    main()
    
    