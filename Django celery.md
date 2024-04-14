
we use celery when we have large task and that counsume more time

https://docs.celeryq.dev/en/stable/django/first-steps-with-django.html



# setp 1)  

Inatall redis in system
pip install celery


# step 2 ) settings.py 

      # Celery configuration
      CELERY_BROKER_URL = 'redis://localhost:6379/0'  # Example Redis broker URL
      CELERY_RESULT_BACKEND = 'redis://localhost:6379/0'  # Example Redis result backend URL
      CELERY_ACCEPT_CONTENT = ['application/json']
      CELERY_RESULT_SERIALIZER = 'json'
      CELERY_TASK_SERIALIZER = 'json'  # Example task serializer (JSON)

# step 3 ) project/celery.py


        import os
        
        from celery import Celery
        
        # Set the default Django settings module for the 'celery' program.
        os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'Amazon.settings')
        
        app = Celery('Amazon')
        
        # Using a string here means the worker doesn't have to serialize
        # the configuration object to child processes.
        # - namespace='CELERY' means all celery-related configuration keys
        #   should have a `CELERY_` prefix.
        app.config_from_object('django.conf:settings', namespace='CELERY')
        
        # Load task modules from all registered Django apps.
        app.autodiscover_tasks()
        
        
        @app.task(bind=True, ignore_result=True)
        def debug_task(self):
            print(f'Request: {self.request!r}')


# app/task.py

        from celery import shared_task
        import time
        
        @shared_task
        def handle_sleep():
            print("Handle sleep started")
            time.sleep(20)

# views.py



        from .task import *
        def home(request):
        
            #  time.sleep(20)
            handle_sleep.delay()
             
            return HttpResponse("Hello from celery")


# Execation command

    celery -A Amazon worker -l INFO
