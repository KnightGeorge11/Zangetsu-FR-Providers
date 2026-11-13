# Zangetsu — Sources francophones

Dépôt communautaire de sources pour [Zangetsu](https://github.com/Spyou/Zangetsu), avec pour objectif de faciliter la découverte d'animes **récents** disposant de pistes **françaises (VF)** et/ou de sous-titres **français (VOSTFR)**, y compris les nouveautés de saison et les épisodes récemment publiés.

## Ajouter ce dépôt dans Zangetsu

Dans l'application : **Settings → Sources → Add repo**, puis coller cette adresse :

```
https://raw.githubusercontent.com/KnightGeorge11/Zangetsu-FR-Providers/main/index.json
```

## Objectifs obligatoires

Les providers de ce dépôt devront répondre à ces quatre exigences :

1. **Anime récents** : nouveautés de saison et épisodes récemment publiés, avec une fraîcheur du catalogue vérifiée.
2. **Français** : distinguer clairement la VF (audio français) de la VOSTFR (audio original avec sous-titres français).
3. **Lecture fonctionnelle** : les épisodes annoncés doivent réellement pouvoir être lus dans Zangetsu.
4. **Téléchargement mobile** : les épisodes doivent pouvoir être téléchargés depuis la fonction intégrée de Zangetsu et lus hors connexion. Les sous-titres doivent être conservés lorsqu'ils sont disponibles et pris en charge par le format/source.

Zangetsu possède déjà une bibliothèque de téléchargements hors ligne. Le rôle du provider est de fournir des sources vidéo compatibles avec le mécanisme de téléchargement de l'application, et non de créer un gestionnaire de téléchargement séparé.

## Recherche des sources

Consulter [`docs/SOURCE_RESEARCH.md`](docs/SOURCE_RESEARCH.md) pour les pistes examinées et leur statut de validation.

## État du projet

Le dépôt est initialisé. Aucun provider de lecture n'est publié pour le moment : chaque intégration doit être vérifiée et testée avant d'être annoncée comme fonctionnelle.

Les pistes étudiées comprennent Anime-Sama, VoirAnime, Taizen et AnimeDoc. AnimeDoc est retenu dans le projet comme **source de catalogue**, même si aucune lecture vidéo n'est intégrée : ses endpoints de catalogue permettent d'explorer les nouveautés, de rechercher des titres et de consulter leurs fiches. Le plan d'intégration est décrit dans [`docs/ANIMEDOC_INTEGRATION.md`](docs/ANIMEDOC_INTEGRATION.md). Taizen reste une source de métadonnées, pas un service de lecture.

Un provider ne sera ajouté que si son utilisation et l'accès aux contenus sont autorisés, sans contournement de DRM, d'authentification, de protections anti-automatisation ou de limites d'accès. La fraîcheur du catalogue sera également testée : nouveautés de saison, épisodes récents et délai de mise à jour.

## Manifeste

Le fichier `index.json` à la racine répertorie les providers installables. Chaque provider devra être un fichier JavaScript autonome placé dans `providers/`, conforme à l'API attendue par Zangetsu.

## Qualité

Avant publication, chaque provider devra être vérifié sur des titres réels : recherche, fiche, liste d'épisodes, langues annoncées, lecture, téléchargement mobile et lecture hors connexion. La version du provider devra être synchronisée avec celle du manifeste.

## Transparence

Une assistance par IA a été utilisée pour préparer la structure et la documentation initiales. Le code ajouté ultérieurement devra être relu, compris et testé avant toute publication.
