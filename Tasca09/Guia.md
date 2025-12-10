# SERVIDOR FITXERS LINUX. NFS

| Fase 1: Preparació de l’entorn |
|----------------------------------------|

Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.

![Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.](img/Imatge01.png)

![Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.](img/Imatge02.png)

![Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.](img/Imatge03.png)

![Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.](img/Imatge04.png)

![Configurem els dos equips amb dues interfícies de xarxa: una NAT per a l'accés a Internet i una adaptador de xarxa només-amb-amfitrió per a la comunicació entre ells i potencialment, treballar via terminal SSH amb el servidor. 
Quan els instalem, posem espanyol (Espanya) d’idioma i amb l'idioma per defecte en espanyol. En Ubuntu Server, seleccionarem la instal·lació del servei SSH durant el procés d'instal·lació per facilitar la gestió remota.](img/Imatge05.png)

Instal·lem el ssh per si de cas a les dues màquines, després fem ping per veure que ambdues màquines tinguin accés a Internet.

Per instalar ssh:
```
sudo apt install ssh
```

![Instal·lem el ssh per si de cas a les dues màquines, després fem ping per veure que ambdues màquines tinguin accés a Internet.](img/Imatge06.png)

![Instal·lem el ssh per si de cas a les dues màquines, després fem ping per veure que ambdues màquines tinguin accés a Internet.](img/Imatge07.png)

Després fem les actualitzacions.

```
sudo apt update && sudo apt upgrade
```

![Després fem les actualitzacions.](img/Imatge08.png)

![Després fem les actualitzacions.](img/Imatge09.png)

| Fase 2: Preparació del servidor |
|----------------------------------------|

Abans de compartir res, hem de preparar els usuaris i els directoris al Servidor.                        
Al zorin instal·lem Users and Groups per poder fer-ho, ja que de fabrica no deixa crear grups. I els creem (Ubuntu).

![Al zorin instal·lem Users and Groups per poder fer-ho, ja que de fabrica no deixa crear grups. I els creem (Ubuntu).](img/ImatgeGroups.png)

![Al zorin instal·lem Users and Groups per poder fer-ho, ja que de fabrica no deixa crear grups. I els creem (Ubuntu).](img/ImatgeUsersSettings.png)

Creació de Grups: Crear dos grups per al client: devs i admins.

![Abans de compartir res, hem de preparar els usuaris i els directoris al Servidor.
Creació de Grups: Crear dos grups per al client: devs i admins.](img/Imatge10.png)

Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).     
Crear un usuari admin01 (membre del grup admins).

![Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).
Crear un usuari admin01 (membre del grup admins).](img/Imatge11.png)

![Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).
Crear un usuari admin01 (membre del grup admins).](img/Imatge12.png)

![Creació d'Usuaris: Crear un usuari dev01 (membre del grup devs).
Crear un usuari admin01 (membre del grup admins).](img/Imatge13.png)

Crear el directori per als projectes de desenvolupament: 
/srv/nfs/dev_projects
```
cd /srv
```

```
sudo mkdir /nfs
```

```
sudo mkdir /nfs/dev_projectes
```

![Crear el directori per als projectes de desenvolupament: 
/srv/nfs/dev_projects](img/Imatge14.png)

Crear el directori per a les eines d'administració: 
/srv/nfs/admin_tools
```
sudo su
```

```
sudo mkdir /srv/nfs/admin_tools
```

![Crear el directori per a les eines d'administració: 
/srv/nfs/admin_tools](img/Imatge15.png)

Permisos del Servidor:

Es vol que els developers tinguin control total sobre els seus projectes.

Es vol que els administradors tinguin control sobre les seves eines.

En tots dos casos, l'usuari propietari serà root.

```
cd /nfs
```

```
sudo chown root:devs dev_projectes
```

```
sudo chown root:admins admin_tools
```

```
sudo chmod 770 dev_projectes
```

```
sudo chmod 770 admin_tools
```

![Permisos del Servidor: Es vol que els developers tinguin control total sobre els seus projectes. Es vol que els administradors tinguin control sobre les seves eines. En tots dos casos, l'usuari propietari serà root.](img/Imatge16.png)

![Permisos del Servidor: Es vol que els developers tinguin control total sobre els seus projectes. Es vol que els administradors tinguin control sobre les seves eines. En tots dos casos, l'usuari propietari serà root.](img/Imatge17.png)

Com a pas final, instal·lem els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.

```
sudo apt install nfs-kernel-server -y
```

```
systemctl status nfs-server
```

![Com a pas final, instal·lem els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.](img/Imatge18.png)

![Com a pas final, instal·lem els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.](img/Imatge19.png)

![Com a pas final, instal·lem els paquets necessaris per al servei NFS al servidor i es configurarà l'exportació dels directoris amb les opcions adequades.](img/Imatge20.png)

Configuració NFS.

```
sudo nano /etc/exports
```

![Configuració NFS.](img/Imatge21.png)

Afegim la següent linea.

![Afegim la següent linea.](img/Imatge22.png)

Fem restart.

```
sudo systemctl restart nfs-kernel-server
```

![Fem restart.](img/Imatge23.png)

Després sudo exportfs -u

```
sudo exportfs -u
```

![Després sudo exportfs -u](img/Imatge24.png)

Ip a.

```
ip a
```

![Ip a.](img/Imatge25.png)

Fem sudo rpcinfo -p a l’IP (192.168.56.106).

```
sudo rpcinfo -p 192.168.56.106
```

![Fem sudo rpcinfo -p a l’IP (192.168.56.106).](img/Imatge26.png)

Instal·lem nfs-common.

![Hola](img/Imatge27.png)

I ens connectem desde el client (Zorin) a l’Ubuntu.

![Hola](img/Imatge28.png)

| Fase 3: L'Exportació d'Administració (El Dilema del root_squash) |
|----------------------------------------|

El client necessita que el directori /srv/nfs/admin_tools sigui accessible per l'equip d'administradors. A vegades, l'usuari root del client (que sou vosaltres, els consultors) necessitarà escriure en aquest directori per instal·lar eines. Aquí mostrarem un error típic i la seva solució. Anem a /etc/exports i posem/deixem la linea del final (que ja estava posada de la Fase 2).

![El client necessita que el directori /srv/nfs/admin_tools sigui accessible per l'equip d'administradors. A vegades, l'usuari root del client (que sou vosaltres, els consultors) necessitarà escriure en aquest directori per instal·lar eines. Aquí mostrarem un error típic i la seva solució.                                                                     Anem a /etc/exports i posem/deixem la linea del final (que ja estava posada de la Fase 2).](img/Imatge29.png)

![Hola](img/Imatge30.png)

![Hola](img/Imatge31.png)

![Hola](img/Imatge32.png)

![Hola](img/Imatge33.png)

![Hola](img/Imatge34.png)

![Hola](img/Imatge35.png)

![Hola](img/Imatge36.png)

![Hola](img/Imatge37.png)

![Hola](img/Imatge38.png)

![Hola](img/Imatge39.png)

![Hola](img/Imatge40.png)





[Anar a l'enunciat](../Tasca09/README.md)  
[Anar a la pàgina inicial](../README.md)
