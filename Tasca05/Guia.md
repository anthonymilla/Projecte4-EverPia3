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

**Instal·lem el ssh amb la següent comanda**

![Instal·lem el ssh amb la següent comanda](img/Imatge06.png)

Després l’habilitem, reiniciem i comprovem l’estat.

![Després l’habilitem, reiniciem i comprovem l’estat.](img/Imatge07.png)

![Després l’habilitem, reiniciem i comprovem l’estat.](img/Imatge08.png)

**Ara fem ip a per veure la ip del adaptador de només amfitrió.**

![Ara fem ip a per veure la ip del adaptador de només amfitrió.](img/Imatge09.png)

Ara anem a la màquina Windows per comprovar la connexió

![Ara anem a la màquina Windows per comprovar la connexió](img/Imatge10.png)

![Ara anem a la màquina Windows per comprovar la connexió](img/Imatge11.png)

![Ara anem a la màquina Windows per comprovar la connexió](img/Imatge12.png)

**Habilitem l’usuari root a l’Ubuntu, fem sudo passwd root y li posem una contrasenya (usuari).**

![Habilitem l’usuari root a l’Ubuntu, fem sudo passwd root y li posem una contrasenya (usuari).](img/Imatge13.png)

**Ara mostrem la configuració relativa als usuaris a l’arxiu sshd_config: usuarios permesos, engabiat, etc. Habilitem només a un usuari per accedir remotament i comprovem com altres no hi poden conectar.**





[Anar a l'enunciat](../Tasca01/README.md)  
[Anar a la pàgina inicial](../README.md)
