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
