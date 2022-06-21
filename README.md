# Checkpoint 3 Blanc - Marmi Wild

## 0. Configuration

Installer les dépendances du projets et configurer l'accès à la base de données.

Lancer le serveur pour voir si tout fonctionne correctement.

## 1. Modélisation

Créer les MCD et MLD du site de recette Marmi Wild.

Sur Marmi Wild, il est possible d'afficher la liste des recettes du site : chaque recette possède un nom et une image. En cliquant sur la recette, une page présente toutes les étapes de la réalisation de celle-ci : une étape étant composée d'un nom, une description et une position. Un utilisateur enregistré (avec son email et son mot de passe) pourra ajouter des recettes à ses favoris.

## 2. API

Créer la base de données `marmiwild` et sa structure à partir du fichier `database.sql`.

Crée les routes suivantes (respecte les conventions de REST, notamment sur des codes HTTP de réponse):

### Les recettes :

- GET `/recipes` : affiche la liste des recettes
- GET `/recipes/{id}` : affiche le nom et le lien de l'image d'une recette, grace à son identifiant
- POST `/recipes` : crée une nouvelle recette à partir de son nom et du lien d'une image
- PUT `/recipes/{id}` : modifie le nom et/ou l'image d'une recette
- DELETE `/recipes/{id}` : supprime une recette grâce à son identifiant
- GET `/recipes/?search={query}` : affiche la liste des recettes ayant le terme recherché contenu dans son nom ou sa description

### Les étapes :

- GET `/recipes/{id}/steps` : récupère la liste des étapes d'une recette, classées par leur position croissante
- POST `/recipes/{id}/steps` : crée une nouvelle étape d'une recette à partir de sa description et de sa position
