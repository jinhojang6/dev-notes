# Django REST Framework
Django REST framework is a powerful and flexible toolkit for building Web APIs.

<br/>

## Intro
Some reasons you might want to use REST framework:

- The Web browsable API is a huge usability win for your developers.
- Authentication policies including packages for OAuth1a and OAuth2.
- Serialization that supports both ORM and non-ORM data sources.
- Customizable all the way down - just use regular function-based views if you don't need the more powerful features.
- Extensive documentation, and great community support.
- Used and trusted by internationally recognised companies including Mozilla, Red Hat, Heroku, and Eventbrite.

Reference: https://www.django-rest-framework.org/

<br/>

## Request

REST framework's Request class extends the standard HttpRequest, adding support for REST framework's flexible request parsing and request authentication.

### query_params

request.query_params is a more correctly named synonym for request.GET.

For clarity inside your code, we recommend using request.query_params instead of the Django's standard request.GET. 
Doing so will help keep your codebase more correct and obvious - any HTTP method type may include query parameters, not just GET requests.

e.g., from http://{host}/project_stats?project=aiworks
```
param = request.query_params.get('project')
```
The param will be `aiworks`

- Reference: https://www.django-rest-framework.org/api-guide/requests/#requests
