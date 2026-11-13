# Zangetsu — Sources francophones

Dépôt communautaire de sources pour [Zangetsu](https://github.com/Spyou/Zangetsu), avec pour objectif de faciliter la découverte d'animes disposant de pistes **françaises (VF)** et/ou de sous-titres **français (VOSTFR)**.

## Ajouter ce dépôt dans Zangetsu

Dans l'application : **Settings → Sources → Add repo**, puis coller cette adresse :

```
https://raw.githubusercontent.com/KnightGeorge11/Zangetsu-FR-Providers/main/index.json
```

## Recherche des sources

Consulter [`docs/SOURCE_RESEARCH.md`](docs/SOURCE_RESEARCH.md) pour les pistes examinées et leur statut de validation.

## État du projet

Le dépôt est initialisé. Aucun provider de lecture n'est publié pour le moment : chaque intégration doit être vérifiée et testée avant d'être annoncée comme fonctionnelle.

Les pistes étudiées comprennent Anime-Sama, VoirAnime, Taizen et AnimeDoc. Leur présence dans la documentation ne signifie pas qu'elles sont compatibles ou autorisées comme providers. Taizen est un catalogue de métadonnées, pas un service de lecture. AnimeDoc expose une API de lecture, mais son mécanisme de clé privée doit être résolu avant toute distribution publique.

Un provider ne sera ajouté que si son utilisation et l'accès aux contenus sont autorisés, sans contournement de DRM, d'authentification, de protections anti-automatisation ou de limites d'accès.

## Langues

Les providers devront déclarer leur langue dans le manifeste et, lorsque le site expose cette information de façon fiable, distinguer :
- **VF** : audio français ;
- **VOSTFR** : audio original avec sous-titres français.

La disponibilité réelle dépendra de chaque titre et de la source. Un compteur de doublage ou de sous-titrage ne prouve pas, à lui seul, qu'un flux est accessible.

## Manifeste

Le fichier `index.json` à la racine répertorie les providers installables. Chaque provider devra être un fichier JavaScript autonome placé dans `providers/`, conforme à l'API attendue par Zangetsu.

## Qualité

Avant publication, chaque provider devra être vérifié sur des titres réels : recherche, fiche, liste d'épisodes, langues annoncées et comportement en cas d'indisponibilité. La version du provider devra être synchronisée avec celle du manifeste.

## Transparence

Une assistance par IA a été utilisée pour préparer la structure et la documentation initiales. Le code ajouté ultérieurement devra être relu, compris et testé avant toute publication.
