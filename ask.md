
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




# 5) what is model manager? And how to create custom model manager?  <br>


# 6) Django revert migration <br>

        1 ) python manage.py migrate app_name migration_file_name

# generator <br>

generator is a special type of iterator that allows you to iterate over a sequence of values without the need to store them all in memory at once <br>
Generators are implemented using functions or generator expressions and provide an efficient way to generate and process large sequences of data lazily.<br>
Generators are useful when working with large datasets or when you need to generate values dynamically. They are memory-efficient because they produce values one at a time, <br> on-the-fly, rather than creating the entire sequence of values upfront.


# 9) what is list & tuple? real time example of list & tuple

**List**

Mutable: Lists are mutable, meaning that you can modify, add, or remove elements after the list is created.
Syntax: Lists are defined using square brackets [ ].
Usage: Lists are typically used to store collections of items where the order and content of the items may change over time.

**Shopping List**: A list of items you need to buy from the grocery store. You may add or remove items from the list as you shop.
**To-Do List:** A list of tasks you need to complete. You can mark tasks as completed or add new tasks to the list.


**Tuple**

Immutable: Tuples are immutable, meaning that once they are created, their elements cannot be modified, added, or removed.
Syntax: Tuples are defined using parentheses ( ).
Usage: Tuples are used to store collections of items where the order and content of the items are fixed and cannot change.

**Coordinates:** A tuple representing the coordinates of a point on a graph (x, y). Once the coordinates are set, they should not change.
**RGB Color:** A tuple representing the red, green, and blue values of a color (r, g, b). The color components are fixed and cannot be modified individually.


# 10) string reverse program

                name = "sachin"
                output = ""
                for i in name:
                    output = i  + output
                print(output)

# 11) How to find the palindrome among first N numbers? Code it

                def is_palindrome(num):
                    # Convert the number to a string and check if it's equal to its reverse
                    return str(num) == str(num)[::-1]
                
                def find_palindromes(N):
                    palindromes = []
                    for i in range(1, N + 1):
                        if is_palindrome(i):
                            palindromes.append(i)
                    return palindromes
                
                # Example usage:
                N = 100
                palindromes = find_palindromes(N)
                print("Palindromes among the first", N, "numbers:", palindromes)
                
                OUTPUT : Palindromes among the first 100 numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 22, 33, 44, 55, 66, 77, 88, 99]


# 12) Which are the collections used in python?

    1) List
    2) Tuple
    3) Sts
    4) Dictionaries
    5) String
       

# 14) Question was to draw a star based pattern according to fibonacci series(1,1,2,3,5) eg. n=5 ***** ***** *** *** ** ** * * *

                n = 5
                
                a = 0
                b = 1
                
                for i in range(n):
                    print("* "*a)
                    c = a + b
                    a = b
                    b = c

# 15) Write Program to get the most frequency occurring in file?

                with open("test.txt","r") as f:
                    file = f.read().lower()
                
                file = file.split(" ")
                
                output = {}
                for res in file:
                    output[res] = file.count(res)
                
                print(output)

# 16) Given a list and a number find two numbers in the list that sums up to the number given?
                numbers = [2, 7, 11, 15, 3, 6]
                target = 9
                
                output = []
                for res in numbers:
                    for i in numbers:
                        if res + i == target:
                            output.append(res)
                print(output)


17) Write Program to print a tree in level order traversal?

18) Write a function that accept the file, count and return the exact occurrence of a word based on count?
19) List a=[ 1,2,3 none, none] list b=[4,5,3] Output=[1,4,2,5,3,3] ?

20) What are decorators in python?

# 21)  How to define private variables in python?

                class MyClass:
                    def __init__(self):
                        self._private_variable = 42
                
                    def _private_method(self):
                        print("This is a private method.")
                
                    def public_method(self):
                        print("This is a public method.")
                        self._private_method()
                
                # Example usage
                obj = MyClass()
                print(obj._private_variable)  # Accessing "private" variable (not truly private)
                obj.public_method()  # Accessing public method, which in turn calls private method

22)  Inheritence,
23)  interface abstraction etc
24)  
# 25)  What is lambda function in python.
A lambda function in Python is a small, anonymous function defined using the lambda keyword. It allows you to create functions <br> on-the-fly without having to formally define a function using the def keyword. Lambda functions are typically used when you need a simple, one-line function for a short period of time

                lst = [1,2,3,4,5,6,7,8,9,10]
                data = lambda i: [i for i in i if i %2==0]
                print(data(lst))


# 26)  input = aabbbccc output = a2b3c3

                string = "aabbbccc"
                output = ""
                for res in string:
                    if res not in output:
                        output = output + res + str(string.count(res))
                print(output)

27)  write a function for return a reverse text of the passed parameter text



28)  Given a string ‘S’, find the length of the Longest Palindromic Subsequence in it
29)  What are lists and the difference between set and lists?
# 30)  What are different class variables?

                class MyClass:
                    static_variable = 10
                
                print(MyClass.static_variable)  # Accessing static variable

31)  Find the Nth fibonacci number.
32)  Python Django Basics and Project Architecture

33)  what is index and what is it used for?
34)  Write fibonacci sequence functions using generator and recursion.
35)  What is a constructor in Python?
36)  when you save python program it creates .pyc file what is it ? what it contains?
37)  find even number betweens 1 to 100 and not divisible by 8 after sum of even number

# 38)  What are the different types of errors in python? When it will occur and How to handle?
    **Type of diffrent error**

     1) Syntax Errors : ex: print("Hello world"  # Missing closing parenthesis
     2) Runtime Errors (Exceptions)

                        x = 10
                        y = 0
                        result = x / y  # Division by zero
     3) Logial error


40)  How will you check and ensure the datatype in python?
41)  Difference between List and Tuples
42)  removing character in a given string
43)  What are use of Django Rest Framework? Why don't we just use Django to create Rest APIs?

44)  How you will perform an Asynchronous Activity

45)  How web browser understands Location of server
46)  What are type of security tokens we use to access third party APIs.
47)  Describe Garbage collector in python
48)  Deep vs Shallow Copy
49)  Memory Management in Python
50)   "==" vs "is"
51)   What are signals in Django?
52)   What are buckets and objects in Amazon S3?
53)   What is lamda equation there in python
54)   Remove the duplicate elements from the list ?

# 55)   How do you process huge file with not enough memory available

**Read code line by line**

        with open("test.txt","r") as f:
            for i in f:
                print(i)
                
**Chnked reading**

        with open("test.txt","r") as f:
            chunk_size = 1024
        
            data = f.read(chunk_size)
        print(data)

**Generator functioin**

                def large_file(filename):
                    with open(filename,'r') as file:
                        for line in file:
                            yield line
                
                for line in large_file("test.txt"):
                    print(line)


56)   Remove the duplicate elements from the list ?

                lst = [1,2,2,3,3,4,5,6,7,8,8]
                
                output = []
                
                data = [output.append(i) for i in lst if i not in output]
                
                print(output)

57)   What are magic methods in Python and what are they used for

**Initialization and Cleanup:**

__init__(self, ...): Constructor method, initializes new instances of a class.<br>
__del__(self): Destructor method, cleans up resources when an object is no longer needed.


**String Representation:**
__str__(self): Returns a string representation of an object when str() function is called. <br>
__repr__(self): Returns a string representation that ideally can be used to recreate the object when repr() function is called.

**Comparison Operations**

__eq__(self, other): Defines behavior for the equality operator (==).
__ne__(self, other): Defines behavior for the inequality operator (!=).
__lt__(self, other): Defines behavior for the less-than operator (<).
__le__(self, other): Defines behavior for the less-than or equal to operator (<=).
__gt__(self, other): Defines behavior for the greater-than operator (>).
__ge__(self, other): Defines behavior for the greater-than or equal to operator (>=).

                class Vector:
                    def __init__(self, x, y):
                        self.x = x
                        self.y = y
                
                    def __add__(self, other):
                        # Define addition behavior for Vector objects
                        return Vector(self.x + other.x, self.y + other.y)
                
                    def __str__(self):
                        return f"({self.x}, {self.y})"
                
                # Create two Vector objects
                v1 = Vector(2, 3)
                v2 = Vector(4, 5)
                
                # Use the addition operator on Vector objects
                result = v1 + v2
                
                # Print the result
                print("Result of addition:", result)  # Output: (6, 8)





58)   What is the difference between Pip and Pep8?
59)   middleware classes in django
60)   Which one is faster to access dictionary or list and why
61)   Does Django suppors NoSQL databases
62)   What is pickling and unpickling
# 63)   what is overloading

 overloading refers to the ability to define multiple methods with the same name but different numbers or types of parameters within a single class. Unlike some other languages like C++ and Java, Python does not support function or method overloading based solely on parameter types. Instead, it implements a single-dispatch mechanism for method overloading based on the type of the first parameter, known as the "dispatching argument."

 


64)   what is GIL in the Python?
# 65)   What is the 'yield' keyword in python?

When a function contains the yield keyword, it becomes a generator function. When the generator function is called, it returns a generator object, which is an iterator. Each time the yield statement is encountered within the generator function, the function's state is saved, and the value after the yield keyword is returned to the caller. The function's execution is then paused

                def my_generator():
                    yield 1
                    yield 2
                    yield 3
                
                # Create a generator object
                gen = my_generator()
                
                # Iterate over the generator object using a loop
                for value in gen:
                    print(value)


66)   Difference in list and array.
# 67)   What is ** in Python

** operator is used for exponentiation, also known as raising a number to a power. It is used to calculate the power of one number raised to the exponent of another number.

                # Calculate 2 raised to the power of 3
                result = 2 ** 3
                print(result)  # Output: 8




68)   What happens when we run any program in Python?
69)   How CSRF works
70)   Give any example of Middlewares in Django
71)   Inheritance in Python (Diamond problem)
72)   Explain MVC/MVT in Django
73)   List comprehension in Python
74)   Write a decorator in Python to print a function name and arguments passed to it.
75)   Recursion & call by reference related questions
76)   Find the length of the largest word in a given string
77)   What do you like about python's interpreter?
78)   What are the synchronization methods in python?
79)   Custom garbage collection in python
# 80)   How encapsulation is implemented in Python

In Python, there's no strict enforcement of private members. However, the convention is to prefix the name of an attribute or method with a single underscore (_) to indicate that it is intended to be private and should not be accessed from outside the class. While this convention is not enforced by the language, it serves as a signal to other developers that the member is intended for internal use only.

                class MyClass:
                    def __init__(self):
                        self._private_attr = 10
                
                    def _private_method(self):
                        print("This is a private method.")
                
                obj = MyClass()
                print(obj._private_attr)  # Accessing private attribute (convention)
                obj._private_method()     # Calling private method (convention)



82)   Which tools does django provide to support backend scaling
83)   Write a function to return a list of all subsequences of a string in sorted order, excluding the empty string.
84)   Python bitwise operator problem
85)   Try catch block
86)   What is regex? Name and explain some libraries you have used in python
87)   Write a program to print whether it is a prime number or not.
88)   check if a string is correct "{{([(())})}}" string is correct if each quotation mark is closed by its corresponding quotation mark.
89)   prefetch_related
# 90)   Python generators what and why we need it. And a example code

Python generators are functions that enable you to create iterators in a more efficient and concise way compared to traditional iterator classes. Generators allow you to iterate over a sequence of values without needing to create and store the entire sequence in memory at once. Instead, they generate values on the fly as they are needed, which can significantly reduce memory consumption and improve performance, especially when dealing with large or infinite sequences.


                def fibonacci_generator():
                    """Generate Fibonacci sequence indefinitely."""
                    a, b = 0, 1
                    while True:
                        yield a
                        a, b = b, a + b
                
                # Create a generator object
                fib_gen = fibonacci_generator()
                
                # Iterate over the first 10 Fibonacci numbers
                for _ in range(10):
                    print(next(fib_gen))  # Output: 0 1 1 2 3 5 8 13 21 34





# 91)   multithreading use in python reason
 
 Multithreading in Python is used to achieve parallelism, allowing multiple threads to execute concurrently within the same process

**Improved Performance:** Multithreading can improve the performance of certain types of applications by leveraging <br> multiple CPU cores or by overlapping I/O-bound tasks with CPU-bound tasks. This can lead to faster execution times and better resource utilization.

**Responsive Applications:** Multithreading can improve the responsiveness of applications by allowing them to perform time-consuming tasks in <br> the background without blocking the main thread. This prevents the user interface from freezing or becoming unresponsive while waiting for tasks to complete

 **Asynchronous Programming:** Multithreading is often used in asynchronous programming paradigms, such as event-driven programming or <br> reactive programming. It enables the application to handle multiple asynchronous events or tasks concurrently without blocking the main thread.

                import threading
                import time
                
                def print_numbers():
                    """Function to print numbers from 1 to 5."""
                    for i in range(1, 6):
                        print(i)
                        time.sleep(1)  # Simulate some time-consuming task
                
                def print_letters():
                    """Function to print letters from 'a' to 'e'."""
                    for letter in 'abcde':
                        print(letter)
                        time.sleep(1)  # Simulate some time-consuming task
                
                # Create two threads to execute the print_numbers and print_letters functions concurrently
                thread1 = threading.Thread(target=print_numbers)
                thread2 = threading.Thread(target=print_letters)
                
                # Start the threads
                thread1.start()
                thread2.start()
                
                # Wait for both threads to finish execution
                thread1.join()
                thread2.join()
                
                print("Both threads have finished execution.")



# 92)   What's the difference between overloading and overriding?


**Overloading**

Overloading in Python refers to the ability to define multiple functions or methods with the same name but <br> different numbers or types of parameters within the same class or module.

**Purpose:** Overloading allows you to provide multiple implementations of a function or method, each tailored to accept <br> different parameter types or numbers. It provides flexibility and convenience when working with different data types or argument lists

**Characteristics:**

Python does not support method overloading based on the number or types of parameters alone, as it does in some other languages like Java. Instead, you can achieve overloading by using default parameter values or variable-length argument lists (e.g., *args and **kwargs).
Overloading is determined dynamically at runtime based on the actual arguments passed to the function or method.


                class Calculator:
                    def add(self, a, b):
                        return a + b
                    
                    def add(self, a, b, c):
                        return a + b + c

------------------------------------------
**Overriding**

Overriding in Python refers to the ability to provide a new implementation of a method in a subclass that is already defined in its superclass

**Purpose:** Overriding allows a subclass to customize the behavior of inherited methods from its superclass. <br> It enables polymorphism, where the same method name can behave differently depending on the object's actual type at runtime.

        
        class Animal:
            def make_sound(self):
                print("Animal makes a sound")
        
        class Dog(Animal):
            def make_sound(self):
                print("Dog barks")



# 93)   What are iterators, how do you implement/override them in python.

the iter() function is used to create an iterator from an iterable object. It returns an iterator object that allows <br> you to iterate over the elements of the iterable using the next() function or a loop

object: The iterable object for which you want to create an iterator.
sentinel (optional): An optional sentinel value that, when provided, indicates the end of the iteration. If the iterator encounters the sentinel value, it will stop iterating

                # Create an iterable object (list)
                my_list = [1, 2, 3, 4, 5]
                
                # Create an iterator from the iterable using iter()
                my_iterator = iter(my_list)
                
                # Iterate over the elements of the iterator using next() function
                print(next(my_iterator))  # Output: 1
                print(next(my_iterator))  # Output: 2
                print(next(my_iterator))  # Output: 3
                
                # Iterate over the remaining elements of the iterator using a loop
                for item in my_iterator:
                    print(item)


94)   What is lambda function ?
95)   Use of __name__ == "__main__"
96)   what common built python function comanly used in oops


**isinstance()**: Checks if an object is an instance of a particular class or type

                obj = MyClass()
                isinstance(obj, MyClass)  # True

**issubclass():** Checks if a class is a subclass of another class.

                issubclass(Subclass, Baseclass)  # True


**getattr():**  Gets the value of an attribute of an object.

                value = getattr(obj, 'attribute_name')

**staticmethod()** 

                class MyClass:
                    @staticmethod
                    def my_method():
                        print("This is a static method")

97)   Find errors in a function declaration regarding *args and **kargs in Python

98)   Why would you want to write a custom middleware in Django?
99)   Write a function that returns the smallest positive number that is evenly divisible by all numbers from 1 to n
100)   can you override parent class constructor ?
101)   What is Line written to in settings file of Django to connect database ?
102)   what is inheritence. what is polymorphism
103)   What is difference between repr and str
104)   What are python context managers?
105)   inheritance‍‌‍‍‍‌‌‌‌‌‌‌‍‌‌‌‍‍‍‌ and composition? Give examples. What is "with" used for? How is it implemented?
106)   What are "comprehensions" in Python and what kinds are there?


<a href="https://www.glassdoor.co.in/Interview/python-interview-questions-SRCH_KO0,6_IP69.htm" > More question </a>



