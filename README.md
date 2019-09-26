# opinion_poll
---------------------------------------------------------------------------------------------------------------------------------

#Poll Script Functionality

Poll and options data is stored in the MySQL database. Poll question and respective options will be fetched from the database and shown 
to the user. The user can be able to select an option and submit their vote. Once the vote is submitted, it will be stored in the database
with the respective poll option.
-------------------------------------------------------------------------------------------------------------------------------------------
#Create Database Tables

poll system required 3 tables in MySQL database, polls, poll_options, and poll_results.

polls-The poll information is stored in the polls table, like the poll subject, status, etc.

poll_options-The poll options associated with the respective poll are stored in the poll_options table.

poll_results-The poll_results table contains votes count of the poll option, respective option id, and poll id.
----------------------------------------------------------------------------------------------------------------------------------------
# Poll Class

The Poll class handles all the operations related to the database. For example, connect to the MySQL database server, insert, update,
and delete records in the database. Specify the database host ($dbHost), username ($dbUser), password ($dbPwd), and name ($dbName) as per
 database server credentials.

__construct() – Connects and select the database.

getQuery() – Executes the SQL query on MySQL database and returns the data. It is a private function used only in this class.

getPolls() – Fetch the poll and respective options. Also, it can fetch the multiple polls data based on the request.

vote() – Inserts or updates the vote count into the database.

getResult() – Provides Poll result with votes count of poll’s options.
-----------------------------------------------------------------------------------------------------------------------------------
#opinionpoll_results.php

-poll result is fetched from the database and result details are shown to the user. Votes count for each option is converted to 
percentage format and appears as a percentage bar.
