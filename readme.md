# API pour l'application monPanier

## Routes
Routes pour la gestion des **articles** :
GET /articles
GET /articles/id
POST /articles
PUT /articles/id
PATCH /articles/id
DELETE /articles/id

Routes pour la gestion des articles dans le **panier** :
GET /panier
GET /panier/id
POST /panier
PUT /panier/id
PATCH /panier/id
DELETE /panier/id

Route statique pour l'accès aux **images** des articles :
GET /images/nom_de_l_image

Toutes les données sont décrites aux format JSON, sauf les images.

Un **article** est décrit par les attributs suivants :
```
{
    "id"
    "description"
    "prix"
    "type"
    "picture"
}
```
exemple :
```
{
    "id": 23,
    "description": "PC 5",
    "prix": 621.9,
    "type": "pc",
    "picture": "/images/pc5.jpg"
}
```

un article du **panier** est décrit par les attributs suivants :
```
{
    "id"
    "quantity"
}
```
exemple :
```
{
    "id": 1,
    "quantity": 2
}
```

##Fonctionnement du serveur
Le serveur se lance en localhost sur le port 7000.

Vous avez à disposition les scripts suivant pour lancer votre serveur et configurer les accès par un périphérique mobile émulé :

* **"start"** (alias api ou json-server) - démarre le serveur d'api
* **"delay-api"** - démarre le serveur en mode dégradé avec un délais de réponse des requètes compris entre 0 et 5 secondes
* **"forward"** - met en place le proxy permettant à un mobile émulé d'accéder au serveur. A ne lancer qu'après avoir démarré l'émulateur
