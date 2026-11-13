# Compatibilité des extensions Aniyomi et Mangayomi

Dernière vérification : 13 novembre 2026.

## Conclusion

Zangetsu possède déjà deux intégrations distinctes :

- **Aniyomi** : extensions anime natives Android.
- **Mangayomi** : catalogue et moteur d'extensions Mangayomi, avec des sources anime, manga et romans.

Il n'est donc pas nécessaire de réécrire automatiquement chaque extension dans le format JavaScript natif de Zangetsu. Il faut d'abord vérifier si la source souhaitée peut être ajoutée directement dans l'onglet correspondant de Zangetsu.

Le dépôt **Zangetsu FR Providers** reste un dépôt de providers natifs Zangetsu. Son `index.json` ne doit pas recevoir directement les manifestes Aniyomi ou Mangayomi : ces deux écosystèmes sont gérés séparément par l'application.

## Ce que le code de Zangetsu confirme

### Aniyomi

Le code de Zangetsu contient un `AniyomiProvider` qui adapte les sources Aniyomi à l'interface interne de Zangetsu. Il relaie notamment :

- les listes populaires et récentes ;
- la recherche et les filtres ;
- les fiches d'anime ;
- les épisodes ;
- les sources vidéo.

Le chargement des extensions Aniyomi est limité à Android dans le code consulté. L'intégration ne garantit pas qu'une extension donnée fonctionne : cela dépend toujours du site source, de son état et de ses formats vidéo.

Références :
- Adaptateur Zangetsu : https://github.com/Spyou/Zangetsu/blob/main/lib/core/aniyomi/aniyomi_provider.dart
- Dépôt de providers Zangetsu : https://github.com/Spyou/zangetsu-providers
- Dépôt communautaire Aniyomi contenant des sources annoncées en français : https://github.com/aniyomi-addons/anime-extensions-repo

Le dépôt communautaire Aniyomi consulté annonce notamment FrenchAnime, VoirAnime et Vostfree comme extensions françaises. Ce sont des pistes à tester, pas des intégrations validées ni une preuve d'autorisation de diffusion ou de réutilisation des liens.

Manifeste Aniyomi indiqué par le dépôt :
`https://raw.githubusercontent.com/goddivor/anime-extensions-repo/repo/index.min.json`

### Mangayomi

Le code de Zangetsu contient un `MangayomiManager` et un `MangayomiProvider`. L'application peut ajouter des dépôts Mangayomi, installer leurs extensions et exécuter leurs sources avec le moteur fourni par `zangetsu_source_bridge`.

L'adaptateur anime récupère notamment les résultats de recherche, fiches, épisodes et vidéos. Il transmet aussi les en-têtes fournis par l'extension et les sous-titres associés aux vidéos lorsqu'ils sont disponibles.

Le hub des sources de Zangetsu affiche une entrée Mangayomi séparée. Contrairement à l'intégration Aniyomi, cette entrée n'est pas conditionnée par un test Android dans l'écran consulté. La disponibilité effective doit toutefois être vérifiée sur chaque plateforme publiée.

Références :
- Adaptateur Zangetsu : https://github.com/Spyou/Zangetsu/blob/main/lib/core/mangayomi/mangayomi_provider.dart
- Gestionnaire Mangayomi : https://github.com/Spyou/Zangetsu/blob/main/lib/core/mangayomi/mangayomi_manager.dart
- Écran des dépôts : https://github.com/Spyou/Zangetsu/blob/main/lib/features/sources/providers_hub_screen.dart
- Application Mangayomi : https://github.com/kodjodevf/mangayomi

## Dépôts Mangayomi examinés

| Dépôt | Ce qui est annoncé | Intérêt VF/VOSTFR |
| --- | --- | --- |
| Mallyd11 | Catalogue JavaScript anime avec plusieurs sources Sub+Dub et une indication de téléchargement | Aucun label français clair dans la liste examinée. « Sub+Dub » ne signifie pas automatiquement VOSTFR/VF. |
| Swakshan | Catalogue JavaScript anime, plusieurs sources indiquées en anglais ou « all » | Pas de preuve suffisante d'une couverture VF/VOSTFR. |
| kodjodevf | Dépôt officiel principalement orienté manga et romans | Pas la piste prioritaire pour les providers anime. |

Liens :
- Mallyd11 : https://github.com/Mallyd11/mangayomi-anime-extensions
- Swakshan : https://github.com/Swakshan/mangayomi-swak-extensions
- Dépôt principal Mangayomi : https://github.com/kodjodevf/mangayomi-extensions

Manifeste anime Mallyd11 :
`https://raw.githubusercontent.com/Mallyd11/mangayomi-anime-extensions/main/anime_index.json`

## Règles de validation pour notre projet

1. Ne pas confondre « Sub+Dub » avec VF/VOSTFR. Vérifier les pistes audio et sous-titres sur des épisodes réels.
2. Vérifier qu'une source propose bien des anime récents et que les épisodes de la saison en cours apparaissent rapidement.
3. Tester la recherche, les fiches, les épisodes, la lecture et le téléchargement hors ligne dans Zangetsu.
4. Ne pas recopier automatiquement le code d'une extension tierce. Vérifier sa licence, ses conditions, ses dépendances et la politique IA de Zangetsu.
5. Ne pas contourner DRM, authentification, protections anti-automatisation, restrictions ou limites d'accès.
6. Ne pas publier de provider qui annonce VF/VOSTFR ou le téléchargement sans vérification réelle.

## Plan de travail

1. Tester d'abord les dépôts d'extensions directement dans Zangetsu, sans modifier notre manifeste.
2. Prioriser les sources explicitement francophones côté Aniyomi.
3. Examiner les extensions Mangayomi et rechercher celles qui identifient réellement les pistes françaises.
4. Noter pour chaque source : langues vérifiées, fraîcheur des épisodes, lecture, téléchargement, état du service et licence.
5. Ne développer un provider natif Zangetsu que lorsqu'une source utile n'est pas déjà accessible et que son intégration est permise.

## Statut

- Compatibilité technique Aniyomi dans le code Zangetsu : **confirmée, Android**.
- Compatibilité technique Mangayomi dans le code Zangetsu : **confirmée dans le code consulté ; tests de plateforme à effectuer**.
- Dépôt Aniyomi francophone : **piste identifiée, non testée**.
- Dépôts Mangayomi examinés : **pas encore de source VF/VOSTFR confirmée**.
- Provider natif publié dans Zangetsu FR Providers : **aucun**.
- `index.json` : **inchangé et volontairement vide**.
