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

<img width="587" height="218" alt="Capture d’écran 2025-08-03 à 00 21 09" src="https://github.com/user-attachments/assets/7ea1e57b-52fd-475b-a0e3-2705d137f299" />
<img width="586" height="265" alt="Capture d’écran 2025-08-03 à 00 20 29" src="https://github.com/user-attachments/assets/e2da4b26-1ba8-42bd-b53d-01f274ff904b" />
<img width="586" height="265" alt="Capture d’écran 2025-08-03 à 00 19 46" src="https://github.com/user-attachments/assets/48ae32ac-c949-4fcc-94f9-718dcfe15b08" />
<img width="586" height="220" alt="Capture d’écran 2025-08-03 à 00 19 19" src="https://github.com/user-attachments/assets/28f1b970-2e4e-4650-8e1f-5a763c4ccfaf" />
<img width="599" height="208" alt="Capture d’écran 2025-08-03 à 00 19 01" src="https://github.com/user-attachments/assets/c5b81d07-f9eb-4f7c-ae0b-68e0c7d81dd9" />

**III. Test du Khi² : exploration statistique des relations**

Une fois les données préparées, il est important de vérifier statistiquement quelles variables sont effectivement liées à la variable cible (EverHadCancer). Pour cela, nous utilisons un test du Khi² afin d’identifier les dépendances significatives entre les variables catégorielles et notre cible.
Cela permet de :
-Identifier les variables importantes à conserver
-Supprimer les variables non pertinentes
-Comprendre les relations entre les habitudes de vie et le diagnostic de cancer
<img width="606" height="515" alt="Capture d’écran 2025-08-03 à 00 12 57" src="https://github.com/user-attachments/assets/33f9ec3f-4c05-461d-9fd2-52fe5b2754e1" />


**IV. Visualisation des types de cancer**

Les résultats du test du Khi² nous donnent une première idée des variables pertinentes. Pour compléter cette approche, nous visualisons la distribution des différents types de cancer selon certaines variables comportementales et socio-économiques.
Nous avons sélectionné les cinq cancers les plus fréquemment déclarés dans notre jeu de données :
-Cancer de la peau
-Cancer du sein
-Cancer de la prostate
-Mélanome
-Cancer de l’utérus
Une analyse croisée (crosstab) et des diagrammes en barres (barplots) permettent d’évaluer les différences de répartition selon les variables explicatives.

<img width="645" height="265" alt="Capture d’écran 2025-08-03 à 00 14 08" src="https://github.com/user-attachments/assets/e282ecdb-5feb-4663-ac5c-d3985015a206" />
<img width="645" height="265" alt="Capture d’écran 2025-08-03 à 00 14 23" src="https://github.com/user-attachments/assets/8dadbffe-abe1-4a90-bc4d-b2e5563ea6a7" />
<img width="642" height="211" alt="Capture d’écran 2025-08-03 à 00 14 52" src="https://github.com/user-attachments/assets/4fa6a9db-54de-48ea-9f62-204c201ed6ff" />
<img width="643" height="211" alt="Capture d’écran 2025-08-03 à 00 15 49" src="https://github.com/user-attachments/assets/9875c536-13c7-4529-b366-b112eb8e36ed" />
<img width="643" height="201" alt="Capture d’écran 2025-08-03 à 00 16 12" src="https://github.com/user-attachments/assets/82cb3a66-e5a5-412d-a9bd-3b005ad24524" />
<img width="643" height="201" alt="Capture d’écran 2025-08-03 à 00 16 35" src="https://github.com/user-attachments/assets/db072c70-adcb-4676-8192-f9788ee2ed96" />

**V. Vers la modélisation prédictive**

Les analyses précédentes nous ont permis d’identifier les variables les plus pertinentes et de mieux comprendre leur lien potentiel avec le risque de cancer. Nous passons désormais à la phase de modélisation prédictive, avec des algorithmes d’apprentissage supervisé comme la Random Forest et la Régression Logistique.

Chaque configuration (avec ou sans équilibrage des classes, validation croisée, etc.) sera testée, puis comparée afin de retenir le modèle le plus performant pour une éventuelle mise en production.

<img width="605" height="271" alt="Capture d’écran 2025-08-03 à 00 11 14" src="https://github.com/user-attachments/assets/7d0abe32-d1f1-4562-8f9b-4cd1adf5f77e" />
<img width="607" height="190" alt="Capture d’écran 2025-08-03 à 00 11 58" src="https://github.com/user-attachments/assets/dd69b993-944b-4d3f-9246-ce0c6fb5f315" />


