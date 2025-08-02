**Introduction**

Le cancer est l'une des principales causes de mortalité dans le monde. Si des facteurs génétiques jouent un rôle, de nombreux cancers sont influencés par des facteurs comportementaux et environnementaux, tels que l’alimentation, le tabagisme, le stress ou encore l’accès aux soins.
Ce projet s’inscrit dans une démarche de prévention, en explorant la possibilité d’anticiper le risque de cancer à partir des habitudes de vie déclarées par les patients. Nous nous appuyons sur un jeu de données riche et varié, qui regroupe des informations de santé, de mode de vie, de statut socio-économique et de conditions médicales.

**I. Analyse exploratoire des données**

Avant de construire un modèle prédictif, il est essentiel de se familiariser avec la structure et le contenu des données. C’est l’objet de l’analyse exploratoire suivante, qui permet de repérer les tendances générales, les valeurs manquantes et les variables les plus pertinentes.
Cette section a pour objectif de mieux comprendre la structure, le contenu et la qualité des données utilisées pour prédire la sévérité du cancer. Cela comprend un aperçu général des colonnes, des types de données, des valeurs manquantes ainsi que des statistiques descriptives.
Nous avons également créé un dictionnaire regroupant l’ensemble des variables issues du questionnaire initial, accompagnées de leurs descriptions. Il nous permet de mieux comprendre la signification de chaque colonne et de guider notre nettoyage des données.

**II. Préparation du DataFrame df_final**

Après avoir nettoyé les données et éliminé les variables les plus incomplètes, nous avons construit un DataFrame final (df_final) contenant les variables sélectionnées pour la suite de notre analyse.
Cela inclut :
La transformation de certaines valeurs (ex : remplacement des "2" par "0" pour les réponses non fournies)
La création de variables catégorielles à partir de variables numériques continues comme SleepWeekdayHr, DrinkDaysPerMonth, ou encore TimesSunburned
L’analyse des colonnes avec plus de 50 % de valeurs manquantes
Le poids d’échantillonnage (Person_W) a été pris en compte pour s’assurer que notre modèle soit représentatif de la population réelle.


**III. Test du Khi² : exploration statistique des relations**

Une fois les données préparées, il est important de vérifier statistiquement quelles variables sont effectivement liées à la variable cible (EverHadCancer). Pour cela, nous utilisons un test du Khi² afin d’identifier les dépendances significatives entre les variables catégorielles et notre cible.
Cela permet de :
-Identifier les variables importantes à conserver
-Supprimer les variables non pertinentes
-Comprendre les relations entre les habitudes de vie et le diagnostic de cancer

**IV. Visualisation des types de cancer**

Les résultats du test du Khi² nous donnent une première idée des variables pertinentes. Pour compléter cette approche, nous visualisons la distribution des différents types de cancer selon certaines variables comportementales et socio-économiques.
Nous avons sélectionné les cinq cancers les plus fréquemment déclarés dans notre jeu de données :
-Cancer de la peau
-Cancer du sein
-Cancer de la prostate
-Mélanome
-Cancer de l’utérus
Une analyse croisée (crosstab) et des diagrammes en barres (barplots) permettent d’évaluer les différences de répartition selon les variables explicatives.

**V. Vers la modélisation prédictive**

Les analyses précédentes nous ont permis d’identifier les variables les plus pertinentes et de mieux comprendre leur lien potentiel avec le risque de cancer. Nous passons désormais à la phase de modélisation prédictive, avec des algorithmes d’apprentissage supervisé comme la Random Forest et la Régression Logistique.
Chaque configuration (avec ou sans équilibrage des classes, validation croisée, etc.) sera testée, puis comparée afin de retenir le modèle le plus performant pour une éventuelle mise en production.

