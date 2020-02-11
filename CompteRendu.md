t
Compte rendu TP1
------------------

Manuel  
 **Commande man**: Permet d'avoir le manuel d'une commande  
 **Commande which** : localiser une commande, renvoit le chemin des fichiers passé en argument  
  Dans man, comment peut-on rechercher un terme --> Une fois le manuel ouvert */[termeRecherché]*  
  On quitte la manuel en appuyant sur la touche **Q**  
  **man 6 intro** : Information sur une section, affiche la première page de la section 6, chaque section de la bibliothéque man possède des informations différente. La section 6 décrit les jeux et petit programmes amusant disponible sur le système. 

Navigation dans l’arborescence des fichiers  
Dossier var/log --> cd /var/log
Remonté dans le dossier de var --> cd ..
Remonté dans le dossier personnel --> cd 
Remonté au dossier précédemment --> cd -
Si on essaye d'accèder au dossier root --> permission denied --> on n'a pas les droits
Avec la commande sudo root --> Commande not found car sudo exécute un programme. 
Créer l'arborescence -- > mkdir Dossier1 Dossier2 Dossier2/Dossier2.1 Dossier2/Dossier2.2; touch Dossier1/Fichier1 Dossier2/Dossier2.2/Fichier2 Dossier2/Dossier2.2/Fichier3
Suppresion --> rm Fichier1 --> fonctionne très bien cependant rm Dossier1 ne fonctionne pas 
Pour supprimer un dossier il faut utiliser rmdir uniquement si le dossier est vide 
Si on applique dans dossier 2 rmdir cela ne fait rien car le dossier n'est pas vide 
Il faut utiliser rm -r Dossier2 pour supprimer le dossier2 

Commande importantes 
Afficher l'heure --> date -u +%k:%M (9:38) ; date +%H (09); le u pour afficher en universel en UTC (pas obligatoire). La commande time donne la durée d'éxécution d'une commande coté user , client et systeme. 
ls et la --> la permet d'afficher les fichiers cachés, les fichiers démarrant par un point sont des fichiers cachés
Trouvé le chemin de ls --> which -a ls --> ls se trouve dans /bin/ls ( -a donne tous les endroits ou se trouve la commande) 
ll --> permet d'afficher comme ls avec les droits en plus de lecture ecriture et éxécution. Savoir qu'il la créer. Il n'existe pas de manuel pour cette commande, alias ll --> comme ls -alF
Afficher les ficher dans le dossier bin --> ls /bin
Commande ls --> ls affiche le contenu (non caché) contenu dans un répertoire.
Commande du dossier courant --> pwd
echo 'yo' > plop --> Exécuté deux fois, créer une fichier plop avec le contenue Yo, la deuxieme exécution, remplace le yo par yo. 
echo 'yo' >> plop --> Le double chevron rajoute une derniere ligne on a donc apres la double exécution 3 fois yo sur trois ligne différente. 
File --> Détermine le type d'un fichier
Créer un fichier toto --> echo 'Hello Toto !' > Toto. 
ln toto titi --> lie les deux fichiers, si ensuite on modifie toto, titi se met à jour automatiquement
Si on supprime toto, titi reste en place avec son contenue. 
Avec le lien symbolique (ls -s titi tutu), le fichier tutu récupere titi, si on modifie titi, le fichier tutu a le même contenu. Si on supprime titi, le fichier tutu n'existe plus (il apparait en rouge) on ne peut plus l'ouvrir. Le lien symbolique peut etre vu comme un raccourci d'un dossier, tandis que le lien normal est plus la copie d'un dossier qui reste à jour car il est liée. 
Pour interrompre le défilement CRTL +S pour reprendre CTRL + Q
Afficher les 5 premières lignes --> head -5 /cheminFichier
Afficher les 15 derniere ligne -> tail -15 /cheminFichier
Affichier ligne 10 à 20 --> sed -n '10,20p' /CheminFichier
dmesg --> Affiche la mémoire tampon de message du noyau 
less --> Permet de visualiser un fichier texte page par page sans modifier, et permet de revenir en arrière 
dmesg | less --> Envoie le résultat de dmseg au less ( le |permet d'envoyer la sortie du programme 1 dans le programme 2), ici la commande less permet l'affichage page par page de la mémoire tampon de message du noyau 
ect/passw --> les informations sur les comptes utilisateur 
man 5 passwd  --> permet d'avoir plus d'information sur ect/passw
Colonne trie ordre alphabétique inverse --> sort -r ect/passw | cut -d: -f1
Pour le nombre d'utilisateur qui on un compte --> reprendre la commande d'avant et ajouter | wc -l  ( wc permet de compter le nombre de ligne) 
Combien de page du manuel comporte 'conversion' --> man -k conversion |wc -l
Trouvé passeword et copier dans un fichier --> sudo find -name "passw" > list_passwd_files.txt











