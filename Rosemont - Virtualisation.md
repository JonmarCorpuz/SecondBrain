La virtualisation est une couche d’abstraction informatique qui permet de faire fonctionner plusieurs serveurs, systèmes ou 
applications sur un même serveur physique et fait comme si ces systèmes fonctionnent sur des machines physiques distinctes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-23%20161904.png)

* Les ressources de la machine physiques sont partagées pour créer les machines virtuelles
* Le CPU donne l’apparence comme chaque système possède son propre processeur
* Chaque système informatique virtuel correspond à une machine virtuelle qui se présente comme un conteneur de logiciels totalement isolé, et doté d'un système d'exploitation et de ses propres applications
* Chaque machine virtuelle est une entité autonome et complètement indépendante


![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Avantages de la virtualisation

* Optimisation des resources: Réduit le nombre de serveurs physiques et le nombre de périphériques réseau, etc.
* Économie d’énergie: La consolidation des serveurs réduit les coûts mensuels d’alimentation électrique et de refroidissement, donc plus écologique
* Provisionnement des serveurs: Beaucoup plus rapide de créer une machine virtuelle qu'un serveur physique
* Meilleur reprise d'activité après sinistre: La virtualisation offre des fonctions avancées de continuité d’activité et la possibilité de copier les machines virtuelles sur d’autres plateformes
* Moins d’espace occupé: La virtualisation permet de réduire l’encombrement du centre de données (Ex: *Diminution des serveurs physiques*, *Diminution des périphériques réseau*, *etc.*)
* Optimisation de la disponibilité des systèmes: les solutions de virtualisation intègrent des fonctionnalités avancées et redondante de tolérance aux pannes (Ex: *Migration dynamique*, *Migration du stockage*, *Haute disponibilité*, *La planification des ressources*, *etc.*)
• Permet la prise en charge d’anciens systèmes
• Réduction des coûts 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Avant la virtualisation

Les entreprises fournissaient des applications et des services via des serveurs dédiés

* Gaspillage de ressources
* Point de défaillance unique
* Profilération des serveurs
* Prend plus d'espace

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Risques

le principal risque de la virtualisation est si vous consolidez les charges de travail dans des machines virtuelles, mais que vous n'en avez pas la capacité, il est donc important de :

* Équilibrer la charge de vos machines virtuelles à travers vos serveurs physiques
* Équilibrer la charge de la capacité et de la performance de vos volumes de stockage
* Superviser et gérer vos VMs et vos serveurs physiques
* Déployer des images en ayant vérifié l’intégrité de ces images 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Vocabulaire utilisé en virtualisation

* Hôte (host) est le système d’exploitation physiquement installé sur l’ordinateur, dans lequel sera utilisé le logiciel de virtualisation
* Machine virtuelle est ordinateur virtuel créé par le logiciel de virtualisation
* Invité (guest) c’est le système d’exploitation installé à l’intérieur de la machine virtuelle
* Un service : Les fonctionnalités, les applications sur les serveurs/machines virtuelles
* Un serveur virtuel est un conteneur de logiciel complètement isolé capable de gérer ses propres systèmes d'exploitation et applications comme s'il s'agissait d'un ordinateur physique, en utilisant des techniques de virtualisation

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Hyperviseur

L'hyperviseur est une plate-forme de virtualisation qui permet à plusieurs systèmes d'exploitation de travailler sur une même machine physique en même temps

* Assure le contrôle du processeur et des ressources de la machine hôte
* Alloue à chaque machine virtuelle les ressources dont elle a besoin
* S’assure que les VMs n’interfèrent pas l’une avec l’autre

## Hyperviseur type 1 (Bare metal)

Un hyperviseur de type 1 est un système qui s’installe directement sur la couche matérielle du serveur à la 
place du système d’exploitation (Ex: *Citrix XenServer*, *VMware ESXi*, *Proxmox*, *Microsft Hyper-V qui est intégré à Windows Server*, *etc.*) 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-23%20162956.png)

* On ne peut avoir qu’un seul hyperviseur sur la machine hôte
* L’hyperviseur est dans ce cas un outil de contrôle, et de gestion des systèmes d’exploitation invités
* Les hyperviseurs bare-metal sont sécurisés par le fait qu’ils sont isolés du système d’exploitation

## Hyperviseur type 2 (Host metal)

Un hyperviseur de type 2 est un logiciel qui s’installe et s’exécute à l’intérieur d’un autre système d’exploitation qui est déjà en place (Ex: *VMware Workstation*, *VirtualBox*, *Microsoft Virtual Desktop*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-23%20163323.png)

* On appelle également les hyperviseurs de type 2 des hyperviseurs hébergés.
* Ici plus de ressources sont utilisées étant donné qu’on fait tourner l’hyperviseur et le système d’exploitation qui le supporte
* Possibilité d’avoir plusieurs hyperviseurs sur le même hôte car ils ne sont pas liés au matériel 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png) 

# Les solutions

## Oracle's Virtualbox

VirtualBox est un puissant produit de virtualisation x86 et AMD64 /Intel64 pour les entreprises ainsi que l'utilisation à domicile :

* C’est une solution gratuite en tant que Logiciel Open source
* S'exécute sur des serveurs Windows, Linux, Macintosh, Solaris
* Prend en charge les systèmes invités comme les systèmes Windows, Windows 3.1, Linux, solaris, OpenBSD etc
* VirtualBox peut présenter jusqu'à 32 CPU virtuelles à chaque machine virtuelle

## Kernel Virtual Machine

KVM est intégré au sein du noyau Linux depuis la version du noyau 2.6.20

* Le système invité n'a pas besoin d'être modifié (Chaque système invité est traité par le noyau comme un processus autonome)
* KVM s'utilise en ligne de commande, il n'y a pas d'interface graphique officielle
* Pour utiliser KVM, le système hôte doit être équipé d’un processeur compatible (architectures x86 disposant des technologies Intel VT ou AMD SVM (AMD-V))
* Actuellement, la majorité des processeurs Intel et AMD récents sont compatibles avec KVM

## Citrix-XEN

## Microsoft Hyper-V

## VMware

## QEMU
