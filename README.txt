Exercices MongoDB avec la Base de Données Pokémon GO

Exercice 1: Création d'une Base de Données et d'une Collection

Utilisez la fonction d'importation de MongoDB ou une commande d'insertion pour ajouter les données dans votre collection Pokemons.

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> use PokemonDB
Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.createCollection("Pokemons")
{ ok: 1 }

// Voir si la base existe (elle apparaît uniquement si elle contient des documents)
show dbs
// Lister les collections dans la base
show collections

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 2: Insertion de Données

Objectif : Insérer les données des Pokémon à partir du fichier pokemonGO.csv dans la collection Pokemons.

hippolytedurand@MacBook-Pro-de-Hippolyte ~ % mongoimport --uri="mongodb+srv://Cluster07320:cVNpS2lYRXtE@cluster07320.m9hhive.mongodb.net/PokemonDB" --collection=Pokemons --type=csv --headerline --file="/Users/hippolytedurand/Documents/INFORMATIQUE/YNOV/NO-SQL/mongodb-TP/Data/pokemonGO.csv"
2025-07-07T19:11:22.221+0200	connected to: mongodb+srv://[**REDACTED**]@cluster07320.m9hhive.mongodb.net/PokemonDB
2025-07-07T19:11:23.743+0200	151 document(s) imported successfully. 0 document(s) failed to import.

// Affiche un Pokémon au hasard
Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.findOne()
{
  _id: ObjectId('686bffba6eace16c513a9dce'),
  'Pokemon No': 2,
  Name: 'Ivysaur',
  'Type 1': 'Grass',
  'Type 2': 'Poison',
  'Max CP': 1643,
  'Max HP': 107,
  'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/7/73/002Ivysaur.png/250px-002Ivysaur.png'
}

// Compte le nombre total de Pokémon insérés
Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.countDocuments()
150

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 3: Lecture de Données

Trouvez tous les Pokémon de type "Feu".

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.find({ "Type 1": "Fire" }).pretty()
[
  {
    _id: ObjectId('686bffba6eace16c513a9dcf'),
    'Pokemon No': 4,
    Name: 'Charmander',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 962,
    'Max HP': 73,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/7/73/004Charmander.png/250px-004Charmander.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9dd1'),
    'Pokemon No': 5,
    Name: 'Charmeleon',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 1568,
    'Max HP': 103,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/4/4a/005Charmeleon.png/250px-005Charmeleon.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9dd9'),
    'Pokemon No': 6,
    Name: 'Charizard',
    'Type 1': 'Fire',
    'Type 2': 'Flying',
    'Max CP': 2620,
    'Max HP': 135,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/7/7e/006Charizard.png/250px-006Charizard.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9df1'),
    'Pokemon No': 37,
    Name: 'Vulpix',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 837,
    'Max HP': 72,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/6/60/037Vulpix.png/250px-037Vulpix.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9df3'),
    'Pokemon No': 38,
    Name: 'Ninetales',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 2203,
    'Max HP': 127,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/0/05/038Ninetales.png/250px-038Ninetales.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e06'),
    'Pokemon No': 58,
    Name: 'Growlithe',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 1344,
    'Max HP': 99,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/3/3d/058Growlithe.png/250px-058Growlithe.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e07'),
    'Pokemon No': 59,
    Name: 'Arcanine',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 3005,
    'Max HP': 154,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/b/b8/059Arcanine.png/250px-059Arcanine.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e18'),
    'Pokemon No': 77,
    Name: 'Ponyta',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 1526,
    'Max HP': 91,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/3/3b/077Ponyta.png/250px-077Ponyta.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e1a'),
    'Pokemon No': 78,
    Name: 'Rapidash',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 2215,
    'Max HP': 115,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/3/3f/078Rapidash.png/250px-078Rapidash.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e4a'),
    'Pokemon No': 126,
    Name: 'Magmar',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 2281,
    'Max HP': 115,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/8/8c/126Magmar.png/250px-126Magmar.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e54'),
    'Pokemon No': 136,
    Name: 'Flareon',
    'Type 1': 'Fire',
    'Type 2': '',
    'Max CP': 2662,
    'Max HP': 115,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/d/dd/136Flareon.png/250px-136Flareon.png'
  },
  {
    _id: ObjectId('686bffba6eace16c513a9e5f'),
    'Pokemon No': 146,
    Name: 'Moltres',
    'Type 1': 'Fire',
    'Type 2': 'Flying',
    'Max CP': 3263,
    'Max HP': 154,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/1/1b/146Moltres.png/250px-146Moltres.png'
  }
]

2) Récupérez les informations du Pokémon nommé "Pikachu".

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.find({ Name: "Pikachu" }).pretty()
[
  {
    _id: ObjectId('686bffba6eace16c513a9de5'),
    'Pokemon No': 25,
    Name: 'Pikachu',
    'Type 1': 'Electric',
    'Type 2': '',
    'Max CP': 894,
    'Max HP': 67,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/0/0d/025Pikachu.png/250px-025Pikachu.png'
  }
]

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 4: Mise à Jour de Données

Objectif : Mettre à jour les informations d'un Pokémon.

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.updateOne(
|   { Name: "Pikachu" },
|   { $set: { "Max CP": 900 } }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.find({ Name: "Pikachu" }).pretty()
[
  {
    _id: ObjectId('686bffba6eace16c513a9de5'),
    'Pokemon No': 25,
    Name: 'Pikachu',
    'Type 1': 'Electric',
    'Type 2': '',
    'Max CP': 900,
    'Max HP': 67,
    'Image URL': 'http://cdn.bulbagarden.net/upload/thumb/0/0d/025Pikachu.png/250px-025Pikachu.png'
  }
]

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 5: Suppression d'Éléments

Objectif : Supprimer un Pokémon de la base de données.

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.deleteOne({ Name: "Bulbasaur" })
{ acknowledged: true, deletedCount: 1 }

Atlas atlas-so71xq-shard-0 [primary] PokemonDB> db.Pokemons.find({ Name: "Bulbasaur" })


---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------

Exercices Avancés MongoDB avec la Base de Données Titanic


Exercice 1: Importation et Création de la Collection

Créez une base de données nommée TitanicDB.
Importez les données de titanic.csv dans une collection nommée Passengers.

hippolytedurand@MacBook-Pro-de-Hippolyte mongodb-TP % mongoimport --uri="mongodb+srv://Cluster07320:cVNpS2lYRXtE@cluster07320.m9hhive.mongodb.net/TitanicDB" \
--collection=Passengers \
--type=csv \
--headerline \
--file="/Users/hippolytedurand/Documents/INFORMATIQUE/YNOV/NO-SQL/mongodb-TP/Data/titanic.csv"
2025-07-07T21:44:38.014+0200	connected to: mongodb+srv://[**REDACTED**]@cluster07320.m9hhive.mongodb.net/TitanicDB
2025-07-07T21:44:40.454+0200	418 document(s) imported successfully. 0 document(s) failed to import.

Validation résultat :

Atlas atlas-so71xq-shard-0 [primary] TitanicDB> show collections 
Passengers
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.findOne()
{
  _id: ObjectId('686c23a6052433f4025f370c'),
  PassengerId: '901,0,3,"Davies, Mr. John Samuel",male,21,2,0,A/4 48871,24.15,,S'
}
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments()
418

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 2: Analyse des Données

Objectif : Effectuer des opérations de lecture et d'analyse sur les données.

Instructions

Comptez le nombre total de passagers : 
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments()
418

Trouvez combien de passagers ont survécu.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments({ Survived: 1 })
152

Trouvez le nombre de passagers femmes.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments({ Sex: "female" })
152
Trouvez le nombre de passagers avec au moins 3 enfants.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments({ SibSp: { $gte: 3 } })
11

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 3: Mise à Jour de Données


Mettez à jour les documents pour lesquels le port d'embarquement est manquant, en supposant qu'ils sont montés à bord à Southampton.
Ajoutez un champ rescued avec la valeur true pour tous les passagers qui ont survécu.

db.Passengers.updateMany(
  { Embarked: { $in: [null, "", undefined] } },
  { $set: { Embarked: "S" } }
  
Confirmation : 
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.find({ Survived: 1 }).limit(1).pretty()
[
  {
    _id: ObjectId('686c26e36e9a0551d7e3998e'),
    PassengerId: 900,
    Survived: 1,
    Pclass: 3,
    Name: 'Abrahim, Mrs. Joseph (Sophie Halaut Easu)',
    Sex: 'female',
    Age: 18,
    SibSp: 0,
    Parch: 0,
    Ticket: 2657,
    Fare: 7.2292,
    Cabin: '',
    Embarked: 'C',
    rescued: true
  }
]

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 4: Requêtes Complexes


Sélectionnez les noms des 10 passagers les plus jeunes.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.find(
|   { Age: { $ne: null } },
|   { Name: 1, Age: 1, _id: 0 }
| ).sort({ Age: 1 }).limit(10)
[
  { Name: 'Dean, Miss. Elizabeth Gladys Millvina""', Age: 0.17 },
  { Name: 'Danbom, Master. Gilbert Sigvard Emanuel', Age: 0.33 },
  { Name: 'Peacock, Master. Alfred Edward', Age: 0.75 },
  { Name: 'Aks, Master. Philip Frank', Age: 0.83 },
  { Name: 'West, Miss. Barbara J', Age: 0.92 },
  { Name: 'Sandstrom, Miss. Beatrice Irene', Age: 1 },
  { Name: 'Klasen, Miss. Gertrud Emilia', Age: 1 },
  { Name: 'Laroche, Miss. Louise', Age: 1 },
  { Name: 'Wells, Master. Ralph Lester', Age: 2 },
  { Name: 'Rosblom, Miss. Salli Helena', Age: 2 }
]

Identifiez les passagers qui n'ont pas survécu et qui étaient dans la 2e classe.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.find(
|   { Survived: 0, Pclass: 2 },
|   { Name: 1, Pclass: 1, Survived: 1, _id: 0 }
| )
[
  { Survived: 0, Pclass: 2, Name: 'Myles, Mr. Thomas Francis' },
  { Survived: 0, Pclass: 2, Name: 'Caldwell, Mr. Albert Francis' },
  { Survived: 0, Pclass: 2, Name: 'Howard, Mr. Benjamin' },
  { Survived: 0, Pclass: 2, Name: 'Keane, Mr. Daniel' },
  { Survived: 0, Pclass: 2, Name: 'Louch, Mr. Charles Alexander' },
  { Survived: 0, Pclass: 2, Name: 'Jefferys, Mr. Clifford Thomas' },
  { Survived: 0, Pclass: 2, Name: 'Pulbaum, Mr. Franz' },
  { Survived: 0, Pclass: 2, Name: 'Mangiavacchi, Mr. Serafino Emilio' },
  { Survived: 0, Pclass: 2, Name: 'McCrae, Mr. Arthur Gordon' },
  { Survived: 0, Pclass: 2, Name: 'Aldworth, Mr. Charles Augustus' },
  { Survived: 0, Pclass: 2, Name: 'Lamb, Mr. John Joseph' },
  { Survived: 0, Pclass: 2, Name: 'Wells, Master. Ralph Lester' },
  { Survived: 0, Pclass: 2, Name: 'Weisz, Mr. Leopold' },
  { Survived: 0, Pclass: 2, Name: 'Stanton, Mr. Samuel Ward' },
  { Survived: 0, Pclass: 2, Name: 'Swane, Mr. George' },
  { Survived: 0, Pclass: 2, Name: 'Bowenur, Mr. Solomon' },
  { Survived: 0, Pclass: 2, Name: 'Schmidt, Mr. August' },
  { Survived: 0, Pclass: 2, Name: 'Beauchamp, Mr. Henry James' },
  { Survived: 0, Pclass: 2, Name: 'Lahtinen, Rev. William' },
  { Survived: 0, Pclass: 2, Name: 'Peruschitz, Rev. Joseph Maria' }
]
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments({ Survived: 0, Pclass: 2 })
63
Atlas atlas-so71xq-shard-0 [primary] TitanicDB>
 
---------------------------------------------------------------------------------------------------------------------------------------

Exercice 5: Suppression de Données

Supprimez les enregistrements des passagers qui n'ont pas survécu et dont l'âge est inconnu.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.deleteMany({ Survived: 0, Age: null })
{ acknowledged: true, deletedCount: 0 }
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.countDocuments({ Survived: 0, Age: null })
0

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 6: Mise à Jour en Masse

Utilisez une opération de mise à jour pour augmenter la valeur du champ Age de 1 pour tous les documents.

---------------------------------------------------------------------------------------------------------------------------------------

Exercice 7: Suppression Conditionnelle

Objectif : Supprimer les enregistrements des passagers qui n'ont pas de numéro de billet (Ticket).

Instructions

Supprimez tous les documents où le champ Ticket est absent ou vide.
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.deleteMany({
|   $or: [
|     { Ticket: { $exists: false } },
|     { Ticket: "" }
|   ]
| })
{ acknowledged: true, deletedCount: 0 }

Bonus: Utiliser les REGEX
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.deleteMany({
|   Ticket: { $regex: /^\s*$/ }
| })
{ acknowledged: true, deletedCount: 0 }

Objectif : Utiliser une regex pour trouver tous les passagers selon une condition.

Utiliser une regex pour trouver tous les passagers qui porte le titre de Dr.
Validation
Atlas atlas-so71xq-shard-0 [primary] TitanicDB> db.Passengers.find({
|   Name: { $regex: /Dr\./, $options: "i" }
| })
[
  {
    _id: ObjectId('686c26e36e9a0551d7e39aa9'),
    PassengerId: 1185,
    Survived: 0,
    Pclass: 1,
    Name: 'Dodge, Dr. Washington',
    Sex: 'male',
    Age: 53,
    SibSp: 1,
    Parch: 1,
    Ticket: 33638,
    Fare: 81.8583,
    Cabin: 'A34',
    Embarked: 'S'
  }
]

---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------

Exercice Pratique sur l'Utilisation de Mongo Shell (mongosh)

### Partie 1: Exploration des Bases de Données et Collections

1. **Connexion :** Lancez `mongosh` pour démarrer le shell MongoDB.
hippolytedurand@MacBook-Pro-de-Hippolyte mongodb-TP % mongosh
Current Mongosh Log ID:	686c2d73840b93e0ce53bce6
Connecting to:		mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.5.5
Using MongoDB:		6.0.24
Using Mongosh:		2.5.5

---------------------------------------------------------------------------------------------------------------------------------------

2. **Lister les Bases de Données :** Utilisez la commande `show dbs` pour afficher toutes les bases de données existantes.
test> show dbs

admin    8.00 KiB
config  12.00 KiB
local    8.00 KiB

---------------------------------------------------------------------------------------------------------------------------------------

3. **Sélectionner une Base de Données :** Utilisez la commande `use` suivie du nom d'une base de données existante ou d'une nouvelle pour la sélectionner. Par exemple, `use testDB`.
test> use testDB
switched to db testDB

---------------------------------------------------------------------------------------------------------------------------------------

4. **Créer une Collection :** Créez une nouvelle collection nommée `testCollection` en utilisant `db.createCollection("testCollection")`.
testDB> db.createCollection("testCollection")
{ ok: 1 }

---------------------------------------------------------------------------------------------------------------------------------------

5. **Afficher les Collections :** Utilisez la commande `show collections` pour lister toutes les collections de la base de données actuelle.
testDB> show collections
testCollection

---------------------------------------------------------------------------------------------------------------------------------------

### Partie 2: Manipulation des Données

6. **Insertion de Données :** Insérez un document dans `testCollection` avec `db.testCollection.insertOne({name: "test", value: 1})`.
testDB> db.testCollection.insertOne({ name: "test", value: 1 })
{
  acknowledged: true,
  insertedId: ObjectId('686c30f5840b93e0ce53bce7')
}

---------------------------------------------------------------------------------------------------------------------------------------

7. **Lecture de Données :** Utilisez `db.testCollection.find()` pour afficher tous les documents dans `testCollection`.
testDB> db.testCollection.find()
[
  { _id: ObjectId('686c30f5840b93e0ce53bce7'), name: 'test', value: 1 }
]

---------------------------------------------------------------------------------------------------------------------------------------

8. **Mise à Jour de Données :** Mettez à jour le document précédemment inséré en augmentant `value` de 1 avec `db.testCollection.updateOne({name: "test"}, {$inc: {value: 1}})`.
testDB> db.testCollection.updateOne(
|   { name: "test" },
|   { $inc: { value: 1 } }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
testDB> db.testCollection.find()
[
  { _id: ObjectId('686c30f5840b93e0ce53bce7'), name: 'test', value: 2 }
]

---------------------------------------------------------------------------------------------------------------------------------------

9. **Suppression de Données :** Supprimez le document avec `db.testCollection.deleteOne({name: "test"})`.
testDB> db.testCollection.deleteOne({ name: "test" })
{ acknowledged: true, deletedCount: 1 }
testDB> db.testCollection.find()

---------------------------------------------------------------------------------------------------------------------------------------

### Partie 3: Nettoyage

10. **Suppression de Collection :** Supprimez `testCollection` en utilisant `db.testCollection.drop()`.
testDB> db.testCollection.drop()
true
testDB> show collections

---------------------------------------------------------------------------------------------------------------------------------------

11. **Suppression de Base de Données :** Supprimez la base de données `testDB` (assurez-vous d'avoir sélectionné `testDB`) avec `db.dropDatabase()`.
testDB> db.dropDatabase()
{ ok: 1, dropped: 'testDB' }
testDB> show dbs
admin   40.00 KiB
config  92.00 KiB
local   40.00 KiB

---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------------------------------------

Exercice sur la Manipulation de Documents Imbriqués avec MongoDB

Partie 1: Préparation

Sélection de la Base de Données : Utilisez use schoolDB pour sélectionner la base de données.
testDB> use schoolDB
switched to db schoolDB

Création de la Collection : Créez une collection classes avec db.createCollection("classes").
schoolDB> db.createCollection("classes")
{ ok: 1 }

---------------------------------------------------------------------------------------------------------------------------------------

Partie 2: Insertion de Données

Insertion d'un Document : Insérez un document dans la collection classes qui représente une classe avec les informations suivantes :
Nom de la classe : "Mathematics 101"
Professeur : "John Doe"
Étudiants : Un tableau contenant deux étudiants, chacun avec un name (Charlie et Dylan), un age (21 et 23 respectivement), et un grades (un objet contenant midterm 79, final 92 pour Charlie, et midterm 79, final 87 pour Dylan).

schoolDB> db.classes.insertOne({
|   className: "Mathematics 101",
|   professor: "John Doe",
|   students: [
|     {
|       name: "Charlie",
|       age: 21,
|       grades: {
|         midterm: 79,
|         final: 92
|       }
|     },
|     {
|       name: "Dylan",
|       age: 23,
|       grades: {
|         midterm: 79,
|         final: 87
|       }
|     }
|   ]
| })
{
  acknowledged: true,
  insertedId: ObjectId('686c3385840b93e0ce53bce8')
}

---------------------------------------------------------------------------------------------------------------------------------------

Partie 3: Requêtes sur Documents Imbriqués

Recherche d'Étudiants : Récupérez tous les documents de la classe où au moins un étudiant a obtenu plus de 85 au final.
schoolDB> db.classes.find({
|   "students.grades.final": { $gt: 85 }
| })
[
  {
    _id: ObjectId('686c3385840b93e0ce53bce8'),
    className: 'Mathematics 101',
    professor: 'John Doe',
    students: [
      { name: 'Charlie', age: 21, grades: { midterm: 79, final: 92 } },
      { name: 'Dylan', age: 23, grades: { midterm: 79, final: 87 } }
    ]
  }
]

Mise à Jour d'un Document Imbriqué : Augmentez de 5 points le final de Bob dans "Mathematics 101".
schoolDB> db.classes.updateOne(
|   { className: "Mathematics 101" },
|   { $push: {
|       students: {
|         name: "Bob",
|         age: 22,
|         grades: { midterm: 75, final: 85 }
|       }
|     }
|   }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

schoolDB>
| db.classes.updateOne(
|   { className: "Mathematics 101", "students.name": "Bob" },
|   { $inc: { "students.$.grades.final": 5 } }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

Vérification : 
schoolDB> db.classes.findOne({ className: "Mathematics 101", "students.name": "Bob" }, { "students.$": 1 })
{
  _id: ObjectId('686c3385840b93e0ce53bce8'),
  students: [ { name: 'Bob', age: 22, grades: { midterm: 75, final: 90 } } ]
}


---------------------------------------------------------------------------------------------------------------------------------------

Partie 4: Ajout et Suppression d'Éléments Imbriqués

Ajout d'un Étudiant : Ajoutez un nouvel étudiant nommé "Charlie" avec un age de 23 et un grades de midterm 82, final 88 à "Mathematics 101".
schoolDB> db.classes.updateOne(
|   { className: "Mathematics 101" },
|   { $push: {
|       students: {
|         name: "Charlie",
|         age: 23,
|         grades: { midterm: 82, final: 88 }
|       }
|     }
|   }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}

Suppression d'un Étudiant : Supprimez l'étudiant Alice de "Mathematics 101".
schoolDB> db.classes.updateOne(
|   { className: "Mathematics 101" },
|   { $pull: { students: { name: "Alice" } } }
| )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 0,
  upsertedCount: 0
}

Vérification : 
schoolDB> db.classes.findOne({ className: "Mathematics 101" }, { _id: 0, students: 1 })
{
  students: [
    { name: 'Charlie', age: 21, grades: { midterm: 79, final: 92 } },
    { name: 'Dylan', age: 23, grades: { midterm: 79, final: 87 } },
    { name: 'Bob', age: 22, grades: { midterm: 75, final: 90 } },
    { name: 'Charlie', age: 23, grades: { midterm: 82, final: 88 } }
  ]
}
---------------------------------------------------------------------------------------------------------------------------------------

Partie 5: Aller Plus Loin avec les Agrégations

Objectif
Utilisez le framework d'agrégation de MongoDB pour calculer la note moyenne finale de la classe "Mathematics 101".

Instructions

Calcul de la Moyenne : Écrivez une requête d'agrégation pour calculer la note moyenne finale des étudiants de "Mathematics 101".
schoolDB> db.classes.aggregate([
|   { $match: { className: "Mathematics 101" } },
|   { $unwind: "$students" },
|   { $group: {
|       _id: "$className",
|       averageFinal: { $avg: "$students.grades.final" }
|     }
|   }
| ])
[ { _id: 'Mathematics 101', averageFinal: 89.25 } ]

Trouver la Note Maximale : Écrivez une requête d'agrégation pour trouver la note finale maximale des étudiants de "Mathematics 101".
schoolDB> db.classes.aggregate([
|   { $match: { className: "Mathematics 101" } },
|   { $unwind: "$students" },
|   { $group: {
|       _id: "$className",
|       maxFinal: { $max: "$students.grades.final" }
|     }
|   }
| ])
[ { _id: 'Mathematics 101', maxFinal: 92 } ]

Vérifiez que vos mises à jour ont été correctement effectuées en utilisant la commande db.classes.find().pretty() pour afficher le document mis à jour.
schoolDB> db.classes.find({ className: "Mathematics 101" }).pretty()
[
  {
    _id: ObjectId('686c3385840b93e0ce53bce8'),
    className: 'Mathematics 101',
    professor: 'John Doe',
    students: [
      { name: 'Charlie', age: 21, grades: { midterm: 79, final: 92 } },
      { name: 'Dylan', age: 23, grades: { midterm: 79, final: 87 } },
      { name: 'Bob', age: 22, grades: { midterm: 75, final: 90 } },
      { name: 'Charlie', age: 23, grades: { midterm: 82, final: 88 } }
    ]
  }
]