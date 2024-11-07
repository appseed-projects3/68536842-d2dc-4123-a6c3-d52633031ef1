# [Flask Material Kit](https://appseed.us/product/material-kit/flask/)

`Open-Source` seed project generated by AppSeed in **Flask** Framework on top of **[Material Kit](https://appseed.us/product/material-kit/flask/)** design. Designed for those who like bold elements and beautiful websites, **Material Kit 2** is ready to help you create stunning websites and web apps. `Material Kit 2` is built with over 60 frontend individual elements, like buttons, inputs, navbars, nav tabs, cards, or alerts, giving you the freedom of choosing and combining.
 
- 👉 Free [support](https://appseed.us/support/) via Email & `Discord` 
- 🚀 [Custom Development Services](https://appseed.us/custom-development/) for `accelerated growth`
- ✅ [Deploy on AWS, DO, and Azure](https://deploypro.dev/) via `DeployPRO` service (read the [DOCS](https://www.docs.deploypro.dev/))

<br />

### `PROMO` [Discounts for Developers](https://appseed.us/discounts/) Up to `30%OFF`

> The **discount is applicable to all products and licenses** (no stock limits) 

[![Discounts for Developers and Designers - AppSeed](https://user-images.githubusercontent.com/51070104/229268648-6ded378f-33aa-4909-a090-31fca49caa49.png)](https://appseed.us/discounts/)

<br />

> Built with [App Generator](https://appseed.us/generator/), timestamp `2024-11-07 04:19`

- ✅ `Up-to-date dependencies`
- ✅ `Database`: `SQLite`, MySql
  - Silent fallback to `SQLite`
- ✅ `DB Tools`: SQLAlchemy ORM, Flask-Migrate (schema migrations)
- ✅ Session-Based authentication (via **flask_login**), Forms validation
- ✅ `Flask-Minify` (page compression)

<br />

![Material Kit - Starter generated by AppSeed.](https://user-images.githubusercontent.com/51070104/167396765-c88b7a95-155f-4236-8691-7b80fa2d9cd9.png)

<br />




## ✨ Set up the MySql Database

**Note:** Make sure your Mysql server is properly installed and accessible. 

> **Step 1** - Create the MySql Database to be used by the app

- `Create a new MySql` database
- `Create a new user` and assign full privilegies (read/write)

<br />

> **Step 2** - Edit the `.env` to match your MySql DB credentials. Make sure `DB_ENGINE` is set to `mysql`.

- `DB_ENGINE`  : `mysql` 
- `DB_NAME`    : default value = `appseed_db`
- `DB_HOST`    : default value = `localhost`
- `DB_PORT`    : default value = `3306`
- `DB_USERNAME`: default value = `appseed_db_usr`
- `DB_PASS`    : default value = `pass`

<br />

Here is a sample:  

```txt
# .env sample

DEBUG=False                 # False enables the MySql Persistence

DB_ENGINE=mysql             # Database Driver
DB_NAME=appseed_db          # Database Name
DB_USERNAME=appseed_db_usr  # Database User
DB_PASS=STRONG_PASS_HERE    # Password 
DB_HOST=localhost           # Database HOST, default is localhost 
DB_PORT=3306                # MySql port, default = 3306 
```

<br />


## ✨ How to use it

> Download the code 

```bash
$ # Get the code
$ git clone https://github.com/appseed-projects/68536842-d2dc-4123-a6c3-d52633031ef1.git
$ cd 68536842-d2dc-4123-a6c3-d52633031ef1
```

<br />

### 👉 Set Up for `Unix`, `MacOS` 

> Install modules via `VENV`  

```bash
$ virtualenv env
$ source env/bin/activate
$ pip3 install -r requirements.txt
```

<br />

> Set Up Flask Environment

```bash
$ export FLASK_APP=run.py
$ export FLASK_ENV=development
```

<br />

> Start the app

```bash
$ flask run
```

At this point, the app runs at `http://127.0.0.1:5000/`. 

<br />

### 👉 Set Up for `Windows` 

> Install modules via `VENV` (windows) 

```
$ virtualenv env
$ .\env\Scripts\activate
$ pip3 install -r requirements.txt
```

<br />

> Set Up Flask Environment

```bash
$ # CMD 
$ set FLASK_APP=run.py
$ set FLASK_ENV=development
$
$ # Powershell
$ $env:FLASK_APP = ".\run.py"
$ $env:FLASK_ENV = "development"
```

<br />

> Start the app

```bash
$ flask run
```

At this point, the app runs at `http://127.0.0.1:5000/`. 

<br />

### 👉 Create Users

By default, the app redirects guest users to authenticate. In order to access the private pages, follow this set up: 

- Start the app via `flask run`
- Access the `registration` page and create a new user:
  - `http://127.0.0.1:5000/register`
- Access the `sign in` page and authenticate
  - `http://127.0.0.1:5000/login`

<br />

## ✨ Code-base structure

The project is coded using blueprints, app factory pattern, dual configuration profile (development and production) and an intuitive structure presented bellow:

```bash
< PROJECT ROOT >
   |
   |-- apps/
   |    |
   |    |-- home/                           # A simple app that serve HTML files
   |    |    |-- routes.py                  # Define app routes
   |    |
   |    |-- authentication/                 # Handles auth routes (login and register)
   |    |    |-- routes.py                  # Define authentication routes  
   |    |    |-- models.py                  # Defines models  
   |    |    |-- forms.py                   # Define auth forms (login and register) 
   |    |
   |    |-- static/
   |    |    |-- <css, JS, images>          # CSS files, Javascripts files
   |    |
   |    |-- templates/                      # Templates used to render pages
   |    |    |-- includes/                  # HTML chunks and components
   |    |    |    |-- navigation.html       # Top menu component
   |    |    |    |-- sidebar.html          # Sidebar component
   |    |    |    |-- footer.html           # App Footer
   |    |    |    |-- scripts.html          # Scripts common to all pages
   |    |    |
   |    |    |-- layouts/                   # Master pages
   |    |    |    |-- base-fullscreen.html  # Used by Authentication pages
   |    |    |    |-- base.html             # Used by common pages
   |    |    |
   |    |    |-- accounts/                  # Authentication pages
   |    |    |    |-- login.html            # Login page
   |    |    |    |-- register.html         # Register page
   |    |    |
   |    |    |-- home/                      # UI Kit Pages
   |    |         |-- index.html            # Index page
   |    |         |-- 404-page.html         # 404 page
   |    |         |-- *.html                # All other pages
   |    |    
   |  config.py                             # Set up the app
   |    __init__.py                         # Initialize the app
   |
   |-- requirements.txt                     # App Dependencies
   |
   |-- .env                                 # Inject Configuration via Environment
   |-- run.py                               # Start the app - WSGI gateway
   |
   |-- ************************************************************************
```

<br />

## ✨ Deploy APP with HEROKU

> The set up

- [Create a FREE account](https://signup.heroku.com/) on Heroku platform
- [Install the Heroku CLI](https://devcenter.heroku.com/articles/getting-started-with-python#set-up) that match your OS: Mac, Unix or Windows
- Open a terminal window and authenticate via `heroku login` command
- Clone the sources and push the project for LIVE deployment

<br />

> **Step 1** - Download the code from the GH repository (using `GIT`) 

```bash
$ # Get the code
$ git clone https://github.com/appseed-projects/<YOUR_BUILD_ID>.git
$ cd <YOUR_BUILD_ID>
```

<br />

> **Step 2** - Connect to `HEROKU` using the console

```bash
$ # This will open a browser window - click the login button (in browser)
$ heroku login
```
<br />

> **Step 3** - Create the `HEROKU` project

```bash
$ heroku create
```

<br />

> **Step 4** - Push Sources to `HEROKU`

```bash
$ git push heroku HEAD:master
```

<br />

> **Step 5** - Srt up the APP Environemnt in `HEROKU` (`.env` file is ignored by the platform)

- `DEBUG`=True
- `FLASK_APP`=run.py
- `FLASK_ENV`=development
- `ASSETS_ROOT`=/static/assets

![AppSeed - HEROKU Set UP](https://user-images.githubusercontent.com/51070104/171815176-c1ca7681-38cc-4edf-9ecc-45f93621573d.jpg)

<br />

> **Step 6** - Visit the app in the browser

```bash
$ $ heroku open
```

At this point, the APP should be up & running. 

<br />

> **Step 7** (Optional) - Visualize `HEROKU` logs

```bash
$ heroku logs --tail
```

<br />


## [Flask Material Kit2 PRO](https://appseed.us/product/material-kit2-pro/flask/)

> For more components, pages and priority on support, feel free to take a look at this amazing starter:

**Material Kit 2** is a premium design crafted by the `Creative-Tim` agency on top of Bootstrap 5 Framework. Designed for those who like bold elements and beautiful websites, Material Kit 2 is made of hundreds of elements, designed blocks, and fully coded pages built with an impressive level of quality.

- 👉 [Flask Material Kit2 PRO](https://appseed.us/product/material-kit2-pro/flask/) - product page
  - ✅ `Enhanced UI` - more pages and components
  - ✅ `Priority` on support

<br >

![Mk2 PRO - Premium Seed project by AppSeed.](https://user-images.githubusercontent.com/51070104/168224733-b054bb46-d454-4aea-bb94-2d01bf4760d2.png)

<br />

---
[Flask Material Kit](https://appseed.us/product/material-kit/flask/) - Open-source starter generated by **[App Generator](https://appseed.us/generator/)**.