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

* Exécuter un fichier python (courant.py) dans scripts_2020 : ``python3 scripts_2020/courant.py<br>``

* Pour copier un fichier par exemple (courant.py) du dossier scripts_2019 vers le dossier scripts_2020 : ``cp scripts_2019/courant.py scripts_2020/.``<br>

**D'autres Exemple de communication de base du python** :<br>
<br>
``bus.read_byte_data(address, 0x27)`` est une commande qui nous permet en communiquant avec la
Raspberry (bus) de lire une donnée en octet (read_byte_data).<br>
Pour cela, il faut préciser l’adresse de
la carte de mesure que l’on veut interroger (address) ainsi que le registre que l’on veut lire qui est
codé en valeur hexadécimale (0x27). <br>

``bus.write_byte_data(address, 0x27, 0xff)`` est une commande fonctionnant exactement comme la
commande ci-dessus, elle sert à écrire une valeur dans un registre.<br>


-------------

## Programmation de pyscada

Récupérer les données sur putty nous permettent ensuite de pouvoir les traiter grâce à un logiciel de supervision
nommé PyScada. Avec ce logiciel, nous pouvons récupérer les valeurs de nos différentes cartes de
mesure, puis les afficher en graphiques (ou autres), les enregistrer, et y avoir accès à tout moment et
n’importe où.<br>
**Méthode de connexion à Pyscada :**<br>
1.  cliquer sur le lien si dessous 

http://95.174.165.162:8090 <br>
2. Ensuite ouvrir une page web, et dans la barre de recherche tapez l’adresse IP : 10.3.208.226.
3. Une page s’affiche demandant un login et un password
Login : pi
Password : trackeriut

