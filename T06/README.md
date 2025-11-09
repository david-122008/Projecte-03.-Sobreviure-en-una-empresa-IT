# Auditoria i Formació sobre el Servei DNS (DigiCore)
Com a membres de l’equip tècnic de la consultora EverPia, se us ha encarregat resoldre un problema de resolució de noms (DNS) que afecta l’empresa de màrqueting digital DigiCore. L’objectiu és realitzar una auditoria teòrica i pràctica per formar el seu personal i proporcionar eines de diagnosi ràpides.

## Fase Teòrica: Sessió Formativa
Cal preparar un material formatiu que expliqui:

### Jerarquia i Estructura del DNS
Estructura en arbre: Root → TLD → Domini de segon nivell.

### Procés de Resolució
Consulta iterativa i recursiva. Servidor Root, servidor autoritatiu.

### Tipus de Zones
Zona directa i zona inversa. Zona primària i zona secundària.

### Registres DNS Principals
A: relació domini → IPv4.
CNAME: alias d’un altre nom.
MX: servidors de correu.
NS: servidors de noms autoritatius.
SRV: especificació de serveis i ports.

### Conceptes Essencials
Resposta autoritativa: indica que la informació prové del servidor propietari de la zona.
TTL (Time To Live): control de la persistència en memòria cau.
SOA (Start of Authority): informació essencial del domini (origen, mail admin, número de sèrie).
Reenviadors: condicionals i incondicionals.

### Resolució Local
Resolució de noms dins xarxes sense servidor DNS dedicat. Protocol mDNS.

### Activitat Fase Teòrica
Crear un vídeo formatiu de 10-15 minuts explicant tots els conceptes anteriors.

## Fase Pràctica: Diagnosi de DNS amb CLI
S’utilitzarà un equip Zorin amb una interfície en NAT i una en adaptador pont configurat.

### Diagnosi amb dig (Linux/macOS)
1. Consulta A:
   dig xtec.cat A
   Identificar IP, TTL i servidor que respon.

2. Consulta NS:
   dig tecnocampus.cat NS
   Identificar servidors de noms autoritatius.

3. Consulta SOA:
   dig escolapia.cat SOA
   Identificar correu de l’administrador i número de sèrie.

4. Resolució inversa:
   dig -x 147.83.2.135
   Observar registre PTR.

### Diagnosi amb nslookup
Entrar en mode interactiu:
nslookup

Comandes:
set type=<TIPUS> (A, AAAA, MX, NS, SOA, etc.)
server <IP o NOM>
exit

1. Consulta no autoritativa:
   set type=A
   tecnocampus.cat
   Analitzar per què no és autoritativa.

2. Consulta autoritativa:
   server <IP_del_NS_autoritatiu>
   set type=A
   tecnocampus.cat
   Comparar amb la resposta anterior.

### Resolució Local
Comprovació del funcionament de resolució dins LAN sense servidor DNS (mDNS).

## Activitat Final
Crear un document guia.md amb:
- Captures de totes les consultes
- Resultats i explicacions
- Proves de resolució local
[solució.md](Solucio.md)
