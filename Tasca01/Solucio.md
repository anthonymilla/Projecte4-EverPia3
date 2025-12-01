# DRP: còpies de seguretat. Estudi cas client (treball cooperatiu)
 
| Fase 1: Treball individual |
|----------------------------------------|

**1. Què copiar?** Quan copiem el que hem de fer es prioritzar, el servidor és la prioritat perquè concentra les dades més crítiques, aleshores:
- **Servidor**:  
  - Base de dades  
  - Documents de Projectes
  - Carpetes Personals dels Usuaris  
- **Equips clients (10 PCs)**:  
  - No cal còpia completa (ja què la feina principal és al servidor)  
  - Només còpia dels documents importants si no estan al servidor (Documents)

---

**2. Periodicitat i Tipus de Còpia**
**Calendari bàsic per a la setmana:**
- Diari, la qual serà una còpia incremental, que són només els canvis del dia. Es fan còpies de seguretat diàries (només dels canvis) per estalviar temps i espai.
- Setmanal, la qual serà una còpia diferencial, que són els canvis des de l'última còpia completa. Hi ha un manual (manual de configuració diferencial) per arreglar coses ràpidament utilitzant aquestes còpies.
- Mensual, la qual serà una còpia completa (tot el servidor). Cada mes, es fa una còpia completa del sistema per tenir una seguretat extra.

---

**3. Mitjans i Ubicació (Regla 3-2-1)**
- **Mitjà de còpia que utilitzaria**:  
  - NAS (intern), ja què és un emmagatzematge connectat a la xarxa per accedir a dades fàcilment. 
  - Núvol (extern), ja què és un emmagatzematge en línia per accedir a les dades des de qualsevol lloc.  
  - Disc dur extern (físic), ja què és un dispositiu físic per guardar dades que pots portar amb tu.

- El NAS és la millor opció com a mitjà principal per la seva rapidesa, permet restauracions molt ràpides (compleix RTO < 4h), el seu Accés local, és fàcil i veloç accedir a les dades des de la mateixa xarxa i perquè és centralitzat, guarda totes les còpies en un sol lloc accessible.

- **Regla 3-2-1**:  
  - 3 còpies totals, necessites 3 còpies de les teves dades (1 original + 2 còpies). Aixís tens més tranquilitat en general i més seguretat. 
  - 2 mitjans diferents, básicament guardar les còpies en 2 tipus diferents de mitjans (ex. NAS i núvol). 
  - 1 fora de l’empresa (Cloud), una còpia ha d'estar fora de la teva empresa (millor al núvol) per protegir-te de pèrdues.

**Com sería l'ubicació seguint la regla 3-2-1 de còpies de seguretat:** 
- **3 còpies**: Original + NAS + Cloud
- **2 tipus de mitjans**: NAS i Cloud
- **1 fora de l’empresa**: Núvol

La còpia més recent s’ha de guardar al **NAS intern**, perquè és el més ràpid i fàcil de restaurar en cas de problema.

---

| Fase 2: Treball per parelles – Proposta Unificada |
|----------------------------------------|

## **Esquema 3-2-1 de Còpies**

| **Element**             | **Proposta de la Parella**                                                                                                                                                                                      | **Justificació**                                                                                                                                    |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Dades Crítiques**     | - Bases de Dades (Comptabilitat i Clients): Crítiques i d’ús diari.<br>- Documents de Projectes: Plànols, especificacions tècniques.<br>- Carpetes Personals dels Usuaris: Són mportants per la feina. | Les Bases de Dades són super importants per la feina diària, els projectes són essencials per als serveis i les carpetes personals contenen informació de treball i això també és molt important. |
| **Periodicitat (BD)**   | - Cada 4 hores: còpia incremental de les Bases de Dades.<br>- Diària: còpia incremental del servidor.<br>- Setmanal: còpia completa.<br>- Mensual: còpia completa per conservar un historial.                       | Complir l’objectiu de pèrdua màxima de dades (RPO), que vol dir que les Bases de Dades no poden perdre més de 4 hores de feina. A més, assegurem la protecció general fent còpies freqüents i còpies completes cada cert temps.                                                             |
| **Tipus de Còpia (BD)** | - Incremental: cada 4 hores per Bases de Dades i diària per altres dades.<br>- Diferencial: setmanal per projectes i carpetes.<br>- Completa: mensual per tot el servidor.                                      | Les còpies incrementals estalvien espai i temps, les còpies diferencials faciliten la restauració i les còpies completes garanteixen que es conserva tota la informació.                                             |
| **Mitjà 1 (Local)**     | NAS intern per còpies diàries i setmanals.                                                                                                                                                                  | Restauració ràpida dins l’empresa, assegurant que es pot recuperar tot en menys de 4 hores.                                                                                               |
| **Mitjà 2 (Extern)**    | Núvol per còpia fora de l’empresa + Disc dur extern per còpia mensual.                                                                                                                                  | El núvol protegeix davant desastres físics (com incendis o robatoris) i el disc dur extern és una còpia addicional que es pot guardar fora de l’empresa.                                                                   |

---

## **Regla 3-2-1 aplicada**

*   3 còpies: Original + NAS + Núvol/Disc dur
*   2 mitjans diferents: NAS i Cloud
*   1 fora de l’empresa: Núvol

---

| Fase 3: Treball en grup - Document Final |
|----------------------------------------|
# Document Final (Fase 3)

El grup ha de generar un document amb els següents punts resolts:

## 1) Dades Objecte de Còpia
Quines dades es copien i amb quina freqüència (separant Servidor/Clients i crítiques/no crítiques).  
Les dades més importants del servidor són sobretot les bases de dades dels clients, perquè són importants per al funcionament de l’empresa i canvien contínuament. També són molt importants els documents de projectes, ja que inclouen plànols i especificacions necessàries per a la feina dels tècnics. Finalment, les carpetes personals dels usuaris també s’han de protegir, perquè contenen informació del treball diari. No cal fer còpia completa dels 10 equips clients, ja que gairebé tot el treball es guarda en un NAS.  
Les bases de dades s’han de copiar amb còpies incrementals cada 4 hores i una còpia completa setmanal, ja que són dades crítiques. Els documents de projectes tindran còpia diferencial diària i còpia completa setmanal. Les carpetes personals es copiaran cada nit amb còpies incrementals i una còpia completa setmanal.

---

## 2) Cronograma Setmanal Detallat

| Dia       | Dades (Ex: BD)          | Tipus de còpia | Mitjà        |
|-----------|-------------------------|----------------|--------------|
| Dilluns   | Base de dades           | Incremental    | NAS          |
| Dimarts   | Base de dades           | Incremental    | NAS          |
| Dimecres  | Base de dades           | Incremental    | NAS          |
| Dijous    | Base de dades           | Incremental    | NAS          |
| Divendres | Base de dades           | Incremental    | NAS          |
| Dissabte  | Documents de projectes  | Diferencial    | NAS          |
| Diumenge  | Tot el server           | Completa       | NAS + Cloud  |

---

## 3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

- **Mitjà 1 (Local):** Quin mitjà concret (p. ex., Disc dur USB, NAS) s'utilitza.  
  El mitjà de còpia local serà un NAS instal·lat a l’empresa. Servirà per fer còpies freqüents del servidor i permet una recuperació ràpida de les dades en cas d’error.

- **Mitjà 2 (Extern):** Quin mitjà (p. ex., Cloud, LTO) i el proveïdor proposat (p. ex., Azure, Google Cloud, servei local).  
  La còpia externa es farà al núvol (cloud) utilitzant un proveïdor de confiança com Google Cloud o Microsoft Azure.

- **Ubicació Fora de Lloc:** On es guarda la còpia externa (física o lògica) i qui és el responsable de la seva gestió.  
  La còpia externa es guarda al núvol, en un lloc fora de l’empresa, perquè així les dades estan protegides encara que passi alguna cosa greu a les oficines, com un incendi o un robatori.

---

## 4) Estratègia de Recuperació (RTO/RPO)

Com es garanteix que les dades de Comptabilitat/Clients compleixen amb el requisit de RPO (4 hores) i RTO (4 hores).  
Per assegurar que no es perden més de 4 hores d’informació de comptabilitat i clients, es fan còpies de seguretat cada 4 hores. Així, si hi ha algun problema, la informació recuperada sempre serà recent. També per garantir que les dades es puguin recuperar en menys de 4 hores, la còpia més recent es guarda al NAS de l’empresa, que permet restaurar les dades ràpidament sense necessitat d’esperar descàrregues del núvol.


[Anar a l'enunciat](../Tasca01/README.md)  
[Anar a la pàgina inicial](../README.md)
