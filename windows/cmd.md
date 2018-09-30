# Utilisation de la ligne de commande sous Windows

### Comment accéder à la ligne de commandes?

Appuyez en même temps sur la touche Windows <kbd>&#8862;</kbd> et la touche <kbd>R</kbd>. Ceci lance la fenêtre de la commande d'exécution. Tapez dans cette fenêtre `cmd` (pour la ligne de commande classique) ou `PowerShell` (pour une version évoluée). Ce tutoriel utilise uniquement `cmd`. Vous avez maintenant accés à l'interpréteur en ligne de commande.
```command
Microsoft Windows [version 6.3.9600]
(c) 2013 Microsoft Corporation. Tous droits réservés.

C:\Users\username>
```
Après les deux premières lignes de présentation, l'invite de commande affiche le *prompt*, qui signale que vous pouvez maintenant entrer une nouvelle commande. Ce prompt vous renseigne également sur le *répertoire courant*, qui est celui sur lequel l'interpréteur pointe actuellement: dans ce cas `C:\Users\username` représente le répertoire `username` (votre nom utilisateur) situé dans le répertoire `Users` situé dans le disque `C:`.

### Changer le répertoire courant

Changer de répertoire se fait grace à la commande `cd` (change directory). Cette commande prend pour argument le répertoire dans lequel on veut se déplacer.
#### Utilisation de `cd` avec un chemin absolu
```command
C:\Users\username> cd C:\Users\username\Documents

```
