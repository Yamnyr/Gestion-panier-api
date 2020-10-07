- API pour l'application monPanier

Routes pour la liste des articles :
GET /articles
GET /articles/id
POST /articles
PUT /articles/id
PATCH /articles/id
DELETE /articles/id

Routes pour la liste des articles dans le panier :
GET /panier
GET /panier/id
POST /panier
PUT /panier/id
PATCH /panier/id
DELETE /panier/id

Route statique pour l'accès aux images des articles :
GET /images/nom_de_l_image

Toutes les données sont décrites aux format JSON, sauf les images.

Un article est décrit par les attributs suivants :
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

un article du panier est décrit par les attributs suivants :
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

Le serveur se lance en localhost sur le port 7000.

Vous avez à disposition les scripts suivant pour lancer votre serveur et configurer les accès par un périphérique mobile émulé :

* "start": "npm run json-server" - démarre le serveur d'api (alias npm run api ou npm run json-server).
* "json-server": "json-server --port 7000 --watch data.json" - démarre le serveur d'api
* "api": "npm run json-server" - démarre le serveur d'api
* "delay-api": "npm run json-server -- --middlewares=delay.js" démarre le serveur en mode dégradé avec un délais de réponse des requètes compris entre 0 et 5 secondes
* "forward": "adb reverse tcp:7000 tcp:7000" - met en place le proxy permettant à un mobile émulé d'accéder au serveur. A ne lancer qu'après avoir démarré l'émulateur
