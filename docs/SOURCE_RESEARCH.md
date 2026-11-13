# Recherche de sources francophones

Dernière vérification : 13 novembre 2026.

Ce document distingue les catalogues de métadonnées, les annuaires de disponibilité et les services qui fournissent réellement une lecture vidéo. Un résultat de recherche ou une fiche d'anime ne suffit pas à constituer un provider de streaming.

## Pistes examinées

| Service | Rôle vérifié | Décision pour ce dépôt |
| --- | --- | --- |
| AniList | Base de données anime avec API GraphQL publique officielle | Utile pour les métadonnées, mais ne fournit pas les flux vidéo : pas un provider de lecture. |
| Taizen | Catalogue indépendant avec API GraphQL publique sans clé. Donne des métadonnées, des compteurs de sous-titres/doublages par langue et des disponibilités de plateformes par région. | Candidat pour enrichir un catalogue ou afficher des liens vers des services officiels. Pas un provider de lecture : Taizen n'héberge pas de vidéo. Toute disponibilité doit conserver l'attribution JustWatch/TMDB requise et tenir compte de la couverture régionale limitée. |
| AnimeDoc | API de recherche, détails et lecture vidéo. Ses conditions déclarent que les contenus proviennent de fournisseurs sous licence. | Candidat technique à approfondir : Zangetsu possède un formulaire de réglages par provider et permet au JavaScript de lire des paramètres saisis par l'utilisateur via `getSettings()`. Cela pourrait permettre à chacun d'entrer sa propre clé sans l'inscrire dans le dépôt. Le plan gratuit reste réservé aux projets personnels/prototypes et impose la mention « Powered by AnimeDoc » ; il faut confirmer auprès d'AnimeDoc que la distribution via un dépôt communautaire et l'usage de clés individuelles respectent ses conditions. Il faut aussi vérifier la couverture VF/VOSTFR et tester réellement les endpoints, le streaming et le téléchargement. Aucune autorisation spécifique n'a encore été obtenue pour ce dépôt. |
| Crunchyroll | Service officiel de streaming | Exclu comme source de lecture automatisée sans autorisation écrite : ses conditions interdisent notamment le scraping automatisé et l'intégration/retransmission du contenu dans une autre application. |
| ADN (Animation Digital Network) | Service officiel de streaming d'anime | À examiner uniquement via une API ou un partenariat explicitement autorisé. Aucune API publique de lecture autorisée n'a été confirmée dans cette recherche. |
| Anime-Sama | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |
| VoirAnime | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |

## Capacités de téléchargement de Zangetsu

La documentation publique de Zangetsu indique que l'application possède déjà un système de téléchargement d'épisodes : l'utilisateur peut télécharger un épisode depuis sa fiche, ou lancer un téléchargement groupé depuis la liste des épisodes. Les flux segmentés pris en charge sont assemblés en un fichier vidéo lisible hors connexion. La documentation des versions récentes indique également que les sous-titres téléchargés peuvent être transmis aux lecteurs externes.

Conséquence pour ce dépôt : le provider ne doit pas implémenter un téléchargeur indépendant. Il doit fournir des sources vidéo exploitables par le lecteur et le gestionnaire de téléchargements de Zangetsu. La compatibilité doit être testée en pratique : un lien de streaming fonctionnel ne garantit pas qu'il puisse être téléchargé. Les URL temporaires, en-têtes requis, flux HLS/DASH, segments, expiration et pistes de sous-titres peuvent modifier le résultat. Aucun mécanisme de protection ou d'accès ne doit être contourné.

Références :
- Guide officiel Zangetsu, section « Save it for offline » : https://zangetsu.online/guide/
- Historique des versions Zangetsu : https://github.com/Spyou/Zangetsu/releases

## Sources de référence

- Documentation officielle AniList : https://docs.anilist.co/guide/introduction
- API Taizen : https://taizen.moe/api-docs
- Conditions Taizen : https://taizen.moe/terms
- Documentation API AnimeDoc : https://www.animedoc.cloud/docs
- Conditions AnimeDoc : https://www.animedoc.cloud/terms
- Conditions officielles Crunchyroll : https://www.crunchyroll.com/en/terms/privacy
- Politique IA du projet Zangetsu : https://github.com/Spyou/Zangetsu/blob/main/AI_POLICY.md
- Contrat et format des dépôts de providers : https://github.com/Spyou/zangetsu-providers

## Critères obligatoires avant d'intégrer une source

1. Identifier l'exploitant du service et les ayants droit ou distributeurs des vidéos.
2. Vérifier les conditions d'utilisation et obtenir une autorisation explicite pour toute API ou intégration non publique.
3. Confirmer que l'accès automatisé est permis et qu'aucune protection, authentification, restriction géographique ou DRM n'est contournée.
4. Ne jamais publier une clé API privée dans un dépôt ou un fichier JavaScript distribué aux utilisateurs.
5. Confirmer les pistes audio françaises et les sous-titres français sur des titres réels. Un simple compteur de langues ne prouve pas la disponibilité d'un flux lisible.
6. Tester le contrat JavaScript de Zangetsu, la recherche, les fiches, les épisodes, la lecture et le téléchargement mobile avant publication.
7. Vérifier la fraîcheur du catalogue : anime de la saison en cours, dates de sortie, épisodes récemment publiés et délai entre publication sur le site et apparition dans l'API. Un simple tri « latest » ne prouve pas un simulcast ni une mise à jour rapide.
8. Tester qu'un épisode téléchargé est lisible hors connexion après fermeture de l'application et que ses sous-titres français restent disponibles lorsque la source les fournit.

## État actuel

Aucun provider de lecture VF/VOSTFR n'est validé ou publié dans ce dépôt. Le manifeste reste vide volontairement.

Taizen peut être utile comme source de métadonnées et de liens vers des services officiels, mais ne fournit pas de lecture vidéo. AnimeDoc expose techniquement des fonctions de lecture et déclare utiliser des fournisseurs sous licence. Sa documentation annonce aussi un flux d'accueil, les tendances et un catalogue triable par nouveautés (« latest ») : c'est la piste la plus prometteuse actuellement pour découvrir des anime récents. Il faudra tester si les sorties de la saison en cours et les nouveaux épisodes apparaissent rapidement, vérifier la disponibilité VF/VOSTFR titre par titre, puis valider le téléchargement dans Zangetsu. Zangetsu permet aux providers JavaScript de proposer un réglage texte pour que chaque utilisateur saisisse sa propre clé ; il existe donc une voie technique sans publier de secret dans le dépôt. Il reste toutefois nécessaire de confirmer auprès d'AnimeDoc que le plan gratuit et la distribution du provider via un dépôt communautaire sont autorisés.

Une API de métadonnées comme AniList ou Taizen ne remplace pas une source vidéo. Cette distinction évite de publier un provider qui affiche des titres sans pouvoir lire ni télécharger leurs épisodes.
