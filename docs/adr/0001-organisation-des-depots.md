# ADR-0001 · Organisation des dépôts de code

- **Statut** : proposé
- **Date** : 2026-10-14
- **Décideurs** : équipe Tech Lead

## Contexte
La solution comprend un back-end Firebase, un back-office web, un simulateur de centrale d'achat, un pipeline de données et deux applications mobiles natives (Android et iOS). Le contrat d'API est partagé avec l'équipe NoCode. L'équipe compte 3 ou 4 développeurs, qui travaillent tous sur le front et le back. La CI doit construire le web et le mobile à chaque pull request.

## Décision
Nous utilisons quatre dépôts : `platform` (Firebase, web, simulateur, pipeline et documentation d'architecture), `app-android`, `app-ios` et `api-contract` (partagé avec l'équipe NoCode).

## Options écartées
1. **Un seul monodépôt pour tout** : les chaînes d'outils Android (Gradle) et iOS (Xcode) alourdiraient chaque CI, et les builds iOS demandent des runners macOS facturés à la minute même pour une PR qui ne touche que le web.
2. **Un dépôt par service (functions, web, simulateur, pipeline séparés)** : trop de dépôts pour une petite équipe, et les modèles de données partagés entre functions, web et simulateur seraient dupliqués.
3. **Contrat d'API dans le dépôt `platform`** : l'équipe NoCode devrait accéder à notre code ; un dépôt dédié garde la frontière nette et sert de source unique co-signée.

## Conséquences
- **Coût** : les runners macOS ne tournent que sur les PR du dépôt iOS.
- **Carbone** : moins de builds inutiles, chaque CI ne construit que ce qui a changé.
- **Performance** : CI plus rapides par dépôt.
- **Risques** : les applications mobiles doivent suivre les versions du contrat d'API ; on référence la version du contrat dans chaque README.
