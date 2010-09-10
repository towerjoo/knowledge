=============
Gunicorn
=============

`Gunicorn`_ 'Green Unicorn' is a Python WSGI HTTP Server for UNIX. It's a pre-fork worker model ported from Ruby's Unicorn project. The Gunicorn server is broadly compatible with various web frameworks, simply implemented, light on server resources, and fairly speedy.

Gunicorn and Django
=====================

1. you can install `Gunicorn`_ using easy_install or pip
2. add *gunicorn* to INSTALLED_APP in django's settings.py
3. run *python manage.py run_gunicorn -b 127.0.0.1:1234 --daemon* to start
4. configure nginx to make it proxy requests to gunicorn by adding *proxy_pass http://127.0.0.1:1234* in the config file

Then everything is done and you can visit your django app in *http://hostname:port* based on the nginx file config.

.. _Gunicorn: http://gunicorn.org/
