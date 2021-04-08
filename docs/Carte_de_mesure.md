# Carte de mesure 



Cette carte électronique de mesure sera le lien entre le raspberry et les points de mesure du système. Il est le cœur du projet car le but premier et de faire un TP pour les étudiant donc les mesures sont indispensables.

### Processus d'installation :

Pour cette partie nous allons vous explique comment nous fabriquer une carte de mesure de A à Z,
Avant même de commencer nous avons fait un inventaire des composants disponibles pour finir ce que le groupe antérieur avait commencé.
Après cela nous avons pu commencer la pose des composants CMS. En effet deux type de composant compose notre carte les “CMS” et les “traversants”
Les composants CMS sont les plus petits et les plus difficiles à poser. C’est un travail minutieux et rigoureux car un composant mal placé et un composant HS.

Pour réaliser cette tâche le plus sûrement possible deux outils sont indispensable, le microscope électronique et le poseur de composant manuel.
De plus la pose des composants CMS ce fait à l'aide de pâte à braser envoyer grâce à de l'air sous pression. 
Un passage au four est obligatoire pour pouvoir cuire les composants CMS. Par la suite, nous pourrons poser les composants traversant avec un fer à souder classique.

### Les problèmes rencontrées :

Trois problématiques se sont posées après avoir fini la première version de la carte proposée par les étudiants de l'année précédente.
L’alimentation du raspberry 3.3 ou 5v?
Le compteur d'énergie bidirectionnel de la batterie
Respecter le temps d'éteignage du raspberry


**Problème 1 : L’alimentation du raspberry**
L'alimentation du raspberry était prévue de base en 3.3V. Mais après l'étude du composant nous avons pu voir que le raspberry pouvait transformer lui-même le 3.3V, il suffisait d’envoyer du 5V. Pour cela nous avons dû refaire des calculs, et voir la datasheet du composant, effectivement à la sortie de l’alimentation il y a un pont diviseur qui nous permet d’obtenir la tension souhaitée. Les étudiants de l’année dernière ont calculé un pont diviseur pour une tension égale à 3.3V, ainsi la datasheet du composant nous permettra de calculer la tension choisie.
la formule du constructeur nous dit:

![Screenshot](pic/logo_iut/carte_mesure/calcul_1.PNG)

Rb = 0.8Rt / Vout - 0.8
Nous avons gardé 39k pour Rt, on trouve donc Rb = 7.4k
Cependant nous avons constaté que ces valeurs de résistance n’étaient pas disponibles en CMS. Pour cela nous avons calculé le rapport entre Rt / Rb et grâce aux valeurs normalisées des résistances nous avons pu trouver les résistances adéquates au pont diviseur.

Grâce à ces valeurs de résistance, la tension de sortie de l’alimentation à découpage est de 5V. 
Ainsi nous avons dû modifier la carte électronique puisque celle des étudiants précédents était faite pour une tension de 3.3V. Après modification de celle-ci, plusieurs autres problèmes sont intervenus, des problèmes sur les composants de mesure LTC 2946, ils n'étaient pas détectés à cause d’un mauvais routage de la carte de mesure.
Pour remédier à ces problèmes, une nouvelle carte à était créée sur le logiciel Easy EDA. Cette nouvelle carte permettra de réaliser des mesures, notamment la mesure d’énergie bidirectionnelle mais aussi de permettre l’alimentation de ces composants en 5V grâce à l’alimentation à découpage, présentée ci-dessous.
Ancien Schéma : 					Nouveau Schéma :

Cette nouvelle carte permettra de répondre aux deux problèmes suivants.

**Problème 2 : Le compteur d'énergie bidirectionnel pour la batterie**
Cette mesure  est indispensable pour pouvoir connaître le courant d’entrée et de sortie de batterie relier au MPPT. Toutes les mesures sont effectuées grâce aux composants LTC 2946 
Un premier test de cette partie du système a été effectué sur des petites cartes de prototype,  en testant la bidirectionnalité des mesures et la communication entre le raspberry et et la carte de mesure en protocole I2C.
Ce premier test ne fut pas une réussite, en effet ces fameux composants sont très fragiles et ont été exposés à de forte chaleur à cause des modifications sur les composants de mesure. De plus le contact entre les deux capteurs n’était pas bon et la bidirectionnalité ne se faisait pas entre les 2 cartes de mesures prototype.
(Le pôle positif sur le pôle négatif et inversement) Ces tests ont révélé des imprécisions dans l’adresse des cartes de mesure qui n'étant pas détectées par le raspberry. 
Pour pouvoir valider cette partie du système nous avons dû refaire une carte avec le même schéma modifié.
Schéma précédent : 

Nouveau schéma  : 

Sur ce schéma plusieurs choses ont changé .
Comme l’apparition de cavaliers qui serviront à l'adressage manuel de tous les composants de mesure.
Pour effectuer ces tests, sur notre nouvelle carte de mesure, nous avons seulement dû souder la partie du nouveau schéma. Sur cette carte il n’y avait pas d’alimentation à découpage, nous avons donc alimenté le raspberry par prise micro USB. Ces tests ont été concluants puisque les composants nous renvoient les mesures, visualiser  grâce au logiciel putty.
Pour permettre la communication entre le Raspberry et les composants de mesure, nous utiliserons un moyen de communication en I2C, c'est-à-dire que nous allons connecter les ports SDA et SCL du Raspberry à la carte de mesure.
Ensuite sur putty nous allons réaliser la commande  pour voir l’adressage des composants de mesure.
Et pour relever les valeurs de courants, de tensions, etc… nous réalisons la commande suivante, python3 test.py 0x6x 
0x6x ( le x sera le dernier chiffre de l’adressage, dans notre cas l’un a une adresse 0x6a et l’autre 0x68 )

Sur ce tableau on peut y voir l’adresse disponible pour les LTC 2946, selon leur câblage, l’adresse sera différente. Les cavaliers simulent donc le changement de câblage.
H = etat zéro (relier a un potentiel négatif )
L = etat un (reliée a un potentiel positif )
NC = non connecté (câble en l aire)
Pour revenir à notre cas, nos adresses sont : 0x6a et 0x68. On fait une conversion hexadécimale vers le binaire et on connaît le type de câblage de notre composant de mesure.
Hexadécimale
Binaire
Câblage
0x6a
1101010
NC    NC
0x68
1101000
NC     H


Cette connaissance de l’adressage des composants de mesure est importante pour la répartition des ces composants selon leurs type de prise de mesure.

**Problème 3 : Respecter le temps d'éteignage du raspberry**
Le raspberry est un mini ordinateur, nous avons besoin de lui pour transmettre les mesures sur une interface graphique. Cependant comme tout ordinateur, il doit s’éteindre le plus sagement possible. Pour cela nous avons dû faire des calculs pour nous permettre de respecter ce temps d’éteignage.
L’idée est de mettre un condensateur, en amont de l'alimentation à découpage pour permettre au raspberry de ne pas s'éteindre brusquement.

Voici les calculs réalisés : 
On sait que, 
	  
De plus,
 
Grâce à cette équation on trouve un temps de 22.5s pour 1F, nous avons choisi un temps de 120s, et avec un produit en croix on trouve le condensateur qu’il nous faut. Ainsi notre choix sera un condensateur de 6F.

Cependant nous devons trouver un condensateur de 6F à 12V, le condensateur choisi existe mais il est très cher, nous sommes donc partis sur une solution de mettre des condensateurs en série. C’est ainsi que rentre en jeu la première équation :
Ceq = 6F 
C/n = 6F => 35/6 6F
Notre choix se portera sur des condensateurs de 35F à 2,7V ( 6 x 2.7 = 16.2V > 12V) qui sont des composants traversants et beaucoup moins cher.









Avant de tester les condensateurs sur la carte, nous avons réalisé à l’aide d’une platine le montage suivant :


Les tests concluants, nous décidons donc de souder tous les composants sur la carte de mesure, pour voir si toutes nos solutions fonctionnent ensemble. 

Sur cette carte nous allons tester l’alimentation 5V pour le Raspberry, le compteur d’énergie bidirectionnel.







	3. Conclusion : 
Pour conclure sur ces trois problématiques. Seulement deux seront validées pour la fin du projet, compteur bidirectionnel et l’alimentation 5V au lieu du 3.3V. La solution des condensateurs présente quelques problèmes dans l’application de la carte en effet avec les condensateurs de la carte alimentent bien le raspberry pendant quelques secondes puis le composant se met en sécurité pour au final ne plus découper l’alimentation 5V.
Cette solution demande encore des tests en laboratoire, voire une nouvelle étude pour pouvoir répondre au nouveau problème créé par cette solution.

Jour après jours nous avons testé, ce fut un travail répétitif et quelquefois, aussi un travail frustrant.
Car sur le papier ces trois solutions auraient dû marcher sans aucun souci mais dans ce projet nous avons pu bien voir la différence entre ce qu’on calcul et ce que l’on constate dans la partie pratique.
Les groupes qui suivront sur ce projet auront aussi beaucoup de tests à faire sur cette carte et sans doute en créer une troisième version.

Pour ce projet beaucoup de compétence fut indispensable comme par exemple les mathématiques sur les différents types de circuit en électricité (R,RC,RL…).
Et les équations qui en découlent.
Des compétences en électricité , sur les ponts diviseurs, sur les formules de base d'électricité étaient indispensables.

Pour terminer sur la conclusion de cette partie le travail effectué en coopération avec M. LARRAMENDY fut indispensable, la science, la connaissance des cartes électroniques étaient nouvelles pour nous et on a acquis énormément de compétences.
On finira par dire que ces solutions sont des réussites mais peut être pas définitives, l’adaptation aux problèmes rencontrés est indispensable pour permettre de surmonter cette épreuve.



