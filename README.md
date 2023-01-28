# Spot Discovery
## Description
Il s'agit d'un projet d'initiation à Flutter.
Vous utiliserez les données mises à votre disposition afin de constuire une interface simple.

## [Collection postman](https://github.com/ectrema/lp_iem_23/files/10527299/firebase.spots.postman_collection.json.zip)



Ces requêtes pointent toutes vers une base de données Firebase avec pour base URL https://spot-discovery-2023-default-rtdb.europe-west1.firebasedatabase.app

## Objectifs
1. Mettez à jour le **HomeViewModel** pour récupérer la liste des spots depuis l'API
2. À l'ouverture d'un spot, appelez l'API de détail. Puis grâce à la réponse détaillée :
   - Affichez la description
   - Utilisez le widget [PageView](https://api.flutter.dev/flutter/widgets/PageView-class.html) pour afficher la liste d'images

Pour ce point vous devrez d'abord modifier le modèle de donnée (la classe Spot)

3. Ajoutez un bouton `Like` (dans la vue de liste, la vue de détail ou les 2).
   En cliquant dessus, le spot sera ajouté (puis supprimé si on reclique) en local. Utilisez le package de votre choix.
   Ajoutez ensuite un moyen d'accéder à la liste des spots favoris, par exemple une bottom navigation bar sur la homepage.
4. Sur la vue de détail d'un spot, afficher la liste de commentaires et ajoutez la possibilité de poster un commentaire

## Historique
<details>
    <summary>Cours 1: Initiation à Flutter</summary>

## HomeViewModel
Vous trouverez dans ce projet le singleton **HomeViewModel** (lib/infrastructure/viewmodel/home_viewmodel.dart) qui vous donne accès à une liste de spots.
Les données sont parsées depuis le fichier spots.json se trouvant dans le dossier `assets/json`.
La classe **Spot** (lib/data/model/spot.dart) représente un lieu et vous donne accès à de nombreuses informations sur celui-ci.

## Objectifs
1. Utilisez une ListView pour afficher la liste des spots. Faites apparaître les infos suivantes du Spot :
   - title
   - imageThumbnail
   - mainCategory : affichez  le `name`

2. Créez la page détail d'un spot, dans laquelle vous afficherez :
   - title
   - imageFullsize
   - address
   - trainStation (attention, la valeur peut-être null)
   - isRecommended : faites apparaître un bandeau avec le label `Recommandé` si **true**
   - isClosed : faites appaître un bandeau avec le label `Fermé` si **true**
   - tagsCategory : affichez les catégories dans une ListView

Lors du clic sur un élément de la liste de votre première vue, redirigez l'utilisateur sur la vue de détail.

3. Implémentez la fonction **getRandom** et ajoutez un FloatingActionButton sur la page d'accueil.
   En cliquant sur ce bouton, vous récupérerez un spot au hasard dans la liste et l'afficherez dans la vue de détail

4. Implémentez la fonction **getSpotByName** dans le singleton `HomeViewModel`.
   Utilisez cette fonction pour implémenter une fonctionnalité de recherche par titre de spot dans votre application.

5. Affectez un **ScrollController** à votre ListView pour implémenter une liste paginée.
   Vous pouvez utiliser la fonction `getSomeSpots` pour simuler une pagination.
</details>
