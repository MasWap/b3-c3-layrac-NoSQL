# Projet Todolist interrogeant une base MongoDB avec Mongoose

Ce projet consiste à développer une application Todolist qui utilise une base de données MongoDB pour stocker les tâches et les informations associées. Nous utiliserons Mongoose, une bibliothèque Node.js pour la modélisation des données MongoDB, afin de faciliter la communication avec la base de données.

## Technologies utilisées

-   Node.js
-   MongoDB
-   Mongoose


## Étapes pour exécuter le projet

1.  Cloner le projet à partir du référentiel Git :

```bash
$ -> git clone https://github.com/MasWap/b3-c3-layrac-NoSQL
```


2.  Installer les dépendances NPM :

```bash
cd b3-c3-layrac-NoSQL
$ -> npm install
```


3.  Créer un fichier `.env` à la racine du projet et y définir les variables d'environnement suivantes :

```bash
DB_CONNECT = mongodb+srv://Lilian:Lilian34!@cluster0.phy80f1.mongodb.net/?retryWrites=true&w=majority
$ -> npm install
```

4.  Exécuter l'application en tapant la commande suivante :

```bash
$ -> npm start
```

L'application sera exécutée sur le port spécifié dans la variable d'environnement `PORT` (ici, 3000).

## Modèle de données

La base de données test contient une collection "todotasks" qui stocke les informations relatives aux tâches.

Le modèle de données Mongoose correspondant est le suivant :

```javascript
const  mongoose = require('mongoose');

const  todoTaskSchema = new  mongoose.Schema({
content: {
	type:  String,
		required:  true
	},
	date: {
		type:  Date,
		default:  Date.now
	}
})

module.exports = mongoose.model('TodoTask', todoTaskSchema);
```

Le modèle contient les champs suivants :

-   `id` : l'id de la tâche, généré automatiquement à l'insertion de l'objet
-   `content` : le contenu de la tâche
-   `date` : date de l'insertion de l'objet

## Routes de l'API

L'API TodoTask expose les routes suivantes :

-   `GET /` : récupère toutes les tâches dans la base de données
-   `POST /` : crée une nouvelle tâche (si l'on click sur le bouton, en fonction de l'information renseigné dans le formulaire)
-   `PUT /edit/:id` : met à jour une tâche existante
-   `DELETE /remove/:id` : supprime une tâche existante


## Elément retourné sur l'interface Mongo Atlas

Voici l'élément retourné dans la collection TodoTasks :

Elément 1
```json
_id : ObjectId('644134157ae9899bdb1f667a')
content : "Pain"
date : 2023-04-20T12:46:13.568+00:00
__v : 0
```
Elément 2
```json
_id : ObjectId('644134187ae9899bdb1f667d')
content : "Lait"
date : 2023-04-20T12:46:16.610+00:00
__v : 0
```


## Conclusion

Ce projet Todolist est un exemple simple d'application Node.js interrogeant une base de données MongoDB à l'aide de la bibliothèque Mongoose. Il peut être utilisé comme point de départ pour développer des applications plus complexes utilisant ces technologies.
