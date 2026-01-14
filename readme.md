# Introduction — Réseaux 🌐

**TCP/IP** = **Transmission Control Protocol / Internet Protocol**.  
Chaque machine sur un réseau IP possède une adresse unique (adresse IP) permettant le routage des paquets.

![Modèle TCP/IP](images/tcp_ip_model.svg)

## Modèle TCP/IP (couches) 🔧

1. **Couche Application**  
   - Protocoles : **HTTP**, **FTP**, **DNS**, **SMTP**, etc.  
   - Fournit des services réseau aux applications utilisateur.

2. **Couche Transport**  
   - Protocoles : **TCP** (fiable, connexion) et **UDP** (non‑fiable, sans connexion).  
   - Gère le multiplexage, la segmentation et le contrôle de flux.

> **Astuce:** TCP assure la livraison et l'ordre des segments, UDP est plus léger et utilisé pour le streaming, DNS, etc.

3. **Couche Internet**  
   - Protocole principal : **IP** (adressage, routage).  
   - Responsabilité : acheminer des paquets entre réseaux.

4. **Couche Accès Réseau (Link)**  
   - Technologies : **Ethernet**, **Wi‑Fi**, **PPP**.  
   - Gère l'accès physique, adresses MAC, ARP.

---

## Points clés 💡
- **IP** s'occupe du routage et de l'adressage; **TCP/UDP** gèrent la livraison entre hôtes.  
- Le modèle TCP/IP est la base d'Internet moderne.

## Encapsulation 🔁

L'encapsulation est le processus par lequel les données d'une application sont entourées d'en-têtes (et parfois de trailers) à chaque couche du modèle TCP/IP avant d'être envoyées sur le réseau.

1. **Application** → Données Brute (payload)
2. **Transport** → Ajout d'un *header* (ex. TCP : ports source/destination, num. de séquence) → **Segment**
3. **Internet** → Ajout du *header* IP (adresses source/destination, TTL) → **Paquet (Packet / Datagram)**
4. **Accès Réseau (Link)** → Ajout du *header*/trailer (adresses MAC, CRC) → **Trame (Frame)**
5. **Physique** → Bits transmis sur le support

> Exemple : "GET /index.html" → segment TCP (src port 12345 → dst port 80) → paquet IP (src 192.0.2.1 → dst 203.0.113.5) → trame Ethernet (MACs) → bits sur le câble.

**Décapsulation** : au récepteur, chaque couche enlève son en-tête dans l'ordre inverse pour restituer les données d'origine.

**Remarques :**
- Les unités de données : **segment** (transport), **paquet/datagram** (internet), **trame** (link).
- Si un paquet dépasse la MTU d'un lien, il peut être fragmenté au niveau IP.
## Adresses MAC 📍

Une adresse MAC (Media Access Control) est un identifiant unique au niveau de la couche liaison (couche 2).

**Composition :**
- **Longueur** : 48 bits (6 octets)
- **Format** : XX:XX:XX:XX:XX:XX (notation hexadécimale)
- **Exemple** : `00:1A:2B:3C:4D:5E`
- **Parties** :
    - **3 premiers octets** : OUI (Organizationally Unique Identifier) — identifie le fabricant
    - **3 derniers octets** : numéro de série unique de l'appareil

---

## Adresses IPv4 🔢

**Composition :**
- **Longueur** : 32 bits (4 octets)
- **Format** : notation décimale pointée (XXX.XXX.XXX.XXX)
- **Exemple** : `192.168.1.1`
- **Plage** : 0.0.0.0 à 255.255.255.255

---

## Adresses IPv6 📶

**Composition :**
- **Longueur** : 128 bits (16 octets)
- **Format** : notation hexadécimale (XXXX:XXXX:XXXX:XXXX:XXXX:XXXX:XXXX:XXXX)
- **Exemple** : `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- **Simplification** : `2001:db8:85a3::8a2e:370:7334` (zéros omis)
- **Capacité** : ~340 undécillions d'adresses

