# Les fondamentaux de Git


Create a new repository on the command line :

echo "# btp-projet-ia" >> README.md

git init            # Cette commande initialise un nouveau dépôt Git dans le répertoire courant. 
                    # Elle crée un dossier caché .git qui contient toute la structure nécessaire pour le versionnement de votre projet.

git add README.md   # Cette commande ajoute le fichier README.md à la zone de staging (index). 
                    # Cela signifie que le fichier est prêt à être inclus dans le prochain commit. Les fichiers doivent être "stagés" avant d'être commités.

git commit -m "first commit"    # Cette commande crée un commit (snapshot) avec tous les fichiers dans la zone de staging. 
                                # L'option -m permet de spécifier directement le message du commit ("first commit"). 
                                # Ce commit devient le premier point de sauvegarde dans l'historique de votre projet.

git branch -M main  # Cette commande renomme la branche actuelle en "main". 
                    # L'option -M force le renommage même si une branche "main" existe déjà. Par défaut, Git créait une branche "master", 
                    # mais la convention moderne privilégie "main" comme nom de branche principale.

git clone https://github.com/wasim-kasmi/btp-projet-ia.git # Clone un repo distant vers l'ordinateur local.

git remote add origin https://github.com/wasim-kasmi/btp-projet-ia.git  # Cette commande configure un dépôt distant nommé "origin" qui pointe vers votre dépôt GitHub.
                                                                        # Le nom "origin" est une convention standard pour désigner le dépôt distant principal. 
                                                                        # Cela permet à Git de savoir où envoyer vos modifications.

[Différences entre git clone et git remote add origin](/Cours/Git/Differences_git_clone_git_remote_add.md)                                                                        

git push -u origin main     # Cette commande envoie (push) votre branche locale "main" vers le dépôt distant "origin". 
                            # L'option -u (ou --set-upstream) établit un lien de suivi entre votre branche locale et la branche distante, 
                            # ce qui simplifie les futurs git push et git pull (vous n'aurez plus besoin de spécifier "origin main").


git fetch origin {nom de la branche}    # Pull une branche du repo distant origin

git pull origin {nom de la branche}     # Pull une branche du repo distant origin vers la branche actuelle (fait un merge)

git restore --staged {nom du fichier}   # Enlève un fichier de la zone d'attente Git


Situation :

On change de branche et il y a des fichiers qui persistent de la branche précédente.

git clean -fd {nom du fichier/dossier}
git clean -fdX {nom du fichier/dossier} inclu aussi les fichiers ignorés (caches etc.)


Renommer la branche actuelle dans git :

git branch -m {nouveau nom}

git rm fichier  # Supprime le fichier du disque et stage la suppression

git add -u      # Stage les suppressions/modifications des fichiers déjà suivis
