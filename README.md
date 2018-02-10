CHOPPRAstats

I am far from a PHP Expert.  I did this project for fun to teach myself some new things.  Please feel free to suggest improvements or request a fork of this project.

A more detailed README will be updated shortly.

Things you will need to know:

- How to setup a web server.
- How to setup a *SELECT* only MYSQL user name with remote access (if your web server is running on a different server)
- How to setup overwrites in EXILE (ExileServer_object_player_event_onMpKilled.sqf)
- How to execute SQL queries to create the required fields and tables.

Critical Files to Edit:
- /includes/condb.php
-- **It is currently setup for two servers.  I will add a secondary file which allows for 1 database if you aren't certain how to edit this file.  I plan to make this a little more modular later on.**
- /navbar.php
-- **Needs to be edited to matck your condb.php**

