
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

**delattr**

for delete attribute


    class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    delattr(e2,"age")
    print(e2.__dict__) # output :- {'name': 'tushar'}

**hasattr**

yat check kel jat object kad attribute ahe ka nahi

    class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    print(hasattr(e1,"name")) #output :- True 

# built in class attribute

1 ) __dict__ :- Dictionary containing class's namespace
2 ) __doc__ :- class documentation string
3 ) __name__ :- class name
4 ) __module__ :- Module name in which class is defined
5 ) __bases__ :- list of base classes

**__doc__**

yane doc string maintain keli jati


    class Employee:
        """ This is employee class for maintaining """
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    print(Employee.__doc__) # This is employee class for maintaining

**__dict__**

yacha wapar class cha data pahayla hoto dictionary format madhe

    class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    
    print(Employee.__dict__) # {'__module__': '__main__', '__doc__': ' This is employee class for maintaining ', '__init__': <function Employee.__init__ at 0x7d40ca134720>, '__dict__': <attribute '__dict__' of 'Employee' objects>, '__weakref__': <attribute '__weakref__' of 'Employee' objects>}


**__name__**

Yane class cha name print hoil
    
    class Employee:
        def __init__(self, name,age):
            self.name = name
            self.age = age
    
    e1 = Employee("Sachin",21)
    e2 = Employee("Sagar",22)
    
    
    print(Employee.__name__) # Employee

# what is instance variable in python

**Types of variable**

1 ) instance variable <br>
2 ) class variable


**Instance variable**

1 ) instance variable he object shi associated astat <br>
2 ) suppose tumchya kad 3 object asel tar instance variable chi 3 copy bantil <br>
3 ) values of variables differs from object to object <br>
4 ) modification is one object wont effect other object <br>


aka instance varibale change kelyavar dusrya var affect hot nahi, yala apan delete pan karu shakto.

    class Student:
        def __init__(self, name,mark):
            self.name = name
            self.mark = mark
    
    a1 = Student("Sachin",21)
    a2 = Student("sagar",21)
    a3 = Student("tushar",21)
    
    a1.age =21
    print(a1.__dict__) # Output :- {'name': 'Sachin', 'mark': 21, 'age': 21}


**Instance method**

    class Student:
        def __init__(self, name,mark):
            self.name = name
            self.mark = mark
        
        def display(self):
            print(self.name,self.mark)
        
        def change_data(self):
            self.name = "abc"
            self.mark = 100
    
    a1 = Student("Sachin",21)
    a2 = Student("sagar",21)
    a3 = Student("tushar",21)
    
    a1.change_data()
    print(a1.__dict__) # {'name': 'abc', 'mark': 100}

# class variable & class method

Instance variable sathi multiple copy banavli jatat, tasach class variable sathi akach copy banavli jat

**Class Variable**

1 ) Variables made for entire class ( All objects ) <br>
2 ) Only one copy is created and distributed to all objects <br>
3  ) Modification in class variable impact on all objects <br>



        class Employee:
            company_name = "infosys" # class variable
            def __init__(self,name,salary):
                self.name = name
                self.salary = salary
        
        e1 = Employee("sachin",300)
        e2 = Employee("Tusahr",500)
        
        print(Employee.company_name) # output :- infosys ) access class variable )
        
        """class variable modify karnya sathi aplyala class ghyava lagto"""
        
        Employee.company_name = "TCS"
        print(Employee.company_name) #output :- TCS


**Class Method**

1 ) Method which works on class variable <br> 
2 ) First argument is class reference <br>
3 ) Made using decorator **@classmethod** <br>



      class Employee:
          company_name = "infosys" # class variable
          def __init__(self,name,salary):
              self.name = name
              self.salary = salary
          
          @classmethod  # class method banavnya sathi
          def get_comapny_name(cls):
              cls.company_name = 'TCS'
              print(cls.company_name)
              
      
      e1 = Employee("sachin",300)
      e2 = Employee("Tusahr",500)
      
      Employee.get_comapny_name() # Output :- Comapy name is  infosys


# setter method & getter method

**Instance method**

**1 ) setter method :-** set values of instance variable <br>
**2 ) getter method :-** get values of instance variables <br>


      class Employee:
          def setName(self,name): # setter method
              self.name = name
          
          def getName(self):
              print(f"the name is {self.name}") # getter method
      
      e1 = Employee()
      
      e1.setName("sachin") # set value
      e1.getName() # get value
      
      print(e1.__dict__) # output:- {'name': 'sachin'}



# static method

1 ) methods which performs operations on external data <br>
2 ) it can also perform operations on class data <br>
3 ) No need to pass object or class reference <br>
4 ) created using decorator **@staticmethod** <br>




      class Bank:
          bank_name = "BOI"
          rate_of_interest = 12.5
          
          def simple_interest(amount,years):
              si = (amount*year*Bank.rate_of_interest)/100
              print(si)
      
      amount = 10000
      year = 3
      Bank.simple_interest(amount,year)


# Inheritance in python ( 14 )

Deriving a new class from an existing class so that new class inherits all members ( attributes  + methods ) of existing class is called as inheritance.


        class Employee:
            bouns = 2000
            
            def display(self):
                print(f"This is employee class method")
        
        class Manager(Employee):
            bonus1 = 5000
            
            def show(self):
                print("This is manager class method")
        
        e1 = Employee()
        m1 = Manager()
        m1.display()
        m1.show()

# what is need of inheritance

1 ) For code reusablity ( write once use many times ) <br>
2 ) when you have relations among classes <br>


# How constructor works in inheritance ( 16 )




        """ Jar son class kad constructor asel tar father class cha constructor call nahi honar ani jar son class kad construcotr asel tar father class cha constructor call hoil"""

        class Father:
             def __init__(self):
                 print("Father constructor called")
                 self.vehicle = "scooter"
        
        
        class Son(Father):
            def __init__(self):
                 print("Son constructor called")
                 self.vehicle = "BMW"
        
        s = Son()
        print(s.__dict__)


# super() function

1 ) Using super() function, we can access parent class properties <br>
2 ) this function return a temporary object which contains reference to parent class. <br>
3 ) It makes inheritance more manageable and extensible.


        class Computer:
            def __init__(self):
                self.ram = "8 GB"
                self.storage = "512 GB"
                print("Computer class constructor call")
        
        class Mobile(Computer):
            def __init__(self):
                super().__init__() # we can accessing parent class attribute using constructor
                self.model = "I-Phone X"
                print("Mobile class constructor call")
        
        apple = Mobile()
        print(apple.__dict__) # Output :- {'ram': '8 GB', 'storage': '512 GB', 'model': 'I-Phone X'}


**Parameterise constructor**

      class Computer:
          def __init__(self, ram,storage):
              self.ram = ram
              self.storage = storage
              print("Computer class constructor call")
          
      
      class Mobile(Computer):
          def __init__(self,ram,storage):
              super().__init__(ram,storage) # we can accessing parent class attribute
              self.model = "I-Phone X"
              print("Mobile class constructor call")
      
      apple = Mobile("8 GB","512, GB")
      print(apple.__dict__) # Output :- {'ram': '8 GB', 'storage': '512 GB', 'model': 'I-Phone X'}


  **call method also**

        class Computer:
          def __init__(self, ram,storage):
              self.ram = ram
              self.storage = storage
              print("Computer class constructor call")
              
          def display(self):
              print("Hello")
          
      
      class Mobile(Computer):
          def __init__(self,ram,storage):
              super().display() # we calling method
              self.model = "I-Phone X"
              print("Mobile class constructor call")
      
      apple = Mobile("8 GB","512, GB")
      print(apple.__dict__) # Output :- {'ram': '8 GB', 'storage': '512 GB', 'model': 'I-Phone X'}
      
      OUTPUT :-
      
      Hello
      Mobile class constructor call
      {'model': 'I-Phone X'}



# Types of inheritance

1 ) Single Inheritance <br>
2 ) Multi-level inheritance <br>
3 ) Hierachical inheritance <br>
4 ) Multiple inheritance <br>
5 ) Hybrid inheritance <br>
6 ) Cyclic Inheritance <br>


**Single Inheritance :-**

1 ) One parent and one is child class <br>
2 ) Chils class can access parent class attribute and method but parent class cannot access child class atributes and method


**Multi-level Inheritance**

1 ) Parent class and child class further inherited into new class forming multple levels <br>

      #constructor in multi-level inheritance
      
      """
      samja jar manager class madhe constructor nasel tar to employee class cha constructor call karel ani jar Employee class madhe pan constructor nasel tar to Human being class chya constructor call karel
      """
      
      class Human_being(object):
          def __init__(self):
              print("Human being construcotr is called")
              self.name = input("Enter your name :")
      
      class Employee(Human_being):
          def __init__(self):
              print("Employee constructor called")
              self.salary = float(input("Enter your salary :"))
      
      class Managers(Employee):
          def __init__(self):
              print("Managers construcotr is called")
              self.bonus = float(input("Enter your bonus :"))
      
      m1 = Managers()


**Variable in multi-level inheritance**



    class Human_being(object):
        salary = 100
    
    class Employee(Human_being):
        salary = 200
    
    class Managers(Employee):
        salary = 300
    
    m1 = Managers()
    
    print(m1.salary)


# Hierachical inheritance

1 ) One parent and multiple child classes


      class Person:
          def __init__(self,name,age):
              self.name = name
              self.age = age
              
      
      class Employee(Person):
          def __init__(self,salary):
              self.salary = salary
      
      class Student(Person):
          def __init__(self,name,age,mark):
              super().__init__(name,age)
              self.mark = mark
      
      s1 = Student("Sachin",21,59)
      print(s1.name,s1.mark,s1.age)


# MRO :- method resoluation order (21)
