# What is celeary

celery is a task que. in this ques wise working means FIFO ( first in first out ). this use of it when heavy task is in system. but we
dont want to execute that in system invorment process effect should not be on system , we use that whenever we want to bulk task 

in celery we need to use redis 


# what is message broker

which task have to done tha all task store in redis


















        from datetime import date

        from django.db import models


        class Blog(models.Model):
            name = models.CharField(max_length=100)
            tagline = models.TextField()

            def __str__(self):
                return self.name


        class Author(models.Model):
            name = models.CharField(max_length=200)
            email = models.EmailField()

            def __str__(self):
                return self.name


        class Entry(models.Model):
            blog = models.ForeignKey(Blog, on_delete=models.CASCADE)
            headline = models.CharField(max_length=255)
            body_text = models.TextField()
            pub_date = models.DateField()
            mod_date = models.DateField(default=date.today)
            authors = models.ManyToManyField(Author)
            number_of_comments = models.IntegerField(default=0)
            number_of_pingbacks = models.IntegerField(default=0)
            rating = models.IntegerField(default=5)

            def __str__(self):
                return self.headline
                
# Starting point

Help of that we can extract all object

        Entry.objects.all()
        
# get first entry
        Entry.objects.first()
        
# select_related()
whenever we want to take foreignkey field access that time we use select related
        blog = entry.blog
        
# without prefetch_related()
to-many relationships (one-to-many, many-to-many )
        
        entry   = Entry.ojects.get(id = 5 )
        authors = list(entry.authors.all())
        
# with prefetch_related()

 annotate identifies the summary from each of the items in the queryset
 
        entries = Entry.objects.annotate(blog_name=F("blog__name"))[:5]
 # filter() and Q()
 
 Use Q() to do more filtering in the database, and less in your application.
 
        low_engagement_posts = Entry.objects.filter(
        Q(number_of_comments__lt=20) | Q(number_of_pingbacks__lt=20)
        )

