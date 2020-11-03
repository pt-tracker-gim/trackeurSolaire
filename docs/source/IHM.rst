

IHM
===
Sur Pyscada, un système de vue est instauré. Une vue englobe des pages et ces pages contiennent le contenu que l'on souhaite afficher, les widgets.

		.. image:: pic/principe_vue.png
		
Les widgets permettent d'afficher le contenu que l'utilisateur souhaite afficher dans une page, selon l'ordre d'apparition **(row)**, le positionnement partie gauche ou droite **(col)** et la largeur du contenu **(size)**. Nous verrons cette fonctionnalité plus en détail dans la partie IHM.

Ci dessous le choix des vues lorsque l'on s'est connecté à notre compte:

		.. image:: pic/choix_vue.PNG
		
Et lorsque l'on clique sur la Vue 1:

		.. image:: pic/Expl_vue.jpg
		
Créer une vue
^^^^^^^^^^^^^
Pour créer une vue il suffit de cliquer sur **Add** view :

		.. image:: pic/view.png

Ensuite insérez le titre de la vue, puis les pages qu'elle contiendra. Chaque élément créé est modifiable par la suite, on pourra donc ajouter des pages après avoir créé la vue.

		.. image:: pic/add_view.PNG

Cliquez ensuite sur **Save** et la vue sera créée.



Créer une page
^^^^^^^^^^^^^^

Dans la page d'accueil admin, cliquez sur **Add** dans la ligne page, puis remplissez les paramètres de votre page et cliquez sur **Save**:

		.. image:: pic/add_page.PNG
		
Créer un control item et un control panel
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Un control item sert à afficher ou modifier une valeur de variable que l'on a créé auparavant. Le control panel sert à afficher sur l'interface utilisateur la valeur de plusieurs control items.

Pour créer un control item, cliquez sur **Add** dans la ligne control item dans la page d'accueil.
Cette page s'affiche:

				.. image:: pic/add_control_item.PNG
				
Voici l'exemple de nos controls items:

				.. image:: pic/control_item.PNG
				
Pour créer un control panel:

				.. image:: pic/control_panel.PNG


Créer un graphique
^^^^^^^^^^^^^^^^^^

Dans la page d'accueil, cliquez sur **Add** dans la ligne *charts*, puis ajoutez les variables qu'il y aura sur le graphique.

		.. image:: pic/add_chart.PNG
		
Exemple du rendu d'un graphique: Température en fonction du temps.

		.. image:: pic/exemple_graphique.PNG
		
Modélisation de la page
^^^^^^^^^^^^^^^^^^^^^^^

Une fois que les éléments sont créés, l'outil Widget sera nécessaire pour choisir ce qui apparaitra sur l'interface utilisateur.

		.. image:: pic/Widget.PNG
		
Cette page permet d'afficher les controls items définis précédemment. On définit la rangée **(row)**, la colonne **(col)** et la taille **(size)** du contenu qui sera affiché.

		.. image:: pic/add_widget.PNG
		
Le contenu de la rangée 1 apparaîtra en haut de la page, la dernière rangée en bas de la page. Pour les colonnes, la 1ère se situe la plus a gauche et la 4ème la plus à droite. Pour la taille vous avez le choix entre 4 formats: 1/4 qui prendra 1/4 de la rangée. 2/4 pour la moitié de la rangée et ainsi de suite jusqu'à 4/4 pour que le contenu choisi prenne la place d'une rangée complète.
		