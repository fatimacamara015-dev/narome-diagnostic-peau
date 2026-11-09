# Narome – Diagnostic de peau

## Problème
Face aux nombreux soins disponibles, les clientes de Narome ne savent pas
lesquels choisir pour leur type de peau et repartent sans acheter, ou
achètent un produit qui ne leur convient pas.

## Utilisatrice cible
Toute personne qui visite [narome-senegal.com](https://narome-senegal.com)
et cherche une routine adaptée à sa peau.

## Objectif
Un quiz de 7 questions qui identifie le type de peau (acnéique, sèche,
mature, grasse) et recommande une routine avec les vrais produits Narome,
leur prix et un lien vers chaque fiche produit.

## Routines recommandées
| Type de peau | Produits |
|---|---|
| Tendance acnéique | Gel nettoyant, Lotion tonifiante, Sérum apaisant N°1, Crème hydra-protect + Savon détoxifiant au charbon |
| Grasse | Gel nettoyant, Lotion tonifiante, Crème hydra-protect (+ Sérum apaisant en option) + Savon détoxifiant au charbon |
| Sèche | Huile démaquillante, Lotion tonifiante, Sérum apaisant N°1, Crème hydra-protect |
| Mature | Huile démaquillante, Lotion tonifiante, Sérum apaisant N°1, Crème hydra-protect |

Le catalogue visage actuel de Narome ne contient pas de gammes séparées par
type de peau : les routines sont construites à partir des bienfaits annoncés
sur chaque fiche produit du site. À faire valider par la marque.

## Commander
Le bouton **Commander ma routine** ouvre WhatsApp avec un message déjà écrit
(profil, produits, total). Un second bouton mène vers narome-senegal.com.
Le numéro se règle dans la constante `WHATSAPP_NUMBER` en haut du script de
`index.html` (format international, sans + ni espaces). Si elle est vide, le
bouton WhatsApp est masqué.

> ⚠ Le numéro actuel (+221 77 123 45 67) est un **numéro d'exemple** : il faut le
> remplacer par le vrai numéro WhatsApp de Narome avant toute mise en ligne.

Remplir le panier du site en un clic n'est pas prévu : le panier WooCommerce
de narome-senegal.com n'accepte normalement qu'un produit par lien d'ajout
(non testé sur le site réel). Pistes : un plugin côté Narome, ou héberger le
quiz sur le site lui-même.

## Sensibilité de la peau
La question 6 demande si la peau réagit facilement. Elle ne change pas le type
de peau : si la réponse est « oui », le sérum apaisant devient obligatoire dans
la routine et entre dans le total (il est optionnel pour la peau grasse sinon).

## Données
Noms, prix, compositions et images des produits sont relevés sur
narome-senegal.com (8 novembre 2026). Les images sont chargées directement
depuis le site Narome. Si les prix ou produits changent, il faut mettre à
jour l'objet `PRODUITS` dans `index.html`.

## Indicateur de succès
Part des visiteuses qui terminent le diagnostic, puis qui consultent la
fiche d'un produit recommandé.

## Lancer le site
Ouvrir `index.html` dans un navigateur, ou lancer `python3 -m http.server 8080`.
