    class Author(models.Model):
        nickname = models.CharField(max_length=20, null=True, blank=True)
        firstname = models.CharField(max_length=20)
        lastname = models.CharField(max_length=40)
        birth_date = models.DateField()
    class Book(models.Model):
        author = models.ForeignKey(Author, related_name="books", on_delete=models.CASCADE)
        title = models.CharField(unique=True, max_length=100)
        category = models.CharField(max_length=50)
        published = models.DateField()
        price = models.DecimalField(decimal_places=2, max_digits=6)
        rating = models.IntegerField()
    




    books = Book.objects.filter(title="Crime and Punishment")
    books = Book.objects.filter(title__startswith="Crime")


# Books published in 2021

    books = Book.objects.filter(published__year=2021)
    
# Books published in the year 2000 or after

    books = Book.objects.filter(published__year__gte=2000)
    
# Books published before the year 2000

    books = Book.objects.filter(published__year__lt=2000)

# With time fields we can even filter using a range lookup to query objects within a specific time range.

    start_date = datetime.date(2021, 1, 1)
    end_date = datetime.date(2021, 1, 3)
    books = Book.objects.filter(published__range=(start_date, end_date))
    
# Q Objects Keyword arguments in a filter query are "AND"ed together. If we want to execute OR queries we can use the Q object. Q objects encapsulate keyword arguments for filtering just like filter, but we can combine Q objects using & or |.

    from django.db.models import Q
   # Get all books published in 2018 or 2020
    books = Book.objects.filter(Q(published__year=2018) | Q(published__year=2020))
   # Get all books published in
   
 # F expressions
 
 F expressions represent a value of a model field. It makes it possible to use field values in queries without actually pulling the value from the database. This is possible because Django creates a SQL query that handles everything for us
 
    from django.db.models import F
    # Query books published by authors under 30 years old (this is not exactly true because years vary in length)
    books = Book.objects.filter(published__lte=F("author__birth_date") + datetime.timedelta(days=365*30))
    
# Annotation
Most often we just want to query the values defined in a model with some filtering criteria. But sometimes you'll be calculating 
or combining values that you need from the result of the query. This can, of course, be done in Python but for performance reasons, 
it might be worth it to let the database handle the calculations. This is where Djangos annotations come in handy.

    from django.db.models import F, Value as V
    from django.db.models.functions import Concat
    author = Author.objects.annotate(full_name=Concat(F("firstname"), V(" "), F("lastname")))
    
    



 
 
 
 
 
 
