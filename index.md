# Knowledge Base — ouritres

> Index léger. Le skill `maxime-kb` lit ce fichier en premier, puis charge
> uniquement les fiches `active/` pertinentes. Ne jamais tout charger.

## Fiches actives

| Thème | Fiche | Portée | Validé le |
|-------|-------|--------|-----------|
| ad-ds | [reference](active/ad-ds/reference.md) | global | 2026-06-16 |
| ad-ds | [unattended-deployment](active/ad-ds/unattended-deployment.md) | global | 2026-06-16 |
| coreapi | [project-goal](active/coreapi/project-goal.md) | coreapi | 2026-06-16 |

## Thèmes disponibles

- `ad-ds` — Active Directory Domain Services (LDAP, .NET DirectoryServices, déploiement)
- `coreapi` — contexte et décisions architecturales du repo coreapi

## Consommation

Ce repo est monté comme submodule à `knowledge-base/` dans chaque repo consommateur :

```bash
git submodule add <url> knowledge-base
```
