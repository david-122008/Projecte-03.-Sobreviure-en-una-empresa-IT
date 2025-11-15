# LDAP — Instal·lació i Configuració

A continuació es mostra el procés complet per instal·lar i configurar un servidor LDAP, la gestió amb LAM i la configuració d’un client Linux.

---

## 1. Configuració inicial del servidor

Primer configurem el nom de la màquina servidor, assignant:

- Hostname: `server`
- Nom complet: `server.innovatech07.test`

(Captura 1)

Comprovem que s’ha aplicat correctament amb:

(Captura 2)

---

## 2. Configuració de xarxa

Configurem els adaptadors de xarxa:

- El primer en mode **NAT**
- El segon en mode **Només amfitrió**

(Captura 3)  
(Captura 4)

Habilitem els adaptadors editant l’arxiu de xarxa.

(Captura 5)

Comprovem les adreces IP.

(Captura 6)

---

## 3. Instal·lació del servei LDAP

Instal·lem el servei LDAP.

(Captura 7)

Comprovem l’estat del servei.

(Captura 8)

Indiquem que **no volem ometre la instal·lació**.

(Captura 9)

Afegim el nom del domini.

(Captura 10)

Afegim la contrasenya.

(Captura 11)

Seleccionem que s’esborri el disc.

(Captura 12)

Movem la informació del directori.

(Captura 13)

Comprovem que s’ha modificat el directori.

(Captura 14)

---

## 4. Creació de les OUs

Entrem a l’arxiu OU.

(Captura 15)

Modifiquem i creem 2 OUs.

(Captura 16)

Afegim l’arxiu al directori.

(Captura 17)

Comprovem totes les OUs creades.

(Captura 18)

---

## 5. Instal·lació del gestor d’usuaris LAM

Instal·lem LAM.

(Captura 19)

Accedim a LAM amb la IP del servidor:

`http://192.168.56.102/lam`

(Captura 20)

Entrem a la configuració de LAM.

(Captura 21)

Editem el perfil del servidor.

(Captura 22)

Configurem:

- Contrasenya: `lam`
- Admin DN: `cn=admin,dc=innovatech07,dc=test`
- Sufix de l’arbre: `dc=innovatech07,dc=test`

(Captura 23)

A “Account Types” configurem els DN dels usuaris i grups.

(Captura 24)

---

## 6. Creació d’usuaris

Creem un usuari nou.

(Captura 25)  
(Captura 26)

Marquem crear un grup amb el mateix nom.

(Captura 27)

Repetim el procés per al segon usuari.

(Captura 28)

---

## 7. Creació de grups

Creem els grups **tech** i **manager**.

(Captura 29)  
(Captura 30)

Assignem a cada usuari el seu grup secundari.

(Captura 31)

---

## 8. Configuració del client LDAP

Creem una nova màquina:

- Primera interfície: **NAT**
- Segona interfície: **Només amfitrió**

(Captura 32)  
(Captura 33)

Editem `/etc/hosts` i afegim la IP i el nom del servidor.

(Captura 34)

Instal·lem els mòduls necessaris per a l’autenticació.

(Captura 35)

Configurem LDAP:

- Identificador del servidor
- Base de cerca
- Versió LDAP
- Root admin
- Mode sense login
- Contrasenya LDAP

(Captura 36)  
(Captura 37)  
(Captura 38)  
(Captura 39)

Comprovem la connectivitat.

(Captura 40)

---

## 9. Fitxers del sistema

Modifiquem `nsswitch.conf`.

(Captura 41)

Modifiquem `common-password` eliminant `use_authtok`.

(Captura 42)

Modifiquem `common-session` afegint la línia PAM.

(Captura 43)

Reiniciem i comprovem que els usuaris són visibles amb:

(Captura 44)

---

## 10. Inici de sessió gràfic

Modifiquem `gdm-launch-environment`.

(Captura 45)  
(Captura 46)

Reiniciem i iniciem sessió amb un usuari LDAP.

(Captura 47)

Comprovem que té carpeta personal.

(Captura 48)

---

# 11. Captures finals del procés (49–60)

(Captura 49)  
(Captura 50)  
(Captura 51)  
(Captura 52)  
(Captura 53)  
(Captura 54)  
(Captura 55)  
(Captura 56)  
(Captura 57)  
(Captura 58)  
(Captura 59)  

---

# Fi del document
