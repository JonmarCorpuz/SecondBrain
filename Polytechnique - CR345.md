# Les serveurs

Un serveur est un système qui offre des services via un réseau informatique
* Peut être matériel ou logiciel
* Offre des services qui sont consommés par un client

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Serveurs logiciels

### Serveurs web

### Serveurs de fichiers

### Serveurs de messageries

### Serveur applicatifs

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Serveurs matériel

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/fgihoidsfgluyizjon%3Bd.PNG)

### Serveurs tour

* Aussi appelé unité centrale
* Peuvent être installé n'importe où
* Faible évolutivité
* Bonne extensibilité et mise à niveau
* Pièces difficile à réparer ou remplacer
* Consomme beaucoup d’espace

### Serveurs rack

* Possédant un format aplati
* Généralement installé dans une Baie ou rangé dans des armoires dans les
salles réservées
* Plus performant que le serveur Tour
* Évolutivité, extensibilité et mise à niveau élevées
* Pièces facile à réparer et à remplacer
* Consomme beaucoup d’énergie

### Serveurs lame

* Ne sont pas autonome
* Doivent être installé dans des châssis qui sont connectés au réseaux et glissés dans des armoires et
connecté avec d’autres serveurs lames
* Évolutivité et évolutivité extrêmement élevées
* Mise à jour limitée
* Pièces facile à réparer et à remplacer
* Faible extensibilité
* Faible consommation d’énergie

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Les systèmes d'exploitation

Le système d'exploitation est un ensemble de programmes qui
dirige l'utilisation des capacités d'un ordinateur par des
logiciels applicatifs

* Reçoit des demandes d'utilisation des ressources de
l'ordinateur de la part de logiciels applicatifs
* Accepte ou refuse les demandes d'utilisation, puis réserve les ressources
en question pour éviter que leur utilisation n'interfère avec d'autres demandes provenant d'autres logiciels

## Catégories de systèmes d’exploitations

### Systèmes d'exploitation serveurs

* Sécurité
* Performance
* Focus minimal sur des fonctionnalités (services)
* Intégration aux hyperviseurs et conteneriseurs

### Systèmes d'exploitation poste de travail

* Facilité d'utilisation
* Convivialité de l'interface graphique
* Intégration de fonctionnalités
* Support matériel

### Systèmes d'exploitation mobiles

* Facilité d'utilisation
* Support d'application

### Systèmes d'exploitation embarqués

* Minimisation de la taille
* APIs d'accès direct au matériel
* Performance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Windows Server

* Conçus pour être plus performant et plus sécuritaire
que les versions bureau
* Opère entre organisations, via réseaux informatiques
* Héberge différents serveurs logiciels (*messageries*, *bases
de données*, *etc.*)
* Support plus de mémoires que les versions
bureau
* Utilisation plus efficace de l’unité de traitement centrale
(CPU)
* Support plus accru de connexions réseau.
* Priorise le traitement des taches en arrière plan (back-end task processing)
* Plus cher que le version bureau, car il est conçu pour les entreprises et le monde des affaires en général
* Conçu pour des taches professionnelles, donc toutes les fonctionnalités de
bureau ne sont pas nécessaires (ex: *navigateur web*, *service
de courriel*, *suite office*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Linux Server

* Généralement installé dans des serveurs Rack ou Tour.
* Plus de longévité, stabilité, performance, sécurité
* Utilisation du code correcting (ECC) RAM
* Pas besoin d’interface graphique
* Pas besoin de clavier, souris et autres périphériques
(headless)
* Permet d'installer certain serveurs applicatifs (ex: *Serveur web
Apache*, *Serveur d’impression*, *Serveur de messagerie*, *Serveur de sécurité*, *etc.*)
* Généralement accédé et géré a travers une connexion SSH distante
* Utilise le même noyau que la version bureau
* On peut installer l’interface graphique sur une version serveur

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Système infonuagique

L’infonuagique est un modèle permettant un accès réseau omniprésent, pratique et à la demande à un basin partagé de ressources informatiques configurables (ex.: *réseaux*, *serveurs*, *stockage*, *applications*, *services*, *etc.*)

* Ces ressources peuvent être rapidement provisionnés et libérés avec un effort minimal de gestion et d’interaction avec le fournisseur de services
* Ce modèle est composé de cinq caractéristiques essentielles, trois modèles de services et quatre modèles de déploiement ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/cjvbasfcdshf%3Blasdasj.PNG)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Architecture Infonuagique

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ccvugadshfvbladikugfaosdfadf.PNG)

### Type 1: Bare metal

L'hyperviseur est hébergé directement sur le matériel

### Type 2: Hosted

L'hyperviseur est hébergé sur le système d’exploitation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Modèles infonuagiques

* Definisse quelle partie est gérée par le fournisseur infonuagique et quelle partie est gérée par le client

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/dsgdbasuvhfasbdfaklfna.PNG)

### SaaS

### PaaS

### IaaS

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Modèles de déploiement infonuagique

### Privé

* Ressources partagées en privé entre les membres d’une organisation
* Peut être détenu, géré et exploité par une organisation ou une tierce partie
* Peut exister l’intérieur des locaux de l’organisation ou a l’extérieur

### Communautaire

* Dédié à une communauté spécifique de consommateurs d'organisations
* Ces consommateurs partagent des préoccupations (ex.: la mission, politique, etc.).
* Peut être détenu, géré et exploité par une ou plusieurs des organisations
* Peut exister sur ou hors des locaux
* Mise à disposition pour une utilisation ouverte par le grand public

### Publique

* Prévue pour une utilisation ouverte au grand public
* Peut être détenu, géré et exploité par une entreprise, une université, une
organisation gouvernementale
* Peut être déployer dans les locaux du fournisseur infonuagique

### Hybride

* Composé d'au moins deux entités infonuagiques distinctes (privées,
communautaires ou publiques)
* Demeurent uniques, mais liées entre elles par une technologie
standardisée ou propriétaire

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Virtulisation légère: Conteneurs

* Déploiement rapide de services
* Pas besoin de système d’exploitation pour le client
  ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/isldyhgfsidgygisdghfgjh%3B.PNG)
* Peut être intégré avec une virtualisation standard
  ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/daskjhgvghjfdghjsdfghjlsdf.PNG)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Platformes client

## Types de platformes client

### Poste de travail (Workstation)

* Facilité d'utilisation
* Convivialité de l'interface graphique
* Intégration de fonctionnalités
* Support matériel

### Mobile

* Facilité d'utilisation
* Support d'application

### Embarqué

* Minimisation de la taille
* APIs d'accès direct au matériel
* Performance

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Structure du système de fichiers

### Structure du système de fichiers Linux

* /: Racine du système
* /etc: Fichiers de configuration
* /dev: Fichier d'accès au matériel
* /proc: Fichier d'accès au noyau
* /bin: fichiers binaires exécutables systèmes
* /sbin: fichiers binaires statiques exécutables système
* /lib: bibliothèque systèmes
* /usr/bin: fichiers binaires exécutables utilisateur
* /usr/sbin: fichiers binaires statiques exécutables utilisateur
* /usr/lib: Bibliothèques utilisateur
* /var: Fichiers de support
* /home: Répertoires personnels des utilisateurs.

### Structure du système de fichiers Windows

* c:\: Racine du système
* c:\Windows: Fichiers du système d'exploitation
* c:\Program Files: Fichiers des applications
  * Il contient toutes les applications dans un système 32-bits
  * Il contient les applications 64-bits dans un système 64-bits
* c:\Program Files (x86): Fichiers des applications
  * Il contient les applications 32-bits dans un system 64-bits
 
### Structure du système de fichiers MacOS

* /: Racine du système
* /etc: Fichiers de configuration
* /dev: Fichier d'accès au matériel
* /Applications: Répertoire d'installation des applications
* /bin: fichiers binaires exécutables systèmes
* /sbin: fichiers binaires statiques exécutables système
* /Library: bibliothèque systèmes
* /usr/bin: fichiers binaires exécutables utilisateur
* /usr/sbin: fichiers binaires statiques exécutables utilisateur
 
## Bases de registres Windows

* Stocke l'information de configuration du SE et les applications.
* Stocke des couples clé/valeur, où la clé est représentée dans une
arborescence

### HKEY_CLASSES_ROOT

Description des classes de fichiers

### HKEY_LOCAL_MACHINE

Configuration globale de la machine

### HKEY_CURRENT_USER

Configuration propre à l'utilisateur courant

### HKEY_USERS

Configuration des autres utilisateurs

### HKEY_CURRENT_CONFIG

Configuration globale liée ni à la machine, ni à un utilisateur

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DNS

## Hiérarchie de domaines

### Sommet

### Domaine

### Sous-domaine

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Types de domaines

### Domaine de Premier Niveau (TLD)

Les domaines qui se trouvent immédiatement sous la racine

### Domaines Génériques (gTLD)

Les domaines dont les noms ne correspondent pas à une extension de pays (ex: *.org*, *.com*, *etc.*)

### Domaine de Premier Niveau National (ccTLD)

Des domaines dont les noms correspondent à des codes de pays (ex: *.ca*, *.us*, *.fr*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Résolution de domaine

* La résolution de domaines est faite en parcourant la hiérarchie depuis le sommet, en passant par les délégations successives
* Les noms de domaines sont parcouru de droite à gauche
* La résolution repose sur une délégation correcte établis dans le domaine de niveau supérieur

### Résolution itérative

* Le host consulte un ou plusieurs serveurs (appelés serveurs récursifs)
* Ces derniers parcourent la hiérarchie DNS en délégant la requête a d’autres serveurs, afin de compléter la résolution
* Ces serveurs récursifs sont souvent offert par le fournisseur d’internet (ISP), mais il y’a aussi des serveurs récursif publiques (ex: *Google Public DNS: 8.8.8.8 et 8.8.4.4*, *OpenNIC: 172.98.193.42*)
* Dans un nom de domaine, la partie la plus générale est à droite (ex: *.org dans fr.wikipedia.org*) donc la résolution est faite de droite à gauche

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ertgerththrtrheatrrywraehg.PNG)

### Résolution inverse

* L'ordre de résolution est inversé et le résultat obtenue est concaténé au pseudo domaine in-addr.arpa (Exemple: *Pour trouver le nom de domaine de l'adresse IP 91.198.174.2, on résout 2.174.198.91.in-addr.arpa*)
* Dans une adresse IPv6, un domaine spécial est utilisé: ip6.arpa (Exemple: *L’adresse Ipv6: 2001:db8::567:89ab est convertie en: b.a.9.8.7.6.5.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.0.8.b.d.0.1.0.0.2.ip6.arpa*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# DHCP

Dynamic Host Configuration Protocol est un protocole réseau, dont le rôle est d’attribuer des adresses IP aux hôtes de façon automatique

* Principalement, il attribue des adresses IP et les masques réseau
* D’autres informations peuvent être attribuées par le DHCP (Ex: *Adresse de la passerelle par défaut*, *Serveurs de noms DNS*, *Serveurs de noms BNNS*, *etc.*)

## Résolution d’adresse

1. Le client envoie un message “DISCOVER” pour contacter les serveurs DHCP disponibles sur le réseau
  * UDP boardcast sur le port 67
  * S’il y’a un DHCP-relais, cette requête est bloquée au niveau du routeur, et une adresse IP est retournée par ce dernier

2. Le serveur répond avec un message “OFFER” qui contient toutes les paramètres réseau.
  * UDP broadcat sur le port 68
  * Tous autres serveurs DHCP sont informés

3. Le client répond avec un message “REQUEST” pour informer le serveur DCHP de l’adresse IP sélectionnée.
  * Le message est reçu par tous les serveurs DHCP dans le réseau, ainsi tous savent quelle adresse a été sélectionnée

4. Le serveur répond avec une message “ACK” (Acknowledge)
  * Les paramètres réseau seront envoyés au client.
