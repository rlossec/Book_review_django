# Application de critique de livre avec Django

## Principe
Il s'agit de créer un site internet qui met en relation des utilisateurs pour échanger leurs avis sur des livres. Il est réalisé dans le cadre d'une formation.

Ce projet nécessite d'installer python, django et PostgreSQL.

## Installation
### Fichiers du site
Sur le terminal se placer sur un dossier cible.

Puis suivre les étapes suivantes :  
1. Cloner le dépôt ici présent en tapant: `git clone https://github.com/S0Imyr/Book_review_django.git`  
2. Accéder au dossier ainsi créé avec la commande : `cd Book_review_django`  
3. Créer un environnement virtuel pour le projet avec 
    - `python -m venv env` sous windows 
    - ou `python3 -m venv env` sous macos ou linux.
4. Activez l'environnement virtuel avec 
    - `./env/Scripts/activate` sous windows 
    - ou `source env/bin/activate` sous MacOS ou Linux.
5. Installez les dépendances du projet avec la commande `pip install -r requirements.txt`

### Variables d'environnement

Ajouter un fichier .env dans le dossier Book_review_django avec ces variables :
```
SECRET_KEY = ''
DEBUG = True
ALLOWED_HOSTS = 'localhost 127.0.0.1'
POSTGRES_USER = ''
POSTGRES_PASSWORD = ''
```
Les variables POSTGRES_USER et POSTGRES_PASSWORD correspondent à l'utilisateur qui administre votre base de données sur Postgresql.  
SECRET_KEY peut être générer sur https://djecrety.ir/

## Creation de la base de données

6. Créer la base de données DATABASE_NAME avec votre nom d'utilisateur sous PostgreSQL : `createdb -O UserName DATABASE_NAME`
7. Renseigner DATABASE_NAME dans le fichier .env :
`POSTGRES_DB = <DATABASE_NAME>`
8. Se placer dans le dossier src : `cd src`
9. Appliquer les migrations `python manage.py migrate`
10. Alimenter la base de données des utilisateurs `python manage.py loaddata authentification/fixtures/auth.json`
Pour vérifier, il doit y avoir 10 objets créés.
11. Alimenter la base de données des critiques `python manage.py loaddata review/fixtures/review.json`
Pour vérifier, il doit y avoir 26 objets créés.

En cas de problème d'encodage, ne pas hésiter à utiliser un éditeur pour ouvrir et sauvegarder les fichiers JSON avec l'encodage utf-8. Puis réalimenter (étape 10 et 11).

## Lancement du serveur en local
Revenir dans le terminal et tapper :

12. Démarrer le serveur avec `python manage.py runserver`

Lorsque le serveur fonctionne, après l'étape 12 de la procédure, le site internet est accessible à l'adresse : [http://localhost:8000/api/](http://localhost:8000/api/).

Voici quelques comptes pour explorer :
  - Utilisateur : johann, 
  Mot de passe : goethegoethe

  - Utilisateur : leon, 
  Mot de passe : tolstoitolstoi

  - Utilisateur : ernest, 
  Mot de passe : hemingway

Une fois installé, toutes les étapes ne sont pas nécessaires. Pour les lancements ultérieurs du serveur de l'API, il suffit d'exécuter les étapes 4 et 12 à partir du répertoire racine du projet.
