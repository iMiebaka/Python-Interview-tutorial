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
                             def __init__(self): #_______________ ha constructor
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
                
                
                
                
                
                
                
                
                
                
                
                
                
                
   







