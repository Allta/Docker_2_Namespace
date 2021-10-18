# TP Docker_2_Namespace - Ynov DevOps B3


## **Rendu :** Un fichier MD : DEVOPS_DOCKER1_[NOM]\_[PRENOM].md

Vous avez un template de rendu dans le repo. 
Pour chaque étape, documenter vos actions : 

        Screenshot commande + output
        Explication d'une ou 2 ligne sur ce que fait la commande
        
A chaque exercice rajouter un titre et le nom de l'exercice. La syntaxe ainsi que l'upload de l'image sont décrit dans des liens en haut du template.

:bangbang::bangbang: Pensez à renommer le fichier avec votre **Nom** et **Prénom**

:sparkles: Une fois le TP et le rendu terminé commitez et pushez le dans le repo. :sparkles:
  
### Tips   
Si vous avez des problèmes sur une command utilisez `docker [command] --help`.

:raising_hand: Si vous avez des soucis n'hésitez pas à m'appeler. 
 
## Exercice 1: Running container

- Lancer un container Ubuntu en partageant le namespid `PID` avec l'hôte
- Créer une variable d'environnement dabs votre container
- Créer un processus sur le container. Exemple : Une boucle while infinie.
- Retrouver ce processus depuis votre hôte et afficher la variable d'environnement. 
