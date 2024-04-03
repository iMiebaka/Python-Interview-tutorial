
1) Difference between Authorization and authentication? And how to implement in application? <br>
# 2) Generator in python? And how to implement in application? <br>

generator is a special type of iterator that generates values on-the-fly, rather than storing them in memory all at once. Generators are defined using functions and the yield keyword, allowing you to iterate over a sequence of values without needing to generate the entire sequence upfront. This makes generators memory-efficient and particularly useful when dealing with large datasets or infinite sequences

        def my_generator():
            yield 1
            yield 2
            yield 3
        
        # Using the generator
        gen = my_generator()
        print(next(gen))  # Output: 1
        print(next(gen))  # Output: 2
        print(next(gen))  # Output: 3

Another example

        def read_lines(filename):
            with open(filename, 'r') as file:
                for line in file:
                    yield line.strip()
        
        # Process each line in a large file
        for line in read_lines('large_file.txt'):
            # Do something with the line
            print(line)

# what is yield keyword

yield keyword is used in generator functions to pause execution and yield a value to the caller. When a generator function is called, it returns an iterator called a generator. The yield statement is what makes a function a generator function.


# 3) Abstract classes in python? <br>

An abstract class in Python is like a blueprint for other classes. It's a class that you define to have methods and properties that must be implemented by its subclasses. However, you cannot create an instance of an abstract class directly. Instead, it serves as a template for other classes to follow

Abstract cass is a class that contans one or more abstract method is called abstract class

Note :- An object of an abstract class cannot be created <br>
 2 ) Python provide abc modue to work with abstact class <br>
 3 ) we use **@abstractmethod** decorator to define abstract method <br>

 **Marathi** apan abstraction teva use karto jeva action common asta ani implementation diffrent asta

 
          from abc import ABC, abstractmethod
          
          class Car(ABC):
          
              def show(self):
                  print("Every car has 4 wheels")
              
              @abstractmethod
              def speed(self):
                  print()
          
          class Maruti(Car):
              def speed(self):
                  print("Speed is 100KM/H")
              
          class Suzuki(Car):
              def speed(self):
                  print("Speed is 7KM/H")
          
          obj = Maruti()
          obj.show()
          obj.speed()
          
          obj1 = Suzuki()
          obj1.show()
          obj1.speed()

Imagine you're designing a game and you have different types of characters like warriors, mages, and archers. You might want to create a base class called Character that defines common behaviors like moving, attacking, and taking damage. However, you don't want anyone to create a generic Character object because each character type should have its own implementation for these behaviors. That's where an abstract class comes in handy.

So, you define Character as an abstract class with methods like move(), attack(), and take_damage(), but you don't provide implementations for these methods in the Character class itself. Instead, you leave them as abstract methods. Then, subclasses like Warrior, Mage, and Archer inherit from the Character class and provide their own implementations for these methods.

# Agregation in django

Aggregate function work on singel colum , ex sum of total student mark
it can find ,average,sum,min,max ya sathi apan aggregate madhe karto

**Sum of numeric field across multiple row**

        from django.db.models import Sum
        
        # Example: Calculate the total sales amount
        total_sales = Sales.objects.aggregate(total_amount=Sum('amount'))

**Avg: Calculates the average (mean) value of a numeric field.**

        from django.db.models import Avg
        
        # Example: Calculate the average price of products
        avg_price = Product.objects.aggregate(avg_price=Avg('price'))



# 4) what is annotations? <br>

Annotate function work on multiple colum 

**Total number of pages**

      from django.db.models import F
      
      # Example: Annotate each book with the total number of pages
      books = Book.objects.annotate(total_pages=F('pages') + F('extra_pages'))




5) what is model manager? And how to create custom model manager?  <br>
6) Django revert migration <br>
7) what is decorator, generator <br>
8) questions on project <br>
9) what is list & tuple? real time example of list & tuple
10) string reverse program
11) How to find the palindrome among first N numbers? Code it
12) Which are the collections used in python?
13) Question was to draw a star based pattern according to fibonacci series(1,1,2,3,5) eg. n=5 ***** ***** *** *** ** ** * * *
14) Write Program to get the most frequency occurring in file?
15) Given a list and a number find two numbers in the list that sums up to the number given?
16) Write Program to print a tree in level order traversal?
17) Write a function that accept the file, count and return the exact occurrence of a word based on count?
18) List a=[ 1,2,3 none, none] list b=[4,5,3] Output=[1,4,2,5,3,3] ?
19) What are decorators in python?
20)  How to define private variables in python?
21)  Inheritence, interface abstraction etc
22)  What is lambda function in python.
23)  input = aabbbccc output = a2b3c3
24)  write a function for return a reverse text of the passed parameter text
25)  Given a string ‘S’, find the length of the Longest Palindromic Subsequence in it
26)  What are lists and the difference between set and lists?
27)  What are different class variables?
28)  Find the Nth fibonacci number.
29)  Python Django Basics and Project Architecture
30)  what is index and what is it used for?
31)  Write fibonacci sequence functions using generator and recursion.
32)  What is a constructor in Python?
33)  when you save python program it creates .pyc file what is it ? what it contains?
34)  find even number betweens 1 to 100 and not divisible by 8 after sum of even number
35)  What are the different types of errors in python? When it will occur and How to handle?
36)  How will you check and ensure the datatype in python?
37)  Difference between List and Tuples
38)  removing character in a given string
39)  What are use of Django Rest Framework? Why don't we just use Django to create Rest APIs?
40)  How you will perform an Asynchronous Activity
41)  How web browser understands Location of server
42)  What are type of security tokens we use to access third party APIs.
43)  Describe Garbage collector in python
44)  Deep vs Shallow Copy
45)  Memory Management in Python
46)   "==" vs "is"
47)   What are signals in Django?
48)   What are buckets and objects in Amazon S3?
49)   What is lamda equation there in python
50)   Remove the duplicate elements from the list ?
51)   How do you process huge file with not enough memory available
52)   Remove the duplicate elements from the list ?
53)   What are magic methods in Python and what are they used for
54)   What is the difference between Pip and Pep8?
55)   middleware classes in django
56)   Which one is faster to access dictionary or list and why
57)   Does Django suppors NoSQL databases
58)   What is pickling and unpickling
59)   what is overloading
60)   what is GIL in the Python?
61)   What is the 'yield' keyword in python?
62)   Difference in list and array.
63)   What is ** in Python
64)   What happens when we run any program in Python?
65)   How CSRF works
66)   Give any example of Middlewares in Django
67)   Inheritance in Python (Diamond problem)
68)   Explain MVC/MVT in Django
69)   List comprehension in Python
70)   Write a decorator in Python to print a function name and arguments passed to it.
71)   Recursion & call by reference related questions
72)   Find the length of the largest word in a given string
73)   What do you like about python's interpreter?
74)   What are the synchronization methods in python?
75)   Custom garbage collection in python
76)   How encapsulation is implemented in Python
77)   Which tools does django provide to support backend scaling
78)   Write a function to return a list of all subsequences of a string in sorted order, excluding the empty string.
79)   Python bitwise operator problem
80)   Try catch block
81)   What is regex? Name and explain some libraries you have used in python
82)   Write a program to print whether it is a prime number or not.
83)   check if a string is correct "{{([(())})}}" string is correct if each quotation mark is closed by its corresponding quotation mark.
84)   prefetch_related
85)   Python generators what and why we need it. And a example code
86)   multithreading use in python reason
87)   What's the difference between overloading and overriding?
88)   What are iterators, how do you implement/override them in python.
89)   What is lambda function ?
90)   Use of __name__ == "__main__"
91)   Find errors in a function declaration regarding *args and **kargs in Python
92)   Why would you want to write a custom middleware in Django?
93)   Write a function that returns the smallest positive number that is evenly divisible by all numbers from 1 to n
94)   can you override parent class constructor ?
95)   What is Line written to in settings file of Django to connect database ?
96)   what is inheritence. what is polymorphism
97)   What is difference between repr and str
98)   What are python context managers?
99)   inheritance‍‌‍‍‍‌‌‌‌‌‌‌‍‌‌‌‍‍‍‌ and composition? Give examples. What is "with" used for? How is it implemented?
100)   What are "comprehensions" in Python and what kinds are there?


<a href="https://www.glassdoor.co.in/Interview/python-interview-questions-SRCH_KO0,6_IP69.htm" > More question </a>



