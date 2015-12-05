# JsonApiCmdLine

The followings command are used for the app.

To start using the api the server has to be up and be run from the directory the file manage.py is located:

>python manage.py runserver

the hosted address is by default: htttp://127.0.0.1:8000. 
To add items or create users via the commandline the libraries httpie or curl are needed. I used httpie because the tutorial also did.If on windows one can simply install those with the following commands in a second cmd screen:

>pip install httpie

All the prerequisites are installed and the server is up and running; the api can be consumed.

Add user:

>python manage.py createsuperuser
a Username, e-mail adress (not necessary) and password are asked.

Add item to list

>http --auth user:password POST http://127.0.0.1:8000/cmdapp/ todo="<enter todo item here>"

The items are saved on a globallist and by default have the variable 'completed' set to False.

Edit status item:

>http --auth user:password PATCH http://127.0.0.1:8000/cmdapp/<global index number>/ completed=<True / False>

Edit item:

>http --auth user:password PATCH http://127.0.0.1:8000/cmdapp/<global index number>/ todo="<edited todo item>

List item:

>http GET http://127.0.0.1:8000/cmdapp/<global index number>/

List all users:

>http GET http://127.0.0.1:8000/users/

List all items:

>http GET http://127.0.0.1:8000/cmdapp/
