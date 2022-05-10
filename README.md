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

