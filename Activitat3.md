# Activitat 3:

Per fer aquesta activitat comptem amb que **ja s'ha configurat el servei Owncloud a una Màquina Virtual** (MV).

**3.1.-** Llista els Virtual Hosts d'Apache per tal de veure si **owncloud.XYZ.com** està habilitat amb la comanda:

```
apache2ctl -S
``` 

**RESPOSTA**

Com podem veure el host està habilitat.

![image](https://user-images.githubusercontent.com/114162341/195857582-dc37afa0-0a32-4a39-b56d-da782d69243f.png)


**3.2.-** A Owncloud podem veure que hi ha una serie de carpetes per defecte, mostra la ruta real a les tres carpetes dins de la teva MV.

![image](https://user-images.githubusercontent.com/110727546/194824543-c49bf482-ac93-432f-884c-d89487e587f3.png)

**RESPOSTA**

Ara ho trobem a la següent ruta:

```cd /var/www/html/owncloud/data/ownclouduser/files```

![image](https://user-images.githubusercontent.com/114162341/195867111-e2877deb-cf72-4a97-ac1c-3e0080cfed94.png)

**3.3.-** Al directori **Learn more about owncloud** hi ha informació en forma de fitxers pdf. Consulta'ls i respon aquestes preguntes:

- Quin són els tres tipus de protecció de dades que ofereix Owncloud?
  - 1 Encryption in Transit
  - 2.1 Encryption at Rest
  - 2.2 Encryption at Rest with Master Key in Hardware Security Module (HSM)
  - 3 End-to-End Encryption

- Fes una petita descripció de cada un d'ells.
  1 Proporciona una manera de protegir les dades entre instancies i sistemes d'arxius muntats mitjançant el cifratge TLS.
  2.2 És un mètode de cifratge 
  2.2 
  3 
 
- Per quina raó ens recomana utilitzar Owncloud per als documents de Microsoft Office de la nostra empresa? 

  Ens recomana ja que ownCloud ens prové un plugin que ajuda als usuaris a unir-se amb el seu email i també té un plugin d'encriptació End-to-End per a asegurar els teus administradors del sistema.

- Això passa a tots els països?
-
- Quina és la llicència d'OWncloud Enterprise?
- I la d'Owncloud Standard?
- Es poden veure videos en Streaming directament des de Owncloud?
- Es poden connectar directoris de Google Drive a Owncloud?
- I Dropbox?
- Compta Owncloud amb antivirus? En cas afirmatiu com es diu? 

**RESPOSTA**

**3.4.-** Mostra els següents canvis de paràmetres d'usuari:

- Posa't una imatge d'usuari.
- Afegeix el teu mail de l'Institut.
- Canvia l'idioma a català.
- Mostra la versió d'Owncloud instal·lada.

**RESPOSTA**
