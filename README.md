# BUT_info-BASH : Systeme bash 

## 1.1 
- Ouvrir un terminal <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd> + <kbd>&uarr;</kbd>
- Chemin absolu de home *iiion


## 1.2 Se repérer et se déplacer 
### cd : Change Directory
revision commande ls et cd
- `cd <nom_fichier>`: permet de se déplacer dans un dossier enfant
- `cd `: permet de se déplacer dans son home, repéré par le ~
- `cd ..` : permet de remonter dans le dossier parent

### ls : list
- `ls ` : permet d'afficher ma liste des dossier et fichiers du dossier actuel

## 1.3 
- `cat <adresse_vers_fichier>` permet de lire les fichier du dossier actuel
- <kbd>Tab</kbd> : autocomplétion du début d'une commande 

## 1.4
 - `ls ..` permet de lister le contenu de home
 - `le <chemin>` permet de lister le contenu d'un chemin 
 - `ls -l` : donne des infos comme les date et les droit sur les fichier lister dans le repertoire
 
## Cours 2 : 
### Nano command

 - `nano <chemin vers un fichier>` : 
    -  Ouvre un éditeur de fichier
    - Commande ^S => Sauvegarder ( `^` = <kbd>ctrl</kbd>)

### Mkdir command
 - `mkdir <repertoir>` :
    -  `mkdir ./doc/` 
    -  `mkdir doc/`
    -  `mkdir /Home/Toto/doc`

    - `mkdir ../../Usr/nachin`
    - `mkdir /Usr/machin/`

    - `mkdir -r /usr/machin/truc/bidule` : (-r = recursive)

    - `mkdir test1 test2 test3 test4` : permet de creer 4 sous dossier en meme temps

### Touch Command 
 - `touch <chemin vers un fichier>` : Permet de mettre a jour (a l'heure / Date) de derniere modification 

 - `touch  <chemin vers fichier inexistant>` : Permet de creer un fichier vide

### Du command 
- `du <chemin vers un dossier` : signifie Disk Usage : permet de connaitre la taille d'un repertoire en Kilo-Byte soit Kilo Octets (512*2 = 1024 bytes)
- `du -s ou --summuerise (somme) <dossier>` : Faire la somme de l'espace disque utilise 
- `du -h ou --human-readable <dossier>` : Affiche la taille avec une unite plus facile a lire 

Taille de votre home 
- `du -sh /home/Toto`
- `du -sh ~`

### rm command : remove

- `rm <chemin de fichier>` : supprime un ficher
- `rm -r ou --recursive<chemin vers dossier>` : Efface les dossier et fichier enfants du chemin specifie 
- `rm -r/` : Efface tout l'ordi

### Taille de fichier 
- bit  -> 0 ou 1
- octet -> 8 bits 
- Ko (Kilo-Octet) -> 1000 (10**3) octets
- Mo (Mega-Octet) -> 1 000 000 (10**6) Octets
- Go (Giga-Octets) -> 1 000 000 000 (10**9) Octets
- To *=(Terra-Octets) -> 10**12 Octets.

### Procesus : (Voir cours de NSI sur Gestion des processus et des ressource dans le drive)

## Cours : 3
## Droits
- ` ls -l ` : -rwxrw---- 1 bob etu  123 sept 22 14h fichier 1.txt ==> Liste les droit de tous les fichier présent dans le repertoir courant
- d : nature dossier ; - : nature fichier ; r : droit de lecture; w : droit d'écriture ; x : droit d'execution
    - droit pour éffectuer les commande : 
        - Droit de lescture :  cat, cp, grep
        - Droit écriture : nano, (rediriger une sortie vers ce fichier (disposer des droits écriture))

### Changer les droits : 
### chmod  : (simple syntax)
- ` <chmod <ugoa><+|-><rwx> FILE...> ` :  permet de changer les droit d'un fichier
- u : propriétair, g : groupe, o : reste du monde, a : toues les catégories de personne Propriétaire, groupe et Other
- droit : 
    - `r` : lecture
    - `w` : ecriture 
    - `x` : execution
- `+` : ajouter des droit 
- `-` : retirer des droits
- `=` : affectation 
- `chmod u-w,go+x <fichier>` 

### chmod syntax octal : 
- `chmod  <octal>` : rwx ==> 111 ==> 2^2 + 2^1 + 2^1 = 7 
- `chmod 760` : rwxrw ==> rwx : 7, rw- : 6, --- : 0
- `chmod 764` : rwx : 7, rw- : 6, r : 4
- `chmod 777` : rwxrwxrwx : donne tous les droit a tous le monde
- `chmod XXX` : 1er X : Droit; 2eme X user; 3eme X : Groupe

### Move command
- `mv <adress de départ> <adresse d'arrivée>` : Déplace un fichier
- `mv fichier1 fichier2` : rename fichier1 e, fochier 2
- `mw <fichier> /home/toto/document/fichier2` : déplacele fichier cer le nouvel emplacement
- `mv <repertoire> <autre repertoire> ` : deplace tout le dossier dans le repertoire choisis
- `mv <fichier> <repertoire+autre nom>` : deplace et renomme le fichier 
- `mv <fichier> ../ ` : deplace dans le repertoire parent


### Copie command : CP
- `cp <fichier> <repertoir>` : copie dans un autre repertoire
- `cp ~/toto/turc.txt /home/toto/truc.bash` : copie et renomme
- `cp truc.txt mashin.txt` : copie dans le même repertoire 
- `cp fichier1 fichier2 fichier3 fichier4 "/mon repertoir/"` : copie de plusieurs fichiers
### MV et CP option : 
- `-n` : permet de ne pas demander la confirmation si on ecrase un fichier. 

### Manuel
- `man <command>` : ouvre le manuel
- <kbd>&uarr;</kbd> et <kbd>&darr;</kbd> : se déplacer
- <kbd> q </kbd> : quitter
- `/<text>` : permet de faire une recherche a partir d'un terme 

### Redirection de sortie : 
- sortie standart : sortie execution de command
- sortie erreur : erreur
- `<command> > <fichier txt>` :  sauvegarde la sortie de la de la commande dans le fichier text en remplacant le contenu
- `<command> >> <fichier, chemin absolu ou relatif>` : ajoute au fichier le contenue de la sortie de la command, sans remplacer le contenu précédent 
- `<command> 2> <fichier.log>` : signifie qu'on souhait que rediriger la sortie d'erreur dans le fichie log
- `<command> 2> <fich.log erreur> > <fich.txt erreur>` : Signifie que l'on veut rediriger les deux sortie, les erreur dans le fichier log et la sortie standart dans le fichier txt
- `<command> 2> <fich.log erreur> >> <fich.txt erreur>` : Même commande sauf que les sprtie standart s'ajoute au fur et a mesure
- `<command 2> /dev/null` :  envoie la sortie d'erreur dans le trou noir
- `<command> 2> /dev/null > <fichier.txt>` : envoie la sortie d'erreur dans le trou noir mais la sortie standart dans le fichier txt

### Script : 
- `#!/bin/bash <command> <$parameter>` : lance la commande avec l'attribut ==> Shebang
- `a=$(<command>)` : stock le resultat une commande dans une variable dans le fichier sh. Les " " (espace) ne marche pas et garder les ()
- `\<character>` : `\` est le caractère d'échapment permet de rajouter des espace ou `" ou '` dans un seul argument
- `<command> $<charactère ou mot>` : `$1` sera l'attribut mis en paramètre lors de l'apelle de la commande
- Trouver l'interpreteur : `which bash`
- 1er ligne de fichier script : `#!/bin/bash`


### Script et attribut : 
- dans le script si son ecrit `echo Bonjour $1` ==> si on appel le fichier tel que : fichier.sh Test ==> Bonjour Test (resultat)
- `$(whoami)` : interprete le resultat de la commande whoami 
    - `echo Bonjour $(whoami)` : resultet = echo '''mon nom d'utilisateur'''

### Variable : 
-`nom=$(<command>)`: variable


### Install Packages 
Advande packages tool : `apt`
- `apt list --installed` : retourne la list de tout les paquet installés
- `sudo apt install <package_name>` : installe le packet demander pour installer le logiciel
- `apt-cache search <key word>` : rechercher un packet par mot clé dans la list de packet 
- `sudo apt update` : mettre a jour la liste de paquets disponibles
- `sudo apt upgrade` : mettre a jour la liste de paquet installés