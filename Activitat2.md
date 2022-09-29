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

