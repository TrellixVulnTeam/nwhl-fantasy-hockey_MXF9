# nwhl-fantasy-hockey
## Running Locally

Make sure you have Python [installed properly](http://install.python-guide.org).  Also, install the [Heroku Toolbelt](https://toolbelt.heroku.com/) and [Postgres](https://devcenter.heroku.com/articles/heroku-postgresql#local-setup).

```sh
If pip isnt installed (on a mac), run:
sudo easy_install pip
If django isn't installed, run: 
pip install django

$ heroku login
$ heroku git:clone -a nwhl-fantasy-hockey
-- if it prompts you for a git username and password, use your Heroku email and the API key for your Heroku account, which you can find near the bottom of your Account settings page 
$ cd nwhl-fantasy-hockey

(if you don't have pipenv installed, run $ pip install pipenv and then run $pipenv install)
$ virtualenv env 

On mac: run the following line
$ source env/bin/activate

On Windows, run the following line:
$ env\Scripts\activate

$ pip install -r requirements.txt

-- dont run this yet, I haven't tried it out, and you can run locally without it -- $ createdb nwhl_fantasy_hockey
(make sure postgresql is running before you do the above command, otherwise it will error)


$ python manage.py migrate
$ python manage.py collectstatic


If using unix (a mac, for example), run the following to run the app locally:
$ heroku local

If using Windows, run the following to run the app locally
$ heroku local web -f Procfile.windows
```

Your app should now be running on [localhost:5000](http://localhost:5000/).
Press Ctrl+C in the terminal/command promt to exit 

## Pushing local changes 

```sh
$ git add .
$ git commit -am "This is a useful message about my changes"
$ git push heroku master
(if the above push doesn't work because your local repository isn't up to date run $ git pull heroku master)
$ git remote add origin https://github.com/haileysholty21/nwhl-fantasy-hockey.git
$ git remote -v
$ git push origin master 
(if the above push doesn't work because your local repository isn't up to date run $ git pull origin master)
```

## Making UI Changes

The main HTML file (index.html) is in nwhl_fantasy/templates, and any additional html files should be added to that same templates folder. In your HTML files, when you want to refer to your CSS file(s) or any images, which should be added/kept in nwhl_fantasy_app/static (or nwhl_fantasy_app/static/images for images), the href should be formatted like href="{% static 'fantasyNWHL.css' %}" (example in the index.html file). As long as <% load static %> is included inside the opening HTML tag, Django will be able to find your CSS file or image and render it.


## Documentation

For more information about using Python on Heroku, see these Dev Center articles:

- [Python on Heroku](https://devcenter.heroku.com/categories/python)
