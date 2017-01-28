docker-compose Example 
======================

Dieses Beispiel soll zeigen, wie man eine umfangreichere Installation mit Hilfe von docker und docker-compose durchführen kann.

unterteilt wird in ein Production (prod) und ein development (dev) environment. 

Ebenfalls enthalten sind beispielhaft 2 Dockerfiles für die php7_fpm images. 

im verzeichnis **mysl** hinterlegen die server der verschiedenen environments, das verzeichnis **html** stellt für beide environments die webinhalte zur verfügung. 

requirements
------------
* docker
* docker-compose


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

Script autocompletion
---------------------
das script **server.completion** muss in das verzeichnis **/etc/bash_completion.d/** kopiert werden, die variable **DOCKER_COMPOSER_PATH** muss auch hier wieder angepasst werden, auf den Pfad, in dem sich das example project befindet, hier ist der übergeordnete pfad notwendig.