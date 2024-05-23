La virtualisation est une couche d’abstraction informatique qui permet de faire fonctionner plusieurs serveurs, systèmes ou 
applications sur un même serveur physique et fait comme si ces systèmes fonctionnent sur des machines physiques distinctes

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Screenshot%202024-05-23%20161904.png)

* Les ressources de la machine physiques sont partagées pour créer les machines virtuelles
* Le CPU donne l’apparence comme chaque système possède son propre processeur

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
