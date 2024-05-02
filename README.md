# Team-Workload

## Manuel d'Utilisation

### 1. Introduction

Bienvenue dans le manuel d'utilisation de Team-Workload ! Cette application a été développée dans le but de permettre aux chefs de projets, responsables de service, de concaténer, visualiser et analyser des données de charge de travail de manière intuitive, interactive et collaborative.

### 2. Installation

Aucune installation n'est nécessaire. Les mises à jour sont automatiques.

### 3. Confidentialité de vos données 

Vos données sont sécurisées : elles ne sont ni stockées, ni divulguées, ni accessibles à d'autres utilisateurs. Toutes les opérations sont effectuées sur un serveur sécurisé dédié au calcul. Vos données sont purgées dès la fermeture de l'interface web.

### 3. Utilisation

Une fois l'application lancée, vous verrez une interface utilisateur divisée en plusieurs pages ou modules :

* **Plan** : C'est ici que vous saisissez, générez, modifiez, importez, enregistrez et visualisez vos données sous forme d’un tableau dynamique.

* **Workload** : Visualisez et analysez vos données sous forme d'histogramme de charge. Utilisez les filtres,  boutons ou la légende interactive du graphique pour adapter l’histogramme à votre convenance. Utilisez l’outil capture pour enregistrer l’histogramme dans un fichier image au format *.png*.

* **Heatmap** : Identifiez en un coup d’œil la sous-charge ou sur-charge de vos ressources sur une carte thermique. Utilisez le filtre à votre convenance. Utilisez l’outil capture pour enregistrer la carte thermique dans un fichier image au format *.png*.

* **Follow-up** : Assurez le suivi de vos projets. En saisissant les données réelles de dépense et d’avancement, cette section vous donne en un coup d’œil les projections financière et de délai de vos projets.

L'application démarre toujours sur le module *Plan*. Pour changer de module, cliquez simplement sur la page correspondante dans le bandeau d'entête.

### 4. Module Plan

#### Import / Export des données

L'import et l'export des données se fait via la section *Plan* :

* **Génération aléatoire** : Vous pouvez générer des données aléatoires en cliquant sur le bouton *Generate random sample*. Ces données sont fictives et ne représentent pas des valeurs réelles en termes de ressources ou de temps. Elles sont utilisées uniquement à des fins de démonstration.

* **Import** : Pour importer des données à partir d'un fichier *.csv*, vous pouvez utiliser le bouton *Import your projects*. Ce bouton offre également la fonctionnalité de "glisser-déposer". Il est possible d'importer plusieurs fichiers simultanément dans le but de les concaténer.

* **Export** : Pour exporter vos données, il vous suffit de cliquer sur le bouton *Save your projects*. Vos données seront alors enregistrées dans le dossier "Téléchagement" de votre explorateur Web, au format *.csv*. Cette fonctionnalité vous permet de réimporter vos données ultérieurement et même de les concaténer avec d'autres fichiers.

#### Pourquoi Team-Workload est un outil collaboratif ?
Chaque nouvelle ligne crée se voit attribuer un numéro d'identification unique ainsi qu'un horodatage en UTC, qui ne sont pas visibles par l'utilisateur. Si une ligne est modifiée ultérieurement, son horodatage est automatiquement actualisé. Cette fonctionnalité est particulièrement utile lors de l'importation simultanée de plusieurs fichiers, car elle permet de fusionner les lignes partageant le même identifiant en une seule, en conservant l'horodatage le plus récent. Les lignes supprimées sont également enregistrées lors de l'exportation. Team-Workload permet ainsi le partage de fichiers entre collègues, tout en permettant à chacun de les modifier (sous réserve des autorisations accordées par vous-même en tant qu'émetteur du fichier source), puis de fusionner ces fichiers grâce à une concaténation intelligente.
	
De plus, chaque collaborateur a la liberté de saisir ses données avec le niveau de précision qu'il préfère (par discipline, par tâche, par ressource, etc.), sans que cela ne compromette l'analyse des données une fois concaténées.
	
Enfin, l'import et l'export de fichier sont rendus possible uniquement si aucune erreur n'est détectée. Ainsi, Team-Workload est à la fois un outil robuste (champs non modifiables + intégrité des données), flexible (saisie de tous les champs facultatifs) et facile à utiliser (aucun paramétrage ni administration ne sont nécessaires).

#### Affichage des données

L'un des principaux avantages de Team-Workload réside dans sa capacité à regrouper les lignes par champ grâce à une fonctionnalité de "glisser-déposer" des en-têtes (par exemple, par discipline > ressource ou par client > projet, etc.). Cela permet à l'utilisateur de visualiser ses données suivant différents axes / regroupements.

Vous pouvez éditer vos données dans les deux modes : avec ou sans regroupement de lignes.

Vous pouvez déplacer les champs qui ne vous intéressent pas en dehors de la fenêtre par simple "glisser-déposer".

Un appui sur le bouton *Reset* réinitialisera l'affichage.

Les boutons *Collapse / Expand* et *Normal / Compact* vous permettent de personnaliser l'affichage à votre convenance.

Enfin, vous pouvez utiliser le *Filtre rapide*, et les fonctions de *Tri* en cliquant sur les entêtes des champs.

#### Edition des données

Vous avez la possibilité de sélectionner et modifier une ou plusieurs lignes individuellement, ou de manière groupée en maintenant la touche "MAJ" de votre clavier enfoncée.

Pour désélectionner des lignes, vous pouvez soit cliquer à nouveau sur les lignes sélectionnées, soit utiliser le bouton *Unselect*.

Vous pouvez ajouter ou supprimer une ou plusieurs lignes simultanément, et ce à l'endroit souhaité dans le tableau. Cette opération se réalise facilement grâce aux boutons *Delete*, *Add above*, et *Add below*.

Vous pouvez déplacer une ou plusieurs lignes individuellement par simple glisser-déposer.

#### Vérification des données

Team-Workload effectue une série de vérifications pour garantir l'intégrité des données saisies. Ces vérifications incluent :

* **Données manquantes** : Les lignes incomplètes sont colorées en gris. Les champs suivants doivent être obligatoirement saisis : *Charge, U, Profil, Début, Fin, Pointe*, ainsi qu'au moins l'un des champs facultatifs : *Client, Référence, Projet, Discipline, Statut, Lot, Tâche, Ressource*, pour permettre la bascule sur les sections autres que *Plan*.

* **Erreurs de saisie** : Les interversions de dates sont détectées et colorées en rouge. Elles doivent être corrigées pour permettre la bascule sur les sections autres que *Plan*.

En plus des vérifications de base, Team-Workload effectue une analyse approfondie des données pour générer des informations supplémentaires utiles. Cela inclut :

* **Calcul du nombre de ressources** : En fonction des données fournies (effort et durée), le système calcule le nombre de ressources nominales (si profil linéaire) ou en pointe (si profil non linéaire) nécessaires pour chaque ligne saisie. Par défaut, le nombre de ressources en pointe est arrondi à l'entier supérieur si le profil est non linéaire. Vous pouvez dans ce cas modifier la valeur en pointe à la hausse mais jamais à la baisse.

* **Profil de charge** : Le système applique par défaut un profil linéaire à chaque ligne (tâche) comme le ferait n'importe quel logiciel de planification. Libre à vous de modifier le profil de charge à votre convenance. "Pic à 20%" signifie que l'activité sera en pointe à 20% de la timeline représentée par les dates de Début et Fin.

Les alertes peuvent s'afficher dans l'interface utilisateur pour signaler des problèmes ou des erreurs. Suivez les instructions fournies avec l'alerte pour prendre les mesures nécessaires.

### 6. Module Workload

Explorez vos données sous forme d'un histogramme de charge, à l'aide des options de filtrage et de personnalisation pour afficher les données souhaitées.

### 7. Module Heatmap

Contrôlez l'utilisation de vos ressources sous forme d'une carte thermique. Utilisez les options de filtrage et de personnalisation pour afficher les données souhaitées.

Le code couleur dans l'onglet *Resource Usage* est par défaut le suivant :

* Vert : Ressource correctement chargée (taux d'utilisation = 100%)
* Bleu : Ressource insuffisamment chargée (taux d'utilisation < 100%)
* Rouge : Ressource en surchage (taux d'utilisation > 100%)

Ajustez le taux de disponibilité des effectifs dans l'onglet *Staff*, afin de normaliser la carte thermique.

Les effectifs saisis dans le module *Plan* sont automatiquememt intégrés à la carte thermique. L'utilisateur peut en ajouter d'autres (i.e. non chargées), de manière à les faire apparaître sur la carte thermique.

Si un prénom est détecté, alors l'effectif est par défaut ajusté à l'unité (1 = une ressource full-time). Les effectifs ne correspondant pas à des prénoms doivent être saisis manuellement et sont mis en évidence en rouge.

### 8. Module Follow-up

En cours de développement...

### 9. Support et Contact

Si vous avez des questions, des commentaires ou des suggestions, n'hésitez pas à contacter notre équipe de support à l'adresse suivante : samuel.gutierrez@gadz.org.

En suivant ce manuel d'utilisation, vous devriez être en mesure de profiter pleinement de notre application Dash et d'explorer vos données de charge de travail de manière efficace et intuitive. Merci de votre intérêt et de votre soutien !
