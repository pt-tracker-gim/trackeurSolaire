# Introduction

## Presentation du projet dans sa globalité

Dans le cadre de notre projet sur le tracker solaire nous sommes amenés à développer une interface permettant à un utilisateur de l'iut de visualiser des données concernant le tracker solaire et éventuellement de faire quelques manipulations sur celui-ci dans le cadre d'un TP

Le département GIM de l’IUT de Bayonne dispose d’un panneau photovoltaïque monté sur un support, celui-ci est orientable sur 2 axes par la commande de deux servomoteurs (angle d’élévation et angle d’azimut). Ce qui permet de garder un alignement constant avec le soleil afin d’obtenir une production d’énergie optimale

Ce projet aura pour but d’être placer sur le toit du bâtiment de l’IUT afin que les élèves du DUT GIM puissent faire des travaux pratiques dessus. 

 ## Materiaux present sur le projet 
 
 Ce projet contient plusieurs materiaux de taille differentes et de complexité multiples  , les materiaux principaux  a notre projet sont :
 
 **- Un raspberry:**
 
 Le raspberry est un nano-ordinateur monocarte à processeur ARM de la taille d'une carte de crédit , Le language de programmation utiliser est le language python, il va egalement nous permettre de generer des pages web..... 
 
 **- Une carte electronique:**
 
 Un circuit imprimé est un support, en général une plaque, permettant de maintenir et de relier électriquement un ensemble de composants électroniques entre eux, dans le but de réaliser un circuit électronique complexe
 
 **- Un MPPT(Maximum Power Point Tracking):**
 
Le régulateur MPP ou un tracker MPP est un principe permettant de suivre, comme son nom l'indique, le point de puissance maximale d'un générateur électrique non linéaire.
 
 **- Un panneau solaire:**
 
 Un panneau solaire est un dispositif convertissant une partie du rayonnement solaire en énergie thermique ou électrique, grâce à des capteurs solaires thermiques ou photovoltaïques respectivement
 
 **- Un Servomoteur:**
 
 Un servomoteur est un moteur capable de maintenir une opposition à un effort statique et dont la position est vérifiée en continu et corrigée en fonction de la mesure
 
 **- Une batterie:** 
 
 la batterie stocke l'energie pour une consommation différée. 
 
 ## Partie supervision 
 
 La partie supervision sera realisé par pyscada , pyscada est une page web generé par le micro-ordinateur (raspberry)
 
----------------


## Annalyse de l'existant

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
