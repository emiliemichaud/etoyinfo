#Utiliser github

##Créer un git à partir d'un dossier local existant

- Créer un repository sur github : add a readme
- Se placer dans mon dossier local : cd /Users/user/monDossierExistant
- `git init -b main`
- `git add *`
- `git commit -m 'initial commit'`
- Copier le lien fourni sur github https et le lier au dossier local : 
  `git remote add origin https://github.com/....git `
- `git remote -v` : pour vérifier l'adresse du remote 
- `git push -u origin main` :  Push les changements locaux sur le remote que l'on a spécifié comme origine
- `git push --set-upstream origin main` 

!!! info "en cas d'erreur 'fetch first'"
    Si l'erreur ! [rejected] main -> main (fetch first) error apparait (par exemple si un README existait déjà) :

    `git push -f origin main`

##Enregistrer des modifications
- `git add * ` : ajouter tous les nouveaux fichiers 
- `git commit -m "[message descriptif]"` : enregistre les changements dans l'historique des versions 
- `git pull`: Récupère tout l'historique du dépôt nommé et incorpore les modifications. git pull est la fusion de deux commandes `git fetch`(pour récupérer le dépôt distant vers le dépôt local) et `git merge` (pour les fusionner).  
- `git push` : Envoie tous les commits de la branche locale vers GitHub
- `git fetch` : permet de vérifier si le dépôt contient des mises à jour que vous n'auriez pas en local

##Annuler le suivi d'un fichier déjà archivé 
- `git rm --cached FILENAME`

##Réaliser une fusion avec les changements dépôt et local
- `git checkout main`: se placer sur la branche principale 
- `git merge mybranch`: pour grouper mybranch dans main 


##Commandes git les plus utilisées :
- `git branch -r`: voir les branches du dépôt
[cheat-sheet](../ressources/github-cheatsheet.pdf)

##Résolution d'un conflit 
- Si un fichier est modifié en local et sur le dépôt distant, on se trouve dans le cas d'un conflit à résoudre après avoir réalisé un git pull.

- `git status` : pour voir l'état du git local
S'il apparaît "You have unmerged paths.", deux possibilités : soit résoudre le conflit (fix conflicts, soit annuler le merge)

<!-- ##Erreur après un git pull (non liée à un merge)
"hint: You have divergent branches and need to specify how to reconcile them.
hint: You can replace "git config" with "git config --global" to set a default
hint: preference for all repositories. You can also pass --rebase, --no-rebase,
hint: or --ff-only on the command line to override the configured default per
hint: invocation."
Passer en deux étapes avec git fetch puis git merge  -->