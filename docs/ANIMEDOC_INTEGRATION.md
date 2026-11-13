# Intégration AnimeDoc — catalogue uniquement

## Décision du projet

AnimeDoc est retenu comme source de catalogue pour Zangetsu-FR-Providers. Son intégration ne doit pas être abandonnée sous prétexte que ses flux vidéo ne seraient pas utilisables.

La première étape visée est **catalogue uniquement** :
- afficher les nouveautés anime ;
- afficher les anime populaires/tendances ;
- rechercher un anime ;
- ouvrir sa fiche ;
- afficher les saisons et le nombre d'épisodes lorsque les données le permettent.

Le streaming et le téléchargement sont des fonctions distinctes. Ils ne sont pas requis pour que la partie catalogue soit utile et pourront être étudiés séparément, sans promettre leur disponibilité.

## Endpoints documentés

Base API : `https://api.animedoc.cloud`

Tous les endpoints API décrits ci-dessous nécessitent un en-tête `X-API-Key`.

| Besoin | Endpoint | Utilisation |
| --- | --- | --- |
| Accueil / nouveautés | `GET /api/v2/anime/home/` | Récupérer les rangées de catalogue, dont « Latest anime ». |
| Parcourir les nouveautés | `GET /api/v2/anime/browse/?channelId=2&sort=Latest&genre=Anime&page=1&perPage=12` | Parcourir le catalogue anime trié par nouveauté. |
| Tendances | `GET /api/v2/anime/trending/?page=0&perPage=12` | Afficher les titres populaires du moment. |
| Recherche | `POST /api/v2/anime/search/` | Chercher un titre avec pagination. |
| Fiche | `GET /api/v2/anime/detail/?detailPath=...` | Obtenir synopsis, genres, saisons et nombres d'épisodes. |

Les endpoints `media-sources` et `stream-file` ne font pas partie de la première étape catalogue.

## Blocage d'authentification à résoudre

Les conditions AnimeDoc indiquent :
- chaque requête API doit être authentifiée par une clé ;
- la clé doit rester sur le serveur de son titulaire et ne doit pas être partagée, vendue ou publiée ;
- le plan gratuit est réservé aux projets personnels et prototypes et doit afficher « Powered by AnimeDoc » ;
- les offres Starter et 3-Day Pass sont indiquées pour un usage personnel/hobby ; les offres Pro et Business peuvent être utilisées dans des produits commerciaux.

Par conséquent :
- ne jamais inscrire une clé dans ce dépôt ;
- ne jamais intégrer une clé commune dans le JavaScript distribué aux utilisateurs ;
- ne pas supposer qu'une clé personnelle saisie dans les réglages de l'application satisfait la règle « keep it on your own server » ;
- demander une confirmation écrite à AnimeDoc avant toute distribution publique de l'intégration ;
- étudier une architecture serveur uniquement si AnimeDoc l'autorise et si les coûts, limites et responsabilités sont acceptables.

Tant que ce point n'est pas réglé, AnimeDoc reste une intégration prévue et documentée, mais aucun provider public fonctionnel ne doit être publié pour cette API.

## Tests à effectuer après autorisation

1. Tester le flux d'accueil et vérifier la présence de la rangée « Latest anime ».
2. Comparer le tri « Latest » aux sorties réellement récentes et aux épisodes de la saison en cours.
3. Tester la recherche avec des titres connus en français, anglais et romaji.
4. Vérifier les fiches, les images, les dates, les saisons et les nombres d'épisodes.
5. Examiner les champs de langue/audio/sous-titres ; ne jamais déduire VF ou VOSTFR d'un simple compteur non confirmé.
6. Mesurer le nombre de requêtes et respecter strictement les limites du plan.
7. Vérifier les erreurs 401, 403 et 429 et afficher des messages clairs.
8. Garder la lecture et le téléchargement hors du périmètre de cette première étape.

## Références officielles

- Documentation API : https://www.animedoc.cloud/docs
- Home Feed : https://www.animedoc.cloud/docs/endpoints/home
- Search : https://www.animedoc.cloud/docs/endpoints/search
- Details : https://www.animedoc.cloud/docs/endpoints/details
- Conditions : https://www.animedoc.cloud/terms

## Statut

- Décision produit : **retenu pour le catalogue**.
- Code provider publié : **non**.
- Autorisation pour distribution communautaire : **à confirmer**.
- Streaming : **non requis pour l'étape catalogue**.
- Téléchargement : **non inclus dans cette intégration catalogue**.
