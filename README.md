# MiniLab VLAN – MSc Cyber Test

## Objectif

Mettre en place une architecture réseau segmentée en VLAN avec :
- Interconnexion inter-VLAN
- DHCP centralisé
- Accès Internet
- Isolation logique des services

---

## Architecture

Le routeur Cisco 1941 joue le rôle de :
- Passerelle Internet
- Serveur DHCP
- Gestionnaire VLAN (Router-on-a-stick)

Chaque bureau contient :
- 1 switch
- 1 point d'accès WiFi
- 1 PC portable
- 2 PC fixes
- 1 téléphone IP

---

## Configuration des VLAN

VLAN 1  → VoIP  
VLAN 10 → WiFi  
VLAN 20 → PC fixes  
VLAN 30 → Administration  

---

## Configuration Switch (exemple)

```bash
enable
conf t

vlan 10
name WIFI
vlan 20
name PC
vlan 30
name ADMIN

interface range fa0/6-7
switchport mode access
switchport access vlan 20

interface fa0/1
switchport mode trunk
# test-d-entr-master-
