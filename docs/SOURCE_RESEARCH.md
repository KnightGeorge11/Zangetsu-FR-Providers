# Recherche de sources francophones

Dernière vérification : 13 novembre 2026.

Ce document distingue les catalogues de métadonnées des services qui fournissent réellement une lecture vidéo. Un résultat de recherche ou une fiche d'anime ne suffit pas à constituer un provider de streaming.

## Pistes examinées

| Service | Rôle vérifié | Décision pour ce dépôt |
| --- | --- | --- |
| AniList | Base de données anime avec API GraphQL publique officielle | Utile pour les métadonnées, mais ne fournit pas les flux vidéo : pas un provider de lecture. |
| Crunchyroll | Service officiel de streaming | Exclu comme source de lecture automatisée sans autorisation écrite : ses conditions interdisent notamment le scraping automatisé et l'intégration/retransmission du contenu dans une autre application. |
| ADN (Animation Digital Network) | Service officiel de streaming d'anime | À examiner uniquement via une API ou un partenariat explicitement autorisé. Aucune API publique de lecture autorisée n'a été confirmée dans cette recherche. |
| Anime-Sama | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |
| VoirAnime | Site évoqué comme piste par le projet | Non validé. Propriété des contenus, autorisation d'accès automatisé et conditions d'intégration restent à établir. |

## Sources de référence

- Documentation officielle AniList : https://docs.anilist.co/guide/introduction
- Conditions officielles Crunchyroll : https://www.crunchyroll.com/en/terms/privacy
- Politique IA du projet Zangetsu : https://github.com/Spyou/Zangetsu/blob/main/AI_POLICY.md
- Contrat et format des dépôts de providers : https://github.com/Spyou/zangetsu-providers

## Critères obligatoires avant d'intégrer une source

1. Identifier l'exploitant du service et les ayants droit ou distributeurs des vidéos.
2. Vérifier les conditions d'utilisation et obtenir une autorisation explicite pour toute API ou intégration non publique.
3. Confirmer que l'accès automatisé est permis et qu'aucune protection, authentification, restriction géographique ou DRM n'est contournée.
4. Vérifier les pistes audio françaises et les sous-titres français sur des titres réels.
5. Tester le contrat JavaScript de Zangetsu, la recherche, les fiches, les épisodes et la lecture avant publication.

## État actuel

Aucun provider de lecture VF/VOSTFR n'est validé ou publié dans ce dépôt. Le manifeste reste vide volontairement. Cette décision évite de publier un scraper hypothétique ou une source dont l'intégration n'est pas autorisée.

Une API de métadonnées comme AniList pourra éventuellement être utilisée pour enrichir les fiches d'un provider autorisé, mais elle ne remplacera pas une source vidéo.
