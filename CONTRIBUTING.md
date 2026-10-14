# Règles de contribution

## Branches
- `main` est protégée : aucun push direct, tout passe par une pull request.
- Une branche par user story : `type/issue-number-short-description` (en anglais)
  - exemples : `feat/12-inventory-entry`, `fix/31-stock-alert-threshold`, `docs/5-adr-firestore`

## Commits (Conventional Commits)
Format : `type(portée): description à l'impératif`

| Type | Usage |
|---|---|
| `feat` | nouvelle fonctionnalité |
| `fix` | correction de bug |
| `docs` | documentation, ADR, schémas |
| `test` | ajout ou correction de tests |
| `refactor` | réorganisation sans changement de comportement |
| `chore` | configuration, dépendances, outillage |
| `ci` | GitHub Actions |

Exemples : `feat(stocks): ajouter la saisie d'inventaire de fin de journée` · `docs(adr): ADR-002 choix de Firestore`

Toujours référencer l'issue dans la PR (`Closes #12`).

## Pull requests
- Au moins **1 review approuvée** d'un autre membre avant merge.
- Remplir le modèle de PR, y compris la section **Usage de l'IA**.
- Toutes les conversations résolues avant merge.
- Merge en *squash* pour garder un historique lisible.

## Definition of Done (une user story est terminée quand…)
- [ ] Les critères d'acceptation de l'issue sont tous vérifiés
- [ ] Le code est relu et approuvé (1 review minimum)
- [ ] Les tests automatisés passent (et des tests ont été ajoutés pour la logique métier)
- [ ] La CI est verte (lint, tests, build)
- [ ] Aucun secret dans le code
- [ ] Accessibilité vérifiée si l'écran est concerné (libellés, contrastes, clavier ou lecteur d'écran)
- [ ] Documentation à jour (README, ADR si décision d'architecture, OpenAPI si l'API change)
- [ ] Démontrable en revue de sprint

## Secrets
Aucune clé, aucun mot de passe, aucun `.env` dans le dépôt. Seul `.env.example` (noms des variables sans valeurs) est versionné.
