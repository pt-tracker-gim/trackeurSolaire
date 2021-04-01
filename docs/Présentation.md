# Introduction

## Présentation du projet dans sa globalité

Le but de ce projet est d'installer un panneau solaire sur le toit de l’iut, ce panneau solaire aura la particularité d'être instrumenté c'est à dire qu'il pourra être piloté sur 2 axes grâce à deux servomoteurs. Ces deux servomoteurs piloteront le panneau selon sont azimut et son élévation pour lui permettre de suivre le soleil durant la journée et donc d'avoir l'angle de soleil optimale afin d’obtenir une production d’énergie optimale

L'énergie produite par ce panneau n'est pas reliée au réseau elle sera utilisée pour charger une batterie mais également alimenter notre raspberry et pourra aussi être utilisé pour brancher un auxiliaire.
De ce fait il nous a été demandé de développer une interface graphique permettant à un utilisateur de l'iut de visualiser des données concernant le tracker solaire et éventuellement de faire quelques manipulations sur celui-ci dans le cadre d'un TP
Il y aura la mise en place d'un TP à distance sur les ordinateurs de l'iut pour étudier ce panneau pour les étudiants.

Ce projet est déjà en place depuis déjà 7 ans ce qui en fait un projet très complexe avec énormément de modification depuis le début 

### Matériaux présent sur le projet 

 
 Ce projet contient plusieurs matériaux de taille différentes et de complexité multiples, les matériaux principaux à notre projet sont :
 
 **- Un raspberry :**
 
 Le raspberry est un nano-ordinateur mono carte à processeur ARM de la taille d'une carte de crédit, Le langage de programmation utiliser est le langage python, il va également nous permettre de générer des pages web…. 
 
 **- Une carte électronique :**
 
 Un circuit imprimé est un support, en général une plaque, permettant de maintenir et de relier électriquement un ensemble de composants électroniques entre eux, dans le but de réaliser un circuit électronique complexe
 
 **- Un MPPT (Maximum Power Point Tracking):**
 
Le régulateur MPP ou un tracker MPP est un principe permettant de suivre, comme son nom l'indique, le point de puissance maximale d'un générateur électrique non linéaire.
 
 **- Un panneau solaire :**
 
 Un panneau solaire est un dispositif convertissant une partie du rayonnement solaire en énergie thermique ou électrique, grâce à des capteurs solaires thermiques ou photovoltaïques respectivement
 
 **- Un Servomoteur :**
 
 Un servomoteur est un moteur capable de maintenir une opposition à un effort statique et dont la position est vérifiée en continu et corrigée en fonction de la mesure
 
 **- Une batterie :** 
 
 La batterie stocke l'énergie pour une consommation différée. 
 
### Partie supervision  

 
 La partie supervision sera réalisée par pyscada, pyscada est une page web généré par le micro-ordinateur (raspberry), sur cette supervision il sera possible d'avoir des relevées de mesures (tension, courant, énergies, puissance) des différents points de mesure de la carte électronique.
 Il sera également possible de piloter le tracker solaire
 
----------------


## Analyse de l'existant

### Réalisation des années antérieur

* L’équation solaire qui permet au tracker de suivre la position du soleil à n’importe quel moment de la journée (angle d’élévation et angle d’azimut en fonction du temps). Cela doit permettre d’augmenter le rendement du panneau. (Début 2013-2014 fin 2017-2018).  
* La conception de l’armoire électrique indépendante du panneau. (2013-2014).  
* La mise en place du Raspberry (micro-ordinateur) qui nous permet de faire l’acquisition des mesures à distance de valeurs à travers des cartes composées d’un capteur. Ainsi que de communiquer à distance grâce à une supervision. (2014-2015).  
* La programmation en Python pour communiquer avec le Raspberry (mini-ordinateur) avec l’application Putty. (2014-2015).  
* La conception d’un boîtier d’étanchéité pour les servomoteurs ainsi que les cartes électroniques et le module MPPT. (2018-2019) et amélioration en (2019-2020).  
* Étude de l’emplacement des points de mesures sur le système afin d’obtenir les données nécessaires pour un suivi du point optimal de fonctionnement du panneau (2019-2020).  
* Création du schéma de la carte électronique (2019-2020).  
* Conception et test des cartes de mesures. (2020-2021).  
* La réalisation de l’interface web sur Pyscada pour traiter les données mesurées et les exploiter. (2020-2021).  
* Création de tuto qui reprennent la totalité du projet afin d’être utilisé par les année suivante. (2020-2021).

 

![Screenshot](pic/logo_iut.png)
