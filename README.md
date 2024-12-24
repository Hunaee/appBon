# appBon



**Une courte présentation générale de l’application (entre 3 et 5 lignes)**

Mon projet est une application visant à simplifier l'utilisation et la gestion des bons d'achat. L'idée principale est de regrouper tous les bons d'achats de différents magasins en un seul endroit. L'utilisateur peut voir tous ses bons d'achat dans l'application et les magasins chez qui il est inscrit. Lors du passage en caisse, un QR code unique (API) est généré pour l'utilisateur, ce qui facilite leur utilisation sans avoir à chercher individuellement chaque QR. Le public cible étant les personnes ayant un smartphone et sachant utiliser des applications de manière autonome.

Attention : Il y a deux types de possibilité pour le client d'avoir des offres.
1. Le premier étant les bons d'achat classique (-30%, -4€)
2. Le deuxième étant par exemple : 10 achetés, 1 gratuits (pour reprendre le concept des sandwicheries)


**Une liste complète des fonctionnalités proposées par l’application**
1. Génération d'un QR code client unique (via une API), attention ce qr code ne fonctionne que pour les magasins qui travailleront avec nous. En effet ayant l'intention de facilité l'utilisation des QR codes, on aimerait rajouter la possibilité de rajouter les cartes de fidélités des magasins qui travailleraient pas avec nous (mais on aurait quand même pas accès aux bons d'achats de ces magasins).
2. Affichage des bons d'achats par catégorie (catégorie + sous catégorie). Lorsque la sous catégorie est sélectionnée, il y a également un affichage des bons par rapport à la distance de l'utilisateur par rapport au magasin (si la personne veut manger à sa pause midi elle n'a pas beaucoup de temps donc peu de possibilité de déplacement). Et aussi par rapport à l'avantage (-30% affiché avant 10%,...)
3. Activation des bons d'achats (par l'utilisateur)
4. Possibilité de filtrer les bons d'achats via la sélection de catégorie (en un à deux cliques)
5. Recherche avancée (Nom magasin, catégorie, montant, date d'expiration (?))
6. Lié sa carte de fidélité avec d'autres utilisateurs (pour partager sa carte de fidélité avec ses amis / sa famille)
7. Page profil également, permettant de voir ses information, changer le mot de passe,... mais aussi voir les bons d'achats expirés ou encore les bons d'achats utilisé. (J'aimerais également rajouté un graphique comme vous l'aviez demandé, je me demande si ce n'est pas intelligent de le rajouter dans cette page profil)
8. Authentification (classique, Google / Apple (?))
9. Gestion de Token 


**Une liste complète des données que devra gérer l’API (= le back-end)**

1. Les utilisateurs (id, mail / password / prenom / nom / date naissance)
2. Carte de fidélité par magasin (id, date création, id_utilisateur, id_magasin)
3. Magasins (id, adresse, label, id_manager, points (true/false), article_offert_dix_points, type(Restaurant/Brico), reduction_premiere_inscription, reductions_recurrentes, reductions_timing)
4. Points, comme pour les sandwicheries : 10 + 1 gratuits (id, valeur(),id_utilisateur, id_magasin )
5. Reductions (valeur, date de création, date d'expiration, date_utilisation, id_carte, id_magasin, id_utilisateur)
6. Reductions anciennes (idem -> si je me souviens bien j'ai fait cette table lorsqu'il y aurait trop d'entrées dans la première)

(Les tables pas nécessaire pour cette application, mais qui sont déjà présente pour une app destinée aux magasins)

7. Manager (mail, password, id_magasin)

8. Equipier (mail, password, id_magasin)

9. Visite (heure de visite, premiere visite (true / false : pour savoir si le client est un nouvel utilisateur)


**Une estimation du niveau de difficulté selon le même barème que celui utilisé pour les suggestions d’applications.**

Moyenne, de part la db, l'API à rajouté, l'Authentification (Google / Apple)


**Le choix des technologies pour chaque partie de l’application**

==SPA==

React pour la réutilisabilité des composants, ce qui me permettra de facilité la réutilisation de mes composants comme mes boutons / bons. Mais également l'amélioration de la performance grace au DOM virtuel ce qui est particulièrement pour les applications qui nécessitent un affichage dynamique (comme des bons d'achat qui changent souvent ou des listes filtrées).

Permet de voir directement les changements sans avoir à recharger l'application (hot reloading).

Ionic : Permet de développer et de mettre en ligne son contenu sous différentes plateformes

==API==

Express.js 
Permet de gérer un grand nombre de connexions simultanées sans ralentir les performances du serveur.
Idéal également pour les mises à jour en tant réel.


==Base de données==

MySQL étant donné sa popularité

==ORM / ODM==

Squelize (si on est obligé d'en avoir un)

Permet de travailler avec la base de données à travers des objets JavaScript
Simplifie le processus d'interaction avec la base de données




**Design Figma** 

Il est bien entendu qu'une version Browser devra être également designer / développer :)
Figma : https://www.figma.com/design/lh3X3u6862VF5RC3xj3KmH/Login-Page-UI-(Community)?node-id=0-1&t=yvehYEKdeWKmbmZv-1

**CLI**

npx create-react-app mon-projet

npm start

npm install react-router-dom (pour le SPA)


Docker et OSRM
Extraction de données : docker run -t -v /c/xampp/htdocs/TFE:/data osrm/osrm-backend osrm-extract -p /opt/foot.lua /data/belgium-latest.osm.pbf
Générer des données de contraction : docker run -t -v /c/xampp/htdocs/TFE:/data osrm/osrm-backend osrm-contract /data/belgium-latest.osrm



Calcul de performance pour les distances:
https://stackoverflow.com/questions/27928/calculate-distance-between-two-latitude-longitude-points-haversine-formula








