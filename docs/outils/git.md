#Utiliser github

##Créer un git à partir d'un dossier local existant

- Créer un repository sur github : add a readme
- Se placer dans mon dossier local : cd /Users/user/monDossierExistant
- `git init -b main`
- `git add *`
- `git commit -m 'initial commit'`
- Copier le lien fourni sur github https et le lier au dossier local : 
  `git remote add origin https://github.com/....git `
- `git remote -v` : Vérifie l'adresse du remote 
- `git push -u origin main` :  Push les changements locaux sur le remote 
- `git push --set-upstream origin main` 



## Enregistrer des modifications
- `git add * ` : ajouter tous les nouveaux fichiers 
- `git commit -m "mon commentaire descriptif"` : Enregistre les changements dans l'historique des versions 
- `git pull`: Récupère tout l'historique du dépôt nommé et incorpore les modifications. git pull est la fusion de deux commandes `git fetch`(pour récupérer le dépôt distant vers le dépôt local) et `git merge` (pour les fusionner).  
- `git push` : Envoie tous les commits de la branche locale vers GitHub
- `git fetch` : Vérifie si le dépôt contient des mises à jour que vous n'auriez pas en local



## Travailler à plusieurs sur un même repo 
- `git checkout main` : Place sur la branche main
- `git pull origin main` : Récupère la dernière version 
- `git checkout -d mybranch` : Crée une branche pour développer notre fonctionnalité
- on réalise des modifications, ajouts etc ... 
- `git add -A` : Ajoute toutes nos modifications
- `git commit -m "message de modification"` : Commente
- `git push origin mybranch` : Push nos modifications réalisées sur notre branche mybranch pour qu'elles soient aussi sur le remote github appelé origin
- `git checkout main` : Replace sur le main
- `git pull origin main` : Récupère les nouveautés de la branche main distante (si d'autres utilisateurs ont réalisé des modifications en même temps)
- `git merge mybranch` : Fusionne la branche main avec notre nouvelle branche mybranch
- `git push origin main` : Transfère cette nouvelle branche modifiée 
- `git branch -d mybranch` : Supprime notre branche de dev

<!-- ##Réaliser une fusion avec les changements dépôt et local
- `git checkout main`: se placer sur la branche principale 
- `git merge mybranch`: pour grouper mybranch dans main  -->



## Résolution d'un conflit 
Si un fichier est modifié en local et sur le dépôt distant, on se trouve dans le cas d'un conflit à résoudre après avoir réalisé un git pull.

- `git status` : pour voir l'état du git local
S'il apparaît "You have unmerged paths.", deux possibilités : soit résoudre le conflit (fix conflicts, soit annuler le merge)

<!-- ##Erreur après un git pull (non liée à un merge)
"hint: You have divergent branches and need to specify how to reconcile them.
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation."
Passer en deux étapes avec git fetch puis git merge  -->

## Ressources
<!-- - `git branch -r`: voir les branches du dépôt -->
- [cheat-sheet](../ressources/github-cheatsheet.pdf) : PDF contenant les commandes de base de github
- https://pcottle.github.io/learnGitBranching/?locale=fr_FR&demo : Site pour visualiser les effets des commandes sur les branches
- https://www.youtube.com/watch?v=USjZcfj8yxE : tutoriel youtube utilisation de github
<!-- - https://www.youtube.com/watch?v=tRZGeaHPoaw&t=8s : tutoriel youtube utilisation de github -->
<!-- http://defeo.lu/in202/tutorials/tutorial4/ -->
## Divers
- `git rm --cached FILENAME` : Annule le suivi d'un fichier déjà archivé 
- Créer un fichier .gitignore pour ne pas que certains fichiers soient envoyés dans le git
- git stash : pour annuler une action précédente 
- Erreur : 

!!! info "en cas d'erreur 'fetch first'"
    Si l'erreur ! [rejected] main -> main (fetch first) error apparait (par exemple si un README existait déjà) :

    `git push -f origin main`

