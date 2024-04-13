
# step 1 ) install django redius cache 

      pip install django-redis

# step 2 ) Configure as cache backend

add below code in settings.py

      CACHES = {
          "default": {
              "BACKEND": "django_redis.cache.RedisCache",
              "LOCATION": "redis://127.0.0.1:6379/1",
              "OPTIONS": {
                  "CLIENT_CLASS": "django_redis.client.DefaultClient",
              }
          }
      }

# step 3 ) views.py


        from django.shortcuts import render,redirect
        from.models import *
        from django.http import JsonResponse
        from django.core.cache import cache
        
        
        
        def delete_emp(request):
            return redirect("/add")
            
        
        def add(request):
            if request.method == "POST":
                Employee.objects.create(name="hacker")
            return render(request,'add.html')
        
        def home(request):
             db = None
             if cache.get('employee'):
                  payload = cache.get('employee')
                  db  = "redis"
                  
             else:
                  objs = Employee.objects.all()
                  payload = []
                  for obj in objs:
                     payload.append(obj.name)
                  db = "sqlite"
                  cache.set("employee",payload)
             return JsonResponse({"status":200,"db":db,'data':payload})

# step 4 ) signlas.py


      # signals.py
      from django.db.models.signals import post_save, post_delete
      from django.dispatch import receiver
      from django_redis import get_redis_connection
      from .models import Employee
      from django.core.cache import cache
      
      @receiver(post_save, sender=Employee)
      def update_redis_cache_on_model_change(sender,created, instance, **kwargs):
          # Update Redis cache after model save
          if created:
              objs = Employee.objects.all()
              payload = []
              for obj in objs:
                  payload.append(obj.name)
              cache.set("employee",payload)
      
      
      @receiver(post_delete, sender=Employee)
      def update_redis_cache_on_model_delete(sender, instance, **kwargs):
          # Update Redis cache after model delete
          redis_conn = get_redis_connection("default")
          # Example: Delete the instance data from cache
          redis_conn.hdel("employee", instance.id)
