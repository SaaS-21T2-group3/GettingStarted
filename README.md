# GettingStarted

# Gihub Desktop
Go to the following [link](https://desktop.github.com/) to download github desktop for your system. This will be useful to pull the marking branch of the repositories.


# Database
We have utilized Postgres as our database technology of choice, and to install that on the system, go to the following [link](https://www.postgresql.org/download/) and follow their advice. We require setting up database credentials as:
- username: comp9323
- password: 0

If the postgres database has already been set onn your system, we would suggest changing it to '0'.

Once the postgres PATH has been set on your system, validate the installation by running the following on Command Prompt/ terminal:
```
psql -U postgres
Password for user postgres:
postgres=# create database comp9323;
```

Once done, pull the marking branch of the Backend repository via Github Desktop. Inside it, you shall find a folder called db and more specifically a file called saas_v9.sql. To install the database dump, execute the following command on Command Prompt/ terminal.
```
psql -U postgres -d comp9323 -f saas_v9.sql
```
and when prompted, put your password.

Feel free to peruse the comp9323 database in the postgres instance by:
```
psql -U postgres
Password for user postgres:
postgres=# \c comp9323;
comp9323=# \d
```
and running the SQL commands on it. For the purposes of marking, please don't modify the schema or modify the data.

Once the database has been confirmed to be found working, navigate to the backend repository that you have cloned. Execute the following command on CommandPrompt / terminal to start the system.
```
python -m swagger_server
```

Once the following output is shown on the terminal, you can open the swagger UI on any [web browser](http://localhost:8080/v1/ui/).
```
Connection pool created successfully
 * Debugger is active!
 * Debugger PIN: 280-682-446
 * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
```

##### Common Error
In case of obtaining the following error after executing the python -m swagger_server command, we suggest checking that the postgres server is up, that the credentials are working (as defined above). In case of persistent issues, reach out to [Kamal](mailto:r.revathi_sridhar_kamal@student.unsw.edu.au) or any team member over mail or MS-Teams chat.
```
AttributeError: 'NoneType' object has no attribute 'getconn'
```



# Installing Front-end