
# 1 ) List vs Tupple <br>
**Mutability:**

**List: <br>**
Lists are mutable, meaning their elements can be changed or modified after the list is created. You can add, remove, or modify elements in a list.
**Tuple:** <br>
Tuples are immutable, which means once they are created, their elements cannot be changed or modified. You cannot add, remove, or alter elements in a tuple.
Syntax:

List: Lists are defined using square brackets []. For example: my_list = [1, 2, 3]. <br>
Tuple: Tuples are defined using parentheses (). For example: my_tuple = (1, 2, 3).<br>
**Performance:**

List: Due to their mutability, lists might have slightly higher memory overhead and slower performance compared to tuples.
Tuple: Tuples are generally more memory-efficient and may provide faster iteration because of their immutability.


# 2 ) diffrent between class and function <br>

**Function:** <br> A function is a block of code that performs a specific task or set of tasks. It encapsulates a sequence of instructions and can be called with specific arguments to produce a result. <br>

**Class:** <br> A class, on the other hand, is a blueprint for creating objects. It defines a data structure and methods that operate on that data. Objects created from a class are instances of that class. <br>

**Function:** <br> Functions are typically used for modularizing code, making it reusable, and promoting a clear and organized structure in a program. <br>

**Class:** <br> Classes are used for creating and managing objects. They provide a way to model real-world entities and their behaviors in a program. <br>

**Function:** <br> Functions do not store data by themselves. They may take input parameters and return output, but they don't have internal states. <br>

**Class:** <br> Classes can have attributes (data members) that store information about the object's state. Methods in a class can operate on this data. <br>


**Function:** <br> Functions don't support inheritance. They are standalone units of code. <br>
**Class:** <br> Classes support inheritance, allowing one class to inherit properties and methods from another. This promotes code reuse and hierarchy in object-oriented programming. <br>



# 3 ) what is list and linked list <br>
4 ) scope resulation in python acceblity ( global variable and local variable ) <br>
5 ) what is abstraction and encapsulation ( example ) <br>
# 6 ) what is inheritance ( explain in django ) <br>

CommonFields serves as an abstract base class with common fields (name and description). MyModel1 and MyModel2 inherit from CommonFields, sharing those fields without creating an additional database table for CommonFields.

            from django.db import models
            
            class CommonFields(models.Model):
                name = models.CharField(max_length=255)
                description = models.TextField()
            
                class Meta:
                    abstract = True
            
            class MyModel1(CommonFields):
                additional_field_1 = models.IntegerField()
            
            class MyModel2(CommonFields):
                additional_field_2 = models.BooleanField()


7 ) what is MVT model  <br>
# 8 ) Process of requst and response how it is process <br>

Client Sends a Request --->> DNS Resolution (if necessary) --->> HTTP Request --->> Server Receives the Request --->> 

9 ) what are middleware in djagno <br>
10 ) what is abstract base calss and mixing class <br>
11 ) Django signles <br>
# 12 ) Django cache strategies  <br>

Cache means jya veles user kadun request yeti kiwa API hit hoti tar pratek veles data ha database madhun anat nahi jar as kela tar persormance down hoil tar ya thikani apan
cache use karto mhanje user kadun request ali database madhe data gheun yeto ani ti cache memory madhe store karto ha data ram madhe pan store karu shakto kiwa local memory madhe
pan store karu shakto ani jeva akhada user same data sathi request hit karel teva just cache memory madhun data send karto ani jar db madhe new data add zala tar just cache memory
madhla data update hoto

                        from django.core.cache import cache
                        from django.shortcuts import render
                        from django.http import HttpResponse
                        
                        def my_view(request):
                            # Check if the data is already in the cache
                            cached_data = cache.get('my_cached_data')
                        
                            if cached_data is not None:
                                # If data is in the cache, use it
                                return HttpResponse(f"Cached Data: {cached_data}")
                        
                            else:
                                # If data is not in the cache, fetch it from the original source
                                original_data = "Data fetched from the original source"
                        
                                # Store the fetched data in the cache for future use (with a timeout of 300 seconds in this example)
                                cache.set('my_cached_data', original_data, timeout=300)
                        
                                return HttpResponse(f"Original Data: {original_data}")


# 13 ) diffrence between class based view and function view in djagno <br>

**Function-Based Views (FBVs)** <br>
FBVs are often simpler and more straightforward, especially for simpler views or views that involve less logic. <br>
The flow of the code is more explicit and linear, making it easier to follow for smaller views.<br>
FBVs often use decorators (e.g., @login_required, @require_http_methods, etc.) to add functionality to views. <br>

            from django.shortcuts import render
            
            def my_view(request):
                # View logic
                return render(request, 'template.html')


**Class-Based Views (CBVs)** <br>

CBVs promote code reuse by allowing the use of mixins and inheritance. Different parts of a view can be implemented in separate methods or classes.<br>
Views are organized as classes, which can lead to a more organized and modular code structure, especially for larger and more complex views.<br>
CBVs allow the use of mixins and inheritance to extend or modify behavior, making it easier to create variations of views.<br>
CBVs allow for better separation of concerns, with different methods or attributes handling different aspects of the view (e.g., get(), post(), etc.).

            from django.views import View
            from django.shortcuts import render
            
            class MyView(View):
                def get(self, request):
                    # View logic
                    return render(request, 'template.html')




14 ) what is function base view and how you can define those <br>
15 ) how data is mapping in djagno <br>
16 ) what is djagno migrations <br>
17 ) diffrence between django rest framework and regular django views <br>
18 ) what is your appoch DRF or regular views <br>
19 ) what is pagination <br>
20 ) Database model example each relation <br>
21 ) role of serializer in DRF <br>
22 ) diffrence between var and varchar in SQL <br>
23 ) what is primary key  <br>
24 ) indexing in mysql <br>
25 ) what is asset property in DB transaction<br>
# 26) select related and prefetch related in DJNGO

            from djagno.db import models
            
            class Author(models.Models):
            	name = models.CharField(max_length = 30)
            
            
            class Course(models.Model):
            	name = models.CharField(max_length=30)
            	author = models.ForeignKey(Author,on_delete=models.CASCADE,related_name)


jeva apan **Course.objects.all()** hi query karto tya veles backend madhe khalchi sql query execute hote

            SELECT "app_course"."id","app_course"."name","app_course"."author_id" FROM "app_course" LIMIT 1; args=()
      

 jeva apan **Course.object.all()[0].author** hi query execute karto tar backend la khalchay donhi query execute hotat

             SELECT "app_course"."id","app_course"."name","app_course"."author_id" FROM "app_course" LIMIT 1; args=();
             SELECT "app_author"."id","app_author"."name" FROM "app_author" WHERE "app_author"."id" = 1 LIMIT = 1; args=(1)

ani jeva apan select related use karto teva to **inner join** karto **Course.objects.select_related()**

            SELECT "app_course"."id","app_course"."name","app_course"."app_author"."id","app_author"."name"
            FROM "app_course" INNER JOIN "app_author" ON ("app_course"."author_id" = "app_author"."id") LIMIT 21; args=()

**Use** : jya veles fakt mala Course che name pahije asta teva **Course.objects.all()** use karaycha ani jeva mala foreign key cha data pan pahije teva **select_related** use karaych


**Prefetch_related** ---------------------


            from django.db import models
            
            class Author(models.Model):
                name = models.CharField(max_length=100)
            
            class Book(models.Model):
                title = models.CharField(max_length=200)
                authors = models.ManyToManyField(Author)

jary apan prefetch related query use keli  **books = Book.objects.prefetch_related('authors').all()** tar backend la left join query run hoti

            SELECT
                "yourapp_author"."id",
                "yourapp_author"."name",
                "yourapp_book_authors"."book_id",
                "yourapp_book_authors"."author_id"
            FROM
                "yourapp_author"
            LEFT JOIN
                "yourapp_book_authors" ON ("yourapp_author"."id" = "yourapp_book_authors"."author_id")
            WHERE
                "yourapp_book_authors"."book_id" IN (<list_of_book_ids>);

**USE** Jya veles many to many field asti tya veles **prefetch_related** use karaych
