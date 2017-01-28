docker-compose Example 
======================

Dieses Beispiel soll zeigen, wie man eine umfangreichere Installation mit Hilfe von docker und docker-compose durchführen kann.

unterteilt wird in ein Production (prod) und ein development (dev) environment. 

Ebenfalls enthalten sind beispielhaft 2 Dockerfiles für die php7_fpm images. 

production environment
----------------------
startet einen webserver auf basis von nginx, eine datenbank auf basis von mariadb und einen php interpreter in der version 7

development environment
-----------------------
dieser build ist analog zu den server im production environment, zusätzlich wird hier noch **xdebug** auf dem server des php7 interpreters installiert.

server script
-------------
zusätzlich liegt unter ./bin ein script namens **server**. das kann man unter **/usr/local/bin hinterlegen** und mit **chmod +x /usr/local/bin/server** ausführbar machen. 
das script dient zum einfacheren starten und beenden sowie, wenn notwendig, builden von servern. 

folgende syntax wird verwendet:

*server start example*

		startet docker-compose im production environment

*server start example dev* 

		startet docker-compose im development environment

*server stop example*

		stopt den server aus dem production environment

*server stop example dev*

		stopt den server aus dem development environment

		mit 

*server destroy example*

		bzw.

*server destroy example dev*

		stopt den jeweiligen server und entfernt auch deren container