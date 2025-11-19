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

**La còpia més recent s'hauria de guardar:**

- En el núvol: per accés fàcil des de qualsevol lloc.
- En un disc dur extern: per tenir una còpia física al teu abast.

Això segueix la regla 3-2-1, ja que recomana tenir 3 còpies de les dades, en 2 mitjans diferents, i 1 fora de l’empresa per garantir la seguretat.

---



[Anar a l'enunciat](../Tasca01/README.md)  
[Anar a la pàgina inicial](../README.md)
