# Accés Remot. Connexió via SSH

| Pràctica SSH |
|----------------------------------------|

A la màquina de ubuntu server, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.

![A la màquina de ubuntu server, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.](img/Imatge01.png)

![A la màquina de ubuntu server, en xarxa, el primer adaptador el posem/deixem en NAT i el segon en Adaptador de només l’amfitrió.](img/Imatge02.png)

Entrem i el primer que fem és editar el netplan.

![Entrem i el primer que fem és editar el netplan.](img/Imatge03.png)

![Entrem i el primer que fem és editar el netplan.](img/Imatge04.png)

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

![Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.](img/Imatge10.png)

![Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.](img/Imatge11.png)

![Ara anem a la màquina Windows per comprovar la connexió. Quan ens demani permisos diem que sí i posem la contrasenya.](img/Imatge12.png)

Habilitem l’usuari root a l’Ubuntu, fem sudo passwd root i li posem una contrasenya (usuari).
```
sudo passwd root
```

![Habilitem l’usuari root a l’Ubuntu, fem sudo passwd root i li posem una contrasenya (usuari).](img/Imatge13.png)

Ara mostrem la configuració relativa als usuaris a l’arxiu sshd_config: usuarios permesos, engabiat, etc. Habilitem només a un usuari per accedir remotament i comprovem com altres no hi poden conectar. 
Entrem al següent arxiu, anem al final i afegim la següent línia. 

![Ara mostrem la configuració relativa als usuaris a l’arxiu sshd_config: usuarios permesos, engabiat, etc. Habilitem només a un usuari per accedir remotament i comprovem com altres no hi poden conectar. 
Entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge14.png)

![Ara mostrem la configuració relativa als usuaris a l’arxiu sshd_config: usuarios permesos, engabiat, etc. Habilitem només a un usuari per accedir remotament i comprovem com altres no hi poden conectar. 
Entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge15.png)

![Ara mostrem la configuració relativa als usuaris a l’arxiu sshd_config: usuarios permesos, engabiat, etc. Habilitem només a un usuari per accedir remotament i comprovem com altres no hi poden conectar. 
Entrem al següent arxiu, anem al final i afegim la següent línia. ](img/Imatge16.png)

Fem login de manera local amb l’usuari root.
```
su - root
```

![Fem login de manera local amb l’usuari root.](img/Imatge17.png)

Ara anem a Windows, fem ssh amb l’usuari root i veurem com ens denega l’accés.

![Ara anem a Windows, fem ssh amb l’usuari root i veurem com ens denega l’accés.](img/Imatge18.png)

Ara posem la següent comanda per generar alguns codis RSA.

![Ara posem la següent comanda per generar alguns codis RSA.](img/Imatge19.png)

Ara seguidament posem la comanda; ls.\ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.

![Ara seguidament posem la comanda; ls.\ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.](img/Imatge20.png)

![Ara seguidament posem la comanda; ls.\ssh\, i mirarem dins del directori de la carpeta ssh els arxius que hi han creats, copiarem a la màquina ubuntu el que acaba en .pub i el copiarem amb la comanda scp.](img/Imatge21.png)

Anem a ubuntu i creem el següent arxiu, ha d’estar dins de la carpeta ssh aleshores el crearem amb la següent comanda:  

![Anem a ubuntu i creem el següent arxiu, ha d’estar dins de la carpeta ssh aleshores el crearem amb la següent comanda.](img/Imatge23.png)

Seguidament copiem la clau id_rsa.pub dins del arxiu que hem creat abans. 

![Seguidament copiem la clau id_rsa.pub dins del arxiu que hem creat abans. ](img/Imatge23.png)




[Anar a l'enunciat](../Tasca01/README.md)  
[Anar a la pàgina inicial](../README.md)
