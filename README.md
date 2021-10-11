# TP Docker_1 - Ynov DevOps B3


## **Rendu :** Un fichier pdf : DEVOPS_DOCKER1_[NOM]\_[PRENOM].md

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

- Lancer un container Ubuntu en background qui affiche la date toutes les 2 secondes.

<details>
  <summary>Hint</summary>
  
  
  ```bash
  while true; do date; sleep 2; done
  ```
  
</details>

- Regarder les logs en temps réel depuis l'hôte
- Rentrer dans le container de afficher les processus
- Kill le container
  - Créer un fichier d'explication sur `docker kill`. Que se passe-t-il côté systeme lorsqu'on lance la commande pour killer un container ? 
 
 <details>
  <summary>Hint</summary>
  
  Les utilitaires `ptrace` ou `ltrace` peuvent vous aider
</details>

## Exercice 2 : Clean Container

- Afficher tout les containers de votre hôte
  - Running
  - Stopped
  - Exited
- Supprimer tout les containers stoppés
- Afficher toutes les images
- Supprimer les images en doublon

- En **une** commande il faut : 
  - Lancer un container ubuntu avec la commande d'affichage de l'heure 
  - Rentrer dans le container
  - Supprimer le container lorsqu'on quitte le container

