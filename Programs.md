# Decorator  in python



                LOGIN = True

                def login_decorator(func):
                    def check_login():
                        if LOGIN:
                            func()
                        else:
                            print("Please login page")

                    return check_login


                @login_decorator
                def dashboard():
                    print("Dashbord")

                dashboard()




# Write a Python function to remove the minimum number of invalid parentheses to make the input string valid



      #Example usage:
      input_string = "()())(()"
      s = input_string
      stack = []
      result = []
      
      #Find indices of invalid parentheses
      for i, char in enumerate(s):
          if char in {'(', ')'}:
              if char == '(':
                  stack.append(i)
              elif not stack:
                  result.append(i)
              else:
                  stack.pop()
      
      #Remove the minimum number of parentheses
      removals = set(stack + result)
      valid_string = ''.join(char for i, char in enumerate(s) if i not in removals)
      
      print("Input String:", input_string)
      print("Minimum Valid Parentheses Removals:", valid_string)



        def lengthOfLongestSubstring(s):
                def check(start, end):
                    chars = [0] * 128
                    for i in range(start, end + 1):
                        c = s[i]
                        chars[ord(c)] += 1
                        if chars[ord(c)] > 1:
                            return False
                    return True

                n = len(s)

                res = 0
                for i in range(n):
                    for j in range(i, n):
                        if check(i, j):
                            res = max(res, j - i + 1)
                return res


        if __name__ == "__main__":
            # Your code goes here
            s = 'abcabcbb'
            print(lengthOfLongestSubstring(s))
            
 # Check if two String are Anagram
 
          s2 = "abcd"
          s1 = "adbc"

          if(sorted(s1) == sorted(s2)):
              print("The strings are anagrams.")
          else:
              print("The strings aren't anagrams."
              
 # Split a string of length N into string of width K
 
          some_string="lakmsldsmsdf sdksv"
          x=4
          res=[some_string[y-x:y] for y in range(x, len(some_string)+x,x)]
          print(res)
          
 # Given a matrix of m x n elements (m rows, n columns), return all elements of the matrix in spiral order.
 
         def spiralOrder(matrix):
            ret = []
            while matrix:
                ret += matrix.pop(0)
                if matrix and matrix[0]:
                    for row in matrix:
                        ret.append(row.pop())
                if matrix:
                    ret += matrix.pop()[::-1]
                if matrix and matrix[0]:
                    for row in matrix[::-1]:
                        ret.append(row.pop(0))
            return ret

        print(spiralOrder([
        [ 1, 2, 3 ],
        [ 4, 5, 6 ],
        [ 7, 8, 9 ]
        ]))
        <b> OUTPUT : [1,2,3,6,9,8,7,4,5] </b>
      
 # Count Vowels and Consonants in a String

        name = "sachin pawar"
        vovels = "aeiou"
        
        output = {}
        for res in name:
            if res in vovels:
                output[res] = name.count(res)
        print(output)
        
        
        {'a': 3, 'i': 1}


# Write a Python function to reverse the order of words in a given string

      name = "sachin pawar"
      
      output = ""
      for res in name:
          output = res +output
      
      print(output)
      
      OUTPUT : rawap nihcas

# Write a Python function that checks if two strings are anagrams of each other.


    s1 ="listen"
    s2 ="silent"
    
    
    if sorted(s1) == sorted(s2):
        print("Yes")
    else:
        print("No")


# Write a Python function to convert the first letter of each word in a string to uppercase.

        name = "this is schin pawar"
        
        output = []
        for res in name.split():
            output.append(res.title())
        
        print(" ".join(output))


# Write a Python function to perform basic string compression using the counts of repeated characters


          name = "sachina"
          count = {}
          for res in name:
              count[res] = name.count(res)
          print(count)

# Write a Python function to find the longest common prefix of a list of strings.

            #Example usage:
            strings = ["flower", "flow", "flight"]
            
            #Sort the list of strings
            strings.sort()
            
            #Compare the first and last strings
            common_prefix = ""
            
            #Iterate over characters in the first string
            for i in range(len(strings[0])):
                # Check if the character is the same in the last string
                if i < len(strings[-1]) and strings[0][i] == strings[-1][i]:
                    common_prefix += strings[0][i]
                else:
                    break
            
            print(common_prefix)
            
            
            OUTPUT: fl

# Question: Remove Duplicates from String

          original_string = "programming"
          
          output = ""
          for res in original_string:
              if res not in output:
                  output  = output +res
          
          print(output)


# String Palindromes

          string = "programming"
          
          output = ""
          for res in string:
              output = res + output
          
          if string == output:
              print("Palindrome")
          else:
              print("Not Palindrome")

# Write a Python function to determine if a string has all unique characters


        string = "programming"
        
        output = ""
        
        for res in string:
            if string.count(res) < 2 :
                output = output +res
        
        print(output)
        
        OUTPUT : poain


# Write a Python function to determine if a string has all unique characters


        name = "hello"
        
        output = None
        
        for res in name:
            if name.count(res) > 1:
                output = False
            else:
                output = True
        print(output)


# Write a Python function to check if a given sentence is a pangram (contains every letter of the alphabet at least once).

      alpha = "qwertyuioplkjhgfdsazxcvbnm"
      
      name = "sachinpawar"
      output = 0
      for res in name:
          if res in alpha:
              output = output
          else:
              output = 1
              
      if output == 0:
          print("pangram string")
      else:
          print("Not pangram string")


# Write a Python function to count the number of words in a sentence that have a palindromic length.

      test_sentence = "The radar and level are examples of palindromic length words"
      count = 0
      for res in test_sentence.split():
          if res == res[::-1]:
              count = count +1
      
      print(count)


# Write a Python function to reverse the order of vowels in a given string.

        def reverse_vowels(input_string):
            vowels = "aeiouAEIOU"
            input_list = list(input_string)
            
            # Collect vowels in the string
            vowel_positions = [i for i, char in enumerate(input_list) if char in vowels]
            
            # Reverse the order of vowels
            for i in range(len(vowel_positions)//2):
                input_list[vowel_positions[i]], input_list[vowel_positions[-i-1]] = input_list[vowel_positions[-i-1]], input_list[vowel_positions[i]]
        
            return ''.join(input_list)
        
        #Example usage:
        input_str = "Hello, World!"
        output_str = reverse_vowels(input_str)
        print(f'Input: "{input_str}", Output: "{output_str}"')


# Write a Python function to find the longest palindromic substring in a given string.

        test_sentence = "ThT computer appa otho server and application sas a"
        
        output = {}
        for res in test_sentence.split():
            if res == res[::-1]:
                output[res] = len(res)
        
        
        max_value = max(output.values())
        for key,value in zip(output.keys(),output.values()):
            if value == max_value:
                output = f"Palindrome is {key} and length is. {value}"
        
        print(output)

# Write a Python function to check if a given string representing a mathematical expression has valid parenthesis

        s = "()())()"
        stack = []
        result = []
        
        #Find indices of invalid parentheses
        for i, char in enumerate(s):
            if char in {'(', ')'}:
                if char == '(':
                    stack.append(i)
                elif not stack:
                    result.append(i)
                else:
                    stack.pop()
        
        #Remove the minimum number of parentheses
        removals = set(stack + result)
        valid_string = ''.join(char for i, char in enumerate(s) if i not in removals)
        
        
        
        print("Input String:", s) # INPUT : ()())()
        print("Minimum Valid Parentheses Removals:", valid_string) #output ()()()


# Write a Python function to rotate an array to the right by a given number of steps

              n = 1
              lst = [10, 20, 30, 40, 50]
              
              data = lst[-n:] + lst[:-n]
              print(data)

              OUTPUT: [50, 10, 20, 30, 40]

# Given an array containing n+1 integers where each integer is between 1 and n, write a Python function to find the duplicate number.

              input_array = [3, 1, 3, 4, 2]
              
              num = None
              
              for res in input_array:
                  if input_array.count(res) > 1:
                      num = res
              
              print(num)



# Write a Python function to merge two dictionaries, and combine values for common keys into a list.

          record1 = {'name': 'Alice', 'age': 25, 'city': 'New York'}
          
          #Record 2
          record2 = {'name': 'Bob', 'age': 30, 'city': 'Los Angeles'}
          
          
          key_list = list(set(record1.keys()))
          
          output = {}
          for key,r1,r2 in zip(key_list,record1.values(),record2.values()):
              
              output[key] = [r1,r2]
          
          print(output)
          
          #OUTPUT : {'city': ['Alice', 'Bob'], 'name': [25, 30], 'age': ['New York', 'Los Angeles']}



# Write a Python function to sort a dictionary based on its values.

          footballers_goals = {'Eusebio': 120, 'Cruyff': 104, 'Pele': 150, 'Ronaldo': 132, 'Messi': 125}
          
          sorted_footballers_by_goals = sorted(footballers_goals.items(), key=lambda x:x[1])
          
          output = {}
          for res in sorted_footballers_by_goals:
              output[res[0]] = res[1]
          print(output)
          
          #{'Cruyff': 104, 'Eusebio': 120, 'Messi': 125, 'Ronaldo': 132, 'Pele': 150}

# Write a Python function to remove keys from a dictionary that have None values.

          dict1 = {'a': 1, 'b': None, 'c': 3, 'd': None, 'e': 5}
          output = {}
          for key,value in zip(dict1.keys(),dict1.values()):
              if value is not None:
                  output[key] = value
          print(output)
          
          OUTPUT: {'a': 1, 'c': 3, 'e': 5}

# Write a Python function to find and return the unique values in a dictionary.

          input_dict = {'a': 1, 'b': 2, 'c': 1, 'd': 3, 'e': 2}
          
          output = []
          for res in input_dict.items():
              if res[1] not in output:
                  output.append(res[1])
          print(output)
          
          OUTPUT :[1, 2, 3]


# Pattern Programming


* 
* * 
* * * 
* * * * 
* * * * * 


        n = 5
        for i in range(0,n+1):
            print("* "*i)
    

----------------------------------------------------------------------------------------------------------------

 1
 1 2
 1 2 3
 1 2 3 4
 1 2 3 4 5

        n = 5
        num = 1
        for i in range(1,n+1):
            output = ""
            for j in range(num,i+1):
                output = output +" "+ str(j)
            print(output)

----------------------------------------------------------------------------------------------------------------


