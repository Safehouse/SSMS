SSMS - Sourcemod Server Management System
=========================================

This tool should help you in the everlasting battle against plugin versions automatic updates and other handy things
when it comes down to handling sourced game servers. At first i got the idea from the great tool nemrun but this would
not work with windows based machines and used the same technique to query the master server for updates which is used
by another great tool [steam condenser]

Install
-------

First make a database, and fill it with the data of ssms.sql.

Copy over all the files to your folder, update the config.php.example and rename it to config.php
to fit your needs (dont fill in what you dont have/need) You can import your servers if you have
them in hlstats or just use the gui to do a addserver in the start.


To update it automaticly dont forget to add a crontab, as example: 
	*/1 * * * * cd /home/lethal/public_html/admin/ && php servers.php -u > /dev/null 2>&1


For updates on the plugin id's and version matching do this (only do it once! and if possible change the time a bit random)
	58 05 * * * cd /home/lethal/public_html/admin/ && php dbplugins.php -u > /dev/null 2>&1

	Please note that the plugin version crontab doensn't work yet since someone deleted some files on AM.

Features
--------

* Automaticly updates your server without the needs to have a tool running locally. This is done by simply sending a _restart towards the server in question (so it can be either windows or linux machines)
* Will warn 1 minute in advance to all players online with a popup or any command you would like to send out to the server before it goes down.
* Overview for all your extensions/metamod/sourcemod plugins nicely in 1 big screen. This way you can easilly see which plugins you have installed and where something is different compared to your other servers.
* Daily restarts set by time and even with a min/max player count
* Alerting of servers that are down via Email, Growl and twitter. 
* Valve Updates for servers get alerted the same way.
* Use the server overview to do quick access things like see the players, restart a server (if empty), use rcon access.

Optional Features
-----------------
* Server crash statistics, you would need to install the plugin that came with ssms on all your servers and add a line to databases.cfg for this to work and set "yes" on the config to allow it to show.
* Admin logging, ever wanted to know if your admins just slap around all the time? Now you can, install the optional admin logging plugin on all your servers, setup databases.cfg and your off.


Credits
-------
1. Nemrun for his great [tool]
2. Koraktor for helping out and debugging issues and ofcourse his [steam condenser]
3. Multiple people from irc mostly from Alliedmodders for helping/ideas.
4. Several people from our community (Pablo/Alias/etc)
5. DarthNinja for creating the frist [crashlogger] plugin.
6. Author of admin logging plugin part (mentioned in the source of supplied plugin)

[tool]: http://nephyrin.net/tools/nemrun/latest/
[steam condenser]: https://github.com/koraktor/steam-condenser
[crashlogger]: http://forums.alliedmods.net/showthread.php?p=1050025
