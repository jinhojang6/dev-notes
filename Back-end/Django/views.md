# View

## Intro

A view function, or view for short, is a Python function that takes a Web request and returns a Web response. 
This response can be the HTML contents of a Web page, or a redirect, or a 404 error, or an XML document, or an image . . . or anything, really. 
The view itself contains whatever arbitrary logic is necessary to return that response. 
This code can live anywhere you want, as long as it’s on your Python path. There’s no other requirement–no “magic,” so to speak. 
For the sake of putting the code somewhere, the convention is to put views in a file called views.py, placed in your project or application directory.

- Reference: https://docs.djangoproject.com/en/3.1/topics/http/views/

```
from django.http import HttpResponse
import datetime

def current_datetime(request):
    now = datetime.datetime.now()
    html = "<html><body>It is now %s.</body></html>" % now
    return HttpResponse(html)
```

<br/>

## Class-based views

A view is a callable which takes a request and returns a response. 
This can be more than just a function, and Django provides an example of some classes which can be used as views. 
These allow you to structure your views and reuse code by harnessing inheritance and mixins. 
There are also some generic views for tasks which we’ll get to later, but you may want to design your own structure of reusable views which suits your use case. 

```
from django.http import HttpResponse
from django.views.generic import ListView
from books.models import Book

class BookListView(ListView):
    model = Book

    def head(self, *args, **kwargs):
        last_book = self.get_queryset().latest('publication_date')
        response = HttpResponse()
        # RFC 1123 date format
        response['Last-Modified'] = last_book.publication_date.strftime('%a, %d %b %Y %H:%M:%S GMT')
        return response
```

<br/>
