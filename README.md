# Django on Openshift

To make this work with Openshift run:

    $ APP_NAME=yourapp
    $ rhc env set OPENSHIFT_PYTHON_WSGI_APPLICATION=wsgi/openshift/wsgi.py -a $APP_NAME
    # You may need to restart your app
    $ rhc app-restart -a $APP_NAME

Also, create the database:

    $ rhc ssh -a $APP_NAME
    $ cd app-root/runtime/repo/wsgi
    $ python manage.py migrate
