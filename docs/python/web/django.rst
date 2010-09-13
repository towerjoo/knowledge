====================
Django is great
====================


tips
=========

.. note::

    when you got the queryset from calling *ModelClass.objects.filter(condition)* and 
    refer the element using [] and save it at last, which **WON'T hit the database**, and 
    it will beyond your expectation. See the below codes:

    ::

        a = Blog.objects.filter(title__contains="django")
        a[0].last_update_time = datetime.now()
        a[0].save()                 # won't work as you expect
        print a[0].last_update_time # this will print the old one

        # but you can
        b = a[0]
        b.last_update_time = datetime.now()
        b.save()                    # will work as expected
