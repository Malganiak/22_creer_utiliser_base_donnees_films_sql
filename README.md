# 22_creer_utiliser_base_donnees_films_sql

Créer et utiliser une base de données sur les films avec SQL

Après vous avoir demandé de créer un moteur de recommandation de films, votre chef vous demande de créer une base de données relationnelles qui servira à stocker les données sur les  films. Elle est sensible à l’importance des données, et elle pense que c'est essentiel pour créer une bonne web app. 

Dans ce cadre, elle vous a confié la création de la base de données permettant de collecter le maximum d'informations sur les films.

**Demandes **:

A partir des données du scraping et de l'API, il te faut construire une base de données SQL. Il faut que tu prépares le dictionnaire des données en respectant le template pour répertorier et décrire les données importantes à stocker : https://www.dropbox.com/s/l1jnycm2mhcons1/template-dictionnaire-donnees.xlsx?dl=0

Ensuite, peux-tu me proposer un modèle conceptuel des données. Ça nous permettra de bien visualiser les différentes entités, associations et cardinalités de la base de données. Pour le formalisme, choisis ce que tu veux entre UML ou MERISE.
Ensuite, il faudra que tu me présentes le schéma relationnel normalisé en 3NF de la base de données qui donnera lieu à la création des tables.

Enfin, il faudra que tu implémentes la base de données

Aucune technologie n’est imposée pour la création de la base, même si nous préférerions tout de même une solution open source (comme MySQL ou PostgreSQL)

Excel et/ou Power Query pourront être utilisés pour préparer les données et les faire correspondre au schéma relationnel

Une fois que tu auras fait ça, tu pourras faire** les requêtes pour extraire les données dont on a besoin** :

le top 10 des films les plus rentables
le top 10 des films les moins rentables
les directeurs qui ont fait le plus de films
l'acteur qui a joué dans le plus de films
le nombre de films avec "love" dans les mots clés
le nombre de films français
le directeur avec au moins 10 films qui obtient la meilleure moyenne (note imdb)
​

Milestone 1 : (Modélisation) Analyse du domaine fonctionnel

Livrable : dictionnaire des données.

L’apprenant doit repérer les variables importantes à mémoriser dans la base de données, et remplir un tableau détaillant le code de la variable, un libellé, un commentaire, une règle de contrainte et le type de la variable.

Milestone 2 : (Modélisation) Modèle conceptuel de données

Livrable : MCD suivant la méthode MERISE ou UML. Il faut bien vérifier :

Pas d’attributs redondants.
Chaque entité doit avoir un identifiant.
Les attributs doivent être atomiques.
Les cardinalités doivent être précisées.

Milestone 3 : (Modélisation) Modèle logique de données

Livrable : Schéma relationnel.

Recommandations : Le schéma relationnel doit respecter la 3e forme normale :

Chaque table doit avoir une clé primaire, et les attributs sont atomiques.
Les dépendances fonctionnelles doivent être élémentaires et directes.
Les clés étrangères sont bien repérées

Milestone 4 : (Implémentation) Création de la base de données

Livrable : La base de données est créée.

La BDD doit être composée de plusieurs tables reliées entre elles avec les clés étrangères/primaires.

Milestone 5 : (Implémentation) Importation des données dans la base de données

Livrable : Les tables de la base de données doivent être remplies.

L'apprenant doit commencer par préparer ses données. Plusieurs pistes peuvent être explorées :

uniquement en utilisant Excel : dans ce cas, l’étudiant devra créer les différents fichiers CSV en combinant des opérations de suppression des doublons (Données / Supprimer les doublons) avec des fonctions de RECHERCHEV pour compléter les clés étrangères. Puis il ne lui restera plus qu’à importer les fichiers CSV dans les tables créées.

avec Power Query : https://docs.microsoft.com/fr-fr/learn/modules/clean-data-power-bi/2-shape-data

Il est aussi possible (mais bien plus compliqué) de créer l’ensemble de la base de données avec SQL. Pour cela, il faut donc importer tout le fichier Excel sous SQL et faire les requêtes nécessaires pour créer l’ensemble des tables

Milestone 6 : (Exploitation) Requêtes SQL pour répondre aux demandes

Livrable : Document avec les requêtes et les résultats.

Livrables
Dictionnaire des données
Modèle conceptuel des données
Schéma relationnel normalisé
Base de données opérationnelle avec les données sur tous les films disponibles
Document avec les requêtes et les résultats ppt.

Critères de performance
Le dictionnaire des données est validé si :

Les variables sont répertoriées dans un tableau présentant pour chaque variable :

le code de la variable ;
un libellé ;
un commentaire ;
une règle de contrainte ;
le type de la variable.

Les données sont atomiques.

❒ Les données sont correctement décrites.

 Le modèle conceptuel des données est validé si :

❒ Le modèle conceptuel suit correctement le formalisme UML ou MERISE.

❒ Les cardinalités sont présentes et cohérentes.

Le schéma relationnel normalisé est validé si :

❒ Le schéma relationnel est normalisé (3NF).

 
Créer des tables dans une base de données
La base de données opérationnelle est validée si :

❒ Les tables correspondent au schéma relationnel.

❒ Les contraintes d'intégrité sont présentes.

❒ Les types de variables respectent le dictionnaire des données.

Charger des données dans une base de données
La base de données opérationnelle est validée si :

❒ Toutes les données sont importées dans les tables de la base de données.

❒ Les données sont intégrées dans les colonnes correspondantes.

 
 Effectuer des requêtes SQL 
Le document avec les requêtes et les résultats est validé si :

❒ Il existe une requête et une réponse pour chaque demande .

❒ Des alias ont été utilisés pour faciliter la lecture des résultats.
ChatGPT
Titre: Projet de Gestion de Base de Données pour un Moteur de Recommandation de Films

Introduction:
Suite à la demande de votre chef de créer un moteur de recommandation de films, vous êtes maintenant chargé de concevoir et utiliser une base de données relationnelle avec SQL. Cette base de données servira à stocker les informations essentielles sur les films. Votre chef insiste sur l'importance de ces données pour assurer le succès de la future application web.

Objectifs du Projet:

Création du dictionnaire des données:

Identifier les variables clés à mémoriser dans la base de données.
Remplir un tableau détaillant le code de la variable, un libellé, un commentaire, une règle de contrainte et le type de la variable.
Assurer que les données sont atomiques et correctement décrites.
Modèle Conceptuel de Données (MCD):

Élaborer un MCD en suivant la méthode MERISE ou UML.
S'assurer qu'il n'y a pas d'attributs redondants.
Chaque entité doit avoir un identifiant.
Les attributs doivent être atomiques.
Préciser les cardinalités entre les entités.
Modèle Logique de Données:

Présenter un schéma relationnel conforme à la 3e forme normale (3NF).
Chaque table doit avoir une clé primaire et des attributs atomiques.
Assurer que les dépendances fonctionnelles sont élémentaires et directes.
Repérer et définir correctement les clés étrangères.
Implémentation de la Base de Données:

Créer la base de données avec plusieurs tables interconnectées par des clés étrangères/primaires.
Assurer la présence des contraintes d'intégrité.
Garantir que les types de variables respectent le dictionnaire des données.
Importation des Données dans la Base de Données:

Préparer les données en utilisant Excel et/ou Power Query.
Importer les données dans les tables créées.
Requêtes SQL pour l'Exploitation des Données:

Réaliser des requêtes SQL pour extraire les informations requises, notamment :
Top 10 des films les plus rentables.
Top 10 des films les moins rentables.
Réaliser d'autres requêtes spécifiées.
Livrables:

Dictionnaire des données.
Modèle conceptuel des données.
Schéma relationnel normalisé.
Base de données opérationnelle avec les données sur tous les films disponibles.
Document avec les requêtes et les résultats.
Critères de Performance:

Chaque livrable doit être validé selon les critères spécifiés.
Les données doivent être correctement décrites et respecter les normes de conception de bases de données.
Les requêtes SQL doivent répondre aux demandes spécifiques avec des alias pour faciliter la lecture des résultats.
