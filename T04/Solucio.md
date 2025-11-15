# LDAP — Instal·lació i Configuració

A continuació es mostra el procés complet per instal·lar i configurar un servidor LDAP, la gestió amb LAM i la configuració d’un client Linux.

---

## 1. Configuració inicial del servidor

Primer configurem el nom de la màquina servidor, assignant:

- Hostname: `server`
- Nom complet: `server.innovatech07.test`

![Imatge 01](IMA/ING1.png)

![Imatge 01](IMA/ING2.png)

Després comprovem que el canvi s’ha aplicat correctament amb la comanda `hostname`.

![Imatge 01](IMA/ING3.png)

![Imatge 01](IMA/ING4.png)

---

## 2. Configuració de xarxa

Configurem els adaptadors de xarxa:

- El primer en mode **NAT**
- El segon en mode **Només amfitrió**

![Imatge 01](IMA/ING5.png)

![Imatge 01](IMA/ING6.png)

Habilitem els adaptadors editant l’arxiu de xarxa.

![Imatge 01](IMA/ING7.png)

Comprovem les adreces IP.

![Imatge 01](IMA/ING8.png)

---

## 3. Instal·lació del servei LDAP

Instal·lem el servei LDAP.

![Imatge 01](IMA/ING9.png)

Comprovem l’estat del servei.

![Imatge 01](IMA/ING10.png)

Despres configurem la base de dades del paquet

![Imatge 01](IMA/ING60.png)


Seleccionem que **no volem ometre la configuració**.

![Imatge 01](IMA/ING11.png)

Introduïm:

- El nom del domini
- La contrasenya de l’administrador LDAP


![Imatge 01](IMA/ING12.png)
![Imatge 01](IMA/ING13.png)

Indiquem que s’esborri el disc i es mogui la informació del directori.

![Imatge 01](IMA/ING14.png)
![Imatge 01](IMA/ING15.png)

Comprovem que el directori ha estat modificat.

![Imatge 01](IMA/ING16.png)

---

## 4. Creació de les Unitats Organitzatives (OU)

Entrem a l’arxiu OU.

![Imatge 01](IMA/ING17.png)

El modifiquem i creem dues OUs.

![Imatge 01](IMA/ING18.png)

Afegim l’arxiu al directori amb la comanda corresponent.

![Imatge 01](IMA/ING19.png)

Comprovem totes les OUs creades.

![Imatge 01](IMA/ING20.png)

---

## 5. Instal·lació i configuració de LAM (LDAP Account Manager)

Instal·lem el gestor d’usuaris LDAP.

![Imatge 01](IMA/ING21.png)

Accedim a LAM des del navegador utilitzant la IP del servidor:

`http://192.168.56.102/lam`

![Imatge 01](IMA/ING22.png)

Entrem a la configuració de LAM.

![Imatge 01](IMA/ING23.png)

Editem el perfil del servidor.

![Imatge 01](IMA/ING24.png)

Ajustem els paràmetres del servidor LDAP:

- Contrasenya: `lam`

![Imatge 01](IMA/ING25.png)

- Usuari admin: `cn=admin,dc=innovatech07,dc=test`

![Imatge 01](IMA/ING26.png)

- Sufix de l’arbre: `dc=innovatech07,dc=test`

![Imatge 01](IMA/ING27.png)

A “Account Types” definim els DN per usuaris i grups. Els tipus d’objectes ja venen per defecte.

![Imatge 01](IMA/ING28.png)

---

## 6. Creació d’usuaris

Per crear un usuari fem clic a “Nou usuari”:

![Imatge 01](IMA/ING29.png)

![Imatge 01](IMA/ING30.png)

Marquem l’opció per crear un grup amb el mateix nom.

![Imatge 01](IMA/ING31.png)

Repetim el procés per al segon usuari.

![Imatge 01](IMA/ING32.png)

---

## 7. Creació de grups

Creem dos grups nous: **tech** i **manager**.

![Imatge 01](IMA/ING34.png)

![Imatge 01](IMA/ING35.png)

Assignem a cada usuari el seu grup secundari corresponent.

![Imatge 01](IMA/ING35.png)

---

## 8. Configuració del client LDAP

Creem una nova màquina virtual amb:

- Primera interfície: **NAT**
- Segona interfície: **Només amfitrió**

![Imatge 01](IMA/ING36.png)

![Imatge 01](IMA/ING37.png)

Editem `/etc/hosts` i afegim la IP i el nom del servidor.

![Imatge 01](IMA/ING39.png)

Instal·lem els mòduls necessaris per a l'autenticació LDAP.

![Imatge 01](IMA/ING34.png)

A la configuració afegim:

- Identificador del servidor LDAP

![Imatge 01](IMA/ING41.png)

- Base de cerca

![Imatge 01](IMA/ING42.png)

- Versió del protocol

![Imatge 01](IMA/ING43.png)

- Root com administrador

![Imatge 01](IMA/ING44.png)

- Que no requereixi login

![Imatge 01](IMA/ING45.png)

- Contrasenya LDAP

![Imatge 01](IMA/ING46.png)

Comprovem la connectivitat amb el servidor.

![Imatge 01](IMA/ING47.png)

![Imatge 01](IMA/ING48.png)

![Imatge 01](IMA/ING49.png)

---

## 9. Modificació dels fitxers del sistema

Modifiquem `nsswitch.conf` perquè utilitzi LDAP per usuaris i grups.

![Imatge 01](IMA/ING50.png)

![Imatge 01](IMA/ING51.png)

Modifiquem `common-password` i eliminem la línia `use_authtok`.

![Imatge 01](IMA/ING52.png)

Afegim la línia PAM corresponent a `common-session`.

![Imatge 01](IMA/ING53.png)

![Imatge 01](IMA/ING54.png)

Reiniciem el sistema i comprovem que els usuaris LDAP són visibles amb la comanda:

![Imatge 01](IMA/ING55.png)

---

## 10. Activació de l'inici de sessió gràfic

Entrem a l’arxiu `gdm-launch-environment` per permetre l’inici de sessió gràfica.

![Imatge 01](IMA/ING56.png)

![Imatge 01](IMA/ING57.png)

Reiniciem la màquina i iniciem sessió amb un usuari LDAP.

![Imatge 01](IMA/ING58.png)

Comprovem que s’ha creat la seva carpeta personal.

![Imatge 01](IMA/ING59.png)

---

# Fi del document
