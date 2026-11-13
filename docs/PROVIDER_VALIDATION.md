# Validation d'un provider

Ce document définit les contrôles à effectuer avant d'ajouter une source au manifeste `index.json`.

## 1. Vérification préalable de la source

- [ ] Le site et le propriétaire de la source sont identifiés.
- [ ] Les conditions d'utilisation et les règles d'accès ont été consultées.
- [ ] L'intégration envisagée est autorisée.
- [ ] Aucun contournement de DRM, d'authentification, de paywall, de protection anti-automatisation ou de limite d'accès n'est nécessaire.
- [ ] Les endpoints utilisés sont documentés publiquement ou leur utilisation est explicitement autorisée.

Si un point reste incertain, ne pas publier le provider.

## 2. Contrat Zangetsu

- [ ] Le fichier JavaScript respecte l'API réellement attendue par la version cible de Zangetsu.
- [ ] `getInfo()` renvoie les métadonnées attendues, dont `name`, `lang`, `baseUrl`, `type` et `version`.
- [ ] Les fonctions exposées correspondent aux capacités prises en charge par l'application.
- [ ] Les identifiants retournés sont stables et propres à la source.
- [ ] Les erreurs réseau et les réponses invalides sont gérées sans bloquer l'application.

Ne pas déduire le contrat d'un provider en recopiant aveuglément le code d'une autre source : vérifier le code de l'application et les exemples actuels.

## 3. Langues et catalogue

- [ ] La recherche retourne des résultats réels et pertinents.
- [ ] La fiche correspond bien au titre sélectionné.
- [ ] Les épisodes correspondent à la bonne saison et au bon ordre.
- [ ] La disponibilité VF est confirmée par une piste audio française réelle.
- [ ] La disponibilité VOSTFR est confirmée par des sous-titres français réels.
- [ ] Une langue inconnue ou non vérifiée n'est jamais présentée comme disponible.

## 4. Lecture, téléchargement et stabilité

- [ ] La lecture a été testée sur au moins deux titres autorisés.
- [ ] Plusieurs épisodes ont été vérifiés lorsque c'est possible.
- [ ] Les pistes audio et sous-titres annoncés correspondent au résultat réel.
- [ ] Les URL temporaires, expirations et erreurs sont gérées proprement.
- [ ] Les délais et le nombre de requêtes restent raisonnables.
- [ ] Les limites d'accès et consignes du site sont respectées.
- [ ] Un épisode peut être téléchargé depuis l'application mobile Zangetsu.
- [ ] Le téléchargement fonctionne jusqu'à son terme, y compris pour les flux segmentés lorsque ceux-ci sont pris en charge.
- [ ] Le fichier téléchargé se lit depuis la bibliothèque hors connexion, sans nouvelle recherche en ligne.
- [ ] Les sous-titres français sont disponibles après téléchargement lorsque la source et le format les exposent.
- [ ] Le comportement est testé après fermeture de l'application et en mode avion.

Un lien qui fonctionne en streaming n'est pas automatiquement téléchargeable. Ne pas déclarer le téléchargement validé sans test réel dans Zangetsu.

## 5. Publication

- [ ] Le code a été relu et compris.
- [ ] Les tests reproductibles sont documentés.
- [ ] La version du provider est identique à celle déclarée dans `index.json`.
- [ ] Le manifeste est un JSON valide.
- [ ] La documentation décrit précisément les langues et limites vérifiées.
- [ ] L'utilisation d'une IA pour produire une part substantielle du code est déclarée.

## État actuel

Aucun provider n'est validé à ce stade. Les noms de sites éventuellement évoqués dans le README sont des pistes de recherche, pas des intégrations disponibles. Un provider ne sera ajouté qu'après vérification de l'autorisation, de la compatibilité Zangetsu, de la lecture et du téléchargement hors connexion.
