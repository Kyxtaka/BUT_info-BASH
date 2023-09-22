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

### Move command
- `mv <adress de départ> <adresse d'arrivée>` : Déplace un fichier
- `mv fichier1 fichier2` : rename fichier1 e, fochier 2
- `mw <fichier> /home/toto/document/fichier2` : déplacele fichier cer le nouvel emplacement

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
`#!/bin/bash <command> <$parameter>` : lance la commande avec l'attribut
`a=$(<command>)` : stock une commande dans un variable dans le fichier sh 
