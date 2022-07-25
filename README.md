A simple Python project demostrating using data from a relational database to create a visualization. The [`master`](https://github.com/craw-daddy/sql-viz-project/tree/master) branch is the starting template and [`minimal-app`](https://github.com/craw-daddy/sql-viz-project/tree/minimal-app) is the branch that contains a minimal working Flask application.

This minimal working application can be found here: https://wells-app.herokuapp.com/

To run, create a file in the project's root named `.env` based on the contents of `.env.template`. Make sure to fill in the database's URL. 

If you are using a virtual environment, run:

* `python3 -m venv venv`
* `source venv/bin/activate`
* `pip install -r requirements.txt`
* `source .env`
* `flask run`

The `Procfile` is only necessary for deployment to Heroku, and specifies that the application should be running a web server for the Flask application, and where that Flask application can be found in the repository's file structure.  The `runtime.txt` file specifies a Python version to use (otherwise Heroku tries to use what it considers as the "latest" version of PYthon, which may be incompatible with some of the libraries specified in `requirements.txt`).

Note that for deployment to Heroku, you must get the `URL_DB` environmental variable into the system in some fashion.  Either you must: 

* remove the `.env` file from the `.gitignore` file, create the `.env` and include it in the git repository (not recommended for security reasons, this is, after all, why the `dotenv` package is being used to hide that URL); or 
* inject the environmental variable into the Heroku configuration using the Heroku CLI by running `heroku config:ser URL_DB=...` with the correct URL for the running SQL server.  (You should also be able to get this environmental variable into the configuration using the Heroku Dashboard.)  
  
