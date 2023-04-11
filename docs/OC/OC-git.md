#Utiliser github
<!-- https://docs.github.com/fr/migrations/importing-source-code/using-the-command-line-to-import-source-code/adding-locally-hosted-code-to-github -->
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
    Si erreur ! [rejected] main -> main (fetch first) error :

    Peut arriver par exemple si un README existait déjà.

    git push -f origin main

Commandes git les plus utilisées :

[cheat-sheet](../ressources/github-cheatsheet.pdf)