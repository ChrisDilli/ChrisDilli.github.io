HubspotMr
==============================

Hubspot integrations for Mobility Research

Getting started:
* git clone from github
    * consider adding an ssh key to your github account
* download PyCharm and open project
* create virtual environment for organizing dependencies
    * File > settings > project > interpreter
    * click the gear > add > new environment > ok
    * make sure it is set to python 3
* in the pycharm terminal, type 'pip install -r requirements/local.txt'

* create a file in the root directory called '.env'
    * it should look like this:

```
HUBSPOT_CLIENT_SECRET=4d7975cb-b980-40d1-bd05-f917a8739895
HUBSPOT_CLIENT_ID=ce8dfbee-c335-4854-8c04-f7924c717481
GOOGLE_GEOCODING_API_KEY=AIzaSyAY-9oWW7EyAKH7hpXBk8ZDPGMToQru54E
HUBSPOT_REDIRECT_URI_PROTOCOL=http
MAPBOX_ACCESS_TOKEN=pk.eyJ1Ijoia2F5dm9uc2VpZiIsImEiOiJjamRyeGNsMWwwNjZwMnB0MzUxdDhhNGoyIn0.gZC5uhwLeJkrVPEURx0yRg
DJANGO_SECRET_KEY=shejfhehjfkbvdfhgvfsrefr3
DJANGO_DEBUG=True
HUBSPOT_REDIRECT_URI=http://localhost:8000/accounts/hubspot/login/callback
```
* set up django database:
    * type 'python manage.py migrate'
* type 'python manage.py createsuperuser' to log in initially
* to run the server type 'python manage.py runserver 0:8000'
    * something should show up at localhost:8000/admin now
* configure hubspot social account:
    * type 'python manage.py runscript setup_social_account'
* the project should now be all set up!

---------

Working on the remote server:

* to log in type 'ssh user@kayvonseif.me' and enter your password
example username: cdilli
* the django code is located in /usr/local/apps/hubspotmr
* to edit anything within /usr/... you need to prepend sudo to your commands
    * For example, sudo vim /usr/.../test.txt
* to test out a crm card type:
    * cd /var/www/kayvonseif.me/apps/d/hubspotmr/static/test
    * sudo vim card1.json (look up how to use vim if you haven't before, edit file)
    * your changes will be immediately accessible at kayvonseif.me/static/hubspotmr/test/card1.json
        * this could be used to test crm cards with a working data fetch url


