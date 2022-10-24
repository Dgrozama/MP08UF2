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
  2.2 És un mètode de cifratge dissenyat per a evitar que l'atacant obtingui accés a les dades sense xifratge assegurant-se de que les dades es xifrin en el disc.
  2.2 És el mateix mètode però amb contrasenya (una clau mestra (master key))
  3 És un procés de comunicació segur que evita que tercers accedeixin a les dades transferides d'un extrem a l'altre.
 
- Per quina raó ens recomana utilitzar Owncloud per als documents de Microsoft Office de la nostra empresa? 

 Perquè emmagatzema les dades (documents, etc...) al núvol per a que estiguin ben guardades i de manera segura.

- Això passa a tots els països?

Sí, a tots els països de la unió europea.

- Quina és la llicència d'OWncloud Enterprise?

És la llicència pensat per a empreses, amb un software amb una llicència comercial .

- I la d'Owncloud Standard?

La edició standard està programanda per a usuaris.

- Es poden veure videos en Streaming directament des de Owncloud?

Sí, owncloud té aquesta característica per a totes les versions de owncloud.

- Es poden connectar directoris de Google Drive a Owncloud?

Sí, és possible.

- I Dropbox?

També és possible.

- Compta Owncloud amb antivirus? En cas afirmatiu com es diu? 

Sí, s'anomena Ransomware.


**RESPOSTA**

**3.4.-** Mostra els següents canvis de paràmetres d'usuari:

- Posa't una imatge d'usuari.

Primer accedeixo a la carpeta "Downloads" i trio la meva imatge descarregada.

![image](https://user-images.githubusercontent.com/114162341/196979436-e521e6f3-58b0-43ec-ad07-1cffeadcada5.png)

I ara li dono a "Seleccionar como foto de perfil".

![image](https://user-images.githubusercontent.com/114162341/196979558-2fec1389-1567-4164-8158-0e6ee28c0eeb.png)

- Afegeix el teu mail de l'Institut.

He posat el meu correu i li he donat a "Establecer correo electrónico".

![image](https://user-images.githubusercontent.com/114162341/196979817-a69b694c-6772-426e-b329-265572fb5b28.png)


- Canvia l'idioma a català.

Per a canviar de idioma sols hem de fer clic damunt de Castellano i allí busquem el Català.

![image](https://user-images.githubusercontent.com/114162341/196980244-c64c1bbd-171b-4f34-afb4-8ac63d310e10.png)

- Mostra la versió d'Owncloud instal·lada.

I abaix de tot ens ensenya la última versió del owncloud.

![image](https://user-images.githubusercontent.com/114162341/196980805-56b0f6ca-2708-4451-81c6-dc456103a5c1.png)
