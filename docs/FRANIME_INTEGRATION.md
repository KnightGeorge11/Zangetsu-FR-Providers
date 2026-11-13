# Étude d'intégration FRAnime

Dernière vérification : 13 novembre 2026.

## État de la source

FRAnime affiche des fiches, des saisons, des épisodes et des étiquettes de langue (VF/VOSTFR). Son site indique explicitement qu'il n'héberge pas les fichiers vidéo et qu'il indexe des liens vers des hébergeurs tiers.

- Page officielle : https://franime.fr/
- Politique DMCA : https://franime.fr/dmca
- Statut des services : https://status.franime.fr/fr

La page DMCA est une déclaration de l'exploitant du site ; elle ne constitue pas une autorisation de réutiliser les liens ou les œuvres dans une application tierce.

## API : piste de recherche, pas validation

Une ancienne référence communautaire publique (script PowerShell publié en 2024) mentionne une API sur `https://api.franime.fr` et un endpoint de catalogue `/api/animes/`. Elle décrit aussi une route de lecteur, mais celle-ci n'est volontairement pas reproduite ni intégrée ici.

Cette référence n'est ni une documentation officielle ni une preuve que l'API est toujours identique, librement réutilisable ou autorisée pour un provider tiers. Une tentative de consultation de l'endpoint depuis l'environnement de recherche n'a pas permis d'obtenir une réponse exploitable. Le tableau de statut FRAnime confirme que le service API existe et est surveillé, mais ne documente pas ses routes ni ses conditions d'utilisation.

Références :
- Statut FRAnime : https://status.franime.fr/fr
- Référence communautaire historique : https://gist.github.com/Minemobs/6738da8d8930837398aaf515b82afd2a

## Décision

**Pas de provider FRAnime publié à ce stade.**

Avant tout code, il faut obtenir de l'exploitant une confirmation écrite sur les points suivants :

1. L'API de catalogue est-elle officiellement documentée et destinée à être utilisée par des applications tierces ?
2. L'accès automatisé par un provider Zangetsu est-il autorisé ?
3. Les métadonnées, images et informations de langue peuvent-elles être affichées dans une application tierce, et sous quelles conditions ?
4. Existe-t-il une API de lecture officielle et autorisée, ou faut-il ouvrir le lecteur sur le site d'origine ?
5. L'intégration peut-elle être distribuée publiquement sans clé privée, compte utilisateur ou serveur intermédiaire ?

Ne pas contourner les protections anti-automatisation, les limites de débit, les connexions ou les restrictions des hébergeurs tiers. Ne pas annoncer qu'un épisode est téléchargeable tant que la compatibilité avec le téléchargement hors ligne de Zangetsu n'a pas été testée.

## Étapes possibles après réponse de FRAnime

- Si seule l'API de catalogue est autorisée : préparer un provider catalogue, si le contrat Zangetsu et l'UX permettent une source sans lecture intégrée.
- Si une API de lecture officielle est fournie : examiner sa documentation, puis implémenter les fonctions Zangetsu avec des tests réels.
- Si aucune intégration n'est autorisée : garder FRAnime dans la liste des pistes non intégrées et privilégier une source avec une API officiellement réutilisable.

## Transparence

Cette étude a été préparée avec une assistance IA. Aucun code de scraping FRAnime n'a été généré ou publié ; les références communautaires historiques ne sont pas traitées comme une autorisation.
