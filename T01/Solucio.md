# Gestor de contrasenyes  
**Data:** 21/10/2025  
**Autor:** David Català  

---

## 📑 Índex
1. [Justificació](#1-justificació)  
2. [Comparativa Tècnica](#2-comparativa-tècnica)  
3. [Avantatges i Inconvenients](#3-avantatges-i-inconvenients)  
4. [Recomanació](#4-recomanació)  

---

## 1. Justificació

L’equip de direcció tècnica ha decidit triar l'opció d'utilitzar un **gestor de contrasenyes** per evitar incidents derivats de l’ús de contrasenyes febles o reutilitzades.  
Els usuaris acostumen a crear contrasenyes fàcils de descobrir o utilitzar la mateixa per a diversos serveis, cosa que suposa un risc crític per a la seguretat corporativa.

Les contrasenyes febles —com noms propis, dates o combinacions curtes— poden ser vulnerades amb tècniques de força bruta o enginyeria social.  
A més, la reutilització de contrasenyes pot provocar que un atacant accedeixi a altres plataformes corporatives si una d’elles es veu compromesa (*credential stuffing*).

### Principals riscos:
- Accés no autoritzat a informació corporativa i dades de clients.  
- Atacs interns dins l’estructura de l’empresa.  
- Pèrdua o alteració de dades.  
- Dany econòmic i sancions per incompliment normatiu.  

### Mesures recomanades:
- Utilitzar **contrasenyes fortes, úniques i complexes** per a cada compte.  
- Fer ús d’un **gestor de contrasenyes corporatiu**.  
- Activar l’**autenticació multifactor (MFA)**.

---

## 2. Comparativa Tècnica

| **Criteri** | **Bitwarden (Online / Núvol)** | **KeePassX / KeePassXC (Offline / Escriptori)** |
|--------------|--------------------------------|-----------------------------------------------|
| **Model** | Solució al núvol amb opció *self-hosted*. Sincronització automàtica entre dispositius. | Aplicació local amb fitxer xifrat (.kdbx). Sense sincronització integrada. |
| **Xifratge / Seguretat** | Xifratge *end-to-end* (AES-256 + PBKDF2/Argon2id). El proveïdor no pot veure les dades. | Xifratge local AES-256 del fitxer .kdbx. Seguretat dependent de la clau mestra. |
| **Sincronització** | Automàtica via servidor (núvol o instància pròpia). | Manual, mitjançant serveis externs (Nextcloud, Dropbox, etc.). |
| **Accés multi-dispositiu** | Aplicacions per escriptori, web, mòbil i extensions de navegador. | Portable entre dispositius, però sincronització manual. |
| **Control de dades** | Dades xifrades al núvol o servidor propi. | Control total local sense dependència externa. |
| **Model econòmic** | *Freemium*: pla gratuït + opcions empresarials. | Gratuït i *open-source*. Sense llicència. |
| **Gestió empresarial** | Permet compartició i administració centralitzada. | Sense gestió central; compartició mitjançant fitxers. |
| **Ideal per a...** | Empreses que necessiten sincronització i control centralitzat. | Organitzacions que busquen control local i simplicitat tècnica. |

---

## 3. Avantatges i Inconvenients

| **Aspecte** | **Bitwarden (Online / Núvol)** | **KeePassX / KeePassXC (Offline / Escriptori)** |
|--------------|--------------------------------|-----------------------------------------------|
| **Seguretat** | **Avantatges:**<br>• Xifratge end-to-end.<br>• Auditories externes.<br>• Opció *self-hosted*.<br>**Inconvenients:**<br>• Dependència del núvol o servidor propi.<br>• Superfície d’atac més gran. | **Avantatges:**<br>• Emmagatzematge local.<br>• Xifratge fort (AES-256 / Argon2).<br>• Control total de dades.<br>**Inconvenients:**<br>• Si es perd el fitxer o la clau, es perd tot.<br>• Sense MFA ni gestió central. |
| **Usabilitat** | **Avantatges:**<br>• Sincronització automàtica.<br>• Accessible des de qualsevol dispositiu.<br>**Inconvenients:**<br>• Requereix Internet per sincronitzar.<br>• Algunes funcions són de pagament. | **Avantatges:**<br>• Funcionament offline.<br>• Portable i multiplataforma.<br>**Inconvenients:**<br>• Sincronització manual.<br>• Menys pràctic per a diversos dispositius. |
| **Continuïtat del negoci** | **Avantatges:**<br>• Alta disponibilitat i còpies al núvol.<br>• Recuperació senzilla.<br>**Inconvenients:**<br>• Dependència del servei o servidor *self-hosted*. | **Avantatges:**<br>• Independència total de proveïdors.<br>• Continuïtat garantida amb còpies internes.<br>**Inconvenients:**<br>• Gestió pròpia de còpies i actualitzacions.<br>• Sense suport tècnic oficial. |

---

## 4. Recomanació

L’equip de direcció tècnica recomana **Bitwarden** com a gestor de contrasenyes corporatiu.

**Justificació:**  
Bitwarden ofereix **alt nivell de seguretat** amb xifratge *end-to-end*, **sincronització automàtica entre dispositius** i possibilitat d’instal·lació *self-hosted*.  
Aquestes característiques el fan més adequat per al **personal tècnic**, ja que combina seguretat, eficiència i facilitat de gestió centralitzada.

---

**Conclusió:**  
Bitwarden és la solució més equilibrada per garantir **seguretat, usabilitat i continuïtat del negoci**, mantenint alhora la possibilitat de control intern sobre la infraestructura.

