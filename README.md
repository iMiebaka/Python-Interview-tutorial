# Python-Interview-tutorial


# String slicing
 
 string slicing means select range of element from string 
 example suppose i have string sachin i want to print s to i so how i will print
 
 it will skip last element
 
          name = "sachin"
          print(name[0:5])



# step Argument

स्टेप arugument  म्हणजे first  पॅरामीटर print  झालयावर किती स्टेप घ्यायच्यात

           name = "sachin"
           print(name[0:5:2])

           Output : sci


# what is strip method

strip method  चा वापर truncates  किंवा remove  करण्यासाठी होतो

लेफ्ट side  चा space  remove करण्यासाठी आपण name.lstrip() method  use करतो . आणि right  side  चा space remove करण्यासाठी आपण name.rstrip() वापरतो

            name = "    sachin     "
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

           for i in range(1 , 10):
               if i == 5:<br/>
                   pass

 # Default Parameter
 
 default  parameter  म्हणजे जे कि आपण function  मध्ये value  pass  करतो . आणि जर function ला call केलं आणि value pass केल्या तर तो default value ला over  right  करतो 

            def name(name = "sachin" , age  = 24): 
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


           a = ["sachin",'pawar'] 
           a.insert(1,"10") <br/>
           print(a) <br/>

           OUTPUT : ['sachin', '10', 'pawar']

# pop method 

pop method list मधून लास्ट element ला delete करिन जर कुठलाच argument पास नाही केला तर

           a = ["sachin",'pawar','sagar'] 
           a.pop()<br/>
           print(a)<br/>

           OUTPUT : ['sachin', 'pawar']


आणि जर index नंबर पास केला तर त्या position चा element delete करिन

           a = ["sachin",'pawar','sagar']  
           a.pop(1) <br/>
           print(a) <br/>

           OUTPUT : ['sachin', 'sagar']

# Split method

split method string ला list मध्ये convert करतो

           a = "sachin pawar" <br/>
           print(a.split(" "))


# Join method

join वापर होतो list join करायला 

          a = ["sachin","pawar"]
          print(" , ".join(a)) 


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

          fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

          newlist = [x for x in fruits if "a" in x]

          print(newlist)

creating a list based on existing lists . it is faster than for loop

Example 2 :
   
   fruits = ["apple", "banana", "cherry", "kiwi", "mango"]

   newlist = [x for x in fruits if x != "apple"]

   print(newlist)
   
   OUTPUT : ['banana', 'cherry', 'kiwi', 'mango']
   
# dictionary comprehension 

dictionary comprenhension is a method for transforming one dictionary into another dictionary

    keys = ['a','b','c','d','e']
    values = [1,2,3,4,5]  
    myDict = { k:v for (k,v) in zip(keys, values)}  
    print (myDict)


    Output : {'a': 1, 'b': 2, 'c': 3, 'd': 4, 'e': 5}

# what is *args

means म्हणजे आपण multiple value pass करू शकतो function ला

      def ok(*args):
          print(type(args))
      ok("sachin",'pawar','application')

      OUTPUT: ('sachin', 'pawar', 'application')

Output he tuple madhe yein


Example 2 :
 
      def total_num(*args):
         count = 0
         for res in args:
             count = count + res
         print(count)
     total_num(1,2,3,4,5)


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

        x = lambda a : a + 10 
        print(x(5))
        
        OUTPUT : 15
        
A lambda is essentially an anonymous function: a function object with no name

# what is enumerate 

converts a data collection object into an enumerate object . Enumerate returns an object that contains a counter as a key for each value within an object, making items within the collection easier to access

याने number आणि position find करायला easy जात

Example :


          l1 = ["eat", "sleep", "repeat"]
          for ele in enumerate(l1):
              print (ele)

          OUTPUT : 

          (0, 'eat')
          (1, 'sleep')
          (2, 'repeat')







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
 
 1 ) server match of the requested url in its url config 
 2 ) then it returns the corresponding view function it will then request the data from the model of that application 
 3 ) if any data required and pass it to the corresponding template which is then rendered in the browser other wise 404 return
 
 # what is django ORM
 ORM is the abstraction between models and the database where the data is stored . it make possible to retrive , save , delete and perform other operations over the database without ever writing any SQL code
 
 it cover many loopholes and takes all the field attributes and gives us more control over ower code in python rather than ay database language
 
 # Explain the use of session framework in django
 Django store and retrieve data on pre-site-visitor basis . it stores data on the server side and abstract the receiving and sending of cookies .  session can be implemented through a piece of middleware
 
 ___________________________________________________________________________
 # Django Intermediate 
 __________________________________________________________________________
 
 
 # what is wsgi 
 WSGI is the main python standard for communicationg between web servers and applications , but it only supports synchronous code
 
 
 # Middlewares - what they are and how they work
 
 Middlewares are hooks to modify django request or response object . it's a light , low-level plugin system for globally altering djagno input ro output
 
 You can use middleware if you want to midfy the request i.e HttpRequest object which is sent to the view . or you might want to modify the HttpResponse object returned from the view
 Example
 security middleware , session middleware , authentication middleware
 
 
 # what is Jinja Templating
 
 Django supports many popular templateing engines and by default it come with one very powerful templating engine . Jinja templating is a very popular templating engine for python , the latest version it the market is is jinja 2 . There are some fetures of jinja templating which makes it a better option then the default template system in django
 
 
 
 __________________________________________________________________
# Django Interview Question 
 
 __________________________________________________________________
 

# How a requeest is processed in django

1 ) first goese request handel by manage.py file
2 ) then these route to the settings.py file
3 ) then routing url.py file 
4 ) then routing views.py file
6 ) then models.py file
7 ) then templates


# what is difference between a project and an app in django
apan jevde pan application use karto tyala djagno project nava dila jat . in that project there are some functionlity astat tyala app mhantat
Accounts , Add to card

1 ) A project is the entire django application and an App is a module inside the project that deals with one specific use case.
for Example : Payment system (app ) in the ecommerce app(project)

2 ) An app is basically a web application that is created to perform a spcific task
3 ) a project , on the other hand , is a collection of these apps.
4 ) Therefore , a single project can consist of 'n' number of apps and a single app can be in multiple project




# why is django called a loosely coupled framewok

1 ) MVT helps in separting the server code from the client -related code
2 ) DJango models and views are present on the client machine and only template return to the client , which are essentially HTML , Css code and contains the required data from the models

3 ) These Components are totally independent of each other and therefore , font-end developer and backend developers can work simultaneously on the project as these two parts changing will have little to no effect on each other when changes 


# what is migrations in django
1 ) migration in djagno is to make changes to our models lke deleting , adding a field , etc into your database schema
2 ) a migration in djagno is a python file that contains changes we make to our models so that tehy can be converted into a database schema
3 ) so insted of manually making changes to our database schemas by writing queries in our DBMS shell, we can just make changes to our modles 
4 ) then we can use django to generate migrations from those model changes and run those migrations to make changes to our database schama


# what is CSRF token
protect from melicias attack

1 ) The csrf token is used to protection against cros - site request forgeries
2 ) This kind of attack takes place when a malicious website consist consists of alink , some javascript or a form whose aim is to perform some action on your website by using the login credentials of a genuine user

2 ) CSRF tokens can preent csrf attack by making it impossible for an attacker to construct a fully valid HTTP request suitable for feeding to a victim user
3 ) A CSRF token is a unique , secret , unpredictable value that is generated by teh server-side application and transmitted to the client in such a way that it is generated by the server -sside application and transmitted to the client in such a way that it is included in subsequent HTTP request makde by the client



# What is migrate do ?


A migration in Python uses the features of an ORM to provide tools to change our database. A migration system compares the current state of our application's models to the existing state of the database. When a difference is found, that difference can be described with a set of operations.



# why list are slower than tuple 

list are slower because it's nedded  two memory block to accesss . Element in list can be remove or move

# why tuple are faster 

Tuples are stored in a single block of memory. Tuples are immutable so, It doesn't require extra space to store new objects.


___________________________________________________________________________________________________________________________________________________

# API CORE CONCEPT

___________________________________________________________________________________________________________________________________________________

# What is API

API stands for Application Programming Interface. APIs let your product or service communicate with other products and services without having to know how they’re implemented . This can simplify app development, saving time and money. The API is not the database or even the server; it’s the code that governs the access point(s) for the server.


# What is a web API ?

A web API is a collection of endpoints that expose certain parts of an underlying database . developer can control each end point 

# API Method Type

1 ) GET   : Retrieve information about the REST API resource
2 ) POST  : Create a REST API resource
3 ) PUT   : Update a REST API resource
4 ) Delete: Delete Rest API resource

# What is CORS ?

Cross-Origin Resource Sharing (CORS) is a protocol that enables scripts running on a browser client to interact with resources from a different origin. This is useful because, thanks to the same-origin policy followed by XMLHttpRequest and fetch, JavaScript can only make calls to URLs that live on the same origin as the location where the script is running.

# How to fix CORS error in Django ?

CORS requires the server to include specific HTTP headers that allow for the client to determine if and when cross-domain requests should be allowed.
The easiest way to handle this–-and the one recommended by Django REST Framework–-is to use middleware that will automatically include the appropriate HTTP headers based on our settings.

We use django-cors-headers:

1 ) add corsheaders to the INSTALLED_APPS
2 ) add CorsMiddleware above CommonMiddleWare in MIDDLEWARE
3 ) create a CORS_ORIGIN_WHITELIST



____________________________________________________________________________________________________________________________________________________

# Djagno RestFramework

____________________________________________________________________________________________________________________________________________________

# What is Django RestFramework

Django REST Framework is a web framework built over Django that helps to create web APIs which are a collection of URL endpoints containing available HTTP verbs that return JSON. It’s very easy to build model-backed APIs that have authentication policies and are browsable.

# What are benefits of using Django Rest Framework 

1 ) Its Web-browsable API is a huge usability win for your developers.
2 ) Authentication policies include packages for OAuth1 and OAuth2.
3 ) Serialization supports both ORM and non-ORM data sources.
4 ) It’s customizable all the way down. Just use regular function-based views if you don’t need the more powerful features.
5 ) It has extensive documentation and great community support.
6 ) It’s used and trusted by internationally recognized companies including Mozilla, Red Hat, Heroku, and Eventbrite.

# What are serializers ?
Serializers allow complex data such as querysets and model instances to be converted to native Python datatypes that can then be easily rendered into JSON, XML or other content types . Serializers also provide deserialization, allowing parsed data to be converted back into complex types, after first validating the incoming data.

# What are Permissions in DRF ?

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.

Permissions are used to grant or deny access for different classes of users to different parts of the API.

The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the IsAuthenticated class in REST framework

# What are Project-Level Permissions ?

1 ) AllowAny - any user, authenticated or not, has full access
2 ) IsAuthenticated - only authenticated, registered users have access
3 ) IsAdminUser - only admins/superusers have access
4 ) IsAuthenticatedOrReadOnly - unauthorized users can view any page, but only authenticated users have write, edit, or delete privileges

          # blog_project/settings.py

          REST_FRAMEWORK = {
           'DEFAULT_PERMISSION_CLASSES': [
               'rest_framework.permissions.IsAuthenticated', # new
           ]
          }
          
 # 
 
 
 # What is Basic Authentication?

 
 The most common form of HTTP authentication is known as “Basic” Authentication. When a client makes an HTTP request, it is forced to send an approved authentication credential before access is granted.

1 ) Client makes an HTTP request
2 ) Server responds with an HTTP response containing a 401 (Unauthorized) status code and WWW-Authenticate HTTP header with details on how to authorize
3 ) Client sends credentials back via the Authorization HTTP header
4 ) Server checks credentials and responds with either 200 OK or 403 Forbidden status code. Once approved, the client sends all future requests with the Authorization HTTP header credentials.



# What is session authentication ? 

At a high level, the client authenticates with its credentials (username/password) and then receives a session ID from the server which is stored as a cookie). This session ID is then passed in the header of every future HTTP request. When the session ID is passed, the server uses it to look up a session object containing all available information for a given user, including credentials. This approach is stateful because a record must be kept and maintained on both the server (the session object) and the client (the session ID)

1 ) A user enters their log in credentials (typically username/password)
2 ) The server verifies the credentials are correct and generates a session object that is then stored in the database
3 ) The server sends the client a session ID — not the session object itself—which is stored as a cookie on the browser
4 ) On all future requests the session ID is included as an HTTP header and, if verified by the database, the request proceeds
5 ) Once a user logs out of an application, the session ID is destroyed by both the client and server
6 ) If the user later logs in again, a new session ID is generated and stored as a cookie on the client



# What is Token Authentication

Tokens are pieces of data that carry just enough information to facilitate the process of determining a user's identity or authorizing a user to perform an action. All in all, tokens are artifacts that allow application systems to perform the authorization and authentication process.

Token-based authentication is stateless: once a client sends the initial user credentials to the server, a unique token is generated and then stored by the client as either a cookie or in local storage. This token is then passed in the header of each incoming HTTP request and the server uses it to verify that a user is authenticated. The server itself does not keep a record of the user, just whether a token is valid or not




# What is Garbage Collection ? 

1 ) Garbage means remove unused object from memory location
2 ) garbage collector is predefine program nused or unreferenced objects from the memory location.
3 ) Any object reference count becomes zero then we call that object as a unused or unreferenced object Then no.of reference variables which are pointing the object is known as a reference count of the object.
4 ) While executing the python program if any object reference count becomes zero, then internally python interpreter calls the garbage collector and garbage collector will remove that object from memory location.
5 ) While executing the python program if any object reference count becomes zero, then internally python interpreter calls the garbage collector and garbage collector will remove that object from memory location.

# How is memory managed in Python ?

1 ) Python memory is managed by Python private heap space . 
2 ) All Python objects and data structures are located in a private heap. 
3 ) The programmer does not have an access to this private heap and interpreter
4 ) Python also have an inbuilt garbage collector
5 ) which recycle all the unused memory and frees the memory and makes it available to the heap space.
6 ) The allocation of Python heap space for Python objects is done by Python memory manager. The core API gives access to some tools for the programmer to code.
7 ) Python has a private heap space to hold all objects and data structures. Being programmers, we cannot access it; it is the interpreter that manages it. But with the core API, we can access some tools. The Python memory manager controls the allocation.


# Diff between shallow copy and deep copy ?

Deep COPY : A deep copy copies an object into another. This means that if you make a change to a copy of an object, it won't affect the original object.             In Python, we use the function deepcopy() for this, and we import the module copy. We use it like

Example : 

           import copy
           b = copy.deepcopy (a)

Shallow COPY : A shallow copy, however, copies one object's reference to another. So, if we make a change in the copy, it will affect the original                      object. For this, we have the function copy()


Example : 

         b = copy.copy(a)
         
         
# Explain split(), sub(), subn() methods of re module in Python

1 ) split() – uses a regex pattern to "split" a given string into a list.
2 ) sub() – finds all substrings where the regex pattern matches and then replace them with a different string
3 ) subn() – it is similar to sub() and also returns the new string along with the no. of replacements.subn() – it is similar to sub() and also returns       the new string along with the no. of replacements.

# What is a Python module ? 

1 ) A module is a Python script that generally contains import statements, functions, classes and variable definitions, and Python runnable code and it "lives" file with a '.py' extension.
2 ) zip files and DLL files can also be modules.Inside the module, you can refer to the module name as a string that is stored in the global variable name .


# Differentiate between append() and extend() methods ?

Both append() and extend() methods are the methods of list. These methods are used to add the elements at the end of the list.

1 ) append(element) – adds the given element at the end of the list which has called this method.
2 ) extend(another-list) – adds the elements of another-list at the end of the list which is called the extend method.


# 










