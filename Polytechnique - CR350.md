# Réseau et sécurité

L'architecture de sécurité désigne l'ensemble des composants technologiques et des processus necessaires pour sécuriser l'environment informatique d'une entreprise en fonction de ses besoins d'affaires, des risques de sécurité qu'elle encourt et de ses obligations légales

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Les besoins:
* Éviter une protection de l'environment informatique non adequate
* Éviter une protection par tatonnement
* Assurer le respect des obligations de conformité
  * Protection des renseignements personnels: *Loi 25 du Québec*, *Personal Information Protection and Electronic Documents Act (PIPEDA)*, *etc*
  * Protection des données de cartes de credit: *PCI DSS*, *etc.*
* Planifier et anticiper l'évolution
* Maitriser les budgetrs de sécurité TI

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Les éléments d'influence sur la sécurité les besoins (intrants):
* Besoins et exigences de sécurité
* Obligations de sécurité et des besoins d'affaires
  * *Mettre en place un site web sécurisé pour réaliser de la vente en ligne*
  * *Déployer des pointes de vente sécurisées pour permettre des achats par carte de crédit en magasin*
  * *etc.*
* Bonnes pratiques de cybersecurité

Portée (Scope):
* Sécurité des applications et des données
* Sécurité des systèmes
* Sécurité du réseau

##
Apercu du framework de sécurité: ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Apercu%20du%20framework.PNG)

##
Apercu de l'architecture de sécurité TI:![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Architecture%20de%20securite%20TI.PNG)

##
4 sous-système:
* Gestion des identités et des accès (GIA)
* Contrôle et sécurité des flux de données
* Auditing de sécurité
* Intégrité et disponibilité

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Gestion des identités et des accès (GIA):
* Sources autoritaires des identités
* Delegation de l'administration de la GIA
* Gestion des arrivées et des départs des employés
* Création, modification et suppresions des comptes
* Approbation des demandes d'accès
* Désactivation et réactivation des comptes
* Révision périodique des accès
* Authentification (*SSO*, *2FA*, *etc.*)
* Gestion des sessions utilisateurs
* Gestion des mots de passe

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Contrôle et sécurité des flux de données:
* Utilisation de protocoles sécurisés (*SSH*, *HTTPS*, *etc.*)
* Sécurité du périmètre (*Firewall*, *Segmentation*, *etc,*)
* Chiffrement ou protection des flux (*PKI*, *IPSec*, *SSL*, *VPN*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Auditing de sécurité:
* Journalisation des événements de sécurité
* Analse, suivi et surveillance des événements de sécurité
* Détection et prévention d'intrusions
  * Niveau réseau: *NIDS*, *NIPS*, *NDR*, *DLP*, *etc.*
  * Niveau applicatif: *WAF*, *etc.*
  * Niveau système: *HIDS*, *HIPS*, *Anti-malware*, *etc.*
* Gestion des incidents de sécurité TI: *Signalement/Détection/Classification*, *Confinement*, *Éradication*, *Récouvrement*, *Clôture*, *etc.*

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Intégrité et disponibilité:
* Protection physique: *Protection des accès physiques*, *Sauvegardes physiques*, *etc.*
* Protection logique: *Contrôle d'accès aux données et sauvegardes*, *MFA*, *Chiffrement des données*, *etc.*
* Continuité des activités: *SLA*, *SLO*, *RTO*, *RPO*, *DRP*, *BCP*, *etc.*
* Tests: *Tests d'intrusions*, *Tests BCP*, *Tests DRP*, *etc.*

##
Architecture de securité: ![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Architecture%20de%20securite.PNG)

## 
Sécurisation des données
* Traitement du risque:
  * Mise en place de mesures correctives (Mitigation)
  * Acceptation du risque
  * Transfer du risque

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

Sécurisation des systèmes et applications
* Endurcissement des systèmes et applications:
  * Minimiser les delais de detection des intrusions et incidents
  * Assurer la disponibilité des services
  * Assurer l'intégrité des données
  * Gestion des vulnérabilités de sécurité

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
 
Sécurisation du réseau
* Firewalls
* IDS
* IPS
* NDR
* EDR
* DLP
* SIEM
* PKI
* VPN
* IPSec
* Chiffrement
* etc.
 
