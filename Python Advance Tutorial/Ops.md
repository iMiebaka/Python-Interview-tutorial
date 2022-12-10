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
 
 
 <b> Type of Inheritance </b>
 
 1 ) Single Inheritance
 2 ) Multi - Level Inheritance
 3 ) Hierarchical Inheritance
 4 ) Multiple Inheritance

 
 
 # declaration of child class
 
 
 # Single Inheritance
 
 If a class is derived from one base class ( Parent Class ), it is called single inheritance.
 
 <b> Syntax:- </b>
 
 
       class ParentClassName(object):
          members of parent class

       class ChildClassName(ParentClassName):
          member of child class
 
 
 
 <b>Example</b>
 
 

         class Father:
             money = 100
             def show(self):
                 print("Parent clss instance method")

             @classmethod
             def showmoney(cls):
                 print("Parent class method",cls.money)

             @staticmethod
             def stat():
                 a = 10
                 print("static method class",a)

         class Son(Father):
             def disp(self):
                 print("Child class instance method")

         s = Son()
         s.disp()
         s.show()
         s.showmoney()
         s.stat()
 
 
 
# Constructor in inheritance in python
 
 By default , The Constructor in the parent class is available to the child class
 
 
          class Father:

              def __init__(self):
                  self.name = "sachin"

          class Son(Father):

              def show(self):
                  print(self.name)

          data = Son()
          data.show()
 
 
 # constructor Overriding in python
 
 if we write constructor in the both classes , parent class and child class then the parent class constructor is not available to the child class.
 in this case only child class constructor is accesible which means child class constructor is replacing class constructor
 
 ( jar child class madhe constructor define asel tar to parent class cha constructor ghet nahi. ani jar parent class cha constructor call kela tar
 error yeil )
 
 
           class Father:

              def __init__(self):
                  self.name = "sachin"

          class Son(Father):

              def __init__(self):
                  self.name = "sagar"

              def show(self):
                  print(self.name)

          data = Son()
          data.show()

           ----------- OUTPUT -----
           sagar
 
 
 
 
 # Multi-Level Inheritance
 
 In multi-level inheritance, the class inherits the feature of another derived class
 
 
         class Father:
            def showF(self):
                print("Father class Method")
                self.name = 100

        class Son(Father):
            def showS(self):
                print("Son class Method")

        class G_Son(Son):
            def showG(self):
                print("Grand son class Method")

        data   = G_Son()

        data.showG()
        data.showS()
        data.showF()
 
 
 
 # Hierarchical Inheritance
 
 In this clas we create a one class to multiple child class
 
 
 
        class Father:
           member oif class father


       class Son(Father):
           member of class son

       class Daughter(Father):
           member of class daughter

 
 
 
 <b>example</b>
 
            class Father:
               def showF(self):
                   self.name = "sachin"
                   print("Father class mehod")


           class Son(Father):
               def showS(self):
                   print("Son class mehod")



           class Daughter(Father):
               def showD(self):
                   print("Daughter class mehod")

           data = Daughter()
           data.showD()
           data.showF()
 
 
 
 # Multiple Inheritance
 
 if a class is derived from more than one parent classs, then it is called multiple inheritance.
 
 <b>Syntax :-</b>
 
          class ParentClassName1(object):
             member of parnet class

         class ParentClassName2(object):
             member of parent class


         class ChildClassName(ParentClassName1,ParentClassName2):
 
 
 
 ----- Eample
 
 
          class Father(object):
             member of father class

         class Mother(object):
             member of mother class


         class Son(Father,Mother):

-------
 
 
         class Father(object):
            def showF(self):
                print("father class method")


        class Mother(object):
            def showM(self):
                print("Mother class method")


        class Son(Father, Mother):
            def showS(self):
                print("son class mehtod")

        data = Son()
        data.showS()
        data.showM()
        data.showF()

 
 
 # Polymorphism
 
 
 plymorphism means same function name ( but different signuture ) being uses for different types
 
 
 
 
 
 
 
 
 
