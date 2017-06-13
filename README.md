Array Application
=======================

Introduction
------------
This application includes the various modules that make up the EdTrak product.
It uses MySQL as the database technology.  PHP 5.4+ is required to run the system?  Who knows?


Installation
------------

1.) Clone the repository using git 

	git clone https://github.com/jpohlmann/edmeasures

2.) Create the system databases and test databases using mysql(these are just my guesses):

	CREATE DATABASE edtrakv3;
	CREATE DATABASE edtrakv3_test;

3.) Create the initial database tables from sql scripts:

	cd database/module/EdTrak/
	mysql edtrakv3 < init.sql
	mysql edtrakv3_test < init.sql

4.) Create the configuration files:
	
	cp database/module/EdTrak/phinx.yml.dist database/module/EdTrak/phinx.yml
	cp config/autoload/local.php.dist config/autoload/local.php
	
Note that these config files have database usernames and passwords that you may need to change to match your database.

5.) Run the database migration scripts:

	cd database/module/EdTrak/
	../../../vendor/robmorgan/phinx/bin/phinx migrate -e development
	../../../vendor/robmorgan/phinx/bin/phinx migrate -e testing

6.) You should be done!
