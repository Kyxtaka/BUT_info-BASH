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
- `du <chemin vers un dossier` : signifie Disk Usage : permet de connaitre la taille d'un repertoire

### rm command : remove

- `rm <chemin de fichier>` : supprime un ficher
- `rm -r ou --recursive<chemin vers dossier>` : Efface les dossier et fichier enfants du chemin specifie 
- `rm -r/` : Efface tout l'ordi
