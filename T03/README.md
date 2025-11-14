# T03: Gestió flexible de discos (LVM i Espais d’emmagatzematge)

## Breu descripció
Un cop superada la fase de formació, ja esteu preparats per afrontar el repte dels nostres clients. Tenim un nou i important client: el bufet d’advocats **Garriga i Associats**, un dels més prestigiosos de la ciutat. Gestiona una gran quantitat d'informació legal sensible, per la qual cosa la integritat, la disponibilitat (alta redundància) i la facilitat de gestió del seu emmagatzematge són d'importància crítica.

La direcció ha expressat la necessitat urgent de renovar els seus sistemes de servidors per garantir que la informació estigui protegida contra fallades de disc i que l'espai pugui ser ampliat sense interrupcions. Com a tècnics d’Everpia, teniu l'encàrrec de dissenyar i documentar dues solucions d'emmagatzematge (Linux i Windows) que compleixin els principis d'alta disponibilitat, redundància i escalabilitat. Com que és una prova de concepte, es farà amb màquines virtuals.

---

# 1. Part Linux: LVM amb Zorin OS

S'utilitzarà Zorin OS (o similar) per demostrar l'ús del gestor de volums lògics (LVM).

## Requisits de la Implementació i Demostració

### Configuració inicial
- Crear un grup de volums (VG) i un volum lògic (LV) utilitzant inicialment dos discs de 10 GB.
- Formatar i muntar el volum automàticament amb `/etc/fstab`.

### Alta Disponibilitat
- Implementar la configuració d’un mirall (**lvm_mirror**) que protegeixi la informació davant fallades.

### Instantànies (snapshots)
1. Afegir dos discs de 10 GB al grup de volums.
2. Crear un volum `lvm_dades` amb el primer disc afegit, formatar-lo i muntar-lo.
3. Afegir arxius al volum (per exemple, imatges).
4. Utilitzar el segon disc per crear un snapshot (`lv_snapshot`).
5. Documentar com restaurar el snapshot si les dades originals es corrompen.

### Escalabilitat
- Ampliar el volum `lv_dades` utilitzant l'espai lliure del grup de volums.

---

# 2. Part Windows: Espais d'Emmagatzematge (Storage Spaces)

S’utilitzarà Windows 11 per demostrar les configuracions possibles mitjançant Storage Spaces.

## Requisits de la Implementació i Demostració

### Configuració inicial
- Crear un *Storage Pool* inicial amb tres discs de 10 GB.

### Estudi de configuracions
- **Mirroring:** Crear un espai amb dos discs i comprovar l’alta disponibilitat.
- **Parity:** Crear un espai amb tres discs i explicar l’eficiència davant el mirall.
- **Triple Mirroring:** Afegir els discs necessaris per crear aquest tipus de resiliència.

### Gestió
- Mostrar des de la consola de Windows:
  - L’estat dels discos
  - L’estat del *storage pool*
  - Facilitat de manteniment i substitució

---

# 3. Com treballareu i què lliurareu?

- El treball és en grup.
- Es dividirà en dos equips:
  - Equip Linux → implementació amb LVM
  - Equip Windows → implementació amb Storage Spaces
- Cada membre prepara el seu guió de comandes i documentació.
- Cada parella realitza la seva demostració i genera documentació.
- El grup revisa els documents finals.
- Cada membre puja la documentació al seu repositori GitHub dins la carpeta `tasca03/`.

La carpeta **tasca03** ha d’incloure:
- Un arxiu `README.md` amb la descripció de la tasca i enllaços als dos documents.
- Dos documents de la pràctica:
  - `linux_lvm.md`
  - `windows_storage_spaces.md`

La nota és conjunta. La comunicació i organització interna és essencial.

Posteriorment s’haurà de preparar una presentació amb les conclusions.

---

# Material de classe (Moodle)
- LVM Linux
- Espais d’emmagatzematge (Windows)
