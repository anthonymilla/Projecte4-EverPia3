# Accés Remot. Connexió via SSH

| Pràctica SSH |
|----------------------------------------|

A la màquina d'Ubuntu Server i Windows, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.

![A la màquina d'Ubuntu Server i Windows, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.](img/Imatge01.png)

![A la màquina d'Ubuntu server i Windows, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.](img/Imatge02.png)

Entrem i el primer que fem és editar el netplan.

```
sudo nano /etc/netplan/50-cloud-init.yaml
```

![Entrem i el primer que fem és editar el netplan.](img/Imatge03.png)

![Entrem i el primer que fem és editar el netplan.](img/Imatge04.png)

Apliquem canvis.

```
sudo netplan apply
```

![Entrem i el primer que fem és editar el netplan.](img/Imatge05.png)

**Instal·lem el ssh amb la següent comanda:**

```
sudo apt install ssh
```

![Instal·lem el ssh amb la següent comanda:](img/Imatge06.png)

Després l’habilitem, reiniciem i comprovem l’estat.
```
sudo systemctl enable ssh
```
```
sudo systemctl restart ssh
```
```
sudo systemctl status ssh
```

![Després l’habilitem, reiniciem i comprovem l’estat.](img/Imatge07.png)

![Després l’habilitem, reiniciem i comprovem l’estat.](img/Imatge08.png)

Ara fem: ip a, per veure la ip del adaptador de només amfitrió.
```
ip a
```

![Ara fem: ip a, per veure la ip del adaptador de només amfitrió.](img/Imatge09.png)

Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.

```
ssh usuari@IP-del-servidor
```

![Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.](img/Imatge10.png)

![Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.](img/Imatge11.png)

Verifiquem el hostname:
```
hostname
```

![Verifiquem el hostname](img/Imatge12.png)

Anem a l'Ubuntu, habilitem l’usuari root, fem sudo passwd root i li posem una contrasenya (usuari).
```
sudo passwd root
```

![Anem a l'Ubuntu, habilitem l’usuari root, fem sudo passwd root i li posem una contrasenya (usuari).](img/Imatge13.png)

Seguidament entrem al següent arxiu, anem al final i afegim la següent línia. 

```
sudo nano /etc/ssh/sshd_config
```

![Seguidament entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge14.png)

![Seguidament entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge15.png)

![Seguidament entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge16.png)

Fem login de manera local amb l’usuari root.

```
su - root
```

![Fem login de manera local amb l’usuari root.](img/Imatge17.png)

Ara anem a Windows, fem ssh amb l’usuari root i veurem com ens denega l’accés.

```
ssh root@IP-del-servidor
```

![Ara anem a Windows, fem ssh amb l’usuari root i veurem com ens denega l’accés.](img/Imatge18.png)

Ara posem la següent comanda per generar alguns codis RSA.

```
ssh-keygen -t rsa
```

![Ara posem la següent comanda per generar alguns codis RSA.](img/Imatge19.png)

Ara seguidament posem la comanda; ls .\.ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.

```
ls .\.ssh\
```

![Ara seguidament posem la comanda; ls .\.ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.](img/Imatge20.png)

```
scp .\.ssh\id_rsa.pub usuari@IP-del-servidor:/home/usuari
```

![Ara seguidament posem la comanda; ls .\.ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.](img/Imatge21.png)

Anem a ubuntu i creem el següent arxiu, ha d’estar dins de la carpeta ssh aleshores el crearem amb la següent comanda: 

```
touch .ssh/authorized_keys
```

![Anem a ubuntu i creem el següent arxiu, ha d’estar dins de la carpeta ssh aleshores el crearem amb la següent comanda.](img/Imatge22.png)

Seguidament copiem la clau id_rsa.pub dins del arxiu que hem creat abans. 

```
cat id_rsa.pub >> .ssh/authorized_keys_
```

![Seguidament copiem la clau id_rsa.pub dins del arxiu que hem creat abans. ](img/Imatge23.png)

Ara anem a Windows i posem la següent comanda per fer la comprovació de que ens podem connectar a la màquina ubuntu sense que ens demani contrasenya.

```
ssh usuari@IP-del-servidor
```

![Ara anem a Windows i posem la següent comanda per fer la comprovació de que ens podem connectar a la màquina ubuntu sense que ens demani contrasenya.](img/Imatge24.png)

Ara anirem a configuració, sistema, anem a características opcionals i cliquem a veure característiques (el que volem és poder tenir el servidor OpenSSH). 

![Ara anirem a configuració, sistema, anem a características opcionals i cliquem a veure característiques (el que volem és poder tenir el servidor OpenSSH). ](img/Imatge25.png)

![Ara anirem a configuració, sistema, anem a características opcionals i cliquem a veure característiques (el que volem és poder tenir el servidor OpenSSH). ](img/Imatge26.png)


![Ara anirem a configuració, sistema, anem a características opcionals i cliquem a veure característiques (el que volem és poder tenir el servidor OpenSSH). ](img/Imatge27.png)

Cliquem a veure les característiques disponibles.

![Cliquem a veure les característiques disponibles.](img/Imatge28.png)

En característiques disponibles buscarem OpenSSH, marcarem la casella i l’agregarem.

![En característiques disponibles buscarem OpenSSH, marcarem la casella i l’agregarem.](img/Imatge29.png)

![En característiques disponibles buscarem OpenSSH, marcarem la casella i l’agregarem.](img/Imatge30.png)

Després desactivem el Firewall, per això anem Firewall i protecció de xarxa i després a Red pública i desactivem. Desactivem el tallafoc per permetre la connexió SSH entre les màquines sense que Windows bloquegi el tràfic.

![Després desactivem el Firewall, per això anem Firewall i protecció de xarxa i després a Red pública i desactivem. Desactivem el tallafoc per permetre la connexió SSH entre les màquines sense que Windows bloquegi el tràfic.](img/Imatge31.png)

![Després desactivem el Firewall, per això anem Firewall i protecció de xarxa i després a Red pública i desactivem. Desactivem el tallafoc per permetre la connexió SSH entre les màquines sense que Windows bloquegi el tràfic.](img/Imatge32.png)

![Després desactivem el Firewall, per això anem Firewall i protecció de xarxa i després a Red pública i desactivem. Desactivem el tallafoc per permetre la connexió SSH entre les màquines sense que Windows bloquegi el tràfic.](img/Imatge33.png)

Ara executem el powershell com administrador.

![Ara executem el powershell com administrador.](img/Imatge34.png)

I iniciem en servei de server SSH.

```
Start-Service sshd
```

![I iniciem en servei de server SSH.](img/Imatge35.png) 

Posem aquesta comanda per què cada vegada que iniciem la màquina s’activi el servei.

```
Set-Service -Name sshd -StartupType "Automatic"
```

![Posem aquesta comanda per què cada vegada que iniciem la màquina s’activi el servei.](img/Imatge36.png)

Posem; ipconfig, per veure la IP de l’adaptador de només amfitrió i després amb aquella IP ens puguem connectar des de l'Ubuntu.

```
ipconfig
```

![Posem; ipconfig, per veure la IP de l’adaptador de només amfitrió i després amb aquella IP ens puguem connectar des de l'Ubuntu.](img/Imatge38.png)

Ara, des de la màquina Ubuntu, fem un ping per comprovar que es poden veure les dues màquines i ens connectem a la màquina Windows amb la IP de la interfície de només amfitrió de la màquina Windows.

```
ping IP-local-de-Windows
```

![Ara, des de la màquina Ubuntu, fem un ping per comprovar que es poden veure les dues màquines i ens connectem a la màquina Windows amb la IP de la interfície de només amfitrió de la màquina Windows.](img/Imatge388.png)

```
ssh usuari@IP-local-de-Windows
```

![Ara, des de la màquina Ubuntu, fem un ping per comprovar que es poden veure les dues màquines i ens connectem a la màquina Windows amb la IP de la interfície de només amfitrió de la màquina Windows.](img/Imatge389.png)

![Ara, des de la màquina Ubuntu, fem un ping per comprovar que es poden veure les dues màquines i ens connectem a la màquina Windows amb la IP de la interfície de només amfitrió de la màquina Windows.](img/Imatge40.png)

Seguidament la creació d’un túnel SSH (Proxy SOCKS), amb la següent comanda: 

```
ssh -D 9876 usuari@IP-del-servidor
```

![Seguidament la creació d’un túnel SSH (Proxy SOCKS), amb la següent comanda: ](img/Imatge41.png) 

Ara fem la configuració del Proxy a Windows, primerament anem a panell de control. 

![Ara fem la configuració del Proxy a Windows, primerament anem a panell de control. ](img/Imatge42.png) 

Després a Xarxa i Internet.

![Després a Xarxa i Internet.](img/Imatge43.png) 

Ara a Opcions d’Internet.

![Ara a Opcions d’Internet.](img/Imatge44.png) 

Anem a connexions i configuració de LAN. 

![Anem a connexions i configuració de LAN. ](img/Imatge45.png) 

Opcions avançades (Deixem marca l'opció de: Usar un servidor proxy para la LAN).

![Opcions avançades (Deixem marca l'opció de: Usar un servidor proxy para la LAN).](img/Imatge46.png) 

Posem en Socks IP local i port 9876.

![Posem en Socks IP local i port 9876.](img/Imatge47.png) 

I després instal·lem Wireshark i fem la validació del túnel amb Wireshark.

![I després instal·lem Wireshark i fem la validació del túnel amb Wireshark.](img/Imatge48.png) 


[Anar a l'enunciat](../Tasca01/README.md)  
[Anar a la pàgina inicial](../README.md)
