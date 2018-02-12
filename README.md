# CHOPPRAstats 
##### Detaled Stats website for ARMA3's Exile MOD.
---
# Disclaimer
I am far from a PHP Expert. I did this project for fun to teach myself some new things. Please feel free to suggest improvements or request a fork of this project.  Also, the EXILE file I made modifications to were done over a year ago.  I am not a exile scripter and if you find a more effcient way of doing it, feel free to.

<<<<<<< HEAD
## Things you will need to do:
1) Setup a webserver
2) Setup a read (Select) only MYSQL user account.
`CREATE USER 'stats-read'@'localhost' IDENTIFIED BY 'password';`
`GRANT SELECT PRIVILEGES ON * . * TO 'stats-read'@'localhost';`
`FLUSH PRIVILEGES;`
Note: if you plan on remotely accessing the database you will need to configure your user and database to allow for remote connections.  Please do this securely if you plan to do so.
3) Setup an Overwrite for ExileServer_object_player_event_onMpKilled.sqf.
`The file is provided in the repo`
4) Add this entry to your exile.ini
`[updatePlayerStats]
SQL1_1 = INSERT INTO player_stats SET killer = ?, victim = ?, weaponused = ?, distance = ?, bambikill = ?, territorykill = ?, raidkill = ?, time = NOW()
SQL1_INPUTS = 1,2,3,4,5,6,7`
5) Alter your DATABASE to include the following field and new table.
`ALTER TABLE account ADD catchphrase VARCHAR(60);`
``CREATE TABLE `player_stats` (
	`id` INT(11) NOT NULL AUTO_INCREMENT,
	`killer` VARCHAR(50) NULL DEFAULT NULL,
	`victim` VARCHAR(100) NULL DEFAULT NULL,
	`weaponused` VARCHAR(50) NULL DEFAULT NULL,
	`distance` INT(11) NULL DEFAULT NULL,
	`bambikill` INT(1) NULL DEFAULT NULL,
	`raidkill` INT(11) NULL DEFAULT NULL,
	`territorykill` INT(11) NULL DEFAULT NULL,
	`time` DATETIME NULL DEFAULT NULL,
	INDEX `Index 1` (`id`),
	INDEX `Index 2` (`victim`),
	INDEX `Index 3` (`killer`)
)
COLLATE='utf8_general_ci'
ENGINE=InnoDB
AUTO_INCREMENT=1
;``
6) Edit /includes/condb.php
`condb.php is setup for 2 servers.  If you have multiple databases, add the second or third one and uncomment the sections in condb.`
7) Edit /includes/navbar.php
`if you have two databses be sure to uncomment the line for the second database.`
=======
Demo: http://45.32.211.193 

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
>>>>>>> b8e72b24117b08a1bc4129f844b99518c68cfb1d

**ExileServer_object_player_event_onMpKilled.sqf**
- This file was modified and created A LONG TIME AGO.  From my understanding, it still works just fine.  Feel free to modify anything you see in there.  A few communities are running this stats page today and have been for almost a year.  It's still working just fine.
