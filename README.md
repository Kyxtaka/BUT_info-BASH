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
- `nb=$(ls -l|wc -l)` : `ls -l|wc -l` envoie la la sortie de la commande `ls -l` dans `wc` et `wc -l` calcul le nombre de ligne soit `nb` obtient le nombre de ligne retourner par `ls *l`
- `$#` : permet d'obtenir le nombre d'argument dans un fichier sh 


### Script et attribut : 
- dans le script si son ecrit `echo Bonjour $1` ==> si on appel le fichier tel que : fichier.sh Test ==> Bonjour Test (resultat)
- `$(whoami)` : interprete le resultat de la commande whoami 
    - `echo Bonjour $(whoami)` : resultet = echo '''mon nom d'utilisateur'''


### Script et expression :
- `expr <number> + <number>` : addition des deux nombres
- `expr <number> - <number>` : la meme en soustraction
- `expr <number> / <number>` : Division
- `expr <number> \+ <number>` : multiplication, bien penser a passer `*` en char. d'echappement

### Variable : 
-`nom=$(<command>)`: variable

### Jokers : liste de char : \*[] ; \*[]\* ; []\* 
- `<commande>  [<char1><char2><charN>]*` : prend en argument tout les fichier commencant par le `<char>` ou `char2` ou `charN`
- `<commande> *[<char1><char2><charN>]*` : prend en argument tout les fichier contenant par le `<char>` ou `char2` ou `charN`
- `<commande> *[<char><char2><charN>]` : prend en argument tout les fichier se terminant par le `<char>` ou `char2` ou `charN`

### Jokers : dict de char : \*{} ; \*{}\* ; {}\* 
- `<commande>  {<str1>,<str2>,<str3>}*` : prend en argument tout les fichier commencant par les chaine de char. `<str1>` ou `str2` ou `str3`
- `<commande> *{<str1>,<str2>,<str3>}*` : prend en argument tout les fichier contenant par les chaine de char `<str1>` ou `str2` ou `str3`
- `<commande> *{<str1>,<str2>,<str3>}` : prend en argument tout les fichier se terminant par les chaine de char `<str1>` ou `str2` ou `str3`

### Jokers : extention : *.{} 
- `<commande> *.{<ext1>,<ext2>,<ext3>}` : prend en argument tout les fichier se terminant par les ext `<ext1>` ou `ext2` ou `ext3`
- `{me,re}*s` : prend en argument tout les fichier commençant pas `me` ou `re` et se terminant par `s`

### Back to Droit : Dossier / repertoire 
- Avec `ls -l` : si dans la premiere colonne on a `drwxrwxr-x`, si ca commence par un d, c'est que c'est un dossier. Dans le cas contraire c'est un fichier
- Si pour le dossier on a le droit `x` c'est qu'on peut le traverser entre autre utiliser la commande `cd`, mais ne veut pas forcement dire que je peux voir ou ecrire le contenu de ce dossier
- Par contre si j'ai les droits d'ecriture et de lecture mais pas d'execution `rw-` je ne pourrais pas creer ni ouvrir de fichier 
- Pour effectuer les commande `ls et find` il faut avoir le droit  `r` mais il faut egalement le droit `x`
- Note si on fait `ls` dans un dossier dont  on n'a le droit d'execution `x`, on obtien un message d'erreurs pour chaque fichier dans le repetoire mais le nom de ces fichier s'affiche :
    -  `ls: cannot access 'Bureau/exemple5': Permission denied `<br> `ls: cannot access 'Bureau/exemple6': Permission denied `<br> `exemple5  exemple6 ` <br> `total 0` <br>
Car ls -ls -l cherche a connaitre la date, le proprietaire, la date de modification et etc donc quand on execute `ls -l` dans un dossier où on a pas le droit d'execution `x` alors la commande nous renvoie :
    - `????????? ? ? ? ?            ? exemple5` <br>`????????? ? ? ? ?            ? exemple6`

- Pour supprimer un fichier dans un dossier il faut juste les droit `r et x` pour le dossier et le droit `w` pour le fichier car on modifie juste le contenu

### Droit : Les inodes 
System de fichier : C'est une façon de stocker les informations et de les organiser dans un espace disque
Metadonnées d'un fichier : Droit - Proprétaire - groupe - taille du fichier - date de derniere modif - on sont stocké les données
- Les blocs de données contiennent les données des fichiers (ce qu'on va voir en regardant le contenu hexadécimal d'un fichier)
- les inodes contiennent les méta-données : permissions, taille du fichier, date de dernière modification, etc. ainsi que l'indication de l'endroit où se trouvent les données associées
`ls -i` : permet d'obtenir la liste des numéros d'inodes des fichiers courants
- Les inodes contiennent les métadonnées des pointeurs vers les données constituant les fichiers
- Des fichier différents sur des partision espace disque différents peuvent avoir les même numéros inodes
- Un Dossier est un fichier associant a chaque nom de fichier un numéro d'inode
    - A retenir: un dossier est un fichier associant à chaque nom de fichier un numéro d'inode. Les dossiers contiennent seulement l'association "nom de fichier -> numéro d'inode"


### Install Packages 
Advande packages tool : `apt`
- `apt list --installed` : retourne la liste de tout les paquet installés
- `sudo apt install <package_name>` : installe le packet demander pour installer le logiciel
- `apt-cache search <key word>` : rechercher un packet par mot clé dans la list de packet 
- `sudo apt update` : mettre a jour la liste de paquets disponibles
- `sudo apt upgrade` : mettre a jour des paquet installés
- `sudo apt purge` : desinstaller un paquet

## Redirection d'entrée standard a partir d'un fichier :
 - `<command> < <fichier>` : redirige l'entrée standard par un fichier 
 - `tr <somme letter> <change letter>` chaque lettre du premier argument en chaque lettre du deuxieme 

## Condition if en bash : 
- `test -e /tmp/` peut aussi s'ecrire ` [ -e /tmp/ ]` : `[` et `]` designe la commande test, il faut respecter les ESPACES
- `if [ bonjour == bonjour ]; then  echo AAAA; else  echo BBBB; fi` : syntaxe, bien respecter les espace
`#/bin/bash` : script qui lit son entree standard
structure du if : <br>
`if <condition>`<br>
`then`<br>
`...`<br>
`...`<br>
`...`<br>
`else`<br>
`...`<br>
`...`<br>
`...`<br>
`fi`

# Retour scripts
## 
`#/bin/bash` <br>
`read Phrase`<br>
`echo $Phrase`
##
`#/bin/bash`<br>
`read mot`<br>
`tr abc....z ABC....Z  < $mot` : script qui prend en argument un mot et le renvoir en MAJ.
##
`#/bin/bash`<br>
`tr [:lower:] [:upper:] < $1 (>>Fichier)`<br>
- `./script.sh 'coucou' ==> argument`
##
`#/bin/bash`<br>
`echo Donner l'addresse du fichier`<br>
`read fichier`<br>
`if [ -x $fichier]`<br>
`then`<br>
`echo ok`<br>
`else`<br>
`chmod u+x $fichier`<br>
`fi`

# Pipeline
` <commande1> | <commande dont l'entree standard est command1` :
`head -X <file path>` : affichier les X premiere ligne d'un fichier file, X est un int
`tail -X <file path>` : affichier les X derniere ligne d'un fichier file, X est un Int

## note :
- `cut -d ':' -f 1 /etc/passwd ` : 
- en bash `read` : permet d'ouvrir un entree standard 
- insérer un image en MD : `![./image.jpg]()`
- `wc` : command wordcount aui permet de compter le nobre de ligne dans un fichier 
- `nb=$(ls -l|wc -l)` : `ls -l|wc -l` envoie la la sortie de la commande `ls -l` dans `wc` et `wc -l` calcul le nombre de ligne soit `nb` obtient le nombre de ligne retourner par `ls *l`


# A faire avant semaine : 
- 6.2 (pas long)
- ! 6.3 redirection
- !! 6.4 Conditions
- !! 7.1 Pipeline

- 8 Boucle for