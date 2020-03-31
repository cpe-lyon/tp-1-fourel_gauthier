***FOUREL Raphael / GAUTHIER Charlotte***
 
 
# Compte rendu TP1


## Prise en main de l’interpréteur de commandes --> Manuel

### 1. A l’aide du manuel, identifiez le rôle de la commande which

### 2. Quand on consulte une page du manuel, comment peut-on rechercher un terme (par exemple, chercher le terme option dans la page de manuel de which ?

### 3. Comment quitte-t-on le manuel ?

### 4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?

- **Commande man**: Permet d'avoir le manuel d'une commande  
- **Commande which** : localiser une commande, renvoit le chemin des fichiers passé en argument  
  Dans man, comment peut-on rechercher un terme --> Une fois le manuel ouvert */[termeRecherché]*  
  On quitte la manuel en appuyant sur la touche **Q**  
-  **man 6 intro** : Information sur une section, affiche la première page de la section 6, chaque section de la bibliothéque man possède des informations différente. La section 6 décrit les jeux et petit programmes amusant disponible sur le système. 

## Prise en main de l’interpréteur de commandes --> Navigation dans l’arborescence des fichiers 

### 1. allez dans le dossier /var/log
 Dossier var/log --> cd /var/log

### 2. remontez dans le dossier parent (/var) en utilisant un chemin relatif
Remonté dans le dossier de var --> cd ..

### 3. retournez dans le dossier personnel
Remonté dans le dossier personnel --> cd 
 
### 4. revenez au dossier précédent (/var) sans utiliser de chemin

### 5. essayez d’accéder au dossier /root ; que se passe-t-il ?
Si on essaye d'accèder au dossier root --> permission denied --> on n'a pas les droits

### 6. essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez
Avec la commande sudo root --> Commande not found car sudo exécute un programme. 
 
### 7. à partir de votre dossier personnel, créez l’arborescence suivante :
Créer l'arborescence -- > mkdir Dossier1 Dossier2 Dossier2/Dossier2.1 Dossier2/Dossier2.2; touch Dossier1/Fichier1 Dossier2/Dossier2.2/Fichier2 Dossier2/Dossier2.2/Fichier3

### 8. revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ?
 Suppresion --> rm Fichier1 --> fonctionne très bien cependant rm Dossier1 ne fonctionne pas 

### 9. quelle commande permet de supprimer un dossier ?
Pour supprimer un dossier il faut utiliser rmdir uniquement si le dossier est vide 

### 10. que se passe-t-il quand on applique cette commande à Dossier2 ?
Si on applique dans dossier 2 rmdir cela ne fait rien car le dossier n'est pas vide 

### 11. comment supprimer en une seule commande Dossier2 et son contenu ?
Il faut utiliser rm -r Dossier2 pour supprimer le dossier2 

## Prise en main de l’interpréteur de commandes --> Commandes importantes

### 1. Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?
Afficher l'heure --> date -u +%k:%M (9:38) ; date +%H (09); le u pour afficher en universel en UTC (pas obligatoire).
La commande time donne la durée d'éxécution d'une commande coté user , client et systeme. 

### 2. Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ?
ls et la --> la permet d'afficher les fichiers cachés, les fichiers démarrant par un point sont des fichiers cachés

### 3. Où se situe le programme ls ?
Trouvé le chemin de ls --> which -a ls --> ls se trouve dans /bin/ls ( -a donne tous les endroits ou se trouve la commande) 

### 4. Essayez la commande ll. Existe-t-il une entrée de manuel pour cette commande ? Utilisez les commandes alias ou alias pour en savoir plus sur la nature de cette commande.
ll --> permet d'afficher comme ls avec les droits en plus de lecture ecriture et éxécution. Savoir qu'il la créer. Il n'existe pas de manuel pour cette commande, alias ll --> comme ls -alF

### 5. Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?
Afficher les ficher dans le dossier bin --> ls /bin

### 6. Que fait la commande ls .. ?
Commande ls --> ls affiche le contenu (non caché) contenu dans un répertoire.

### 7. Quelle commande donne le chemin complet du dossier courant ?
Commande du dossier courant --> pwd

### 8. Que fait la commande echo 'yo' > plop exécutée 2 fois ?
echo 'yo' > plop --> Exécuté deux fois, créer une fichier plop avec le contenue Yo, la deuxieme exécution, remplace le yo par yo.

### 9. Que fait la commande echo 'yo' >> plop exécutée 2 fois ?
echo 'yo' >> plop --> Le double chevron rajoute une derniere ligne on a donc apres la double exécution 3 fois yo sur trois ligne différente. 

### 10. A quoi sert la commande file ? Essayez la sur des fichiers de types différents.
File --> Détermine le type d'un fichier

### 11. Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?
- Créer un fichier toto --> echo 'Hello Toto !' > Toto. 
- ln toto titi --> lie les deux fichiers, si ensuite on modifie toto, titi se met à jour automatiquement
- Si on supprime toto, titi reste en place avec son contenue

### 12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?
Avec le lien symbolique (ls -s titi tutu), le fichier tutu récupere titi, si on modifie titi, le fichier tutu a le même contenu. Si on supprime titi, le fichier tutu n'existe plus (il apparait en rouge) on ne peut plus l'ouvrir. Le lien symbolique peut etre vu comme un raccourci d'un dossier, tandis que le lien normal est plus la copie d'un dossier qui reste à jour car il est liée.

### 13. Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?
Pour interrompre le défilement CRTL +S pour reprendre CTRL + Q

### 14. Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20
- Afficher les 5 premières lignes --> head -5 /cheminFichier
- Afficher les 15 derniere ligne -> tail -15 /cheminFichier
- Affichier ligne 10 à 20 --> sed -n '10,20p' /CheminFichier

### 15. Que fait la commande dmesg | less ?
- dmesg --> Affiche la mémoire tampon de message du noyau 
- less --> Permet de visualiser un fichier texte page par page sans modifier, et permet de revenir en arrière 
- dmesg | less --> Envoie le résultat de dmseg au less ( le |permet d'envoyer la sortie du programme 1 dans le programme 2), ici la commande less permet l'affichage page par page de la mémoire tampon de message du noyau 

### 16. Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ?
- ect/passw --> les informations sur les comptes utilisateur 
- man 5 passwd  --> permet d'avoir plus d'information sur ect/passw

### 17. Affichez seulement la première colonne triée par ordre alphabétique inverse
Colonne trie ordre alphabétique inverse --> sort -r ect/passw | cut -d: -f1

### 18. Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?
Pour le nombre d'utilisateur qui on un compte --> reprendre la commande d'avant et ajouter | wc -l  ( wc permet de compter le nombre de ligne) 

### 19. Combien de pages de manuel comportent le mot-clé conversion dans leur description ?
Combien de page du manuel comporte 'conversion' --> man -k conversion |wc -l

### 20. A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine
Trouvé passeword et copier dans un fichier --> sudo find -name "passw" > list_passwd_files.txt











