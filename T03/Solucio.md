# DISCS

## 1. Creació de la màquina
El primer de tot serà crear la màquina amb els paràmetres inicials.

[Imatge 01](IMG/IMA1.png)

## 2. Configuració de l’espai de la màquina
Després entrarem a la configuració d'espai de la màquina, on crearem les tres particions de disc amb **10 GB d’espai** i les afegirem.

## 3. Muntatge dels discos
Després entrarem a la màquina virtual i muntarem els 3 discos dins d'ella, i crearem un grup.

## 4. Comprovació
Utilitzant aquesta comanda podrem comprovar l’estat dels discos.

## 5. Creació del grup de volums
Crearem un **grup de volums** anomenat `lv01`.

## 6. Format del VG
Després formatem el VG per un sistema d'arxius.

## 7. Muntatge permanent
Després entrarem en aquest arxiu i el modificarem perquè estigui muntat permanentment.

## 8. Comprovació addicional
Aquesta comanda és simplement de comprovació.

## 9. Alta Disponibilitat
Implementarem la configuració d’un **mirall (lvm_mirror)** que protegeixi la informació davant la fallada d'un disc.

## 10. Creació del volum “dades”
Crearem un altre volum anomenat **dades**.

## 11. Muntatge
Muntem la còpia.

## 12. Creació d’un arxiu
Ara crearem un arxiu per posar-lo dins de *dades*.

## 13. Modificació de l’arxiu
I tornem a modificar l’arxiu.

## 14. Creació del LV “snapshot”
En aquesta captura crearem un altre LV que es dirà **snapshot**.

## 15. Replicació d’estructura
Crearem un altre cop l’estructura d’abans.

## 16. Modificació de l’arxiu
Modificarem l'arxiu un altre cop.

## 17. Creació d’un arxiu a snapshot
Crearem un altre arxiu per posar-lo a *snapshot*.

## 18. Creació del LV “copia”
Crearem un altre LV que es dirà **copia**, que contindrà el mateix que *snapshot*.

## 19. Escalabilitat
Demonstrarem el procés d'ampliació utilitzant l'espai lliure del grup de volums per **ampliar el volum dades**.
