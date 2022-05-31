# Projet 08 du parcours Data Scientist (OpenClassrooms)
The project number 8 (Openclassrooms data sciences journey)

-------------------

### Déployez un modèle dans le cloud

Data Scientist au sein dans une très jeune start-up de l'AgriTech**, nommée "Fruits!", qui cherche à proposer des solutions innovantes pour la récolte des fruits.
*L'AgriTech est un secteur qui, sur le papier, contribue à répondre aux nouvelles exigences du marché tout en produisant de manière plus responsable, plus compétitive etc. On parle de data pour l’optimisation, blockchain pour la traçabilité etc. En gros : innovation au service de l'agriculture et de l'alimentation.*

La volonté de l’entreprise est de préserver la biodiversité des fruits en permettant des traitements spécifiques pour chaque espèce de fruits en développant des robots cueilleurs intelligents.

La start-up souhaite dans un premier temps se faire connaître en mettant à disposition du grand public une application mobile qui permettrait aux utilisateurs de prendre en photo un fruit et d'obtenir des informations sur ce fruit.

La création de cette application à 3 buts : <br>
:one: Sensibiliser le grand public à la biodiversité des fruits <br>
:two: Mettre en place une première version du moteur de classification des images de fruits. <br>
:three: Permettra de construire une première version de l'architecture Big Data nécessaire. <br>

Les données sont accessibles dans le kaggle dataset ["fruits360"](https://www.kaggle.com/datasets/moltean/fruits). Il s'agit de plus de 90 000 images de 131 fruits ou légumes pris en photos sous tous les angles.

--------------------------


### Concrètement

Le vrai but de ce projet est de se familiariser avec l'architecture big data. <br>
J'ai donc uniquement sélectionné 5 fruits ou légumes différents pour lesquels j'ai choisis 5 images (dans un but de limitation des couts tous en conservant l'architecture big data). <br>
Les images sont ensuite prétraitées pour l'utilisation d'un réseau de neuronnes spécialisé dans le traitement des images (*voir aussi projet 6*). <br>
Liens vers mon [script](https://github.com/Condefruit/P08_formation_DS/blob/main/P08_notebook_cloud.ipynb). <br>
Dans le cadre de l'architecture big data, j'ai travaillé avec des RDD, des dataframes Spark et les librairies Mlib et Keras et les services AWS. <br>
Liens vers ma [présentation](https://github.com/Condefruit/P08_formation_DS/blob/main/Support_presentation.pdf).

