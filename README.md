# EventHub

## Conventions de commit

Ce projet suit la spécification [Conventional Commits](https://www.conventionalcommits.org/fr/v1.0.0/).

### Format

```
type(scope): description
```

- **type** : la nature du changement (obligatoire)
- **scope** : la partie du projet concernée (optionnel)
- **description** : résumé court, à l'impératif, sans point final

### Types autorisés

| Type | Usage |
|------|-------|
| `feat` | Nouvelle fonctionnalité |
| `fix` | Correction de bug |
| `docs` | Documentation uniquement |
| `style` | Mise en forme (pas de changement de logique) |
| `refactor` | Refonte du code sans nouvelle fonctionnalité ni correction |
| `test` | Ajout ou modification de tests |
| `chore` | Maintenance, config, dépendances |

### Exemples

```
feat(auth): ajoute la connexion par email
fix(api): corrige le calcul de la date de fin
docs(readme): ajoute les conventions de commit
chore: configure husky et lint-staged
```