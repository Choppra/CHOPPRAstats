CHOPPRAstats

I am far from a PHP Expert.  I did this project for fun to teach myself some new things.  Please feel free to suggest improvements or request a fork of this project.

A more detailed README will be updated shortly.

Things you will need to know:

- How to setup a web server with PHP Support.
- How to setup a *SELECT* only MYSQL user name with remote access (if your web server is running on a different server)
-- remember, SELECT ONLY to keep your arma database safe.
- How to setup overwrites in EXILE (ExileServer_object_player_event_onMpKilled.sqf)
- How to execute SQL queries to create the required fields and tables.

Critical Files to Edit:
- /includes/condb.php
-- **It is currently setup for two servers.  I will add a secondary file which allows for 1 database if you aren't certain how to edit this file.  I plan to make this a little more modular later on.**
- /navbar.php
-- **Needs to be edited to matck your condb.php**

**ExileServer_object_player_event_onMpKilled.sqf was modified and created A LONG TIME AGO.  From my understanding, it still works just fine.  Feel free to modify anything you see in there.  A few communities are running this stats page and have been for almost a year.  It's still working just fine.**
