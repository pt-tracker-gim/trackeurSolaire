Réalisation d'un script
=======================

Sur Pyscada
^^^^^^^^^^^



Pour interagir avec l'interface les scripts sont nécessaires. Ils serviront à lire ou à écrire des données dans putty et donc sur la carte. Nous allons prendre l'exemple de la création d'un bouton.
Allez dans la page d'accueil Admin, cliquez sur **Add** dans la ligne script qui se situe plus bas dans la page.

		.. image:: pic/pyscada_scripting.PNG

Complétez ensuite les paramètres du script:

		.. image:: pic/add_scripting.PNG
		
Sur putty
^^^^^^^^^
Dans le programme sur putty, on définit d'abord ce que l'on a besoin pour faire fonctionner le script, puis on exécute un protocole en 3 parties: Le démarrage du script, son exécution et son arrêt.
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

