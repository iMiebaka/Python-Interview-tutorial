
# How to do OR queries in Django ORM


      from django.db.models import Q
      qs = User.objects.filter(Q(first_name__startswith='R')|Q(last_name__startswith='D'))
      
# How to do AND queries in Django ORM

      queryset_1 = User.objects.filter(
          first_name__startswith='R',
          last_name__startswith='D'
      )
      
# 4. How to do a NOT query in Django queryset

      from django.db.models import Q
      queryset = User.objects.filter(~Q(id__lt=5))

# 5. How to do union of two querysets from same or different models?

      q1 = User.objects.filter(id__gte=5)
      q2 = User.objects.filter(id__lte=9)
      q1.union(q2)

      OUTPUT --->>

      <QuerySet [<User: yash>, <User: John>, <User: Ricky>, <User: sharukh>, <User: Ritesh>, <User: Billy>,<User: Raghu>, <User: rishab>]>
      
 # 6. How to select some fields only in a queryset?
 
     queryset = User.objects.filter( first_name__startswith='R' ).values('first_name', 'last_name')

     OUTPUT ---->>

     <QuerySet [{'first_name': 'Ricky', 'last_name': 'Dayal'}, {'first_name': 'Ritesh', 'last_name': 'Deshmukh'}]
     
 # 7. How to do a subquery expression in Django
 
 Django allows using SQL subqueries. Let’s start with something simple, We have a UserParent model which has OnetoOne relation with auth user.
 We will find all the UserParent which have a UserParent.
 
 
     from django.db.models import Subquery

     users = User.objects.all()
     data = UserParent.objects.filter(user_id__in=Subquery(users.values('id')))

     OUTPUT ---->>

     <QuerySet [<UserParent: UserParent object (2)>, <UserParent: UserParent object (5)>, <UserParent: UserParent object (8)>]>


# 8. How to filter a queryset with criteria based on comparing their field values

Django ORM makes it easy to filter based on fixed values. To get all User objects with first_name starting with 'R', you can do User.
objects.filter(first_name__startswith='R').



Now you can find the users where first_name==last_name


    User.objects.filter(last_name=F("first_name"))
    
# 9. How to filter FileField without any file


            no_files_objects = MyModel.objects.filter(
                Q(file='')|Q(file=None)
            )
# 10. How to perform join operations in django ORM

            a1 = Article.objects.select_related('reporter') // Using select_related
            
 # 11. How to find second largest record using Django ORM
 
            user = User.objects.order_by('-last_login')[1]
            
 # 12. Find rows which have duplicate field values¶
 
            duplicates = User.objects.values( 'first_name' ).annotate(name_count=Count('first_name')).filter(name_count__gt=1)
            
 # 13. How to find distinct field values from queryset
 
            distinct = User.objects.values( 'first_name' ).annotate( name_count=Count('first_name') ).filter(name_count=1) records =           User.objects.filter(first_name__in=[item['first_name'] for item in distinct])



# 14. How to use Q objects for complex queries

In previous chapters we used Q objects for OR and AND and NOT operations. Q objects provides you complete control over the where clause of the query.


            from django.db.models import Q
            queryset = User.objects.filter( Q(first_name__startswith='R') | Q(last_name__startswith='D') )

            OUTPUT ---->>>

            <QuerySet [<User: Ricky>, <User: Ritesh>, <User: Radha>, <User: Raghu>, <User: rishab>]>
            
# 15. How to group records in Django ORM

Grouping of records in Django ORM can be done using aggregation functions like Max, Min, Avg, Sum. Django queries help to create, retrieve, update and delete objects. But sometimes we need to get aggregated values from the objects

            from django.db.models import Avg, Max, Min, Sum, Count

            1 ) User.objects.all().aggregate(Avg('id'))

            OUTPUT --->> {'id__avg': 7.571428571428571}

            2 ) User.objects.all().aggregate(Max('id'))

            OUTPUT -->> {'id__max': 15}

            3 ) User.objects.all().aggregate(Min('id'))

            OUTPUT --->> {'id__min': 1}

            4 ) User.objects.all().aggregate(Sum('id'))

            OUTPUT -->> {'id__sum': 106}
            
_________________________________________________________________________________

# Creating, Updating and Deleting things

_________________________________________________________________________________

# 1. How to create multiple objects in one shot

            Category.objects.bulk_create( [Category(name="God"), Category(name="Demi God"), Category(name="Mortal")] )
            
