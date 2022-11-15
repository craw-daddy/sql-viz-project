A simple Python project demostrating using data from a relational database to create a visualization. The [`master`](https://github.com/craw-daddy/sql-viz-project/tree/master) branch is the starting template and [`minimal-app`](https://github.com/craw-daddy/sql-viz-project/tree/minimal-app) is the branch that contains a minimal working Flask application.

This minimal working application can be found here, deployed on Render.com: https://sql-viz-project.onrender.com/

To run, create a file in the project's root named `.env` based on the contents of `.env.template`. Make sure to fill in the database's URL. 

If you are using a virtual environment, run:

* `python3 -m venv venv`
* `source venv/bin/activate`
* `pip install -r requirements.txt`
* `source .env`
* `flask run`

Note that for deployment on Render.com, you must get the `URL_DB` environmental variable into the system.  
Since the code is using the `dotenv` library, an easy way to do this is to create a `.env` file where this variable is defined.  On the Render dashboard, when you first create the deployment (or afterwards, if you forget), you can inject a `.env` file into the directory of the deployment (since this file is not part of the repository).  

Make certain that you specify where to find the main application, in the command to run `gunicorn` on the project dashboard, as the main application is not in the root-level directory of the project.  
