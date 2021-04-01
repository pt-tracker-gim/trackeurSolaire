# Partie Supervision

## Programmation du Raspberry (PUTTY)

### Présentation


Pour faire simple, PuTTY vous permet de vous connecter en ssh (protocole de connexion sécurisé) et d’émuler directement le terminal serveur afin de vous permettre d’interagir avec celui ci sans pour autant avoir accès à l’écran ou au clavier.
Dans ce logiciel il est possible de venir écrire des lignes de programme en **python** qui vont nous permettre de venir **lire et échanger** avec un ordinateur à distance (dans notre cas un Raspberry pi4) et obtenir des relevées sur un Pc connecté au même réseau que le Raspberry.

Avec ces programmes, nous sommes maintenant capables de demander au Raspberry les valeurs mesurées par la carte de mesure 

-------------

### Telecharger PUTYY

https://the.earth.li/~sgtatham/putty/latest/w32/putty.exe

-------------

### Connexion a PUTTY
 
<h4 align="center">SUR WINDOWS</h4>
<br>

**Adresse:** ``95.174.165.162`` 
**Port:** ``8092`` <br>


![Screenshot](pic/PUTTY.PNG)



<h4 align="center">SUR MAC</h4>
<br>

Ouvrir un terminal et entrer la commande:
``ssh PV@95.174.165.162 -p 8092``


![Screenshot](pic/terminal_code.png)


### Identification:

**Identifiant**: ``PV`` 

**MDP**: ``*********``

-------------
### Commande sur PUTTY

Une fois connecté sous putty ou ssh plusieurs commandes de base sont à connaitre :

* Pour lister un dossier : ``ls -l`` 

En écrivant cette commande on retrouve deux dossiers (scripts_2019 et scripts_2020) qui regroupe tout les programmes qui vont nous être utile pour le Raspberry 


![Screenshot](pic/partie_logiciel/ouvrir.png)


* Pour Rentrer dans le dossier, par exemple : ``ls -l scripts_2020/`` 
 voici les dossiers présent dans ce script


![Screenshot](pic/partie_logiciel/lister.png)


* Pour éditer le fichier courant.py par exemple:``nano scripts_2020/courant.py``


![Screenshot](pic/partie_logiciel/Script_tension.PNG)

* Exécuter un fichier python (courant.py) dans scripts_2020 : ``python3 scripts_2020/courant.py<br>``

* Pour copier un fichier par exemple (courant.py) du dossier scripts_2019 vers le dossier scripts_2020 : ``cp scripts_2019/courant.py scripts_2020/.``

**D'autres Exemple de communication de base du python** :

``bus.read_byte_data(address, 0x27)`` est une commande qui nous permet en communiquant avec la
Raspberry (bus) de lire une donnée en octet (read_byte_data).

Pour cela, il faut préciser l’adresse de
la carte de mesure que l’on veut interroger (address) ainsi que le registre que l’on veut lire qui est
codé en valeur hexadécimale (0x27). 

``bus.write_byte_data(address, 0x27, 0xff)`` est une commande fonctionnant exactement comme la
commande ci-dessus, elle sert à écrire une valeur dans un registre.


-------------

## Programmation de pyscada

Récupérer les données sur putty nous permettent ensuite de pouvoir les traiter grâce à un logiciel de supervision
nommé PyScada. Avec ce logiciel, nous pouvons récupérer les valeurs de nos différentes cartes de
mesure, puis les afficher en graphiques (ou autres), les enregistrer, et y avoir accès à tout moment et
n’importe où.

**Méthode de connexion à Pyscada :**

1. Cliquer sur le lien si dessous 
http://95.174.165.162:8090 

2. Apres avoir cliquer sur le lien s'identifier 

 identifiant : ``******``
 
mot de passe : ``*******`` 


Méthode pour créer un graphique 
1. Créer une page (qui viendra se placer dans la vue)


![Screenshot](pic/logo_iut.png)
