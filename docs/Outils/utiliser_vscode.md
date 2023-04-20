# Comment coder en python sur VS Code sur MacOS 
<!-- EM 20.04.23 v1 -->

1. Télécharger et installer Visual Studio Code (gratuit)
2. Dans la barre de gauche, descriptions des icônes : 
   1. fichiers : explorateur pour voir les fichiers ouverts
   2. loupe : pour recherche dans fichier
   3. Git 
   4. Debugger 
   5. Installer des extensions
3. Ajouter extensions Python (la plus populaire)
4. Pour pouvoir lancer VSCode avec le terminal via la commande Code il faut : 
   1. Ouvrir le menu Commande Palette (Cmd+Shift+P)
   2. Taper shell commande et cliquer sur Shell Command: Install 'code' command in PATH command.
   3. VSCode pourra être démarré à partir de la commande `code .`
5. Un workspace est un endroit pour lequel on peut avoir ses propres préférences et spécificités.
Chaque projet dans vscode doit être un workspace. Il faut donc toujours ouvrir vos projet par "menu File > open folder" et pas en ouvrant seulement des fichiers contenu dans votre projet avec "menu File > open folder".



# Création d'un environnement virtuel en python

Un environnement virtuel permet d'installer des packages python uniquement dans cet environnement (et non dans l'ensemble de base des packages). 

- Pour installer un package python on utilise : `pip3 install nomDuModule`. Par exemple : `pip3 install panda`
- Pour voir les package installés : `pip3 freeze`
- Pour donner les packages à installer aux autres programmeurs, il faut créer un fichier requirements.txt qui contient tous les noms de ces packages : `pip3 freeze > requirements.txt`


1. Se placer dans le dossier de son projet
2. `python -m venv env` : par convention on appelle toujours un environnement virtuel env 
3. `source env/bin/activate`: pour l'activer . Il est nécessaire de toujours l'activer lorsque l'on veut travailler avec
4. `deactivate`: pour désactiver l'environnement virtuel python
5. pip3 list : liste les paquets installés dans l'environnement virtuel

# Conda, Miniconda, Anaconda

Conda est un gestionnaire de paquets multiplateforme qui permet l’installation et la mise à jour de paquets (notamment Python).
Permet d'installer dans le dossier d’installation de Conda, sans besoin d’accès administrateur.

On peut au choix installer Anaconda ( = gestionnaire de paquet Conda + bibliothèques scientifiques + un environnement de développement…) ou Conda + qq bibliothèques en installant miniconda ou installer conda seulement comme gestionnaire de paquet.
(double emploi avec pip3).



Si l'on a déjà une version de Python installée, Conda demande lors de l’installation s’il faut mettre la version de Conda par défaut (consiste à redéfinir le PATH pour y ajouter le dossier bin de Conda.)
Ainsi, les scripts lancés en tant qu’utilisateur à la main, de même que la commande python utiliseront le python de Conda, tandis que les scripts python du système continueront à utiliser le python du système.
Si vous ne le faites pas, alors en lançant la commande python, vous arriverez sur le python système. Les bibliothèques installées avec Conda ne seront pas accessibles. Il vous faudra explicitement lancer la commande python du répertoire d’installation Conda pour avoir accès à ces dernières.

`conda update -n base -c defaults conda` : mettre à jour conda


`conda install noms_paquets`: pour installer un paquet
`conda update noms_paquets`: pour mettre à jour un paquet
`conda update --all`: mettre à jour tous les paquets
`conda remove noms_paquets` : supprimer un paquet
`conda list`: lister les paquets


`conda create -n myenv` : créer un environnement dans conda
`conda install -n myenv noms_paquets` : pour installer un paquet dans myenv
`conda info --envs` # forme courte : -e 
`conda env list` : pour lister les environnements (celui avec * est le courant) sinon `conda info --envs`
`conda activate myenv` : pour activer un environnement (celui de base s'appelle base: conda activate base)
`conda deactivate` : pour désactiver un environnement 
`conda env remove --name myenv` : supprimer un environnement

Par défaut les environnements sont installés dans le dossier envs du dossier conda. 
Avec pip on indique les packages dans un fichier requirements.txt, en général avec conda c'est dans un fichier environment.yml
`conda env create -f environment.yml`: pour créer un environnement à partir du fichier environment.yml fourni. 
Puis `conda activate myenv`
`conda env export > environment.yml` : pour exporter l'environnement actuel.

On peut quand même utiliser pip dans un environnement conda, mais installer le plus possible les extensions avec conda d'abord. 


# Des extensions recommandées pour VSCode

- python
- Code Spell Checker et French - Code Spell Checker pour la correction orthographique
- git graph : visualisation des gits
- Material Icon Theme : pour de jolies icones

bjoun cooment 
 
