# Abbeal - Test technique Symfony

**Projet: Horses Race**

Nous allons créer un jeux de course de chevaux.

Il y a 8 chevaux.

Chaque cheval a un nom.

Une course est caractérisée par une date et heure, la position de chaque cheval à l’arrivée.

Au début de la course, chaque cheval a 1 chance sur 8 pour arriver premier. Une fois le premier arrivé, chaque cheval a 1 chance sur 7 pour arriver 2ème et ainsi de suite, jusqu’à la l’arrivée du dernier.

**Instructions**:

* **Forkez** le repository: [https://github.com/abbealBZZZ/test-technique-symfony](https://github.com/abbealBZZZ/test-technique-symfony)

* Travaillez sur votre propre repository. Une fois le travail fini, **ne créez pas de pull request**. Renvoyez simplement le **lien** de votre repository en précisant jusqu’à quelle étape vous êtes arrivé.

* Gardez un historique de commits clair et précis.

* La règle de nommage des commit est la suivante: "PART-x.y-message_commit". **Exemple: **“PART-2-3-unit-test-added”

* Veillez au respect des bonnes pratiques de Symfony.

* Commentez votre code.

* Si vous êtes bloqué, ne vous attardez pas et passez à l’étape suivante.

* Aucune étape est éliminatoire. 

* Installez n’importe quelle dépendance que vous jugez utile ou nécessaire.

  

**PARTIE I:**

1. Créez le **modèle de données** et générez la **migration**

2. Mettez en place des **fixtures** pour remplir le jeu de données (Référentiel des chevaux)

3. Créer une **API REST** pour **déclencher** et **sauvegarder le résultat** d’une course. L’output de l’api devrait être sous cette forme:

```json
{ 
"date":"datetime",
"results":{ 
    "1":"nom du cheval",
    "2":"nom du cheval",
    "3":"nom du cheval",
    "4":"nom du cheval",
    "5":"nom du cheval",
    "6":"nom du cheval",
    "7":"nom du cheval",
    "8":"nom du cheval"
    }
}
```

**PARTIE II:**

1. **Dockerisez** le projet avec 4 containers: PHP, MySql, Apache (ou Nginx)et PhpMyAdmin. 

2. Implémentez un fichier **Makefile** dans lequel vous définissez:
    1. un make install : pour installer les dépendance du projet
    2. un make db: pour créer la base de données
    3. un make fixtures: pour remplir la base de données avec les fixtures
    4. un make reset-db: pour supprimer la base de données, la recréer et la remplir avec les fixtures.

3. **Testez unitairement l'algorithme** du déroulement d’une course

4. Ajouter un make test pour exécuter les **tests unitaires**.

**PARTIE III:**

1. Ajouter un container RabbitMq.

2. Ajouter un attribut "**number**" de type entier avec une **contrainte** **d’unicité**

3. Ajouter une API pour déclencher une course de façon **asynchrone**. Un message est envoyé à une queue RabbitMq. Un consumer avec un délais de **2** **secondes** va sauvegarder le résultat en base de données.

4. Ajouter une **API** pour récupérer le **résultat** d’une course, **identifié** par son numéro.

**PARTIE IV:**

1. Ajouter un container **Elasticsearch**.

2. **Indexer** les résultats de courses.

3. Ajouter une API pour récupérer le **classement** total des chevaux avec position et total des points sachant que:
    - position 1 = 15 pts
    - position 2 = 13 pts
    - position 3 = 10 pts
    - position 4 = 8 pts
    - position 5 = 6 pts
    - position 6 = 4 pts
    - position 7 = 2 pts
    - position 8 = 1 pts
4. Ajouter une API pour récupérer les **statistiques** d’un cheval défini: **nombres de fois en 1ère**, **2ème** et **3ème** **position** et sa **position moyenne**.
