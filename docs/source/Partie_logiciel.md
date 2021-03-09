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
 
<h4 align="center">SUR WINDOWS</p>

<img src="https://raw.githubusercontent.com/pt-tracker-gim/trackeurSolaire/master/docs/source/pic/PUTTY.PNG">

**Adresse:** ``95.174.165.162`` 

**Port:** ``8092`` 

<h4 align="center">SUR MAC</p>

Ouvrir un terminal et entrer la commande:
``ssh PV@95.174.165.162 -p 8092``

<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/terminal_code.png">



### Identification:

**Identifiant**: ``PV`` 

**MDP**: ``tracker 2020``

-------------
### Commande sur PUTTY

Une fois connecté sous putty ou ssh plusieurs commande de base sont a connaitre :

*Pour lister un dossier: ls -l

<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/partie_logiciel/ouvrir.png">

*Lister un autre dossier, par exemple : ls -l scripts_2020/
 
<img src="https://github.com/pt-tracker-gim/trackeurSolaire/blob/master/docs/source/pic/partie_logiciel/lister.png">

-------------

**Réalisation d'un script**


Dans le programme sur putty, on définit d'abord ce que l'on a besoin pour faire fonctionner le script, puis on exécute un protocole en 3 parties: 

* Le démarrage du script, 
* son exécution 
* son arrêt.
Voici l'exemple du programme de script pour putty:

		.. image:: pic/script_putty.png

Le paramètre ``interval`` évoque le temps d'actualisation du script.
Le chemin de votre script est à insérer dans le paramètre ``Script file``.

Sous forme txt pour copier coller::

	$from time import time
	import logging
	import smbus
	
	#logger = logging.getLogger(__name__)
	
	def startup(self):
		"""
		write your code startup code here, don't change the name of this function
		:return:
		"""
		pass
	
	def shutdown(self):
		"""
		write your code shutdown code here, don't change the name of this function
		:return:
		"""
		pass
	
	def script(self):
	
		data = self.read_values_from_db(variable_names=['bouton2'], current_value_only=True)
		#logger.debug(bouton2)
		bus = smbus.SMBus(1)
		bus.close()
		
Le programme est le même pour chaque script que nous avons créé, la seule partie modifiable se situe après la ligne ``def script(self)``.
La ligne ``#logger.debug(bouton2)`` permet de voir les logs du script lorsque l'on enlève le # du programme.


-----------------------------


Creation d'interface (Pyscada)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

