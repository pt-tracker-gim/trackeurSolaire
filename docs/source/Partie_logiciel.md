# Partie logiciel

## Programmation du Raspberry (PUTTY)

### Présentation

Le logiciel de programmation utilisée se nomme Putty, dans ce logiciel il est possible de venir écrire des lignes de programme en **python** qui vont nous permettre  de venir **lire et échanger** avec un ordinateur à distance ( dans notre cas un Raspberry pi4) et obtenir des relevées sur un Pc connecté au même réseau que le Raspberry.
<br>
Avec ces programmes nous sommes maintenant capables de demander au Raspberry les valeurs mesurées avec la carte électroniques. 

-------------

### Telecharger PUTYY

https://the.earth.li/~sgtatham/putty/latest/w32/putty.exe

-------------

### Connexion a PUTTY
 
<h4 align="center">SUR WINDOWS</h4>
<br>

**Adresse:** ``95.174.165.162`` 
**Port:** ``8092`` <br>

<img src="./pic/PUTTY.PNG">




<h4 align="center">SUR MAC</h4>
<br>

Ouvrir un terminal et entrer la commande:
``ssh PV@95.174.165.162 -p 8092``

<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/terminal_code.png">



### Identification:

**Identifiant**: ``PV`` 

**MDP**: ``tracker 2020``

-------------
### Commande sur PUTTY

Une fois connecté sous putty ou ssh plusieurs commande de base sont a connaitre :

* Pour lister un dossier: ``ls -l`` <br>
En ecrivant cette commande on retrouve deux dossier (scripts_2019 et scripts_2020) qui regroupe tout les programmes qui vont nous etre utile pour le raspberry 
<br>
<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/partie_logiciel/ouvrir.png">
<br>

* Pour Rentrer dans le dossier, par exemple : ``ls -l scripts_2020/`` <br>
 voici les dosier present dans ce scripts
<br>
<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/partie_logiciel/lister.png">
<br>

* Pour éditer le fichier courant.py par exemple:``nano scripts_2020/courant.py``
<br>
<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/partie_logiciel/Script_tension.PNG">

-------------



