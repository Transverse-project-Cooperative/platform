# Plateforme d'approvisionnement · Réseau BIAM

Plateforme Tech Lead du projet transverse .decode (PST1, RNCP38822 bloc 2) : stocks en temps réel des brasseries du réseau, stock réseau, commandes groupées aux centrales d'achat, données et prévisions.

## Contenu du dépôt
| Dossier | Rôle |
|---|---|
| `functions/` | Cloud Functions (Node.js / TypeScript) : API REST, déclencheurs Firestore |
| `web/` | Back-office React |
| `purchasing-simulator/` | Simulateur de centrale d'achat (service séparé avec API et webhooks) |
| `pipeline/` | Collecte et traitement des données, stockage analytique, analyses |
| `docs/adr/` | Décisions d'architecture (ADR) |
| `docs/architecture/` | Schémas C4, BPMN, UML |
| `firestore.rules` | Règles de sécurité Firestore |

## Installation locale
> À compléter quand le socle Firebase sera initialisé.

1. Node.js 24 et Firebase CLI (`npm install -g firebase-tools`)
2. `cp .env.example .env` puis renseigner les valeurs (jamais commitées)
3. `firebase emulators:start`

## Contribuer
Voir [CONTRIBUTING.md](CONTRIBUTING.md).

## Dépôts liés
- `api-contract` : contrat OpenAPI partagé avec l'équipe NoCode
- `app-android` : application Android (Kotlin, Jetpack Compose)
- `app-ios` : application iOS (Swift, SwiftUI)
