# Encasulation 


data la encapsulate karun thevne . 
example:

samja A,B,C variable ahe te mi var declare kelay ani 100 line nantar mi punha A declare kela . yamule kay hoil adhicha declare kelela variable
ani attacha declare kelela variable conflict yein hi condition handle karnya sathi apan A,B,C ya variable la aka class madhe encapsulation karto 
te class madhle variable private astat tyana class chya baher access hot nahi class chay atle variable private astat

# Abstraction

abstraction mhanje jya goshtichi garaj ahe tyach dakhavne bakiche hide karne . mhanje user la tevdach dakhavla jat ki tyala jyachi garaj ahe
bakicha sagla tya pasun hide karun thevla jat


# Inheritance

mhaje kuthli gosha virasat madhe milne jas father kadun son kade inheritance houn yene
ya madhe code la repeate lihava lagat nahi . aka class madhun data 


# Polymorphism

function name same pan tyacha kam define kel ahe mhanje input madhe kay yetay tya according action perform karta tyachya according data show karto





______________________________________________________________________________________________
# Class
A python class is a group of attibutes and methods.

1 ) Attributes
Attribute are represented by variable that contains data

jas code python mandhe ( a= 10) tylach yethe attributes mhatat

2 ) What is method

method mhanjech function . tech function class madhe method mhantat 

What is class 

        class ClassName(objects):
          def __init__(self):
              self.variable_name = value

          def method_name(self):
              Body of method
              
              
1 ) class : class keyword in used to create a class
2 ) object : object represents the base clas name from where all class in python are derived this class is also derived from object class this 
             optional
             
3 ) __init__() : hi method initilize karte variable la . hya method la call karnyachi gar nahi automatically call hoto . yacha kam asta variable la
                 initilize karne 
                 
4 ) self         : self variable chay javal current object asto 



Rules  -----------------------------

1 ) The class ame can be any valid identifier
2 ) it cant be python reserverd word
3 ) a valid class name starts with latter 
4 ) class generally start with capital letter


how to declare class




              class Mobile:
                def __init__(self):
                    self.model = "RealMe X"
                def show_model(self):
                     print("Model",self.model)



              Create class with arugment

              class Classname:
                def __init__(self ):
                  self.variable_name = value
                  self.variable_name = "value"

                def method_name(self):
                  body of method
    
   
   @ ) what is object
   
   
   object ha class type cha variable ahe 
   
   
   
   create object
   
                object_name = class_name()
                
                
                
                
                
   Real class
   
   Eample
   
   
   
          class Mobile:
            def __init__(self):
              self.model = "RealMe X"

            def show_mobile(self):
              print("Model",self.model)

          realme = Mobile()
                
                
 ________ HOW it works _____________
 
 realme = Mobile()
 
 1 ) a block of memory is allocated on heap .  the size of allocated memory is to be decided from the attributes and methods are avaialbel in the
     class (Mobile) 
     
 2 ) After allocating memeory block the special method  __init__() is called internally . the method stores the initial data into variable
 
 3 ) The allocated memory location address of the instance is returned in to object
 
 4 ) the memory location is passed to self
 
 
 
_____________ Accessing class member using object __________

1 ) We can access variable and method of a class using class object or instance of class

                        object_name.variable_name
                        realme.mode

                        object_name.method_name()
                        realme.show_model():

_________________ Self variable ______

self is a default variable that contains the memory address of the current object this variable is used to refere to allthe instance variable and method
when we careate aobject of a class the object name contains the memory location of the object
this imemofy location is internally passed to self as self as self know the memory address of the object so we can access variable and method of object
self is the first argument o any objhect method because the first argument is always the object referance . this is automatic whether you call it
self or not


___________ Object _______

Each time you create an object of a class a copy of ech variable defined in the class is created

                class Mobile:
                    def __init__(self):
                        self.model  = "Readme X"

                    def show_model(self):
                        print("Model",self.model)

                realme = Mobile()
                redmi  = Mobile()
                geek   = Mobile()



_______________ Real work Example ______


          class Mobile:
              def __init__(self , m):
                  self.model = m


              def show_model(self , p):
                  price = p
                  print("model", self.model , "Price",price)

          x = Mobile("Realme X")
          x.show_model(1000)
                
                
                
# Constructor

class object banavlyavar constructor automatically call hoto yala call karnyachi garj nahi. ha akdach call hosto jeva instance create hoto
jeva object create karto . 2 instance ( object ) banavle asle tar constructor 2 da call hoto 

Example :
                       
                       class Mobile:
                             def __init__(self): _______________ ha constructor
                                self.model = "RealME  x"

                        realme = Mobile()
                        
                        
 Example :
 
                class Mobile:
                    def __init__(self,m , v = 100):
                        self.m = m
                        self.v = v
                        print("Construtor is call")


                    def show_m(self , mobile , price):
                        self.mobile = mobile
                        self.price = price

                        print(self.mobile)
                        print(self.price)


                m = Mobile("Iphone")
                m.show_m(mobile = "Realme",price = 234)

                ok = Mobile("Samsung")
                ok.show_m(mobile = "Samsung" , price = 321)
                
                
                OUTPUT : 
                Construtor is call
                Realme
                234
                Construtor is call
                Samsung
                321




1 ) Python supports a special type of method called constructor for initializing the instance variable of a class
2 ) A class constructor , if defined is called whenever a program creates an object of that class
3 ) A constructor is called only once at the time of creating an instance . if two instance are created for a class , the constructor will be called once for each instance
                
                
                
                
                
                
 # Type of variable
 
 instance variable la constroctor chay aat initilize ani define kel jat
 
 1 ) Instance  Variable 
                1 ) Intance variable are the variable whose separate copy is created in every object instance varibale are defined and initialized using 
                a constructor with self parameter
                
    
  Example 
  
                  class Mobile:
                    def __init__(self):
                        self.model = "Realme X"

                    def show_model(self):
                        print(self.model)

                realme = Model()
                
  ________________________________________________________________________________________
  2 ) Accessing instance variable
  ________________________________________________________________________________________
    
  with Instance method
  
  to access instance variable , we need instance methods with self as first parameter then we can access instance variable using self.variable_name
  
  Example : 
  
                          class Mobile:
                            def __init__(self):
                                self.model = "Realme X"   _____________ Instance variable
                                
                                print(self.model)
                            def show_model(self):        _______________ Instance method
                                print(self.model)        ________________ Accessing instance variable
                                
                        realme = Mobile()

___________________________________


Access instance variable outside class

___________________________________

class chay baher instance variable access karaycha aslyavar objectname.variable_name

Example 

                        class Mobile:
                            def __init__(self):
                                self.model = "Realme X"
                            def show_model(self):
                                self.model
                        realme = Mobile()


                        print(realme.model) ________________ we access outside of the class
                        

POINT : 
        Intance variable are the variable whose separate copy is created in every object if we modify the copy of instance variable , it will not efect           all the copies in the other instance
        
        
        ( ya madhe pratek object sathi ak navin copy banel copy object madhe changes kelyavar real object var effect padnar nahi ) 
        
                        class Mobile:
                            def __init__(self):
                                self.model = "Realme X"
                            def show_model(self):
                                print(self.model)

                        realme = Mobile()

                        redme = Mobile()

                        geek = Mobile()
                        
                        
Example : 


                                class Mobile:
                                    def __init__(self):
                                        self.model = "RealMe X"  # Instance Variable

                                    def show_model(self):
                                        print(self.model)        # Accessing instance Variable

                                realme = Mobile()
                                redmi = Mobile()
                                geek = Mobile()


                                print(realme.model , f"ID is {id(realme.model)}")
                                print(redmi.model, f"Id Is {id(redmi.model)}")
                                print(geek.model, f"ID is {id(geek.model)}")

                                print()
                                redmi.model = "Redmi 7s"

                                print(realme.model , f"ID is {id(realme.model)}")
                                print(redmi.model, f"Id Is {id(redmi.model)}")
                                print(geek.model, f"ID is {id(geek.model)}")
                                
                                
                                OUTPUT _____________
                                RealMe X ID is 139975711000688
                                RealMe X Id Is 139975711000688
                                RealMe X ID is 139975711000688

                                RealMe X ID is 139975711000688
                                Redmi 7s Id Is 139975711001264
                                RealMe X ID is 139975711000688
   





_______________________________________________________________________________________________
2 ) Class Variable / Static Variable 
_______________________________________________________________________________________________
yamadhe akach object copy aste ti saglay madhe share hote . jar aka object chay variable madhe jar kahi update kel tar te saglay var update hot

1 ) classs variable are the variable whose single copy is avaialble to all the instance of the class if we modify the copy of class variable in an instance , it will effect all the copies in the other instance

Example :

                class Mobile:
                    fp = "Yes"

                    def __init__(self):
                        self.model = "Readme"

                s = Mobile()
                print(s.fp)
                
                
 access class variable outside of the classs
 
 Example :
 
                         class Mobile:
                            fp = "Yes"           # class variable
                            def __init__(self):
                                self.model = "Readme"
                            def show_model(self):
                                print(self.model)
                            @classmethod
                            def is_fp(cls):      # class method
                                cls.fp
                        s = Mobile()
                        print(s.fp)
                        
                        
  POINT : 
        Class variable are the variable whose single copy is available to all the instance of the class . if we modify the copy of class variable in an 
        instance , it will effecct all the copies in the other instance
        
        
        
Example : 

                                class Mobile:
                                    fp = "Yes"   # class variable

                                    def __init__(self):
                                        self.model = "RealMe X"

                                    def show_model(self):
                                        print("Model :", self.model)

                                    @classmethod    # Decorator
                                    def is_fp(cls):
                                        print(cls.fp)

                                realme = Mobile()
                                realme.show_model()
                                Mobile.is_fp()

                                # +++++++++ after modify
                                print()
                                Mobile.fp = "No"
                                Mobile.is_fp()
                                
                                
                                OUTPUT __________________________
                                
                                
                                Model : RealMe X
                                Yes
                                No
                                
                                


__________________________________________________________________________________
# Namespace 
__________________________________________________________________________________
        
In python , namespace represents a memory block where names are mapped to object

class Namespace - A class maintains it own namespace known as class namespace. in the class namespace , the names are mapped to class variables

instance Namespace - Every instance have it's own namespace known as instance namespace . In the instance namespace , the names are mapped to instance variable


____

MARATHI :

        yamadhe namespace ha represents karto mamory block la ani block ha mapped karto object la
        
        class namespace madhe name la class variable shi match kel jat
        
        instance name variable madhe instance variable la namespace shi match kel jat
        
        
        
        
        
 Example :
         
         class Mobile:
                fp  = "Yes"
                
         realme = Mobile()
         redmi  = Mobile()
         geek   = Mobile()
         
         
         
         
         ( Yamadhe  realme , redme , geek he instance name space ahe ) 
         
         
         
Example :

                                class Mobile:
                                    fp = "Yes"

                                    @classmethod
                                    def is_fp(cls):
                                        print("Finger pring " , cls.fp)

                                realme = Mobile()
                                redmi  = Mobile()
                                geek   = Mobile()

                                print("Class FP" , Mobile.fp)
                                print("realme" , realme.fp)
                                print("redmi" , redmi.fp)
                                print("Geek" , geek.fp)

                                print()

                                Mobile.fp = "No"
                                print("Class FP" , Mobile.fp)
                                print("realme" , realme.fp)
                                print("redmi" , redmi.fp)
                                print("Geek" , geek.fp)

                                print()

                                realme.fp = "Not Working"
                                print("Class FP" , Mobile.fp)
                                print("realme" , realme.fp)
                                print("redmi" , redmi.fp)
                                print("Geek" , geek.fp)
                                
                                
                                OUTPUT :_____________________
                                
                                Class FP Yes
                                realme Yes
                                redmi Yes
                                Geek Yes

                                Class FP No
                                realme No
                                redmi No
                                Geek No

                                Class FP No
                                realme Not Working
                                redmi No
                                Geek No










_________________________________________________________________________________________________
# Type Of Methods
_________________________________________________________________________________________________
        
 
 
 1 ) Instance Methods
        - Accessor Methods
        - Mutator Methods
        
 2 ) Class Methods
 
 
 3 ) Static Mehod
 
 
 ________________________________________________________________________________________________
 
 # Instance Method
 
 Instance methods are the methods which act upon the instance variables of the class instance method need to know the memory address of the instance       which is provided through self variable by default as first parameter for the instance method
 
 
                 def method_name(self):
                        function body

  
  # calling instance method W/O Argument
  
  instance methods are bound to object of the class so we call instance method with o bject name
  
  Syntax - object_name.method_name()
  
  
                  class Mobile:
                        def show_model(self):
                                print("RealMe X ")

                  realme = Mobile()
                  realme.show_model()
  
  
  
  # Instance Method with Parameter
  
                  class Mobile:
                        def __init__(self):
                                self.model = "ReadMe X"


                        def show_model(self , p):
                                self.price = p
                                print(self.model, self.price )

                   realme = Mobile()
   
   # calling instance method with argument
   
   Syntax :- object_name.method_name(Actual_argument)
   Ex :-     show_model(1000 )
   
                   class Mobile:
                        def __init__(self):
                                self.model = "RealMe X"

                        def show_model(self , p ):
                                self.price = p
                                print(self.model , self.price )
                   realme = Mobile()
                   realme.show_model(1000)
                   
                   
                   
   
 # Nested Class
 A class within a class is calles as nested calss or nesting of a class
 
 Example :
 
 
                         class OuterClassName():
                                def __init__(self):
                                        self.variable_name = value
                                        self.innterClassObjectName = self.InnerClassName()

                                def method_name(self):
                                        method body



                                class InnerClassName:
                                        def __init__(self):
                                                self.variable_name = value
                                        def method_name(self):
                                                method body
                                                
                                                


Example 2 :
 
 
                                class Army:
                                    def __init__(self):
                                         self.name = "Rahul"
                                         self.gn   = self.Gun()

                                    def show(self):
                                         print(self.name)


                                    class Gun:
                                         def __init__(self):
                                               self.name = "AK47"
                                               self.capacity = "75 Rounds"
                                               self.length   = "34.3 In"

                                         def disp(self):
                                               print(self.name , self.capacity , self.length)

                                a = Army()
                                
                                
Example 3 :

                        class Army:
                            def __init__(self):
                                self.name = "Rahul"
                                self.gn = self.Gun()

                            def show(self):
                                print("Name :",self.name)



                            class Gun:
                                def __init__(self):
                                    self.name = "AK47"
                                    self.capacity = "75 Round"
                                    self.length  = "34.3 In"

                                def disp(self):
                                    print("Gun Name",self.name)
                                    print("Capacity", self.capacity)
                                    print("Length : ", self.length)


                        a = Army()
                        print(a.name)
                        a.show()


                        print(a.gn.name)
                        
                        
                         OUTPUT :::
                         
                         Rahul
                         Name : Rahul
                         AK47
                                                
                                                
                                                

_______________________________________________________________________________________________________________________


# Iheritance


_______________________________________________________________________________________________________________________

1 ) The mechanism of deriving a new calss from an old one  ( existing class ) such that the new class inherit all the member (variable and method ) of odd class is called inheritance or derivation .





old class pasun new class banavne tyala inheriitance mahantat

_________________________________________________________________________________________________________________________________
Other Name


Parent Class         - Base Class or Super Class
Child Class          - Derived Class or Sub Class



# Super Class And Sub Class 

The old class is referred to as the Super class and the new one is called the sub class



# Inheritance

1 ) All classes in python are built in from a single super class called "object"  so whenever we create a class in python  , object will become super class for them internally


Class Mobile(object):
class Mobile:


2 ) The main advantage of inheritance is code reusability




# Why do we need Inheritance




class Employee:
    id = 1
    
    @classmethod
    def getid(cls):
        return cls.id
        
     def setname(self , name):
        self.name
        
     def getname(self , name):
        self.name
        
     def getsalary(self , salary):
        return self.salary
        
     def setovertime ( self , ot):
        self.ot = ok
    
     def getovertime(self):
        return self.ot
        
        
        
        
 # inherit two classs
 
 
 ________________________________ Parent Class __________
 
 
class Employee:
     id = 1
     @classmethod
     
     def getid(cls):
        return cls , id
        
     def setname(self , name ):
        self.name = name
        
     def getname(self):
        return self.name
        
     def setsalary(self):
         self.salary = salary
         
     def getsalary(self , salary):
         return self.salary
         
     def setovertime ( self , ot):
         self.ot = ot
         
     def getovertime(self):
         return self.ot
         
         
________________________ Child Class________

class Manager:
    def setsalary(self , salary):
        self.salary = salary
        
    def getsalary(self):
        return self.salary
        
    def getseniorname(self , sname):
        self.name = sname
     
    def getseniorname(self):
        return self.sname
         
         
         
        
        
        





















                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
                                                
 
 
 
 
 
 
 
 
 
        
        
