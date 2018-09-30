# Utilisation de la ligne de commande sous Windows

### Comment accéder à la ligne de commandes?

Appuyez en même temps sur la touche Windows <kbd>&#8862;</kbd> et la touche <kbd>R</kbd>. Ceci lance la fenêtre de la commande d'exécution. Tapez dans cette fenêtre `cmd` (pour la ligne de commande classique) ou `PowerShell` (pour une version évoluée). Ce tutoriel utilise uniquement `cmd`. Vous avez maintenant accés à l'interpréteur en ligne de commande.
```cmd
Microsoft Windows [version 6.3.9600]
(c) 2013 Microsoft Corporation. Tous droits réservés.

C:\Users\username>
```
Après les deux premières lignes de présentation, l'invite de commande affiche le *prompt*, qui signale que vous pouvez maintenant entrer une nouvelle commande. Ce prompt vous renseigne également sur le *répertoire courant*, qui est celui sur lequel l'interpréteur pointe actuellement: dans ce cas `C:\Users\username` représente le répertoire `username` (votre nom utilisateur) situé dans le répertoire `Users` situé dans le disque `C:`.

### Changer le répertoire courant

Changer de répertoire se fait grace à la commande `cd` (change directory). Cette commande prend pour argument le répertoire dans lequel on veut se déplacer.

#### Utilisation de `cd` avec un chemin absolu
Un *chemin absolu* indique tout le chemin depuis la racine (par exemple sous Windows le disque `C:`) jusqu'au fichier ou répertoire que l'on veut atteindre.
```cmd
C:\Users\username> cd C:\Windows

C:\Windows> cd C:\Users\username\Documents

C:\Users\username\Documents>
```
:wink: A tout moment vous pouvez utiliser la touche <kbd>Tab</kbd> pour obtenir la complétion du nom de répertoire que vous êtes en train d'écrire. Ainsi si vous avez écrit `cd C:\U`, presser la touche <kbd>Tab</kbd> va compléter automatiquement en `cd C:\Users`, vous n'avez plus qu'à continuer à écrire `cd C:\Users\us` puis presser <kbd>Tab</kbd> pour obtenir `C:\Users\username`, ... Apprenez à travailler rapidement

#### Utilisation de `cd` avec un chemin relatif
Un *chemin relatif* indique tout le chemin depuis le répertoire courant (par exemple `C:\Users\username`) jusqu'au fichier ou au répertoire que l'on veut atteindre. Notons que  `.` représente le répertoire en cours d'évaluation et `..` le répertoire qui le contient.
```cmd
C:\Users\username> cd ..

C:\Users> cd .

C:\Users> cd username

C:\Users\username> cd .\Documents\..

C:\Users\username>
```
### Examiner le répertoire courant

Afin de naviguer dans les répertoires, il est souvent utile de pouvoir examiner ce qu'il y a dans le répertoire courant. Pour cela dex commandes sont utiles: `dir` et `tree`.

#### Utilisation de `dir`
La commande `dir` (*directory*) liste tous les fichiers et les répertoires contenus dans un répertoire.
```cmd
C:\Users\username\Documents> dir
 Le volume dans le lecteur C s'appelle mainDisk
  Le numéro de série du volume est DA13-FB36
  
  Répertoire de C:\Users\username\Documents
  
30/04/2016  16:21     <DIR>                .
30/04/2016  16:21     <DIR>                ..
17/08/2018  01:17                     1148 documentation.txt
24/12/2017  23:59     <DIR>                GitHub  
02/06/2016  13:01     <DIR>                LaTeX
02/05/2016  12:34     <DIR>                Programmation
15/08/2018  13:47                    32167 rapport.pdf 
               2 fichier(s)                      33415 octets
               5 Rép(s)          34 189 342 720 octets libres

C:\Users\username\Documents>
```
La commande `dir` a trouvé 5 répertoires et 2 fichiers dans le répertoire courant. Les répertoires sont indiqués par `<DIR>`. Noter que `.` (le répertoire courant) et `..` (le répertoire contenant, dans ce cas `C:\Users\username`) sont comptabilisés dans les 5 répertoires. On peut aussi utiliser différentes options, par exemple `dir /AH` qui affiche les fichiers et répertoires cachés (et uniquement ceux-ci). La liste complète des options possibles est donnée par la commande `help dir`. On peut également passer en paramètre de `dir` le chemin (absolu ou relatif) d'un fichier dont on veut lister le contenu.
```cmd
C:\Users\username\Documents> dir /AH GitHub
 Le volume dans le lecteur C s'appelle mainDisk
  Le numéro de série du volume est DA13-FB36
  
  Répertoire de C:\Users\username\Documents\GitHub
  
25/12/2017  00:03     <DIR>                .git 
               0 fichier(s)                          0 octets
               1 Rép(s)          34 189 342 720 octets libres

C:\Users\username\Documents>
```
Ici le répertoire `C:\Users\username\Documents\GitHub` ne contient qu'un répertoire invisible (i.e. dont le nom commence par `.`), le répertoire `.git`.

#### Utilisation de `tree`
La commande `tree` affiche une représentation en mode texte de l'arborescence de répertoires sous un répertoire donné (par défaut le répertoire courant). Avec l'option `/A`, cette représentation n'utilise que des cracatères ASCI, avec l'option `/F`, les fichiers sont également indiqués. Le répertoire racine peut également être donné en argument.
```cmd
C:\Users\username\Documents> tree /A LaTeX
Structure du dossier pour le volume mainDisk
Le numéro de série du volume est DA13-FB36
C:\USERS\USERNAME\DOCUMENTS\LATEX
+---Cours
|   +---Cours Maths
|   |   +---chapters
|   |   +---geogebra
|   |   \---pictures
|   \---Cours Prog
|       +---C++
|       +---Java
|       +---Python
|       \---Scheme
+---DnD
    +---rules
    \---scenarios
C:\Users\username\Documents>
```

