# GettingStarted

# Gihub Desktop
Go to the following [link](https://desktop.github.com/) to download github desktop for your system. This will be useful to pull the marking branch of the repositories.


# Database
We have utilized Postgres as our database technology of choice, and to install that on the system, go to the following [link](https://www.postgresql.org/download/) and follow their advice. We require setting up database credentials as:
- username: comp9323
- password: 0
If the postgres database has already been set onn your system, we would suggest changing it to '0'.

Once the postgres PATH has been set on your system, validate the installation by running the following on Command Prompt/ terminal:
'''
psql -U postgres
Password for user postgres:
postgres=# create database comp9323;
'''

Once done, pull the marking branch of the Backend repository via Github Desktop. Inside it, you shall find a folder called db and more specifically a file called saas_v9.sql. To install the database dump, execute the following command on Command Prompt/ terminal.
'''
psql -U postgres -d comp9323 -f saas_v9.sql
'''
and when prompted, put your password.

Feel free to peruse the comp9323 database in the postgres instance by:
'''
psql -U postgres
Password for user postgres:
postgres=# \c comp9323;
comp9323=# \d
'''
and running the SQL commands on it. For the purposes of marking, please don't modify the schema or modify the data.

# Installing Front-end