 # TP de Synthèse – Ensea in the Shell

 ## 1- Affichage d’un message d’accueil, suivi d’un prompt simple : 
 On affiche le message d'accueil suivant : 
 
 <img width="259" alt="Capture d’écran 2024-12-07 à 13 57 58" src="https://github.com/user-attachments/assets/8d9c4a2d-cf03-4ba1-969e-aafac6fe7a47">

## 2- Exécution de la commande saisie et retour au prompt :

### a/ Lecture de la commande saisie :
dans la fonction main on réalise une boucle infinie avec while(1).
Pour lire une commande on doit utiliser la commande read, ce qui nous permet d'obtenir dans le terminal :

<img width="259" alt="Capture d’écran 2024-12-07 à 15 20 09" src="https://github.com/user-attachments/assets/8e9c6c06-9d8f-485b-bfd4-2110c41d9321">

### b/ Exécution d’une commande simple :
On veut maintenant pouvoir exectuer des commandes simples dans le terminal. Pour cela on va devoir utiliser execlp. Pour cela on va crée une fonction nommer exeCommand() qui va prendre en argument char* buf et commande_size.
Dans cette fonction on va crée un processus fork. ce qui nous permet au final d'obtenir :

<img width="797" alt="Capture d’écran 2024-12-07 à 15 27 54" src="https://github.com/user-attachments/assets/feacb3f9-3ab6-4483-919c-3a7daf1a3814">

### c/ Retour au prompt enseash % et attente de la commande suivante :
Pour cela on utilise la commande write dans la boucle infinie.

## 3- Gestion de la sortie du shell avec la commande “exit” ou un <ctrl>+d :

pour cela on modifie notre fonction exeCommand afin de quitter le terminal. Pour cela on place un if avant l'initialisation du fork, dans lequel on compare buf[0] avec "exit". quand a contrôle d, on sais qu'il envoie comme signal END OF FILE, c'est a dire qu'il n'y a plus rien à lire autrement dit commande_size est nulle, on rajoute donc la condition ou commande_size == 0. 
On obtient donc : 

<img width="459" alt="Capture d’écran 2024-12-07 à 15 40 42" src="https://github.com/user-attachments/assets/9114f5ef-23fe-4aa1-ad83-86d66ddbf124"> 
<img width="741" alt="Capture d’écran 2024-12-07 à 15 41 52" src="https://github.com/user-attachments/assets/c60d0ac9-c0a6-4475-83f9-cf491ff46620"> 
