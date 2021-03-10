# Partie electronique 

## Le Raspberry Pi

<img src="./pic/Partie_electronique/Raspberry.PNG">

<br>

Le Raspberry Pi est un nano ordinateur mono carte à
processeur ARM. Il permet l’exécution de plusieurs variantes du
système d’exploitation libre GNU/Linux et des logiciels
compatibles.

<br> 

Le modèle utilisé pour le projet est le modèle B+ V1.2.
Il possède un processeur ARM à 4 coeurs d’une fréquence
d’horloge de 700MHz. Il est capable d’assigner 16 registres
généraux (stockage temporaire des données) codés sur 32
bits. C’est-à-dire que les mots (signé ou non) manipulés par
le processeur peuvent prendre jusqu’à plus de 4 milliard de
valeurs (soit 232).

<br> 

Sa mémoire vive (RAM) est de 512 Mo. La mémoire
vive est l'espace principal de stockage du microprocesseur,
mais le contenu disparaît lors de la mise hors tension de
l'ordinateur.

<br> 

Il a 40 broches GPIO, c’est-à-dire des entrées/sorties. Elles permettent de
communiquer avec différents composants électroniques. Les connecteurs GPIO sont
généralement alimentés en 3.3Vcc et ne peuvent émettre que des courants de faible
capacité, allant de 3mA à 50mA. Cela lui offre d’être à la fois un ordinateur et un
contrôleur pour des applications purement électroniques.

<br> 

Pour permettre la liaison, la communication et la sauvegarde des données il
possède également :
* Une prise d’alimentation micro-USB (700mA),
* 1 sortie stéréo jack,
* 4 ports USB2,
* 1 port réseau ETHERNET (de 10 à 100 Mbits/seconde),
* 2 sorties vidéos (HMDI et prise RCA),
* Une micro SD card,
* Il a une consommation globale de 3 Watts.

<br> 

Le Raspberry pi va donc nous permettre de :
* Récupérer les donner de la carte Arduino en python,
* Calculer la position du soleil avec python,
* Piloter les servomoteurs avec python,
* Gérer la récupération des données météo avec python,
* Rapatrier des données vers un fichier (Json ou .txt),

L’utilisation du Raspberry Pi B+ V1.2 va nous permettre de faire de la
programmation et de générer des pages web. En effet, il se comporte comme un microordinateur
et il est capable de créer des pages web sous format PHP ou HTML.
Le Raspberry pi va donc nous permettre de :
* Récupérer les donner de la carte Arduino en python,
* Calculer la position du soleil avec python,
* Piloter les servomoteurs avec python,
* Gérer la récupération des données météo avec python,
* Rapatrier des données vers un fichier (Json ou .txt),
* Gérer les données de sécurité du système,
* Héberger une interface WEB avec HTML, PHP et CSS.

## Controleur de charge MPPT

Le régulateur est indispensable afin d’optimiser la charge de
la batterie dû aux variations de production énergétique du tracker
solaire. L’énergie de sortie sera utilisée pour l’alimentation d’un
réseau de courant continue, par exemple, les servomoteurs et la
batterie.
