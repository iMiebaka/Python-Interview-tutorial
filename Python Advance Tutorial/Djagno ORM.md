
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
    
