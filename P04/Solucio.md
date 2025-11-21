# Configuració DNS - Fitxers BIND

## Arxiu db.192.168.4.7 (Zona inversa)

; BIND reverse data file for local loopback interface  
$TTL 604800  
@ IN SOA ns1.digicore-07.test. server.digicore-07.test. (  
        1       ; Serial  
   604800       ; Refresh  
    86400       ; Retry  
  2419200       ; Expire  
   604800 )     ; Negative Cache TTL  

@ IN NS ns1.digicore-07.test.  
26  IN PTR server.digicore-07.test.  
126 IN PTR dbserver.digicore-07.test.  

---

## Arxiu db.digicore-07.test (Zona directa)

; BIND data file for local loopback interface  
$TTL 604800  
@ IN SOA ns1.digicore-07.test. server.digicore-07.test (  
        2       ; Serial  
   604800       ; Refresh  
    86400       ; Retry  
  2419200       ; Expire  
   604800 )     ; Negative Cache TTL  

IN NS ns1.digicore-07.test.  

ns1      IN A 192.168.4.7  
server   IN A 192.168.4.107  
dbserver IN A 192.168.4.138  

---

## Arxiu named.conf.local

zone "digicore-07.test" {  
    type master;  
    file "/etc/bind/zones/db.digicore-07.test";  
    allow-transfer {192.168.4.7;};  
};  

zone "4.168.192.in-addr.arpa" {  
    type master;  
    file "/etc/bind/zones/db.192.168.4";  
    allow-transfer {192.168.4.7;};  
};  

zone "waytoit.test" {  
    type slave;  
    file "db.waytoit";  
    masters {172.0.2.49;};  
};  

zone "digicore-07.test" {  
    type slave;  
    file "db.digicore-07";  
    masters {192.168.4.7;};  
};  

zone "facebook.com" {  
    type forward;  
    forwarders {192.134.30.12;};  
};  

---

## Arxiu named.conf

acl "trusted" {  
    192.168.4.0/24;  
};  

options {  
    directory "/var/cache/bind";  

    recursion yes;  
    allow-recursion { trusted; };  
    listen-on { 192.168.4.7; };  
    allow-transfer { none; };  

    forwarders {  
        172.0.2.2;  
        8.8.8.8;  
    };  

    dnssec-validation auto;  
    listen-on-v6 { any; };  
};
