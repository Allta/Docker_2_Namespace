# Correction Docker Namespace

## Exercice 1 : 

L'objectif de cet exercice est de démontrer l'utilité des namespaces dans l'architecture des containers Docker.
Comme vu en cours, les namespaces sont un des principes d'isolation des processus qui sont à l'origine des containers.
Chaque namespaces (UTS,USER,PID etc...) permettent d'isoler des ressources (Utilisateurs, PID, hostname, point de montage etc..) entre différents processus sur une machine Linux.


Le flag `--pid=host` permet de partager le namespace **pid** entre l'hôte et le container.

![docker run ](https://i.imgur.com/nP8nPoM.png)

Le container ubuntu et notre hôte partagent le même namespace donc depuis le container nous pouvons voir et interargir avec les processus de l'ĥote.
La commande ps nous montre que le **PID 1** est le processus **d'initialisation** de la machine Linux et non le programme **bash** que nous avions spécifié lors du lancement du container. Cela montre bien que depuis le container nous ayons bien accés aux processus de l'hôte.

![docker ps](https://i.imgur.com/YdMw8iS.png)

Pour confirmer cette hypothèse nous pouvons vérifier les ID des namespaces liés à chaque processus.
Toutes les informations liées aux processus sont retrouvable dans le dossier `/proc/<PID>/`.

![namespaces](https://i.imgur.com/JbT32qz.png)

Ci-dessus : Le terminal supérieur présente les namespaces du container et celui du bas ceux de l'hôte. On constate bien que l'ID du namespace PID est le même pour les 2 processus. Le namespace UTS est lui différent et nous pouvons le constater facilement en regardant l'hostname du container et celui de l'hôte, ce ne sont pas les mêmes donc le namespace UTS ne sont pas partagés

Note : `/proc/self`équivaut au process actuellement en cours qui appele le symlink /proc/self
Source : https://unix.stackexchange.com/questions/333225/which-process-is-proc-self-for 
Code source du kernel Linux : https://elixir.bootlin.com/linux/latest/source/fs/proc/self.c 


![process container](https://imgur.com/yGd0q1p.png)

Dans le container, nous créons une variable d'environnement `FOO` ainsi qu'un processus qui va tourner non stop.
Le processus ici sera `sleep`.
Puisque le namespace pid est partagé nous devrions pouvoir le retrouvé depuis notre hôte.


Depuis l'hôte nous pouvons retrouver le 

![ps host](https://i.imgur.com/f3y6T4q.png)

![process environ](https://i.imgur.com/HfCKF2g.png)
    Créer une variable d'environnement dans votre container
    Créer un processus sur le container. Exemple : Une boucle while infinie qui affiche l'heure.
    Retrouver ce processus depuis votre hôte et afficher la variable d'environnement.
