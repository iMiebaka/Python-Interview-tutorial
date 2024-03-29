
# what is OOP

**Programming pardigms** <br>

Ways of organizing programs <br>
python supports multiple paradigms. These are follows :- <br>

**1 ) Procedural oriented paradigm** <br>

Ya madhe apan aplya program la line by line madhe arrange karto. ya madhe ak problem ahe to mhanje resuablity <br>

**2 ) Functional oriented paradgm** <br>
Ya madhe apan resuablity problem solve kela pan ya madhe apan real world problem solve karu shakat nahi <br>


**3 ) Object-oriented paradigm**


# what is object

1 ) An object in oop represent real-life objects ex. Email, man, student, employee <br>

2 ) Every object has two properties <br>

A ) Attribute  B ) Behaviours


# what is object oriented programming

Object oriented programming is an approach of writing programs by creating classes and object. <br>

More focus is on data rather than logic

# why OOP

To solve real-world problems effectively <br>

OOp provides some :- <br>
  1 ) Inheritance : Reusability <br>
  2 ) Encapsulation :- Data security <br>
  3 ) Abstraction :- Data hiding <br>


# what is class

1 ) class is a template/plueprint/ prototype for creating object. <br> 
2 ) Every object belong to some class <br>
3 ) Email class :- email1 + email2 + email3 + email4 <br>
4 ) class is a collection of attributes and methods <br>
5 ) class is a collection of objects <br>
6 ) Technically, class is a user-defined datatype. <br>

      class class_name:
        #attributes
        #methods
      
      obj1 = class_name([args])
      obj2 = class_name([args])


# what is constructor

1 ) Special method used for initializing objects with attributes <br>
2 ) it is __init__() method <br>
3 ) First argument is self <br>
4 ) constructor is not required <br>
5 ) without constructor object cannot be created if we not create constructor it will create automatically<br>
create empty constructor


**Types of constructor**


1 ) Parameterized constructor <br>
2 ) Non-Parameterized constructor <br>
3 ) Default Constructor <br>

**Non parameterize constructor**

      class Employee:
          def __init__(self):  # --- we have not any parameter because its non parameterize constructor
              self.salary = 22000
              self.age = 31
      
      e1 = Employee()
      e2 = Employee()
      
      print(e1.__dict__)

**Parameterize constructor**

    class Employee:
        def __init__(self,salary,age): # we have given parameter 
            self.salary = salary
            self.age = age
    
    e1 = Employee(2000,21)
    
    print(e1.__dict__)


# self variable

self is a variable which containts the memory refrance of current object



# Accessing class members


**Class members :-** Attributes(varuables) + Actions( Methods ) <br>

we can access these variable using object outside the class. <br>

    Syntax:-
      Accessing attribute :- object_name.variable_name <br>
      Accessing method :-    object_name.method_name() <br>

**accessing attribute outside the class**

      class Employee:
          def __init__(self,salary,age):
              self.salary = salary
              self.age = age
          
          def display(self):
              print(f"salary is {self.salary} and age is {self.age}")
      
      e1 = Employee(2000,21)
      e2 = Employee(4000,41)
      
      # accessing attribute outside the class
      
      print(e1.salary) # Output :- 2000
      e1.salary = 2100 # updating salary
      print(e1.salary) # Output :- 2100


**accessing method outside the class**



      class Employee:
          def __init__(self,salary,age):
              self.salary = salary
              self.age = age
          
          def display(self):
              print(f"salary is {self.salary} and age is {self.age}")
      
      e1 = Employee(2000,21)
      e2 = Employee(4000,41)
      
      print(e1.salary) # Output :- 2000
      e1.salary = 2100 # updating salary
      print(e1.salary) # Output :- 2100
      
      # accessing method outside the class
      e1.display()


# Build in class functions

 1 ) getattr(obj_name, attribute_name) <br>
 2 ) setattr(obj_name,attribute_name,new_value) <br>
 3 ) delattr(obj_name, attribute_name) <br>
 4 ) hasattr(obj_name, attribute_name) <br>


 **getattr** <br>
 this is taking attribute value

     class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    print(getattr(e1,"name")) # output :- sachin

**setattr**

we can set value by help of this

    class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    setattr(e2,"name","tushar") # setter example
    
    print(getattr(e2,"name")) # Output :- tushar



