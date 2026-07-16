# Knowledge Base — ouritres

> L'index des fiches vit dans [`index.json`](index.json) (format JSON, un objet
> par fiche, sans `content`). Ce fichier ne documente que les conventions
> humaines du repo ; le skill `maxime-kb` lit `index.json`, pas ce fichier.

## Thèmes disponibles

- `ad-ds` — Active Directory Domain Services (LDAP, .NET DirectoryServices, déploiement)
- `coreapi` — contexte et décisions architecturales du repo coreapi
- `powershell` — patterns PowerShell/Windows génériques (pas spécifiques à AD DS)

## Consommation

Ce repo est monté comme submodule à `knowledge-base/` dans chaque repo consommateur :

```bash
git submodule add <url> knowledge-base
```

Voir `CLAUDE.md` pour le schéma complet des fiches JSON.
