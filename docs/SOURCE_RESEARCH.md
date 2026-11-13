# Recherche de sources francophones

Dernière vérification : 13 novembre 2026.

Ce document distingue les catalogues de métadonnées, les annuaires de disponibilité et les services qui fournissent réellement une lecture vidéo. Un résultat de recherche ou une fiche d'anime ne suffit pas à constituer un provider de streaming.

## Pistes examinées

| Service | Rôle vérifié | Décision pour ce dépôt |
| --- | --- | --- |
| AniList | Base de données anime avec API GraphQL publique officielle | Utile pour les métadonnées, mais ne fournit pas les flux vidéo : pas un provider de lecture. |
| Taizen | Catalogue indépendant avec API GraphQL publique sans clé. Donne des métadonnées, des compteurs de sous-titres/doublages par langue et des disponibilités de plateformes par région. | Candidat pour enrichir un catalogue ou afficher des liens vers des services officiels. Pas un provider de lecture : Taizen n'héberge pas de vidéo. Toute disponibilité doit conserver l'attribution JustWatch/TMDB requise et tenir compte de la couverture régionale limitée. |
| AnimeDoc | API de recherche, détails et lecture vidéo. Ses conditions déclarent que les contenus proviennent de fournisseurs sous licence. | Candidat technique à examiner, mais pas intégrable tel quel dans un provider public : chaque compte reçoit une clé API qui doit rester privée. Le plan gratuit est réservé aux projets personnels/prototypes et impose la mention « Powered by AnimeDoc ». Il faut obtenir une solution compatible avec une distribution client-side (clé utilisateur, proxy autorisé ou accord spécifique) et confirmer la couverture VF/VOSTFR avant toute intégration. Les conditions déclarent la provenance sous licence, mais cela ne constitue pas une autorisation spécifique donnée à ce dépôt. |
| Crunchyroll | Service officiel de streaming | Exclu comme source de lecture automatisée sans autorisation écrite : ses conditions interdisent notamment le scraping automatisé et l'intégration/retransmission du contenu dans une autre application. |
| ADN (Animation Digital Network) | Service officiel de streaming d'anime | À examiner uniquement via une API ou un partenariat explicitement autorisé. Aucune API publique de lecture autorisée n'a été confirmée dans cette recherche. |
| Anime-Sama | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |
| VoirAnime | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |

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
6. Tester le contrat JavaScript de Zangetsu, la recherche, les fiches, les épisodes et la lecture avant publication.

## État actuel

Aucun provider de lecture VF/VOSTFR n'est validé ou publié dans ce dépôt. Le manifeste reste vide volontairement.

Taizen peut être utile comme source de métadonnées et de liens vers des services officiels, mais ne fournit pas de lecture vidéo. AnimeDoc expose techniquement des fonctions de lecture et déclare utiliser des fournisseurs sous licence, mais sa clé privée et les conditions du plan gratuit empêchent une intégration client-side publique immédiate. Une autorisation ou un mécanisme officiel de distribution de clé serait nécessaire.

Une API de métadonnées comme AniList ou Taizen ne remplace pas une source vidéo. Cette distinction évite de publier un provider qui affiche des titres sans pouvoir lire leurs épisodes.
