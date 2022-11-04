# Activitat 4:

## Gestió d'usuaris:

Hi ha dos tipus d'usuaris, els admins amb permissos per gestionar Owncloud i els usuaris normals.

On fica resposta afegeix una captura de pantalla on es vegi que has fet l'acció que es demana.

**Aquesta part de la pràctica la feu amb un company/a, li creeu un usuari i li doneu el vostre nom de domini d'Owncloud.**

Per a que pugui accedir necessitarà:

- La MV amb owncloud ha d'estar en mode "adaptador pont".
- El fitxer /etc/hosts del company ha de tenir la IP de la MV i el nom de domini de la MV del company/a.


**4.1.-** Crea un usuari admin que es digui adminXYZ, on XYZ són les inicials del teu nom:

![image](https://user-images.githubusercontent.com/114162341/198646795-9769cd2a-57fb-45a9-ae4c-36d644554ecc.png)

**4.2.-** Inicia sessió com a l'usuari adminXYZ.

![image](https://user-images.githubusercontent.com/114162341/198647840-071097f8-d06a-44db-af0b-f05c23a19960.png)

**4.3.-** Crea un usuari XYZ on XYZ son les inicials del company/a i afegeix-lo al grup usuaris, aquest usuari tindrà una quota de 512 MB.

![image](https://user-images.githubusercontent.com/114162341/198649163-cca91088-2318-4c7f-bde0-6946330107f7.png)

**4.4.-** Podem crear fitxers d'una mida determinada a Linux amb la comanda:

```
truncate -s 10M file.txt
```

A l'exemple es crea un fitxer de 10MB.

Crea 6 fitxers de 100MB i pujal's a Owncloud un per un.

![image](https://user-images.githubusercontent.com/114162341/198654268-7acd5c50-59f3-4fac-b2d2-ab1a15c60f94.png)

![image](https://user-images.githubusercontent.com/114162341/198655201-429bda47-fd2f-4254-a28f-14cfae268a36.png)

**4.5.-** Mostra el missatge d'error per haver superat la quota d'usuari.

![image](https://user-images.githubusercontent.com/114162341/198671031-1a8e7f90-320e-4b6c-b819-b56c51dc4b3b.png)

**4.6.-** Busca al teu perfil quin percentatge de quota estas utilitzant.

![image](https://user-images.githubusercontent.com/114162341/199528038-ee9499b9-153a-4f17-ae99-ffa7d4909e9d.png)

**4.7.-** Canvia la quota de l'usuari a 1GB i mostra tots els fitxers pujats.

![image](https://user-images.githubusercontent.com/114162341/199528239-8292b3a1-0cc8-4f42-97f5-b800d465579e.png)

![image](https://user-images.githubusercontent.com/114162341/199531468-a1777195-e8b0-41db-ac48-ef4178951d62.png)

**4.8.-** Crea un usuari anomenat usuari2XYZ i fical al grup usuaris.

![image](https://user-images.githubusercontent.com/114162341/199530252-1fc474a2-6cc3-461a-9ae1-10cbefa6b1d9.png)


**4.9.-** Comparteix un fitxer de usuariXYZ a usuari2XYZ i mostra com l'usuari2XYZ pot veure i descarregar el fitxer.

![image](https://user-images.githubusercontent.com/114162341/199531922-d6920f44-17c5-4db8-83e5-bbe332cae45e.png)

![image](https://user-images.githubusercontent.com/114162341/199532370-eb53fe15-a237-42be-92c1-2542a9ce7b88.png)


**4.10.-** Esborra la carpeta Learn more about owncloud.

![image](https://user-images.githubusercontent.com/114162341/199532449-1693cfec-0d78-41ed-9b2c-a16df149dc63.png)

**4.11.-** Recupera la carpeta Learn more about owncloud.

![image](https://user-images.githubusercontent.com/114162341/199532522-e8e984f1-8828-4bc3-ae2e-82360c88dac1.png)

![image](https://user-images.githubusercontent.com/114162341/199532634-6e5f4ce4-5754-483b-bd4f-30379938b1b5.png)


**4.12.-** Com a usuariXYZ crea una carpeta nova anomenada shared i comparteix-la amb l'usuari usuari2XYZ.

![image](https://user-images.githubusercontent.com/114162341/199533418-fad35053-a3c0-495b-a048-9bd4987ff6a7.png)

![image](https://user-images.githubusercontent.com/114162341/199533586-971e4b97-db37-4aac-9680-eaf08dba22f1.png)


**4.13.-** Entra a Market instal·la dues aplicacions que no estiguin ja instal·lades i explica què fan i com funcionen.

![image](https://user-images.githubusercontent.com/110727546/196159706-705ff624-c409-4632-acb4-f43ffcc486d4.png)

La primera app serveix per a afegir contactes al owncloud.

![image](https://user-images.githubusercontent.com/114162341/199534586-458e39de-67ad-4304-a524-9101f6052481.png)

S'utilitza per a afegir clients i proveïdors o simplement als teus amics, però aquesta opció está pensada per a empreses, el que fa és afegir contactes i poder veure-ls des de owncloud.

![image](https://user-images.githubusercontent.com/114162341/199534705-1d12500a-a233-4a24-952d-35a1e88a50e1.png)

Aquesta app serveix per a afegir invitats a owncloud, és a dir és un usuari temporal que no té nom ni contrasenya.

![image](https://user-images.githubusercontent.com/114162341/199535326-1984abe8-8cd4-436e-ac6a-3e0f47eb6a9d.png)

**4.14.-** Crearem una carpeta nova per emmagatzematge a Owncloud, la carpeta serà /media/publicXYZ on XYZ són les teves inicials i apareixerà amb el nom de public als usuaris.

Aquesta carpeta haurà de pertànyer a l'usuari www-data.

![image](https://user-images.githubusercontent.com/114162341/200000239-58ca3bd2-a455-4935-9e2d-44ec6d07876f.png)

![image](https://user-images.githubusercontent.com/114162341/200003188-91f3d7e4-0196-47e4-8423-c5d3c11579bc.png)


**4.15.-** Connectarem la carpeta publicXYZ com emmagatzematge local, tal i com s'indica [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/local.html). Tots els usuaris tindran accés a la carpeta.

![image](https://user-images.githubusercontent.com/114162341/200005121-ae07e78e-09bf-4a90-bc0a-daa306254d21.png)

![image](https://user-images.githubusercontent.com/114162341/200006426-c10d9d4b-afc8-4114-b0a4-053d961496ae.png)


**4.16.-** Un usuari normal pujarà un fitxer a la carpeta public.

![image](https://user-images.githubusercontent.com/114162341/200006723-a0767baf-fbdf-4f65-8f91-fc41647c8307.png)

**OPCIONAL.-** Aquesta tasca és opcional.

Intenta connectar com a emmagatzematge extern el teu compte de Google Drive de l'Institut. Tens com fer-ho [aquí](https://doc.owncloud.com/server/next/admin_manual/configuration/files/external_storage/google.html).

**RESPOSTA**
