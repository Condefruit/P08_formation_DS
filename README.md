# Projet 08 du parcours Data Scientist (OpenClassrooms)
The project number 8 (Openclassrooms data sciences journey)

-------------------

### Déployez un modèle dans le cloud

Data Scientist au sein dans une très jeune start-up de l'AgriTech**, nommée  "Fruits!", qui cherche à proposer des solutions innovantes pour la récolte des fruits.
* **L'AgriTech est un secteur qui, sur le papier, contribue à répondre aux nouvelles exigences du marché tout en produisant de manière plus responsable, plus compétitive etc. On parle de data pour l’optimisation, blockchain pour la traçabilité etc. En gros : innovation au service de l'agriculture et de l'alimentation.*

La volonté de l’entreprise est de préserver la biodiversité des fruits en permettant des traitements spécifiques pour chaque espèce de fruits en développant des robots cueilleurs intelligents.

:one: Mettre en œuvre un outil de « scoring crédit » <br>
:two: Classifier la demande en crédit accordé ou refusé <br>
:three: Implémenter un tableau de bord interactif pour les chargés de clientèle (avec données clients et transparence de la décision) <br>.
à partir de données clients ayant contracté des prêts bancaires et classifié en "bon client" (0) ou "mauvais client" (1 : retard ou défaut de paiement). <br>
Les données sont accessibles dans différentes bases de données comprenant des : <br>
données comportementales <br>
données provenant d'autres institutions financières, <br>
etc <br>

--------------------------

#### Prétraitement:

Version simple utilisant uniquement la base de données principale (inspiré du script de [Will Koehrsen](https://www.kaggle.com/code/willkoehrsen/start-here-a-gentle-introduction/notebook)) sur KAGGLE). <br>
Liens vers mon [script](https://github.com/Condefruit/P07_formation_DS/blob/main/P7_Data_Analysis_main_database_only.ipynb). <br>
Version plus avancée utilisant toutes les bases de données (inspiré du script d'[AGUIAR](https://www.kaggle.com/jsaguiar/lightgbm-with-simple-features) sur KAGGLE. <br>
Liens vers mon [script](https://github.com/Condefruit/P07_formation_DS/blob/main/P7_Data_Analysis_full_database.ipynb). <br>

---------------------------

#### Modélisation

La base de donnée est très déséquilibrée en terme de cible, 91.2 % de bon clients, il faut donc prendre en compte se déséquilibrage en terme de choix de modèle et de score d'évaluation. <br>
Avec un score d'accuracy ((TP+TN)/(𝑇𝑃+𝑇𝑁+𝐹𝑃+𝐹𝑁)) et un modèle qui prédit 100 % de bons clients, on obtient un score d'accuracy sur notre base de données de 91.2 %. Dans le détail on retrouve 100 % d'accuracy pour la classe majoritaire et 0 % pour la classe minoritaire. Dans la prédiction ou l’analyse de risques de crédit, c’est justement les défauts de paiement (classe minoritaire) qui sont les plus importants à déceler car ce qui entraine des pertes.

Je compare donc différents scores (roc_auc / fbeta / score personnalisé {pour coller au mieux aux cahier des charges}) et différents modèles (dont des modèles qui gèrent le déséquilibre {dit "cost sensitive"} et des algorithmes de type "SMOTE" pour rééquilibrer la base de données) afin de donner le plus d'importance à la classe minoritaire. <br>
Voir le script [script](https://github.com/Condefruit/P07_formation_DS/blob/main/P7_comparaison_scores_modèles.ipynb). <br>

Pour expliciter le modèle et permettre aux chargés de clientèles de faire un retour clair au client, j'utilise la librairie SHAP (Shapley Additive exPlanations). Je propose aussi une évaluation du bénéfice (fonction à retravailler avec retour métier) en fonction du seuil de classification choisis. <br>
Liens vers le [script](https://github.com/Condefruit/P07_formation_DS/blob/main/P7_shap.ipynb).

---------------------------

#### Dashboard

Le tableau de bord interactif est hébergé sur Streamlit, les données sont stockées sur S3 (AWS) et la prédiction se fait sur Heroku. <br>
Le tableau de bord permet au chargé clientèle de sélectionner un client, d'avoir accès à la décision le concernant en fonction de la stratégie adoptée (seuil de classification) et à ses données.
Liens ver le [dashboard](https://share.streamlit.io/condefruit/p07_formation_ds/main/banking.py). <br>

---------------------------

Lien vers le [support de présentation](https://github.com/Condefruit/P07_formation_DS/blob/main/P7_support_presentation.pdf). <br>
et la [note explicative](https://github.com/Condefruit/P07_formation_DS/blob/main/note_méthodologique.pdf) à destination des chargés de clientèle.
