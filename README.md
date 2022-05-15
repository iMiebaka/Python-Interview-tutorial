# Python-Interview-tutorial


# String slicing
 
 string slicing means select range of element from string 
 example suppose i have string sachin i want to print s to i so how i will print
 
 it will skip last element
 
          name = "sachin"<br/>
          print(name[0:5])



# step Argument

स्टेप arugument  म्हणजे first  पॅरामीटर print  झालयावर किती स्टेप घ्यायच्यात

           name = "sachin"<br/>
           print(name[0:5:2])

           Output : sci


# what is strip method

strip method  चा वापर truncates  किंवा remove  करण्यासाठी होतो

लेफ्ट side  चा space  remove करण्यासाठी आपण name.lstrip() method  use करतो . आणि right  side  चा space remove करण्यासाठी आपण name.rstrip() वापरतो

            name = "    sachin     "<br/>
            print(name.lstrip())


# string is a immutable
string is a immutable  कारण आपण main  string चांगले करू शकत नाही

example 
असा केला तर error  येईन 

          a = "sachin"<br/>
          a[0]="S"


पण जर आपण replace  केला तर तो नवी string बनवतो पण आधीची तशीच ठेवतो

           a = "sachin"<br/>
           print(a.replace("s","a"))<br/>
           print(a)

           OUTPUT : aachin
                    sachin

         
# what is pass statement

pass  स्टेटमेंट चा वापर आपण तेव्हा करतो when we don't want to aything

           for i in range(1 , 10):<br/>
               if i == 5:<br/>
                   pass

 # Default Parameter
 
 default  parameter  म्हणजे जे कि आपण function  मध्ये value  pass  करतो . आणि जर function ला call केलं आणि value pass केल्या तर तो default value ला over  right  करतो 

            def name(name = "sachin" , age  = 24): <br/>
               print(name , age)<br/>


           name("sachinpaar",20)


# what is list
list is a order collections of item 

append method element हा प्रत्येक वेळेस last  ला add करील
           a = ["sachin",'pawar'] <br/>
           a.append("10")<br/>
           print(a)<br/>


# insert method in list

या मध्ये आपण element position ला add करू शकतो


           a = ["sachin",'pawar'] <br/>
           a.insert(1,"10") <br/>
           print(a) <br/>

           OUTPUT : ['sachin', '10', 'pawar']

# pop method 

pop method list मधून लास्ट element ला delete करिन जर कुठलाच argument पास नाही केला तर

           a = ["sachin",'pawar','sagar'] <br/>
           a.pop()<br/>
           print(a)<br/>

           OUTPUT : ['sachin', 'pawar']


आणि जर index नंबर पास केला तर त्या position चा element delete करिन

           a = ["sachin",'pawar','sagar'] <br/> 
           a.pop(1) <br/>
           print(a) <br/>

           OUTPUT : ['sachin', 'sagar']

# Split method

split method string ला list मध्ये convert करतो

           a = "sachin pawar" <br/>
           print(a.split(" "))


# Join method

join वापर होतो list join करायला 

          a = ["sachin","pawar"] <br/> 
          print(" , ".join(a)) <br/>


          OUPTUT : sachin , pawar



# List VS Array

list or array means order collections of item

array मध्ये एकाच type चा data store करू शकतो म्हणजे int , किंवा string 

list madhe store any data


# List VS string

1 ) String are immutable means we cant change 
2 ) list are mutable means original element la change karto 


# what is list comprehension in python

creating lists based on existing iterables <br/>

        list1 = [1,43,53,65,32,74,23] <br/>
        l = [i for i in list1 if i % 2 == 0] <br/>
        print(l)

        OUTPUT : [32, 74]



# What is tuple 
tuple is emmutable means we cant change in data . we cant append  , remove . tuple आपण तेव्हा असे करतो जेव्हा आपल्याला माहित असता कि आपला डेटा चांगले नाही होणार
emaple . day's tuple त्यासाठी असे करतो कि तो faster आहे list पेक्षा

method we can use in tuple 1 ) count 2 ) index 3 ) length 4 ) slicing


# What is list comprehension
comprehension means आपण list  ला एक line मध्ये create करू शकतो
Example.

          fruits = ["apple", "banana", "cherry", "kiwi", "mango"]<br/>

          newlist = [x for x in fruits if "a" in x]<br/>

          print(newlist)<br/>

creating a list based on existing lists . it is faster than for loop

Example 2 :
   
   fruits = ["apple", "banana", "cherry", "kiwi", "mango"]<br/>

   newlist = [x for x in fruits if x != "apple"]<br/>

   print(newlist)<br/>
   
   OUTPUT : ['banana', 'cherry', 'kiwi', 'mango']
   
# dictionary comprehension 

dictionary comprenhension is a method for transforming one dictionary into another dictionary

    keys = ['a','b','c','d','e']<br/>
    values = [1,2,3,4,5]  <br/>
    myDict = { k:v for (k,v) in zip(keys, values)}  <br/>
    print (myDict)<br/>


    Output : {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}

# what is *args

means म्हणजे आपण multiple value pass करू शकतो function ला

      def ok(*args):<br/>
          print(type(args))<br/>
      ok("sachin",'pawar','application')<br/>

      OUTPUT: ('sachin', 'pawar', 'application')

Output he tuple madhe yein


Example 2 :
 
      def total_num(*args):<br/>
         count = 0<br/>
         for res in args:<br/>
             count = count + res<br/>
         print(count)<br/>
     total_num(1,2,3,4,5)<br/>


# what is ** Kwargs

means we can pass multiple keyword arguments

      def ok(**Kwargs):
          print(Kwargs)
      ok(name = "sachin",age = 20)

      OUTPUT : {'name': 'sachin', 'age': 20}

output dictionary madhe mile

Emaple : 
       def ok(**Kwargs):
    for k ,v in Kwargs.items():
        print(k,v)
    ok(name = "sachin",age = 20)


OUTPU : name sachin
        age 20


# what is Lambda

A lambda function is a small anonymous function. A lambda function can take any number of arguments, but can only have one expression

Syntax : lambda arguments : expression


Example : 

        x = lambda a : a + 10 <br/>
        print(x(5))<br/>
        
        OUTPUT : 15
        
A lambda is essentially an anonymous function: a function object with no name

# what is enumerate 

converts a data collection object into an enumerate object . Enumerate returns an object that contains a counter as a key for each value within an object, making items within the collection easier to access

याने number आणि position find करायला easy जात

Example :


          l1 = ["eat", "sleep", "repeat"]<br/>
          for ele in enumerate(l1):<br/>
              print (ele)<br/>

          OUTPUT : 

          (0, 'eat')<br/>
          (1, 'sleep')<br/>
          (2, 'repeat')<br/>







# what is map function 


हे आपल्याला allow करता process करायला आणि iterable करायला without using loop 

useful when you need to apply a transformation function to each item in an iterable and transform them into a new iterable.

Emaple :

       def addition(n):
           return n + n

       # We double all numbers using map()
       numbers = (1, 2, 3, 4)
       result = map(addition, numbers)
       print(list(result))
       
       Output : [2, 4, 6, 8]
       
       
# what is filter function

The filter() method filters the given sequence with the help of a function that tests each element in the sequence to be true or not.

Example : 

       def is_even(a):
           return a % 2 == 0

       numbers = [1,2,3,4,5,6,7]
       is_even = tuple(filter(is_even , numbers))
       print(is_even)
       
       OUTPUT : (2, 4, 6)
       
it will return only even numbers


# what is zip() Function

zip() function returns a zip object . हा zip करतो २ item ला 


Example : 

       f = ["sachin","pawar","application"]
       c = ["ok",'system','ss']
       print(list(zip(f,c)))
       
       Output : [('sachin', 'ok'), ('pawar', 'system'), ('application', 'ss')]
       
       
pan samja list of item lenght same nasel tar ha 2 element return karin last wala skip karin

Emaple :

        f = ["sachin","pawar","application"]
        c = ["ok",'system']
        print(list(zip(f,c)))

        Output : [('sachin', 'ok'), ('pawar', 'system')]
       
 

# oops programming




# what is class

class is blueprint of object


# what is method

class च्या आत जे function define करतो त्याला क्लास म्हणतात 

A class method is a method which is bound to the class and not the object of the class. They have the access to the state of the class as it takes a class parameter that points to the class and not the object instance

Example :

          class DemoClass:

              a = 10
              def showvalue(self):
                  self.c = self.a*self.a
                  print(self.c)

              def showvalue1(self,a,b):
                  print(a + b)

          obj = DemoClass()
          obj.showvalue()
          obj.showvalue1(10,20)

# what is self 

The self parameter is a reference to the current instance of the class, and is used to access variables that belongs to the class.



Emaple :

        class DemoClass:

            a = 10
            def sumvalue(self):
                print(20+30)

        demoobject = DemoClass()

        demoobject.sumvalue()
        
        
        
        
        
# what is constructor 

जसा आपण class चा object बनवतो त्या वेळी constructor automatic call होतो . constructor ला आपल्याला call नाही करावा लागत method ला call करावा लागतो , constructor automatic कॉल होतो
allow you to create and properly initialize objects of a given class, making those objects ready to use



Example :

       class DemoClass:

           a = 10

           def __init__(self):
               print("welcome sachin")

           def showvalue(self):
               self.c = self.a*self.a
               print(self.c)

           def showvalue1(self,a,b):
               print(a + b)

       obj = DemoClass()
       obj.showvalue()
       obj.showvalue1(10,20)
       
       
       OUTPUT : 
       welcome sachin
       100
       30


# what is inheritance

Inheritance allows us to define a class that inherits all the methods and properties from another class

inherits  आपल्याला allow करता कि all method आणि properties from another class .In this hierarchical order, the class which inherits another class is called subclass or child class, and the other class is the parent class.


# Single Inheritance

single inheritance म्हणजे एका class मधून दुसऱ्या class मध्ये inherit करणे

     class A:
         def displayA(self):
             print("Welcome Sachin A")

     class B(A):
         def displayB(self):
             print("Welcome Sachin B")

     obj = B()
     obj.displayA()
     obj.displayB()
     
     
# Multilevel Inheritance 
multilevel inheritance mhanje aka class madhun dusrya class madhe ani dusrya madhun 3 rya class madhe inherits karne

Example

       class A:
           def displayA(self):
               print("Welcome Sachin A")

       class B(A):
           def displayB(self):
               print("Welcome Sachin B")


       class C(B):
           def displayC(self):
               print("Welcome Sachin C")

       obj = C()
       obj.displayA()
       obj.displayB()
       obj.displayC()

# multiple inheritance 

multiple inheritance mhanje A , B class madhun C madhe inherit karne

Example :

          class A:
              def displayA(self):
                  print("Welcome Sachin A")

          class B:
              def displayB(self):
                  print("Welcome Sachin B")


          class C(A , B):
              def displayC(self):
                  print("Welcome Sachin C")

          obj = C()
          obj.displayA()
          obj.displayB()
          obj.displayC()
          
          



+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
# DJANGO INTERVIEW QUESTION
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
 # what architecture does djagno follow
 Django follow MVT patterns . stand for model view template
 
 # can we connect multiple database with djagno
 
 Yes we can multiple databse with django
 
 
 Emaple :

         DATABASES = {
            'default': {
                'NAME': 'app_data',
                'ENGINE': 'django.db.backends.postgresql',
                'USER': 'postgres_user',
                'PASSWORD': 's3krit'
            },
            'users': {
                'NAME': 'user_data',
                'ENGINE': 'django.db.backends.mysql',
                'USER': 'mysql_user',
                'PASSWORD': 'priv4te'
            }
        }



        python manage.py migrate --database=users
        python manage.py migrate --database=customers
        
        
 # what does makemigrations command do ?
 
 हे migrations create करत models साठी जे कि models.py  file मध्ये define असतं 
 ANS : it creates migrations for the models that you define in models.py file
 
 # so you said django follows MTV patterns . you mean django doesn't follow MVC right
 
 MVT is a similar to MVC . framework  controller चा most of the itself handle करतो त्यामुळे most  of the things ह्या models  , views  , and templates होतात 
 
 MVT closely resembles MVC . because , the framework handles the controller part itself so most things happen only in models  view and templates.
 
 
 # How is djagno code resusability feature different from other framworks
 djagno offer code reusability then other frameworks out there .  django project project is collection of diffrent application like ,  login , sign up
 these application we can just copy from one directory to another with some tweaks to settings.py file . we won't nedd to wirte new signup application from scratch
 
 # what happens wehn a typical django website gets a request ? Explain
 
 
 
 
 






 



