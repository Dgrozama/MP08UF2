# Instal·lació Owncloud

## Guía d'instal·lació Owncloud

### Requisits prèvis:

- Linux: Ubuntu 22.04LTS
- BBDD: MariaDB
- Servidor Web Apache2
- PDP: 7.4

### Instal·lació Apache2 i MariaDB:

Primer hem d'instal·lar l'apache2. Per a fer-ho fem de posar aquesta comanda a la terminal:

``` sudo apt install apache2 ```


![image](https://user-images.githubusercontent.com/114162341/193052646-67d4635d-e2f9-4986-b937-30ff584b6107.png)

Segon desactivem el llistat de directoris del servidor amb la comanda:

```sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf```

![image](https://user-images.githubusercontent.com/114162341/193052438-e1398500-cb3a-4456-918a-bb18f45c1f3b.png)

Després hem d'instal·lar MariaDB, per a fer-ho posem aquesta comanda:

```sudo apt-get install mariadb-server mariadb-client -y```

![image](https://user-images.githubusercontent.com/114162341/193053503-afa503ca-794a-40f7-9308-ea6c9537e49a.png)

I ara per a configurar la instal·lació posem aixo:

```sudo mysql_secure_installation```

![image](https://user-images.githubusercontent.com/114162341/193054313-e262cb2f-cf2d-45b9-b2b0-d1f1910363e3.png)

A continuació ens farà diverses preguntes, és preferible contestar amb:

- Switch to unix_socket authentication [Y/n] y
- Change the root password? [Y/n] n
- Remove anonymous users? [Y/n] y
- Disallow root login remotely? [Y/n] y
- Remove test database and access to it? [Y/n] y
- Reload privilege tables now? [Y/n] y

I per últim reiniciem el servidor MariaDB.

```sudo systemctl restart mariadb.service` o `sudo service mariadb.service restart```

![image](https://user-images.githubusercontent.com/114162341/193056517-3ddf2a3e-254c-45c4-b4b9-2f2bc166e575.png)

### Creació de la base de dades d'owncloud

Primer entrem en MariaDB.

```sudo mysql -u root -p```

![image](https://user-images.githubusercontent.com/114162341/193056941-4a7d15d0-abaf-43c2-9e09-a5721bd23475.png)

Després creem la base de dades.

```CREATE DATABASE owncloud;```

![image](https://user-images.githubusercontent.com/114162341/193057090-f989472e-685f-4984-b03a-8037b9e1754a.png)

Ara creem un usuari anomenat "ownclouduser" i la contrasenya "Admin1234".

```CREATE USER 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234';```

![image](https://user-images.githubusercontent.com/114162341/193057560-1a14e526-7b12-485f-8b1f-9f9fe519cb8e.png)

I després li donem accés a l'usuari a la base de dades anteriorment creada.

```GRANT ALL ON owncloud.* TO 'ownclouduser'@'localhost' IDENTIFIED BY 'Admin1234' WITH GRANT OPTION;```

![image](https://user-images.githubusercontent.com/114162341/193057787-da0814fd-e0a7-4cc7-a91d-cab1b75cb0ff.png)

I finalment apliquem els canvis i sortim.

```FLUSH PRIVILEGES;```
```EXIT;```

![image](https://user-images.githubusercontent.com/114162341/193058212-beabe2a0-10c4-46ee-bdeb-8ba17040615d.png)

### Instal·lació de PHP i els mòduls neccesaris

Primer li instal·lem un repositori per a ell.

```sudo apt-get install software-properties-common -y sudo add-apt-repository ppa:ondrej/php```

![image](https://user-images.githubusercontent.com/114162341/193059134-b7ef086b-b9cd-4fb2-9966-e42534cdfae4.png)

I ara actualitzem els paquets amb el repositori afegit.

```sudo apt update```

![image](https://user-images.githubusercontent.com/114162341/193059568-76e3f4a8-4d8f-4382-a6ca-477c6d709a6d.png)

Després instal·lem el PHP amb els seus mòduls neccesaris.

```sudo apt install php7.4 libapache2-mod-php7.4 php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-apcu php7.4-smbclient php7.4-ldap php7.4-redis php7.4-gd php7.4-xml php7.4-intl php7.4-json php7.4-imagick php7.4-mysql php7.4-cli php7.4-mcrypt php7.4-ldap php7.4-zip php7.4-curl -y```

![image](https://user-images.githubusercontent.com/114162341/193060053-92fbb3f9-4fac-424c-98d7-d2d805ce4234.png)

I ara accedim al fitxer php.ini i canviem alguns valors.

```sudo gedit /etc/php/7.4/apache2/php.ini```

![image](https://user-images.githubusercontent.com/114162341/193060452-49292049-d277-4cee-bd76-7c691779806c.png)

Una vegada dins fem "Ctrl+F" i escrivim "Memory_limit" i canviem de 128M a 256M.

![image](https://user-images.githubusercontent.com/114162341/193061428-f0636096-6fd4-415f-bba2-58ea778426c1.png)

També busquem "upload_max_filesize" i canviem de 2M a 100M.

![image](https://user-images.githubusercontent.com/114162341/193061884-9e1cf437-953b-4b68-989d-b1c4dee25d85.png)

I finalment busquem "date.timezone" i escrivim Europe/Madrid.

![image](https://user-images.githubusercontent.com/114162341/193062298-ce0cd5f0-5863-4ff1-ab20-86ac15b3bca5.png)

### Descarga del Owncloud

Ara descarguem l'última versión del programa i descomprimim els arxius, a més a més movem els arxius d' Owncloud a "/var/www/html/owncloud".

```cd /tmp && wget https://download.owncloud.com/server/stable/owncloud-complete-latest.zip```

![image](https://user-images.githubusercontent.com/114162341/193063086-e37a1510-f2c0-41a9-a40f-a5af735aeec8.png)

```unzip owncloud-complete-lastest.zip```

![image](https://user-images.githubusercontent.com/114162341/193064211-1edb0053-25fb-488c-87a6-9fb510c8ac39.png)

```sudo mv owncloud /var/www/html/owncloud/```

![image](https://user-images.githubusercontent.com/114162341/193064564-8d9a6012-7fa5-466e-84e3-2cc50a92570d.png)

I ara canviem el propietari i els permissos dels directoris d'owncloud. www-data per a que els pugui usar Apache, 755 para que els pugui executar i llegir qualsevol usuari de Linux:

```sudo chown -R www-data:www-data /var/www/html/owncloud/```
```sudo chmod -R 755 /var/www/html/owncloud/```

![image](https://user-images.githubusercontent.com/114162341/193068651-b470232b-81fa-4362-a6bc-00e77ab33cf4.png)

Ara posem aquesta comanda per a modificar el nom del host. Una vegada obert posem una altra ruta amb la ip 127.0.0.1 i el nom del domini "owncloud.dlgm.com".

```sudo gedit hosts```

![image](https://user-images.githubusercontent.com/114162341/194343747-436a0b9e-b3b6-4ecd-82b8-85442e6e3d6b.png)

I ara he entrat a la carpeta de apache2 i dins he entrat a sites-avaliable, dins d'aquesta carpeta he clonat el arxiu de 000-default.conf a owncloud.conf.

![image](https://user-images.githubusercontent.com/114162341/194346203-ce4ec847-6bae-49c0-aba9-aa7dbdf6b07c.png)

I ara entro al arxiu clonat i he afegit dos formes d'accedir a la web (owncloud.dlgm.com i www.owncloud.dlgm.com

![image](https://user-images.githubusercontent.com/114162341/194346690-57260469-5dea-4ab3-9fc1-a70629f35a2c.png)

I ara posem aquesta comanda per a activar la nova configuració.

![image](https://user-images.githubusercontent.com/114162341/194347281-73e00389-4c13-4df5-af07-fcd4f39616b8.png)

Ara entrem a aquest arxiu de configuració per a configurar l'owncloud.

![image](https://user-images.githubusercontent.com/114162341/195612579-70e3680c-b661-4cd3-96f0-ac1b41de3a5d.png)

I dins del document escrivim aquesta linea de comandes. 

![image](https://user-images.githubusercontent.com/114162341/195612901-7df6568f-34d3-476f-bd22-910fecbf0d76.png)

 - VirtualHost *:80: Vol dir que el servidor contestará per qualsevol ip i el 80 vol dir el port pel qual contestará.
 - ServerAdmin: És el correu del administrador del servidor.
 - DocumentRoot: És el directori de nivell superior de l'arbre del document visible des de la web i aquesta directiva estableix el directori en la configuració des del qual Apache2 cerca serveis fitxers web des de l'URL sool·licitat fins a l'arrel del document.
 - ServerName: Aquest és el nom del nostre servidor.
 - ServerAlias: És un link al qual si l'escrivim ens porta a la mateixa pàgina, és a dir, si el meu link és owncloud.com, amb www.owncloud.com no em portarà, però si ho poso al alias sí que em direcciona a la meva pàgina.
 - Alias /owncloud "/var/www/html/owncloud/": Aquesta comanda li diu a apache2 on mirar si t'estás connectant al teu servidor owncloud.
 - <Directory /var/www/html/owncloud/>: Aquest és el directori al qual s'aplicarán la següent configuració.
 - Options +FollowSymlinks: És una directiva dels servidors web apache.
 - AllowOverride All: És una opció que ens permet anul·lar alguns paràmetres d'Apache mitjançant un fitxer.
 - Require all granted: És una opció per al control d'accés.
 - IfModule mod_dav.c: És una extensió del protocol HTTP que permet crear, moure, copiar i suprimir recursos i col·leccions en un servidor web remot.
 - Dav off: Desactiva aquesta extensió.
 - /IfModule: Tanca la extensió.
 - SetEnv HOME /var/www/html/owncloud: Estableix el valor de la variable d'entorn d'Apache2 especificat per variable.
 - SetEnv HTTP_HOME /var/www/html/owncloud: Estableix el valor de la variable d'entorn d'Apache2 especificat per variable.

I ara posem aquestes comandes per a habilitar el owncloud i el rewrite.

```sudo a2ensite owncloud.conf
sudo a2enmod rewrite
sudo a2enmod headers
sudo a2enmod env
sudo a2enmod dir
sudo a2enmod mime
```

![image](https://user-images.githubusercontent.com/114162341/195872181-542e935d-a8a2-43c1-b6a5-c82ec0da515d.png)

I ara fem un restart.

```sudo service apache2 restart```

![image](https://user-images.githubusercontent.com/114162341/195873032-fc2e24a6-aca8-4e23-abbc-9fd5df6fc196.png)

I ara busquem l'arxiu config.php amb aquesta comanda:

```sudo find / -iname config.php```

![image](https://user-images.githubusercontent.com/114162341/195873690-f434104e-ef50-4fb1-849c-8b70a98a68a9.png)

I ara copiem la ruta i fem un:

```sudo nano /var/www/html/owncloud/config.php```

![image](https://user-images.githubusercontent.com/114162341/195874330-ee2793c2-c775-40ef-8ffb-79d19778d616.png)

I dins del arxiu hem de trobar 0 => 'localhost', el copiem i peguem justament abaix i posem el link de la nostra pàgina web.

![image](https://user-images.githubusercontent.com/114162341/195874863-70b2fe23-08af-43d8-b9f3-f6b8e31a4d90.png)

I ara ja podrem accedir a la nostra pàgina web.

Què fa la comanda a2ensite?

Permet activar un lloc web virtual en un servidor web apache2.

I la comando a2dissite?

Desactiva el lloc web apache2.

Què significa la línia de /etc/hosts

127.0.0.1 owncloud.XYZ.com

Significa que en lloc de sortir-nos la ip del lloc web ens sortirà l'adreça de la nostra web, en el meu cas seria owncloud.DLGM.com
