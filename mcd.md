Address (0,N) ---- (1,N) User

Order (1,N) ---- (0,N) User

Order (1,N) ---- (0,N) Delivery

Order (1,N) ---- (0,N) OrderProduct (1,1) ---- (1,N) Product

Delivery (1,N) ---- (0,1) Address

La table "Address" contient les champs suivants :

* id : identifiant unique de chaque adresse
* street
* city
* zip_code

La table "User" contient les champs suivants :
* id : identifiant unique de chaque utilisateur
* email
* password
  
La table "Order"  :
* id : identifiant unique de chaque commande
* amount:
* status :
* user_id : identifiant de l'utilisateur qui a passé la commande (clé étrangère liée à la table "User")
* delivery_id : identifiant de l'adresse de livraison pour cette commande (clé étrangère liée à la table "Delivery")

La table "Product" :
* id : identifiant unique de chaque produit
* name :
* desc :
* mug_type :
* amount :

La table "Delivery" contient les champs suivants :

* id : identifiant unique de chaque adresse de livraison
* order_id : identifiant de la commande correspondante (clé étrangère liée à la table "Order")
* address : identifiant de l'adresse de livraison (clé étrangère liée à la table "Address")
  Les relations entre les tables sont les suivantes :
* La table "Order" est liée à la fois à la table "User" (via la clé étrangère "user_id") et à la table "Delivery" (via la clé étrangère "delivery_id"). Cela permet de spécifier l'utilisateur qui a passé la commande ainsi que l'adresse de livraison correspondante.