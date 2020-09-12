# GLPI 9.5.1 avec Fusion inventory

## Exemple

$docker build . -t secudev-glpi:9.5.1 --rm

$docker run --name glpi-mysql  -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=glpi -e MYSQL_USER=glpi -e MYSQL_PASSWORD=glpi --volume glpi-db:/var/lib/mysql  -d mariadb:10.5.5

$docker run --name glpi --hostname glpi --link mysql:mysql --volume glpi-data:/var/www/html/glpi/files/ -p 81:80 -p 62354:62354  -d secudev-glpi:9.5.1
