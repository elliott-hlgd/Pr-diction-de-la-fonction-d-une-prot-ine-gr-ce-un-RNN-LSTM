Prédiction par un modèle LSTM dans TensorFlow de la fonction d'une protéine en utilisant sa séquence d'acides aminés comme données d'entrée. Ces séquences d'acides aminés proviennent de la base de données UniProt
et sont classées en 4 fonctions distinctes :  GPCR (3369 séquences), protease (519 séquences), p450 (252 séquences) et ferritin (35 séquences).
Ce projet est une tentative de reproduction des résultats de l'article "Deep Recurrent Neural Network for Protein Function Prediction from Sequence" (2017) de Xueliang Leon Liu.

L'ensemble du code est contenu dans le fichier code_projet.ipynb. Celui-ci contient, dans l'ordre, une première tentative de prédiction sur toutes les classes avec un premier LSTM bidirectionnel, 
puis la même chose mais avec un modèle CNN 1D et enfin une nouvelle tentative avec un LSTM bidirectionnel de prédiction binaire (1 classe vs toutes les autres). Pour cette dernière partie, on
divise également la classe GPCR, contenant beaucoup plus de séquences que les 3 autres, en plusieurs sous-groupes, appelés chunk dans l'article. Pour chaque tâche de classification binaire, on répète le processus 
d'entrainement autant de fois qu'il y a de sous-groupes de cette classe, en mettant à chaque fois un sous-groupe différent. Cette technique est utilisée pour éviter au modèle d'être entrainé sur des données trop
déséquilibrées et de toujours prédire la même classe.



Lien vers l'article de Xueliang Leon Liu : https://arxiv.org/pdf/1701.08318
