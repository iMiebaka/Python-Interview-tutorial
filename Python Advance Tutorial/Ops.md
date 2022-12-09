# what is class

a pytho class is a group of attributes and methods

# what is attributes
 Attrubutes are represented by varuable that contains data
 
 # what is method
 method performs an action or task. It is similar to function
 
 
 <b>Self is a variable</b>
 
 
       class Classname(object):

          def __init__(self):
              self.variable_name = value
              self.variable_name = "value"

          def method_name(self):
              Body of method

1 ) class - class keyword is used to create a class
2 ) object - object represents the base class name from where all classes in python are derived
     this class is also derived from object class. This is optional.
     
3 ) __init__() - This method is used to initialize the variable. This is a special method. We do not call this method explicitly
4 ) self - self is a variable which refers to current class instance/object


# Rules

1 ) The class name can be any valid identifier.
2 ) It can't be python reserved word.
3 ) A valid class name starts 


 # Object
 
 Each time you create an object of a class a copy of each variable defined in the clas is created
 
 
 
    class Mobile:

        def __init__(self):
            self.model = "RealMe X"

        def show_model(self):
            print("Model",self.model)

    realme = Mobile()
    redmi = Mobile()
    geek = Mobile()

    redmi.show_model()
    

<b>1 Example </b>

      class Myclass:
          def show(self):
              print("I am a Method")

      x = Myclass()
      x.show()
 
 <b> 2 Example </b>
 
     class Mobile:
        def __init__(self):
            self.model = "RealMe X"

        def show_model(self):
            print("Modelo :",self.model)

    realme = Mobile()

    realme.show_model()
 
 
 <b>3 Example </b>
 
     class Mobile:
        def __init__(self):
            self.model = "RealMe X"

        def show_model(self):
            print("Modelo :",self.model)

    realme = Mobile()
    realme.model = "RealMe Pro2"

    print(realme.model)
    realme.show_model()
    
OUTPUT 

RealMe Pro2
Modelo : RealMe Pro2


_____________________________________________________

# Constructor

Python supports a special type of method called constructor for initializiing the instance variable of a class
A class constructor , if defined is called whenever a program creates an objec of that class

A construcotr is called only once at the time of creating an instance
if two instance are created for a class, the constructor will be called once for each instance




# Constructor without parameter

       class Mobile:

          def __init__(self , a):
              self.name = a

      data = Mobile("I-phone")

      print(data.name)


# Type of variable

1 ) Instance variables are the variables whose separate copy is created in every object

2 ) Instance variables are defined and initialized using a constructor with self parameter


        class Mobile:
            def __init__(self):
                self.name = "Iphone"     <<---- Instance Variable

        data = Mobile()

# Accessing Instance Variable


To access instance variable, we need instance methods with self as first parameter then we can access instance variable using self.variable_name


       class Mobile:
           def __init__(self):
               self.name = "I-Phone" <<---- Instance Variable

           def show(self):      <<------ Instance Method
               self.name <<----  Accessing instance variable

       mobile = Mobile()
       print(mobile.name)


# Accessing Instance Variable

<b>Outside Class</b>

We can access instance variable using <b>object_name.variable_name</b>


      class Mobile:
          def __init__(self):
              self.name = "I-Phone"

      data = Mobile()
      print(data.name)      <<----- Access instance variable
      
 

# Instance Variable

Instance variable are the variables whose separate copy is created in every object. if we modify the copy of instance variable in an instance, it will
not effect all the copies in the other instance



       class Mobile:
           def __init__(self):
               self.model = "RealMe X"

           def show_model(self):
               print(self.model)

       realme = Mobile()
       redmi = Mobile()
       geek = Mobile()




# class Variable / Static Variable


class variables are the variables whose single copy is available to all the instance of the class
if we modify the copy of class variable in an instance, it will effect all the copies in the other instance

class Mobile:
    fp = "yes"     <<<<---- class varaible
    
    def show(self):
        self.name = "sachin"
        print(self.fp)
    
data = Mobile()
data.show()

 ___________________________________________________________
 
# Inheritance

The mechanism of deriving a new class from an old one ( existing class ) such that the new clas inherit all the members ( variable and mehods ) of old class is called inheritance or derivation


 old class
    |
    |
 New CLass


# Super class and sub class

The old class is referred to as the super class and the new one is called the sub class

* Parent class - Base class  or super class
* Child class  - Derived class or sub class



<b>Real life example<b>
 
         Father
          1) Home
          2) Money
          3) Business

         Son
           1 ) BMW



# Inheritance
 
All classes in python are build from a single super class called 'object' so whenever we create a class inpython, object will become super class for 
 them internally.
 
         class Mobile(object):
         class Mobile:

* The main advantage of inheritance is code resuability.
 
 

 # Single Inheritance
 
 
 
