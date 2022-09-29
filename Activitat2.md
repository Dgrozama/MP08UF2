# Instal·lació Owncloud

## Guía d'instal·lació Owncloud

### Requisits prèvis:

- Linux: Ubuntu 22.04LTS
- BBDD: MariaDB
- Servidor Web Apache2
- PDP: 7.4

### Instal·lació:

Primer hem d'instal·lar l'apache2. Per a fer-ho fem de posar aquesta comanda a la terminal:

``` sudo apt install apache2 ```


![image](https://user-images.githubusercontent.com/114162341/193052646-67d4635d-e2f9-4986-b937-30ff584b6107.png)

Segon desactivem el llistat de directoris del servidor amb la comanda:

```sudo sed -i "s/Options Indexes FollowSymLinks/Options FollowSymLinks/" /etc/apache2/apache2.conf```

![image](https://user-images.githubusercontent.com/114162341/193052438-e1398500-cb3a-4456-918a-bb18f45c1f3b.png)

